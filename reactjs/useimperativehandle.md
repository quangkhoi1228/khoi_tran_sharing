# UseImperativeHandle

`useImperativeHandle` là một hook trong React cho phép bạn tùy chỉnh cách mà một child component tiếp cận và tương tác với các phương thức hoặc thuộc tính của nó từ một parent component. Điều này thường được thực hiện bằng cách tạo một giao diện cho child component mà parent component có thể sử dụng, thay vì thông qua các `props`.

**Bước 1: Import các thư viện cần thiết**

```jsx
import React, { useRef, useImperativeHandle, forwardRef } from 'react';
```

Trong ví dụ trên, chúng ta đã import các hook và thành phần cần thiết: `useRef`, `useImperativeHandle` và `forwardRef`.

**Bước 2: Định nghĩa child component**

```jsx
const ChildComponent = forwardRef((props, ref) => {
  const inputRef = useRef(null);

  useImperativeHandle(ref, () => ({
    focusInput: () => {
      inputRef.current.focus();
    },
    getValue: () => {
      return inputRef.current.value;
    }
  }));

  return <input ref={inputRef} type="text" />;
});
```

Trong đoạn mã trên:

* Chúng ta tạo một function component `ChildComponent` sử dụng `forwardRef`, cho phép chúng ta truyền tham chiếu từ parent component vào.
* Chúng ta sử dụng hook `useRef` để tạo một tham chiếu đến phần tử DOM (input).
* Chúng ta sử dụng `useImperativeHandle` để định nghĩa các phương thức mà parent component có thể gọi thông qua tham chiếu.

**Bước 3: Định nghĩa parent component**

```jsx
function ParentComponent() {
  const childRef = useRef(null);

  const handleFocusClick = () => {
    childRef.current.focusInput();
  };

  const handleGetValueClick = () => {
    const value = childRef.current.getValue();
    console.log('Input value:', value);
  };

  return (
    <div>
      <ChildComponent ref={childRef} />
      <button onClick={handleFocusClick}>Focus Input</button>
      <button onClick={handleGetValueClick}>Get Input Value</button>
    </div>
  );
}
```

Trong đoạn mã trên:

* Chúng ta tạo một function component `ParentComponent` và sử dụng hook `useRef` để tạo tham chiếu đến `ChildComponent`.
* Chúng ta sử dụng các phương thức mà đã được định nghĩa trong `useImperativeHandle` để tương tác với `ChildComponent`.

Tóm lại, `useImperativeHandle` cho phép bạn tùy chỉnh cách mà một child component chia sẻ phương thức hoặc thuộc tính với parent component, giúp tạo ra một giao diện tương tác linh hoạt và tránh truyền dữ liệu thông qua `props` trong một số trường hợp đặc biệt.
