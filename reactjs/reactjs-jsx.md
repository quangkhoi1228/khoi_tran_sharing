# 3. useState hook

### Khái niệm useState

`useState` là một **React Hook** dùng để tạo và quản lý **state** trong function component. Khi giá trị state thay đổi, component sẽ tự động **re-render** và cập nhật giao diện tương ứng.

Cú pháp:

```tsx
const [state, setState] = useState<Loại>(giáTrịKhởiTạo);
```

* `state`: biến chứa giá trị hiện tại của state.
* `setState`: hàm để cập nhật giá trị state.
* `giáTrịKhởiTạo`: giá trị mặc định khi component lần đầu render.
* `Loại`: kiểu dữ liệu bạn muốn lưu trong state (TypeScript).

### Cách dùng useState với ví dụ cơ bản

Ví dụ đếm số đơn giản:

```tsx
'use client';

import { useState } from 'react';

export default function Counter() {
  const [count, setCount] = useState<number>(0);

  return (
    <div>
      <p>Bạn đã click {count} lần</p>
      <button onClick={() => setCount(count + 1)}>Click tôi</button>
    </div>
  );
}
```

Giải thích:

* Khởi tạo state `count` bằng 0.
* Khi click nút, gọi `setCount(count + 1)` để tăng giá trị `count` lên 1.
* Component tự động render lại hiển thị số lần click.

### Cập nhật state với callback

Khi việc cập nhật phụ thuộc vào giá trị cũ, nên dùng callback để đảm bảo chính xác:

```tsx
setCount(prevCount => prevCount + 1);
```

### useState với các kiểu dữ liệu khác nhau

#### String

```tsx
const [text, setText] = useState<string>('');
setText('Xin chào');
```

#### Boolean

```tsx
const [isVisible, setIsVisible] = useState<boolean>(true);
setIsVisible(false);
```

#### Mảng

```tsx
const [list, setList] = useState<string[]>([]);

setList(prevList => [...prevList, 'item mới']);
```

#### Object

```tsx
type User = {
  name: string;
  age: number;
};

const [user, setUser] = useState<User>({ name: 'An', age: 20 });

setUser(prevUser => ({ ...prevUser, age: 21 }));
```

### Sự khác nhau giữa biến thường và useState

| Đặc điểm                     | Biến thường          | useState                    |
| ---------------------------- | -------------------- | --------------------------- |
| Giá trị có giữ qua render?   | Không                | Có                          |
| Thay đổi có làm UI cập nhật? | Không                | Có                          |
| Khởi tạo khi nào?            | Mỗi lần hàm chạy lại | Một lần khi component mount |

Ví dụ:

```tsx
'use client';

import { useState } from 'react';

export default function Demo() {
  let normal = 0;
  const [state, setState] = useState(0);

  return (
    <div>
      <p>Biến thường: {normal}</p>
      <p>State: {state}</p>
      <button
        onClick={() => {
          normal++;
          setState(prev => prev + 1);
        }}
      >
        Click
      </button>
    </div>
  );
}
```

**Kết quả:** `normal` không thay đổi khi click vì không giữ giá trị qua render, `state` thay đổi và UI cập nhật.

### Bài tập thực hành

#### Bài tập 1: Tạo counter

* Tạo component đếm số.
* Có nút tăng, nút giảm.
* Hiển thị giá trị hiện tại.

#### Bài tập 2: Form nhập liệu

* Tạo form nhập tên và email.
* Dùng `useState` lưu giá trị input.
* Hiển thị thông tin nhập bên dưới.

#### Bài tập 3: Danh sách todo

* Tạo danh sách công việc cần làm.
* Thêm công việc mới.
* Xóa công việc khi click.
