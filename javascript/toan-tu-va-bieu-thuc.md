---
description: >-
  Chúng ta sẽ tìm hiểu về các toán tử và biểu thức trong ngôn ngữ lập trình
  JavaScript. Các toán tử là các ký hiệu được sử dụng để thực hiện các phép tính
  hoặc so sánh giữa các giá trị
---

# Toán tử và biểu thức

## I. Toán Tử Số Học

JavaScript hỗ trợ các toán tử số học cơ bản như `+` (cộng), `-` (trừ), `*` (nhân), `/` (chia), và `%` (chia lấy dư).

**Ví dụ:**

```javascript
var sum = 10 + 5; // sum = 15
var difference = 10 - 5; // difference = 5
var product = 10 * 5; // product = 50
var quotient = 10 / 5; // quotient = 2
var remainder = 10 % 3; // remainder = 1
```

## II. Toán Tử Gán Giá Trị

Toán tử `=` được sử dụng để gán giá trị cho biến.

**Ví dụ:**

```javascript
var x = 10;
var y = 5;
```

## III. Toán Tử So Sánh

JavaScript cung cấp các toán tử so sánh như `==` (bằng), `!=` (khác), `>` (lớn hơn), `<` (nhỏ hơn), `>=` (lớn hơn hoặc bằng), và `<=` (nhỏ hơn hoặc bằng).

**Ví dụ:**

```javascript
var a = 10;
var b = 5;
console.log(a == b); // false
console.log(a > b); // true
console.log(a <= b); // false
```

## IV. Toán Tử Logic

Các toán tử logic trong JavaScript bao gồm `&&` (và), `||` (hoặc), và `!` (phủ định).

**Ví dụ:**

```javascript
var x = true;
var y = false;
console.log(x && y); // false
console.log(x || y); // true
console.log(!x); // false
```

## V. Biểu Thức

Biểu thức trong JavaScript là một tổ hợp của các giá trị, biến và toán tử có thể đánh giá thành một giá trị duy nhất.

**Ví dụ:**

```javascript
var result = (10 + 5) * 2; // result = 30
var age = 25;
var isAdult = age >= 18; // isAdult = true
```

## VI. Bài Tập Thực Hành

1. Viết một biểu thức tính tổng của hai số và in kết quả ra console.
2. Viết một biểu thức kiểm tra xem một số có lớn hơn 10 không và in kết quả ra console.
3. Viết một biểu thức kiểm tra xem một số có chia hết cho 2 và 3 không và in kết quả ra console.

## VII. Tài Liệu Tham Khảo

* [MDN Web Docs - JavaScript Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators)
