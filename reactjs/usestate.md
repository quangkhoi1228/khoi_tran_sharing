# UseState

Trong React, `useState` là một hook được sử dụng để quản lý state (trạng thái) của một component. Nó cho phép bạn giữ và cập nhật dữ liệu trong một component functional (không phải là class component). `useState` cho phép bạn thay đổi state mà không cần phải viết lại toàn bộ component.

Để sử dụng `useState`, bạn cần import nó từ thư viện React:

```jsx
import React, { useState } from 'react';
```

Sau đó, bạn có thể sử dụng nó trong component của bạn như sau:

```jsx
function Counter() {
  // Khởi tạo state và hàm để cập nhật state
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1); // Cập nhật state count
  };

  const decrement = () => {
    setCount(count - 1); // Cập nhật state count
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
    </div>
  );
}
```

Trong ví dụ trên, `useState(0)` khởi tạo state `count` với giá trị ban đầu là 0 và trả về một cặp giá trị: giá trị của state và hàm để cập nhật state đó. Bằng cách gọi `setCount` với một giá trị mới, bạn có thể cập nhật state `count`.

Mỗi khi state thay đổi, React sẽ tự động render lại component, hiển thị các thay đổi mới.

Lưu ý rằng tên biến và hàm cập nhật state có thể khác nhau (không nhất thiết phải đặt theo mẫu `setTênBiến`). Điều này giúp bạn tạo ra mã dễ đọc hơn và tránh nhầm lẫn.
