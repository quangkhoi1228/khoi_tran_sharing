# JS Class

## JavaScript Class

Trong JavaScript, class là một cấu trúc dữ liệu giúp tạo ra các đối tượng có cùng thuộc tính và phương thức. Sử dụng class, bạn có thể tạo ra các đối tượng mới dựa trên một mẫu cụ thể, giúp quản lý mã nguồn dễ dàng hơn và tạo ra các ứng dụng phức tạp hơn.

### Định Nghĩa Class

Bạn có thể định nghĩa một class bằng cách sử dụng từ khóa `class` và tên của class.

```javascript
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
}
```

Trong ví dụ trên, `Person` là tên của class. Phương thức `constructor` được sử dụng để khởi tạo các thuộc tính của đối tượng khi nó được tạo. `greet()` là một phương thức của class `Person`.

### Tạo Đối Tượng từ Class

Để tạo một đối tượng từ class, bạn sử dụng từ khóa `new` và gọi constructor của class.

```javascript
let person1 = new Person("John", 30);
let person2 = new Person("Alice", 25);

person1.greet(); // Output: Hello, my name is John and I am 30 years old.
person2.greet(); // Output: Hello, my name is Alice and I am 25 years old.
```

### Bài Tập Thực Hành

1. Tạo một class `Car` có các thuộc tính như `brand`, `model` và `year`.
2. Thêm một phương thức `displayInfo()` vào class `Car` để hiển thị thông tin của chiếc xe.
3. Tạo một số đối tượng từ class `Car` và gọi phương thức `displayInfo()` của chúng.
