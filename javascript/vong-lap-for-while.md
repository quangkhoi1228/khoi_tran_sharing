---
description: >-
  Trong bài học này, chúng ta sẽ tìm hiểu về hai loại vòng lặp cơ bản trong
  JavaScript: vòng lặp for và while.
---

# Vòng lặp For / While

## I. Vòng Lặp `for`

Vòng lặp `for` được sử dụng để lặp qua một tập hợp các giá trị nhiều lần.

**Cú Pháp:**

```javascript
for (var i = 0; i < 5; i++) {
    console.log(i);
}
```

## II. Vòng Lặp `while`

Vòng lặp `while` được sử dụng để lặp một khối mã khi một điều kiện cụ thể vẫn là đúng.

**Cú Pháp:**

```javascript
var i = 0;
while (i < 5) {
    console.log(i);
    i++;
}
```

## III. Sự Khác Biệt Giữa `for` và `while`

* `for`: Thường được sử dụng khi bạn biết trước số lần lặp cụ thể.
* `while`: Thường được sử dụng khi bạn không biết trước số lần lặp và muốn lặp lại cho đến khi một điều kiện cụ thể không còn đúng nữa.

## IV. Bài Tập Thực Hành

1. Viết một chương trình sử dụng vòng lặp `for` để in ra các số từ 1 đến 10.
2. Viết một chương trình sử dụng vòng lặp `while` để in ra bảng nhân của một số cụ thể.
3. Viết một chương trình sử dụng vòng lặp `for` để tính tổng của các số từ 1 đến 100.

## V. Tài Liệu Tham Khảo

* [MDN Web Docs - JavaScript Loops and Iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops\_and\_iteration)
