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






























