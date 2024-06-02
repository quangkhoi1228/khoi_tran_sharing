# Kiểu dữ liệu trong Java

Giới thiệu về Kiểu Dữ Liệu

Trong Java, kiểu dữ liệu (data type) xác định loại và kích thước của dữ liệu mà một biến có thể lưu trữ. Java là ngôn ngữ có kiểu dữ liệu tĩnh, có nghĩa là kiểu của một biến phải được xác định tại thời điểm biên dịch và không thể thay đổi trong suốt quá trình thực thi chương trình.

### Các Kiểu Dữ Liệu thường gặp

Java hỗ trợ các kiểu dữ liệu nguyên thủy sau đây:

<table data-full-width="true"><thead><tr><th width="143">Kiểu Dữ liệu</th><th width="147">Kích thước</th><th>Mô tả</th></tr></thead><tbody><tr><td>byte</td><td>1 byte</td><td>Lưu trữ số nguyên từ -128 đến 127</td></tr><tr><td>short</td><td>2 byte</td><td>Lưu trữ số nguyên từ -32,768 đến 32,767</td></tr><tr><td>int</td><td>4 byte</td><td>Lưu trữ số nguyên từ -2,147,483,648 đến 2,147,483,647</td></tr><tr><td>long</td><td>8 byte</td><td>Lưu trữ số nguyên từ -9,223,372,036,854,775,808 đến 9,223,372,036,854,775,807</td></tr><tr><td>float</td><td>4 byte</td><td>Lưu trữ số thập phân. Đủ để lưu trữ từ 6 đến 7 chữ số thập phân</td></tr><tr><td>double</td><td>8 byte</td><td>Lưu trữ số thập phân. Đủ để lưu trữ 15 chữ số thập phân</td></tr><tr><td>boolean</td><td>1 bit</td><td>Lưu trữ giá trị true hoặc false</td></tr><tr><td>char</td><td>2 byte</td><td>Lưu trữ một ký tự / chữ cái hoặc giá trị ASCII</td></tr><tr><td>String</td><td></td><td>Kiểu dữ liệu String được sử dụng để lưu trữ một chuỗi ký tự (văn bản). Giá trị chuỗi phải được bao quanh bởi dấu ngoặc kép <code>""</code></td></tr></tbody></table>

#### Ví dụ về Các Kiểu Dữ Liệu Nguyên Thủy

```java
public class KieuDuLieu {
    public static void main(String[] args) {
        byte soNho = 10;
        short soNgan = 1000;
        int soNguyen = 100000;
        long soLon = 1000000000L;

        float diemTrungBinh = 8.5f;
        double pi = 3.14159;

        char kyTu = 'A';
        boolean laDung = true;
        String myName = "Khôi"

        System.out.println("Byte: " + soNho);
        System.out.println("Short: " + soNgan);
        System.out.println("Int: " + soNguyen);
        System.out.println("Long: " + soLon);
        System.out.println("Float: " + diemTrungBinh);
        System.out.println("Double: " + pi);
        System.out.println("Char: " + kyTu);
        System.out.println("Boolean: " + laDung);
        System.out.println("String: " + myName);
    }
}
```

### Chuyển Đổi Kiểu Dữ Liệu

Java hỗ trợ chuyển đổi kiểu dữ liệu ngầm định và tường minh giữa các kiểu dữ liệu.

{% hint style="info" %}
Trong Java, có hai loại casting:

1. **Widening Casting (tự động):** chuyển đổi từ kiểu dữ liệu nhỏ hơn sang kiểu dữ liệu lớn hơn:&#x20;

`byte` -> `short` -> `char` -> `int` -> `long` -> `float` -> `double`

2. **Narrowing Casting (thủ công):** chuyển đổi từ kiểu dữ liệu lớn hơn sang kiểu dữ liệu nhỏ hơn:

&#x20;`double` -> `float` -> `long` -> `int` -> `char` -> `short` -> `byte`
{% endhint %}

#### Chuyển Đổi Tự động

Chuyển đổi ngầm định xảy ra khi một giá trị của kiểu dữ liệu nhỏ hơn được chuyển đổi sang kiểu dữ liệu lớn hơn mà không cần sự can thiệp của lập trình viên.

```java
public class ChuyenDoiKieuDuLieu {
    public static void main(String[] args) {
        int soNguyen = 10;
        double soThuc = soNguyen;  // Chuyển đổi ngầm định từ int sang double

        System.out.println("Số nguyên: " + soNguyen);
        System.out.println("Số thực: " + soThuc);
    }
}
```

#### Chuyển Đổi Thủ Công

Chuyển đổi tường minh xảy ra khi một giá trị của kiểu dữ liệu lớn hơn được chuyển đổi sang kiểu dữ liệu nhỏ hơn, yêu cầu sự can thiệp của lập trình viên.

```java
public class ChuyenDoiKieuDuLieuTuongMinh {
    public static void main(String[] args) {
        double soThuc = 9.78;
        int soNguyen = (int) soThuc;  // Chuyển đổi tường minh từ double sang int

        System.out.println("Số thực: " + soThuc);
        System.out.println("Số nguyên: " + soNguyen);
    }
}
```

### Bài Tập Thực Hành

1. Khai báo và khởi tạo các biến với tất cả các kiểu dữ liệu.
2. Viết chương trình chuyển đổi thủ công và tự động giữa các kiểu dữ liệu.

#### Bài Tập 1: Khai báo và Khởi tạo Biến

Khai báo các biến với các kiểu dữ liệu nguyên thủy và khởi tạo chúng với các giá trị tùy ý.

<details>

<summary>Bài giải</summary>

```java
public class KieuDuLieuNguyenThuy {
    public static void main(String[] args) {
        byte b = 10;
        short s = 200;
        int i = 30000;
        long l = 4000000L;

        float f = 5.75f;
        double d = 19.99;

        char c = 'A';
        boolean bool = true;

        System.out.println("Byte: " + b);
        System.out.println("Short: " + s);
        System.out.println("Int: " + i);
        System.out.println("Long: " + l);
        System.out.println("Float: " + f);
        System.out.println("Double: " + d);
        System.out.println("Char: " + c);
        System.out.println("Boolean: " + bool);
    }
}
```



</details>

#### Bài Tập 2: Chuyển Đổi Kiểu Dữ Liệu

Viết chương trình thực hiện chuyển đổi ngầm định từ `int` sang `double` và chuyển đổi tường minh từ `double` sang `int`.

<details>

<summary>Bài giải</summary>

```java
public class ChuyenDoiKieu {
    public static void main(String[] args) {
        int soNguyen = 10;
        double soThuc = soNguyen;  // Chuyển đổi ngầm định

        double soThucKhac = 9.78;
        int soNguyenKhac = (int) soThucKhac;  // Chuyển đổi tường minh

        System.out.println("Số nguyên: " + soNguyen);
        System.out.println("Số thực (ngầm định): " + soThuc);
        System.out.println("Số thực: " + soThucKhac);
        System.out.println("Số nguyên (tường minh): " + soNguyenKhac);
    }
}
```



</details>

### Kết Luận

Kiểu dữ liệu là một khái niệm cơ bản nhưng cực kỳ quan trọng trong lập trình Java. Việc hiểu và sử dụng đúng cách các kiểu dữ liệu giúp bạn viết mã hiệu quả và tránh được nhiều lỗi trong quá trình lập trình. Thông qua bài giảng này, bạn đã biết cách sử dụng các kiểu dữ liệu nguyên thủy, kiểu dữ liệu tham chiếu, cũng như cách chuyển đổi giữa các kiểu dữ liệu khác nhau. Hãy thực hành thêm để nắm vững kiến thức này!
