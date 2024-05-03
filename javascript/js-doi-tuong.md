# JS Đối tượng

## JavaScript Object

Trong JavaScript, đối tượng (Object) là một cấu trúc dữ liệu dạng tập hợp các cặp key-value, trong đó key là một chuỗi (hoặc symbol), và value có thể là bất kỳ kiểu dữ liệu nào, bao gồm cả hàm, mảng, hoặc đối tượng khác.

### Khai Báo Đối Tượng

Để khai báo một đối tượng trong JavaScript, bạn sử dụng cặp dấu ngoặc nhọn `{}` và liệt kê các cặp key-value bên trong.

```javascript
let person = {
    name: "John",
    age: 30,
    address: "123 Main Street"
};
```

### Truy Cập Thuộc Tính của Đối Tượng

Bạn có thể truy cập vào các thuộc tính của một đối tượng bằng cách sử dụng "dot notation" hoặc "bracket notation".

```javascript
let personName = person.name; // Sử dụng dot notation
let personAge = person['age']; // Sử dụng bracket notation
```

### Thêm và Xóa Thuộc Tính của Đối Tượng

Bạn có thể thêm hoặc xóa các thuộc tính của một đối tượng bằng cách gán giá trị hoặc sử dụng phương thức `delete`.

```javascript
person.email = "john@example.com"; // Thêm thuộc tính mới vào đối tượng
delete person.address; // Xóa thuộc tính address của đối tượng
```

### Bài Tập Thực Hành

1. Tạo một đối tượng mô tả một cuốn sách với các thuộc tính như `title`, `author` và `year`. In các thuộc tính của đối tượng này ra console.
2. Thêm một thuộc tính mới vào đối tượng và in lại các thuộc tính của đối tượng sau khi thêm ra console.
3. Xóa một thuộc tính của đối tượng và in lại các thuộc tính của đối tượng sau khi xóa ra console.
