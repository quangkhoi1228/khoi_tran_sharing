# Java Array

## Giới thiệu về Mảng trong Java

Mảng là một cấu trúc dữ liệu quan trọng trong lập trình Java, cho phép lưu trữ nhiều giá trị cùng loại trong một biến. Trong bài giảng này, chúng ta sẽ tìm hiểu về mảng trong Java, cách khai báo, truy cập và sử dụng mảng.

## **Khai Báo Mảng**

Cú pháp để khai báo một mảng trong Java như sau:

```java
// Khai báo mảng kiểu dữ liệu[]
kiểu_dữ_liệu[] tên_mảng;

// Khai báo và khởi tạo mảng
kiểu_dữ_liệu[] tên_mảng = new kiểu_dữ_liệu[kích_thước];
```

Ví dụ về khai báo mảng:

```java
// Khai báo mảng kiểu int
int[] mangSoNguyen;

// Khai báo và khởi tạo mảng kiểu double có kích thước là 5
double[] mangSoThuc = new double[5];
```

## **Truy Cập và Gán Giá Trị cho Mảng**

Mỗi phần tử trong mảng được truy cập thông qua chỉ số (index) của nó, bắt đầu từ 0. Để truy cập và gán giá trị cho một phần tử trong mảng, bạn sử dụng cú pháp sau:

```java
// Gán giá trị cho phần tử thứ i trong mảng
ten_mang[i] = gia_tri;

// Truy cập giá trị của phần tử thứ i trong mảng
gia_tri = ten_mang[i];
```

Ví dụ:

```java
int[] mangSoNguyen = new int[3];
mangSoNguyen[0] = 10;
mangSoNguyen[1] = 20;
mangSoNguyen[2] = 30;

int phanTuThuHai = mangSoNguyen[1]; // phanTuThuHai sẽ có giá trị là 20
```

## **Lấy Kích Thước của Mảng**

Để lấy kích thước của mảng, bạn sử dụng thuộc tính `length`:

```java
int kichThuocMang = ten_mang.length;
```

Ví dụ:

```java
int[] mangSoNguyen = {10, 20, 30, 40, 50};
int kichThuoc = mangSoNguyen.length; // kichThuoc sẽ có giá trị là 5
System.out.println("Kích thước của mảng là: " + kichThuoc);
```

## **Bài Tập Thực Hành**

1. Viết một chương trình Java để khai báo và khởi tạo một mảng các chuỗi, sau đó in ra kích thước của mảng bằng cách sử dụng thuộc tính `length`.

## **Kết Luận**

Mảng là một cấu trúc dữ liệu quan trọng trong Java, cho phép lưu trữ nhiều giá trị cùng loại trong một biến. Việc hiểu và sử dụng mảng cùng với các hàm built-in của chúng sẽ giúp bạn viết các chương trình Java linh hoạt và hiệu quả hơn.
