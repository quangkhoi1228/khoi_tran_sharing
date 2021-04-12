# JS class

## JS class là gì?

ECMAScript 2015 hay còn được biết đến là ES6, đã giới thiệu về JavaScript Classes

JavaScript Classes là template cho JavaScript Objects nhưng nó không phải là Object

## Cú pháp

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





























