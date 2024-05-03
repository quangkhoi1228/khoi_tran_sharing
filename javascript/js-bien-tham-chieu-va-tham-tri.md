---
description: >-
  Trong JavaScript, khi bạn làm việc với biến, có sự khác biệt giữa biến tham
  trị và biến tham chiếu. Hiểu sự khác biệt này là quan trọng để tránh các lỗi
  logic và hiểu rõ cách làm việc của JavaScript.
---

# JS Biến Tham Chiếu và Tham Trị

### Biến Tham Trị

Biến tham trị là biến mà giá trị của chúng được sao chép khi được gán cho một biến khác. Các kiểu dữ liệu như số, chuỗi và boolean được xem là biến tham trị.

```javascript
let a = 5;
let b = a; // Giá trị của a (5) được sao chép vào b
b = 10;
console.log(a); // Output: 5
console.log(b); // Output: 10
```

### Biến Tham Chiếu

Biến tham chiếu là biến mà giá trị của chúng là địa chỉ của vùng nhớ chứa dữ liệu thực sự. Điều này có nghĩa là khi bạn gán một biến tham chiếu cho một biến khác, cả hai biến đều trỏ vào cùng một đối tượng hoặc mảng.

```javascript
let arr1 = [1, 2, 3];
let arr2 = arr1; // arr2 tham chiếu đến cùng một mảng như arr1
arr2.push(4);
console.log(arr1); // Output: [1, 2, 3, 4]
console.log(arr2); // Output: [1, 2, 3, 4]
```

### Bài Tập Thực Hành

1. Viết một hàm `changeNumber` nhận một tham số là một số và thay đổi giá trị của tham số đó thành 10. Kiểm tra xem giá trị của biến gốc có thay đổi hay không sau khi gọi hàm.
2. Viết một hàm `changeArray` nhận một tham số là một mảng và thêm số 4 vào mảng đó. Kiểm tra xem mảng gốc có thay đổi hay không sau khi gọi hàm.
