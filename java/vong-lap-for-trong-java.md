# Vòng lặp For trong Java

## Giới thiệu về Vòng Lặp For trong Java

Vòng lặp `for` trong Java là một công cụ mạnh mẽ để lặp lại một khối mã một số lần nhất định. Trong bài giảng này, chúng ta sẽ tìm hiểu cách sử dụng vòng lặp `for` trong Java và cách áp dụng chúng trong các trường hợp khác nhau.

## **Cú Pháp của Vòng Lặp For**

Cú pháp tổng quát của vòng lặp `for` trong Java như sau:

```java
for (khởi_tạo; điều_kiện; bước) {
    // Khối mã được lặp lại cho đến khi điều_kiện trở thành false
    // Bước này được thực thi sau mỗi lần lặp
}
```

Trong đó:

* `khởi_tạo`: là phần khởi tạo, thường là gán giá trị ban đầu cho biến lặp.
* `điều_kiện`: là điều kiện kiểm tra trước mỗi lần lặp, nếu điều kiện là `true`, vòng lặp sẽ tiếp tục, nếu là `false`, vòng lặp sẽ kết thúc.
* `bước`: là bước thay đổi giá trị biến lặp sau mỗi lần lặp.

## **Ví dụ về Vòng Lặp For**

Dưới đây là một ví dụ minh họa về cách sử dụng vòng lặp `for` để in ra các số từ 1 đến 5:

```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

## **Từ Khoá Break và Continue**

* `break`: Từ khoá `break` được sử dụng để kết thúc vòng lặp ngay lập tức khi nó được gọi. Nó giúp thoát khỏi vòng lặp và chuyển quyền điều khiển đến câu lệnh sau vòng lặp.
* `continue`: Từ khoá `continue` được sử dụng để bỏ qua phần còn lại của vòng lặp và tiếp tục với lần lặp tiếp theo.

## **Bài Tập Thực Hành:**

1. Viết một chương trình Java sử dụng vòng lặp `for` để tính tổng của các số từ 1 đến 10, nhưng bỏ qua số 5. Sau đó in ra kết quả.

## **Lưu Ý:**

* Biến lặp (`i` trong ví dụ trên) được khai báo và sử dụng cục bộ trong phạm vi của vòng lặp `for`.
* Vòng lặp `for` thích hợp khi bạn biết trước số lần lặp cụ thể.

## **Kết Luận**

Trên đây là cách sử dụng vòng lặp `for` trong Java để lặp lại một khối mã một số lần nhất định và hướng dẫn sử dụng từ khoá `break` và `continue`. Việc hiểu và sử dụng chúng đúng cách sẽ giúp bạn viết các chương trình Java linh hoạt và hiệu quả.
