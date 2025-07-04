# 6. useEffect hook

## useEffect – Hook theo dõi và side effect

### useEffect dùng để làm gì?

`useEffect` là một hook của React được sử dụng để xử lý các **side effects** trong component. Side effects là các tác động phụ bên ngoài ngoài việc render giao diện, ví dụ như:

* Gọi API lấy dữ liệu.
* Đăng ký sự kiện (event listener).
* Cập nhật DOM thủ công.
* Khởi tạo hoặc dọn dẹp timer (setInterval, setTimeout).
* Theo dõi hoặc ghi log dữ liệu khi state hoặc props thay đổi.

`useEffect` cho phép bạn chạy một hàm nào đó **sau khi component được render** (hoặc khi dependency thay đổi), không làm cản trở quá trình render UI.

***

### Cách dùng useEffect với dependency array

Cú pháp cơ bản:

```tsx
useEffect(() => {
  // Code side effect
  return () => {
    // Cleanup (nếu cần)
  };
}, [dependencies]);
```

* Tham số đầu tiên: hàm callback chạy khi component render và khi dependency thay đổi.
* Tham số thứ hai: mảng `dependencies` là các biến React theo dõi. Nếu giá trị trong mảng này thay đổi, hàm callback sẽ chạy lại.
* Nếu không truyền dependency array, effect sẽ chạy sau mỗi lần render (gây lặp lại nhiều lần).
* Nếu truyền mảng rỗng `[]`, effect chỉ chạy **1 lần khi component mount** (tương đương componentDidMount).

***

### Các trường hợp dùng useEffect theo dependency

* `[]` (mảng rỗng): chạy 1 lần sau khi component mount. Ví dụ: gọi API một lần hoặc đăng ký event listener.
* `[someVar]`: chạy mỗi khi biến `someVar` thay đổi. Ví dụ: khi user nhập input, muốn theo dõi giá trị input để làm gì đó.
* Không truyền mảng dependency: chạy sau mỗi lần render (ít dùng vì gây hiệu suất kém).

***

### Cleanup function trong useEffect

Khi effect tạo ra các side effect có thể tồn tại lâu (ví dụ: timer, event listener), ta cần **dọn dẹp** để tránh rò rỉ bộ nhớ hoặc hành vi không mong muốn.

* `useEffect` trả về một hàm `cleanup` sẽ được gọi trước khi effect chạy lại hoặc khi component unmount (gỡ bỏ).

Ví dụ cleanup:

```tsx
useEffect(() => {
  const intervalId = setInterval(() => {
    console.log('Tick');
  }, 1000);

  return () => {
    clearInterval(intervalId); // Dọn dẹp timer khi component unmount hoặc effect chạy lại
  };
}, []);
```

***

### Ví dụ thực hành chi tiết

```tsx
'use client';

import { useState, useEffect } from 'react';

export default function UseEffectExample() {
  const [count, setCount] = useState(0);
  const [inputValue, setInputValue] = useState('');

  // Effect theo dõi count
  useEffect(() => {
    console.log(`Count đã thay đổi: ${count}`);
  }, [count]); // chỉ chạy khi count thay đổi

  // Effect theo dõi inputValue
  useEffect(() => {
    console.log(`InputValue đã thay đổi: ${inputValue}`);
  }, [inputValue]);

  // Effect chạy 1 lần khi component mount (tạo interval)
  useEffect(() => {
    const intervalId = setInterval(() => {
      console.log('Interval đang chạy mỗi giây');
    }, 1000);

    // Cleanup interval khi unmount
    return () => {
      clearInterval(intervalId);
      console.log('Interval đã được dọn dẹp');
    };
  }, []);

  return (
    <div style={{ padding: 20 }}>
      <h2>useEffect – Ví dụ theo dõi và side effect</h2>

      <button onClick={() => setCount(count + 1)}>Click đếm số lần: {count}</button>

      <div style={{ marginTop: 20 }}>
        <label>
          Nhập text: 
          <input
            type="text"
            value={inputValue}
            onChange={e => setInputValue(e.target.value)}
            placeholder="Gõ gì đó..."
          />
        </label>
      </div>
    </div>
  );
}
```

#### Giải thích ví dụ

* Mỗi khi nhấn nút, state `count` thay đổi, effect đầu tiên chạy in ra log.
* Mỗi khi nhập input, state `inputValue` thay đổi, effect thứ hai chạy.
* Khi component mount, effect thứ ba tạo timer `setInterval` chạy log mỗi giây.
* Khi component unmount, hàm cleanup dọn dẹp timer để không còn chạy nữa.

***

## Bài tập thực hành

1. Tạo component đếm số lần click và hiển thị số lần click.
2. Theo dõi giá trị input text và in ra console mỗi khi thay đổi.
3. Tạo `setInterval` đếm ngược từ 10 đến 0, mỗi giây giảm 1. Khi đếm đến 0, dừng timer.
4. Dùng cleanup function để dọn timer khi component unmount.
5. Thêm nút "Reset" để khởi động lại đếm ngược.
