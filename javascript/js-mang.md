---
description: >-
  Trong JavaScript, mảng (Array) là một cấu trúc dữ liệu được sử dụng để lưu trữ
  và quản lý một tập hợp các giá trị. Mảng cho phép lưu trữ nhiều giá trị trong
  một biến và truy cập vào chúng bằng chỉ số.
---

# JS Mảng

### Khai Báo Mảng

Để khai báo một mảng trong JavaScript, bạn sử dụng cặp dấu ngoặc vuông `[]` và liệt kê các phần tử của mảng, phân cách bởi dấu phẩy.

```javascript
let numbers = [1, 2, 3, 4, 5];
```

### Truy Cập Phần Tử trong Mảng

Để truy cập một phần tử trong mảng, bạn sử dụng chỉ số của phần tử đó, bắt đầu từ 0.

```javascript
let firstNumber = numbers[0]; // Lấy phần tử đầu tiên trong mảng
```

### Các Phương Thức của Mảng

JavaScript cung cấp một loạt các phương thức hữu ích để thao tác với mảng như `push()`, `pop()`, `shift()`, `unshift()`.

#### 1. `push()`

Phương thức `push()` được sử dụng để thêm một phần tử vào cuối mảng.

```javascript
numbers.push(6); // Thêm phần tử 6 vào cuối mảng
```

#### 2. `pop()`

Phương thức `pop()` loại bỏ phần tử cuối cùng của mảng và trả về phần tử đó.

```javascript
let lastNumber = numbers.pop(); // Loại bỏ và trả về phần tử cuối cùng của mảng
```

#### 3. `shift()`

Phương thức `shift()` loại bỏ phần tử đầu tiên của mảng và trả về phần tử đó.

```javascript
let firstNumber = numbers.shift(); // Loại bỏ và trả về phần tử đầu tiên của mảng
```

#### 4. `unshift()`

Phương thức `unshift()` thêm một phần tử vào đầu mảng và trả về độ dài mới của mảng.

```javascript
let newLength = numbers.unshift(0); // Thêm phần tử 0 vào đầu mảng
```

### Bài Tập Thực Hành

1. Tạo một mảng chứa tên của bạn và in mảng đó ra console.
2. Thêm một số mới vào mảng và in mảng sau khi thêm ra console.
3. Loại bỏ phần tử cuối cùng của mảng và in mảng sau khi loại bỏ ra console.
