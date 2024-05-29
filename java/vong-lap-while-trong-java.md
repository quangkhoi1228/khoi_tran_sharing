# Vòng lặp While trong Java

## Giới thiệu về Vòng Lặp While trong Java

Trong lập trình Java, vòng lặp `while` được sử dụng để lặp lại một khối mã cho đến khi điều kiện kiểm tra trở thành `false`. Trong bài giảng này, chúng ta sẽ tìm hiểu cách sử dụng vòng lặp `while` trong Java và cách áp dụng chúng trong các trường hợp khác nhau.

## **Cú Pháp của Vòng Lặp While**

Cú pháp của vòng lặp `while` trong Java như sau:

```java
while (điều_kiện) {
    // Khối mã được lặp lại khi điều_kiện là true
    // Các câu lệnh trong khối mã này sẽ được thực thi cho đến khi điều_kiện trở thành false
}
```

### **Ví dụ về Vòng Lặp While**

Dưới đây là một ví dụ minh họa về cách sử dụng vòng lặp `while` để in các số nguyên từ 1 đến 5:

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
    i++;
}
```

## **Bài Tập Thực Hành:**

1. Viết một chương trình Java sử dụng vòng lặp `while` để in ra các bảng cửu chương từ 2 đến 9.

{% hint style="info" %}
**Lưu Ý:**

* Tránh việc gán giá trị cho biến điều kiện bên trong vòng lặp mà không thay đổi giá trị của biến đó, điều này có thể dẫn đến vòng lặp vô hạn.
* Luôn đảm bảo rằng điều kiện của vòng lặp sẽ trở thành false tại một điểm nào đó để tránh vòng lặp vô hạn.
{% endhint %}

## **Kết Luận**

Trên đây là cách sử dụng vòng lặp `while` trong Java để lặp lại một khối mã cho đến khi điều kiện trở thành `false`. Việc hiểu và sử dụng chúng đúng cách sẽ giúp bạn viết các chương trình Java linh hoạt và hiệu quả.
