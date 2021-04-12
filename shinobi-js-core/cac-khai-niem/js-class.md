# JS class

## JS class là gì?

ECMAScript 2015 hay còn được biết đến là ES6, đã giới thiệu về JavaScript Classes

JavaScript Classes là template cho JavaScript Objects nhưng nó không phải là Object

## Cú pháp

 Sử dụng từ khóa `class` để tạo class và luôn nhớ thêm phương thức `constructor()`

```javascript
class ClassName {
  constructor() { ... }
}
```

Ví dụ: 

```javascript
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
}
```

Tạo ra 1 lớp Car với 2 thuộc tính là name và year

## Cách sử dụng

Có thể tạo Object nếu bạn đã có 1 JS class trước đó

```javascript
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
}

myCar = new Car("Ford", 2014);
console.log(myCar.name + " " + myCar.year);
//Ford 2014
```

## Phương thức Constructor

Phương thức `constructor` là một phương thức đặc biệt:

* Nó phải có tên chính xác là "constructor"
* Nó được tự động thực thi khi một Object được tạo
* Nó được sử dụng để khởi tạo các thuộc tính của đối tượng

Nếu bạn không định nghĩa `constructor`, JS sẽ tự động thêm 1 `constructor` rỗng 

## Phương thức của class\(Class method\)

Class methods được tạo với cú pháp giống như Object methods

Sử dụng từ khóa `class` để tạo class và thêm phương thức `constructor()` 

Sau đó thêm các method cần thiết

```javascript
class ClassName {
  constructor() { ... }
  method_1() { ... }
  method_2() { ... }
  method_3() { ... }
}
```

Ví dụ:

```javascript
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;

  }
  age() {
    let date = new Date();
    return date.getFullYear() - this.year;
  }
}

let myCar = new Car("Ford", 2014);
console.log("My car is " + myCar.age() + " years old.")
//My car is 7 years old.
```

## Class trước ES6

Trước 2015, JS chưa hỗ trợ Class nhưng chúng ta có thể tạo template cho Object bằng cú pháp khác.

```javascript
(function () {
    // constructor
    var constructor = function () {
    ...
    };
    return constructor;
})();
```

 Ưu điểm:

* Trình duyệt không hỗ trợ Class vẫn có thể hiểu được
* Cách viết các thuộc tính và phương thức không khác cách viết bằng JS class

Nhược điểm:

* Cấu trúc dài dòng và khó hiểu hơn class
* Không truy suất được từ khóa `this` trực tiếp

Ví dụ:

```javascript
var Car = (function () {
    // constructor
    var constructor = function (name, year) {
        this.name = name;
        this.year = year;
        this.age = function () {
            var object = this
            let date = new Date();
            return date.getFullYear() - this.year;
        };
    };
    return constructor;
})();

let myCar = new Car("Ford", 2014);
console.log("My car is " + myCar.age() + " years old.")
//My car is 7 years old.
```



























