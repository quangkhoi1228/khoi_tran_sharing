# UseRef

Trong React, `useRef` là một hook được sử dụng để tham chiếu đến các phần tử DOM hoặc để lưu trữ các giá trị có thể thay đổi mà không gây ra việc render lại component. `useRef` thường được sử dụng trong các tình huống không liên quan đến việc cập nhật giao diện người dùng.

Để sử dụng `useRef`, bạn cũng cần import nó từ thư viện React:

```jsx
import React, { useRef } from 'react';
```

Sau đó, bạn có thể sử dụng `useRef` trong component của bạn như sau:

```jsx
function TextInput() {
  // Khởi tạo một tham chiếu đến phần tử input DOM
  const inputRef = useRef(null);

  const focusInput = () => {
    // Sử dụng current để truy cập vào phần tử DOM
    inputRef.current.focus();
  };

  return (
    <div>
      <input type="text" ref={inputRef} />
      <button onClick={focusInput}>Focus Input</button>
    </div>
  );
}
```

Trong ví dụ trên, `useRef(null)` tạo một tham chiếu đến phần tử input DOM. Khi bạn gọi `inputRef.current`, bạn có thể truy cập vào phần tử DOM tương ứng.

`useRef` cũng có thể được sử dụng để lưu trữ giá trị có thể thay đổi mà không gây ra việc render lại component. Điều này có thể hữu ích trong các trường hợp mà bạn cần lưu trữ dữ liệu nhưng không muốn kích hoạt việc render lại component khi dữ liệu thay đổi.

```jsx
function Counter() {
  const countRef = useRef(0);

  const increment = () => {
    countRef.current += 1; // Cập nhật giá trị mà không gây render lại component
    console.log('Current count:', countRef.current);
  };

  return (
    <div>
      <p>Counter using useRef</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
}
```

Lưu ý rằng việc thay đổi giá trị của `useRef` sẽ không gây ra việc render lại component. Điều này làm cho nó phù hợp để lưu trữ các giá trị "không gây ảnh hưởng" đến giao diện người dùng.
