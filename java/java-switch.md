# Java Switch

## Giới thiệu về Câu lệnh Switch trong Java

Trong lập trình Java, câu lệnh switch được sử dụng để kiểm tra giá trị của một biểu thức và thực thi các khối mã khác nhau dựa trên giá trị đó. Trong bài giảng này, chúng ta sẽ tìm hiểu cách sử dụng câu lệnh switch trong Java và cách áp dụng chúng trong các trường hợp khác nhau.

## **Cú pháp của Switch**

Cú pháp tổng quát của câu lệnh switch trong Java như sau:

```java
switch (biểu_thức) {
    case giá_trị_1:
        // Khối mã được thực thi nếu biểu_thức bằng giá_trị_1
        break;
    case giá_trị_2:
        // Khối mã được thực thi nếu biểu_thức bằng giá_trị_2
        break;
    // Các trường hợp khác...
    default:
        // Khối mã mặc định được thực thi nếu không có trường hợp nào khớp
}
```

Trong đó:

* `biểu_thức`: là biểu thức hoặc giá trị sẽ được kiểm tra.
* `giá_trị_1`, `giá_trị_2`,...: là các giá trị mà `biểu_thức` có thể có.
* `break`: từ khóa `break` được sử dụng để kết thúc câu lệnh switch và ngăn không cho mã lệnh tiếp theo trong switch được thực thi.
* `default`: là trường hợp mặc định, được thực thi nếu không có trường hợp nào khớp với giá trị của `biểu_thức`.

## **Ví dụ về Switch**

Dưới đây là một ví dụ minh họa về cách sử dụng câu lệnh switch để kiểm tra ngày trong tuần:

```java
int day = 3;
String dayString;

switch (day) {
    case 1:
        dayString = "Chủ Nhật";
        break;
    case 2:
        dayString = "Thứ Hai";
        break;
    case 3:
        dayString = "Thứ Ba";
        break;
    case 4:
        dayString = "Thứ Tư";
        break;
    case 5:
        dayString = "Thứ Năm";
        break;
    case 6:
        dayString = "Thứ Sáu";
        break;
    case 7:
        dayString = "Thứ Bảy";
        break;
    default:
        dayString = "Ngày không hợp lệ";
}

System.out.println("Hôm nay là: " + dayString);
```

## **Bài tập thực hành:**

1. Viết một chương trình Java sử dụng câu lệnh switch để kiểm tra và in ra mùa tương ứng với một tháng (ví dụ: tháng 1, 2, 3 là mùa xuân).

## **Kết luận**

Trên đây là cách sử dụng câu lệnh switch trong Java để kiểm tra giá trị của biểu thức và thực thi các khối mã tương ứng. Việc hiểu và sử dụng chúng đúng cách sẽ giúp bạn viết các chương trình Java linh hoạt và hiệu quả.
