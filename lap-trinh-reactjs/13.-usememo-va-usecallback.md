# 13. useMemo và useCallback

### useMemo là gì?

`useMemo` là một hook của React dùng để **ghi nhớ kết quả tính toán** và **chỉ tính lại khi dependency thay đổi**.

Cú pháp:

```tsx
const memoizedValue = useMemo(() => {
  // Logic tính toán nặng
  return result;
}, [dependencies]);
```

* `useMemo` trả về `result` đã ghi nhớ.
* Nếu `dependencies` không đổi, React **sẽ không gọi lại hàm bên trong**, giúp tránh tính toán lại không cần thiết.

#### Khi nào cần dùng `useMemo`?

* Khi một hàm trả về **giá trị tính toán nặng** (như filter, sort, reduce, loop lớn).
* Khi bạn muốn tránh render lại **component con có `React.memo`** mà phụ thuộc vào prop từ hàm tính toán.

***

### useCallback là gì?

`useCallback` là hook dùng để **ghi nhớ một hàm (function)** và **chỉ tạo lại khi dependency thay đổi**.

Cú pháp:

```tsx
const memoizedCallback = useCallback(() => {
  // Hàm xử lý logic
}, [dependencies]);
```

#### Khi nào cần dùng `useCallback`?

* Khi truyền callback xuống component con dùng `React.memo`.
* Khi callback được dùng trong các effect hoặc trong dependency array.

> `useCallback(fn, deps)` tương đương với `useMemo(() => fn, deps)`

***

### So sánh useMemo và useCallback

| Tiêu chí        | useMemo                 | useCallback                         |
| --------------- | ----------------------- | ----------------------------------- |
| Ghi nhớ         | **Giá trị trả về**      | **Hàm (function)**                  |
| Trường hợp dùng | Tính toán nặng          | Callback truyền xuống component con |
| Tránh re-render | Giá trị prop không đổi  | Callback prop không đổi             |
| Tối ưu          | Performance (render UI) | Performance (callback & children)   |

***

### Ví dụ minh họa re-render không cần thiết

Ta có component cha tính toán giá trị lớn, truyền xuống component con. Nếu không dùng `useMemo` hoặc `useCallback`, component con có thể bị re-render **dù props không đổi**.

#### Component con dùng `React.memo`

```tsx
'use client';

import React from 'react';

type Props = {
  onClick: () => void;
};

const Child = ({ onClick }: Props) => {
  console.log('Render: Child');
  return (
    <div>
      <p>Component con</p>
      <button onClick={onClick}>Bấm tôi</button>
    </div>
  );
};

export default React.memo(Child);
```

#### Component cha không dùng `useCallback` → bị re-render mỗi lần

```tsx
'use client';

import { useState } from 'react';
import Child from './Child';

export default function ParentWithoutCallback() {
  const [count, setCount] = useState(0);

  const handleClick = () => {
    console.log('Clicked!');
  };

  return (
    <div>
      <h2>Không dùng useCallback</h2>
      <button onClick={() => setCount(count + 1)}>Tăng: {count}</button>
      <Child onClick={handleClick} />
    </div>
  );
}
```

➡️ **Child bị re-render mỗi lần count thay đổi** vì `handleClick` là **hàm mới** mỗi lần render.

***

### Dùng useCallback để tối ưu

```tsx
'use client';

import { useState, useCallback } from 'react';
import Child from './Child';

export default function ParentWithCallback() {
  const [count, setCount] = useState(0);

  const handleClick = useCallback(() => {
    console.log('Clicked!');
  }, []); // Không đổi => Child không bị render lại

  return (
    <div>
      <h2>Dùng useCallback</h2>
      <button onClick={() => setCount(count + 1)}>Tăng: {count}</button>
      <Child onClick={handleClick} />
    </div>
  );
}
```

➡️ `Child` **không bị render lại** khi `count` thay đổi.

***

### Thực hành: So sánh performance với React.memo

#### Mục tiêu:

* Tạo 2 phiên bản `Parent` (1 dùng `useCallback`, 1 không dùng).
* Mỗi `Parent` có 1 `Child` dùng `React.memo`.
* Thêm console.log để xem lần render.

#### Bài tập:

1. Tạo component `ExpensiveComponent`:
   * Tính toán một dãy số lớn (100,000 phần tử).
   * Dùng `useMemo` để tối ưu hóa.
2. Tạo component cha dùng `useMemo` và không dùng `useMemo`.
   * So sánh thời gian render.
3. Ghi lại log console để xác định component nào bị render lại và lý do.

***

## Gợi ý nâng cao

* Kết hợp `React.memo`, `useMemo`, `useCallback` để tối ưu hệ thống component phức tạp.
* Chỉ nên dùng `useMemo/useCallback` khi **có vấn đề về hiệu năng** – tránh lạm dụng vì có thể gây tốn bộ nhớ.
