# Java If-else

## Giới thiệu về Câu lệnh If-Else trong Java

Trong lập trình Java, câu lệnh if-else được sử dụng để kiểm tra điều kiện và thực thi các khối mã khác nhau dựa trên kết quả của điều kiện đó. Trong bài giảng này, chúng ta sẽ tìm hiểu về cách sử dụng câu lệnh if-else trong Java và cách áp dụng chúng trong các trường hợp khác nhau.

## **Câu lệnh If đơn giản**

Câu lệnh if được sử dụng để kiểm tra một điều kiện. Nếu điều kiện là đúng (true), khối mã bên trong câu lệnh if sẽ được thực thi.

```java
int age = 20;

if(age >= 18) {
    System.out.println("Bạn đã đủ tuổi để lái xe.");
}
```

## **Câu lệnh If-Else**

Câu lệnh if-else được sử dụng khi chúng ta muốn thực thi một khối mã nếu điều kiện là đúng và một khối mã khác nếu điều kiện là sai.

```java
int age = 15;

if(age >= 18) {
    System.out.println("Bạn đã đủ tuổi để lái xe.");
} else {
    System.out.println("Bạn chưa đủ tuổi để lái xe.");
}
```

## **Câu lệnh If-Else If-Else**

Câu lệnh if-else if-else được sử dụng để kiểm tra nhiều điều kiện và thực thi các khối mã tương ứng với điều kiện đúng đầu tiên.

```java
int marks = 75;

if(marks >= 90) {
    System.out.println("Xuất sắc");
} else if(marks >= 80) {
    System.out.println("Giỏi");
} else if(marks >= 70) {
    System.out.println("Khá");
} else if(marks >= 60) {
    System.out.println("Trung bình");
} else {
    System.out.println("Yếu");
}
```

## **If-Else Shorthand (Ternary Operator)**

If-else shorthand là một cách viết ngắn gọn hơn cho câu lệnh if-else, thường được sử dụng khi chúng ta muốn gán giá trị cho một biến dựa trên một điều kiện.

```java
javaCopy codeint age = 15;
String status = (age >= 18) ? "Đủ tuổi" : "Chưa đủ tuổi";
System.out.println("Tình trạng: " + status);
```

Trong ví dụ trên, nếu age lớn hơn hoặc bằng 18, biến status sẽ được gán giá trị là "Đủ tuổi", ngược lại sẽ được gán giá trị là "Chưa đủ tuổi".

## **Bài tập thực hành:**

1. Viết một chương trình Java để kiểm tra xem một năm là năm nhuận hay không và in ra thông báo tương ứng.

{% hint style="info" %}
Cách tính năm nhuận:

Cách tính năm nhuận Dương lịch như sau: bạn lấy số năm đem chia cho 4, nếu kết quả chia hết cho 4 thì năm nó là năm nhuận. Với những năm tròn thế kỷ có 2 số 00 ở cuối thì lấy số năm chi cho 400, nếu kết quả chia hết cho 400 thì năm đó là năm nhuận.
{% endhint %}

## **Kết luận**

Trên đây là cách sử dụng câu lệnh if-else trong Java để kiểm tra điều kiện và thực thi các khối mã tương ứng. Việc hiểu và sử dụng chúng đúng cách sẽ giúp bạn viết các chương trình Java linh hoạt và hiệu quả.
