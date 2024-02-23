---
description: >-
  Trong bài học này, chúng ta sẽ tìm hiểu về các hàm built-in cơ bản của
  JavaScript. Các hàm này là những hàm được cung cấp sẵn bởi ngôn ngữ JS và có
  thể được sử dụng mà không cần phải định nghĩa
---

# Các hàm có sẵn

## I. Hàm `alert()`

Hàm `alert()` được sử dụng để hiển thị một hộp thoại thông báo với một thông điệp cho người dùng.

**Cú pháp:**

```javascript
alert("Hello, world!");
```

## II. Hàm `prompt()`

Hàm `prompt()` được sử dụng để hiển thị một hộp thoại yêu cầu người dùng nhập vào một giá trị.

**Cú pháp:**

```javascript
var userInput = prompt("Nhập tên của bạn:");
console.log("Bạn đã nhập: " + userInput);
```

## III. Hàm `confirm()`

Hàm `confirm()` được sử dụng để hiển thị một hộp thoại xác nhận với hai lựa chọn "OK" hoặc "Cancel".

**Cú pháp:**

```javascript
var isConfirmed = confirm("Bạn có chắc chắn muốn tiếp tục?");
if (isConfirmed) {
    console.log("Người dùng đã chọn OK.");
} else {
    console.log("Người dùng đã chọn Cancel.");
}
```

## IV. Hàm `console.log()`

Hàm `console.log()` được sử dụng để ghi thông điệp ra console của trình duyệt hoặc của môi trường thực thi JavaScript.

**Cú pháp:**

```javascript
console.log("Hello, world!");
```

Hàm `parseInt()` được sử dụng để chuyển đổi một chuỗi thành một số nguyên, còn `parseFloat()` để chuyển đổi thành số thực.

**Cú pháp:**

```javascript
var integerNumber = parseInt("10");
var floatNumber = parseFloat("3.14");
```

## V. Hàm `String()`, `Number()` và `Boolean()`

Các hàm `String()`, `Number()` và `Boolean()` được sử dụng để chuyển đổi các kiểu dữ liệu khác thành chuỗi, số và boolean tương ứng.

**Cú pháp:**

```javascript
var str = String(123); // str = "123"
var num = Number("3.14"); // num = 3.14
var bool = Boolean(0); // bool = false
```

## VI. Bài Tập Thực Hành

1. Sử dụng hàm `alert()` để hiển thị thông điệp chào mừng.
2. Sử dụng hàm `prompt()` để yêu cầu người dùng nhập tên của họ và sau đó hiển thị tên đó lên console.
3. Sử dụng hàm `confirm()` để xác nhận có muốn tiếp tục không và sau đó hiển thị kết quả lên console.
