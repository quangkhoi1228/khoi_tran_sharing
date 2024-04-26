---
description: >-
  Trong phần này, chúng ta sẽ tìm hiểu về biến và các kiểu dữ liệu cơ bản trong
  ngôn ngữ lập trình JavaScript. Đây là những kiến thức cơ bản nhưng quan trọng
  khi bắt đầu học về JavaScript.
---

# Biến và kiểu dữ liệu

## I. Biến trong JavaScript

Trong JavaScript, biến được sử dụng để lưu trữ dữ liệu. Bạn có thể tưởng tượng biến như là một hộp để lưu trữ thông tin. Dưới đây là cách khai báo một biến:

```javascript
var myVariable;
```

Sau khi bạn đã khai báo một biến, bạn có thể gán giá trị cho nó:

```javascript
myVariable = 10;
```

Hoặc bạn có thể khai báo và gán giá trị cho biến cùng một lúc:

```javascript
var anotherVariable = "Hello, world!";
```

## II. Kiểu dữ liệu trong JavaScript

JavaScript hỗ trợ nhiều kiểu dữ liệu khác nhau, dưới đây là một số kiểu dữ liệu phổ biến:

1. **Number:** Kiểu dữ liệu số. Ví dụ:

```javascript
var age = 25; // Kiểu số nguyên
var price = 9.99; // Kiểu số thực
```

2. **String:** Kiểu dữ liệu chuỗi. Ví dụ:

```javascript
var name = "John"; // Chuỗi kí tự
var message = 'Hello, world!'; // Cũng là chuỗi kí tự
```

3. **Boolean:** Kiểu dữ liệu logic. Ví dụ:

```javascript
var isStudent = true;
var isWorking = false;
```

4. **Array:** Mảng là một cấu trúc dữ liệu để lưu trữ một tập hợp các giá trị. Ví dụ:

```javascript
var numbers = [1, 2, 3, 4, 5]; // Mảng các số nguyên
var fruits = ['apple', 'banana', 'orange']; // Mảng các chuỗi
```

5. **Object:** Đối tượng là một tập hợp các thuộc tính được đặt tên và các giá trị tương ứng. Ví dụ:

```javascript
var person = {
    name: 'John',
    age: 30,
    isStudent: false
};
```

## III. Làm việc với biến và kiểu dữ liệu

Để sử dụng biến và kiểu dữ liệu trong JavaScript, bạn có thể thực hiện các hoạt động như sau:

1. Khai báo biến và gán giá trị cho biến.
2. Sử dụng các toán tử để thực hiện các phép tính số học hoặc các thao tác khác.
3. Sử dụng biến trong các biểu thức điều kiện để kiểm tra và điều khiển luồng của chương trình.
4. Sử dụng biến để lưu trữ thông tin và thao tác với dữ liệu.

## IV. Bài tập thực hành

1. Khai báo một biến và gán một giá trị số cho nó. In ra giá trị của biến.
2. Khai báo một biến và gán một chuỗi kí tự cho nó. In ra chuỗi kí tự đó.
3. Tạo một mảng chứa các số nguyên từ 1 đến 5. In ra các phần tử trong mảng.
4. Tạo một đối tượng để lưu trữ thông tin về một người gồm tên, tuổi và trạng thái học tập. In ra thông tin của người đó.

## V. Tài liệu tham khảo

* [MDN Web Docs - JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
