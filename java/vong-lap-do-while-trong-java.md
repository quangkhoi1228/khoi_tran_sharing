# Vòng lặp Do-while trong Java

## Giới thiệu về Vòng Lặp Do-While trong Java

Trong lập trình Java, vòng lặp `do-while` được sử dụng để lặp lại một khối mã ít nhất một lần, sau đó kiểm tra điều kiện để xác định xem vòng lặp có tiếp tục hay không. Trong bài giảng này, chúng ta sẽ tìm hiểu cách sử dụng vòng lặp `do-while` trong Java và cách áp dụng chúng trong các trường hợp khác nhau.

## **Cú Pháp của Vòng Lặp Do-While**

Cú pháp của vòng lặp `do-while` trong Java như sau:

```java
do {
    // Khối mã được lặp lại ít nhất một lần
    // Các câu lệnh trong khối mã này sẽ được thực thi trước khi kiểm tra điều kiện
} while (điều_kiện);
```

### **Ví dụ về Vòng Lặp Do-While**

Dưới đây là một ví dụ minh họa về cách sử dụng vòng lặp `do-while` để in các số nguyên từ 1 đến 5:

```java
int i = 1;

do {
    System.out.println(i);
    i++;
} while (i <= 5);
```

## **Bài Tập Thực Hành:**

1. Viết một chương trình Java sử dụng vòng lặp `do-while` để yêu cầu người dùng nhập một số nguyên dương, sau đó in ra các số từ 1 đến số nguyên đó.

## **Lưu Ý:**

* Vòng lặp `do-while` đảm bảo rằng khối mã bên trong nó được thực thi ít nhất một lần, ngay cả khi điều kiện không thỏa mãn.

## **Kết Luận**

Trên đây là cách sử dụng vòng lặp `do-while` trong Java để lặp lại một khối mã ít nhất một lần và kiểm tra điều kiện sau mỗi lần lặp. Việc hiểu và sử dụng chúng đúng cách sẽ giúp bạn viết các chương trình Java linh hoạt và hiệu quả.
