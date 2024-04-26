---
description: >-
  Trong bài học này, chúng ta sẽ tìm hiểu về cách khai báo và sử dụng hàm trong
  ngôn ngữ lập trình JavaScript.
---

# Hàm (Function)

## I. Khái Niệm về Hàm

Hàm là một khối mã có thể được gọi lại (hay được "gọi") từ một nơi khác trong chương trình. Hàm thường được sử dụng để thực hiện một nhiệm vụ cụ thể hoặc một tác vụ nhất định.

## II. Khai Báo Hàm

Trong JavaScript, bạn có thể khai báo hàm bằng cách sử dụng từ khóa `function`.

**Cú Pháp:**

```javascript
function myFunction() {
    // Khối mã thực hiện một tác vụ cụ thể
    console.log("Đây là một hàm!");
}
```

## III. Gọi Hàm

Sau khi bạn đã khai báo một hàm, bạn có thể gọi nó từ bất kỳ đâu trong chương trình bằng cách sử dụng tên của hàm, theo sau bởi các dấu ngoặc đơn `()`.

**Ví dụ:**

```javascript
myFunction(); // Gọi hàm myFunction()
```

## IV. Tham Số và Trả Về

Hàm có thể nhận đầu vào thông qua các tham số và có thể trả về một giá trị sử dụng từ khóa `return`.

**Ví dụ:**

```javascript
function add(a, b) {
    return a + b;
}

var result = add(3, 5); // result = 8
```

## V. Hàm Vô Danh (Anonymous Function)

Bạn cũng có thể tạo hàm không có tên gọi là hàm vô danh, hoặc còn được gọi là hàm lambda.

**Ví dụ:**

```javascript
var greeting = function() {
    console.log("Xin chào!");
};

greeting(); // In ra "Xin chào!"
```

## VI. Hàm Arrow (Arrow Function)

Hàm arrow là một cách ngắn gọn để khai báo hàm trong JavaScript.

**Ví dụ:**

```javascript
var multiply = (a, b) => a * b;

var result = multiply(3, 4); // result = 12
```

## VII. Bài Tập Thực Hành

1. Viết một hàm tính tổng của hai số và in ra kết quả.
2. Viết một hàm kiểm tra xem một số có phải là số nguyên tố hay không và trả về true hoặc false.
3. Viết một hàm nhận vào một mảng các số và trả về số lớn nhất trong mảng đó.

#### VIII. Tài Liệu Tham Khảo

* [MDN Web Docs - Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
