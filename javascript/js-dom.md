---
description: >-
  Trong lập trình web, DOM (Document Object Model) là một giao diện lập trình
  ứng dụng (API) cho phép các trang web tương tác và thay đổi nội dung, cấu trúc
  và kiểu dáng của các phần tử HTML.
---

# JS DOM

### Truy Cập Phần Tử HTML

Để truy cập các phần tử HTML trong DOM, bạn có thể sử dụng các phương thức sau:

* `getElementById()`: Truy cập phần tử bằng id.
* `getElementsByClassName()`: Truy cập các phần tử bằng class.
* `getElementsByTagName()`: Truy cập các phần tử bằng tên thẻ.
* `querySelector()`: Truy cập phần tử đầu tiên phù hợp với selector.

Ví dụ:

```javascript
// Truy cập phần tử có id là "myElement"
let elementById = document.getElementById("myElement");

// Truy cập các phần tử có class là "myClass"
let elementsByClassName = document.getElementsByClassName("myClass");

// Truy cập các phần tử thẻ "p"
let elementsByTagName = document.getElementsByTagName("p");

// Truy cập phần tử đầu tiên có class là "myClass"
let elementByQuerySelector = document.querySelector(".myClass");
```

### Thay Đổi Nội Dung của Phần Tử HTML

Bạn có thể thay đổi nội dung của các phần tử HTML bằng cách sử dụng thuộc tính `innerHTML` hoặc `textContent`.

```javascript
// Thay đổi nội dung của phần tử có id là "myElement"
elementById.innerHTML = "<strong>Hello</strong>, world!";
```

Hoặc:

```javascript
// Thay đổi nội dung của phần tử có id là "myElement"
elementById.textContent = "Hello, world!";
```

### Thêm và Xóa Phần Tử HTML

Bạn có thể thêm và xóa các phần tử HTML trong DOM bằng cách sử dụng các phương thức sau:

* `appendChild()`: Thêm một phần tử con vào cuối danh sách phần tử con của một phần tử.
* `removeChild()`: Xóa một phần tử con khỏi danh sách phần tử con của một phần tử.

Ví dụ:

```javascript
// Tạo một phần tử mới
let newElement = document.createElement("div");
newElement.textContent = "New element";

// Thêm phần tử mới vào phần tử có id là "container"
document.getElementById("container").appendChild(newElement);
```

Hoặc:

```javascript
// Xóa phần tử có id là "myElement"
let elementToRemove = document.getElementById("myElement");
elementToRemove.parentNode.removeChild(elementToRemove);
```

### Bài Tập Thực Hành

1. Tạo một trang web với một phần tử `<div>` có id là "container".
2. Sử dụng JavaScript để thêm một phần tử `<p>` vào bên trong phần tử có id là "container", với nội dung là "Hello, world!".
3. Thêm một sự kiện click vào phần tử `<p>` và khi được click, thay đổi nội dung của phần tử thành "You clicked me!".
