# 10. UseRef và thao tác với DOM

### useRef là gì?

`useRef` là một hook trong React được dùng để **tạo ra một tham chiếu (reference)** có thể lưu giữ giá trị hoặc tham chiếu đến một phần tử DOM **mà không gây re-render** khi giá trị thay đổi.

Cú pháp:

```tsx
const myRef = useRef<GiáTrịHoặcKiểuPhầnTử>(giáTrịBanĐầu);
```

* Nếu bạn truyền vào `useRef(null)`, nó sẽ trả về một object có dạng `{ current: null }`.
* Khi bạn gán `ref={myRef}` vào một phần tử JSX, `myRef.current` sẽ trỏ tới phần tử DOM đó sau khi render.

***

### Lưu giá trị không làm re-render

Một điểm quan trọng của `useRef` là **thay đổi giá trị `current` sẽ không làm component bị re-render** (khác với `useState`).

Ví dụ:

```tsx
'use client';

import { useRef, useState } from 'react';

export default function RefCounter() {
  const [count, setCount] = useState(0);
  const renderCount = useRef(0);

  renderCount.current += 1;

  return (
    <div>
      <p>Giá trị count: {count}</p>
      <p>Số lần render: {renderCount.current}</p>
      <button onClick={() => setCount(prev => prev + 1)}>Tăng</button>
    </div>
  );
}
```

Giải thích:

* `renderCount` được tăng mỗi lần component render lại.
* Vì `renderCount.current` không được quản lý bởi `useState`, việc thay đổi giá trị không gây render lại component.

***

### Truy cập DOM trực tiếp bằng ref

Bạn có thể dùng `useRef` để **lấy phần tử DOM thật (giống như `document.querySelector`)**.

Ví dụ: tự động focus vào một ô input sau khi component được mount:

```tsx
'use client';

import { useEffect, useRef } from 'react';

export default function AutoFocusInput() {
  const inputRef = useRef<HTMLInputElement>(null);

  useEffect(() => {
    inputRef.current?.focus(); // focus vào input khi trang load
  }, []);

  return (
    <div>
      <label>Nhập tên:</label>
      <input ref={inputRef} type="text" placeholder="Gõ gì đó..." />
    </div>
  );
}
```

***

### Cuộn đến phần tử

Bạn cũng có thể dùng `useRef` để **cuộn đến một phần tử bất kỳ trên trang**.

```tsx
'use client';

import { useRef } from 'react';

export default function ScrollToElement() {
  const sectionRef = useRef<HTMLDivElement>(null);

  const scrollToSection = () => {
    sectionRef.current?.scrollIntoView({ behavior: 'smooth' });
  };

  return (
    <div>
      <button onClick={scrollToSection}>Cuộn đến phần nội dung</button>

      <div style={{ height: '800px' }}></div>

      <div ref={sectionRef} style={{ background: '#f0f0f0', padding: '2rem' }}>
        <h2>Đây là phần bạn cuộn tới!</h2>
      </div>
    </div>
  );
}
```

***

## Bài tập thực hành

### Mục tiêu

Áp dụng `useRef` để:

* Focus tự động vào input khi component được render.
* Đếm số lần render mà không làm component re-render.
* Cuộn mượt đến một phần tử cụ thể khi nhấn nút.

### Đề bài

Tạo một component tên là `RefPractice` với các chức năng:

1. Có một ô input và khi trang load sẽ tự động focus vào ô đó.
2. Có một nút "Tăng" để tăng một biến count sử dụng `useState`.
3. Hiển thị số lần render bằng `useRef`.
4. Có một khối nội dung nằm phía dưới và một nút "Cuộn xuống" để cuộn đến khối đó.

### Gợi ý code mẫu

```tsx
'use client';

import { useEffect, useRef, useState } from 'react';

export default function RefPractice() {
  const [count, setCount] = useState(0);
  const renderCount = useRef(0);
  const inputRef = useRef<HTMLInputElement>(null);
  const scrollTargetRef = useRef<HTMLDivElement>(null);

  useEffect(() => {
    inputRef.current?.focus();
  }, []);

  renderCount.current += 1;

  const scrollToBottom = () => {
    scrollTargetRef.current?.scrollIntoView({ behavior: 'smooth' });
  };

  return (
    <div style={{ padding: '1rem' }}>
      <h1>Thực hành useRef</h1>

      <input ref={inputRef} type="text" placeholder="Auto focus vào đây..." />

      <div style={{ marginTop: '1rem' }}>
        <p>Giá trị count: {count}</p>
        <button onClick={() => setCount(c => c + 1)}>Tăng</button>
        <p>Số lần render: {renderCount.current}</p>
      </div>

      <button onClick={scrollToBottom} style={{ marginTop: '2rem' }}>
        Cuộn đến phần nội dung
      </button>

      <div style={{ height: '600px' }}></div>

      <div ref={scrollTargetRef} style={{ backgroundColor: '#eee', padding: '2rem' }}>
        <h2>Cuộn đến đây rồi nè!</h2>
      </div>
    </div>
  );
}
```

***

## Kết luận

* `useRef` là công cụ cực kỳ mạnh trong React để giữ lại giá trị hoặc thao tác trực tiếp với DOM mà không gây re-render.
* Thường dùng `useRef` để:
  * Focus input.
  * Scroll đến phần tử.
  * Đếm render hoặc lưu giá trị cũ.
