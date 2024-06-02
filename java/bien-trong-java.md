# Biến trong Java

### Giới thiệu về Biến

Trong lập trình Java, **biến** là một tên đại diện cho một vùng nhớ có thể lưu trữ dữ liệu. Biến cho phép chương trình lưu trữ và thao tác với các giá trị trong quá trình thực thi. Biến có thể là các kiểu dữ liệu cơ bản như số nguyên, số thực, ký tự, hoặc các kiểu dữ liệu phức tạp hơn như mảng và đối tượng.

### Khai báo Biến

Để khai báo một biến trong Java, chúng ta cần chỉ định kiểu dữ liệu của biến và tên biến. Cú pháp cơ bản để khai báo biến như sau:

```java
kiểu_dữ_liệu tên_biến;
```

Ví dụ:

```java
int tuoi;
double luong;
char kyTu;
```

#### Khai báo và Khởi tạo Biến

Khai báo biến chỉ là bước đầu tiên. Để sử dụng biến, chúng ta thường cần khởi tạo nó với một giá trị ban đầu. Cú pháp khởi tạo biến như sau:

```java
kiểu_dữ_liệu tên_biến = giá_trị_ban_đầu;
```

Ví dụ:

```java
int tuoi = 25;
double luong = 5000.50;
char kyTu = 'A';
```

### Các Kiểu Dữ Liệu Cơ Bản

Java hỗ trợ nhiều kiểu dữ liệu cơ bản:

* `int`: Số nguyên (ví dụ: 1, 2, 3)
* `double`: Số thực (ví dụ: 3.14, 2.718)
* `char`: Ký tự đơn (ví dụ: 'A', 'B')
* `boolean`: Giá trị đúng/sai (true/false)
* `String`: Chuỗi

Ví dụ:

```java
int soNguyen = 10;
double soThuc = 20.5;
char kyTu = 'C';
boolean laDung = true;
```

### Gán Lại Giá Trị Cho Biến

Sau khi biến đã được khai báo và khởi tạo, chúng ta có thể gán lại giá trị khác cho biến. Cú pháp gán lại giá trị cho biến như sau:

```java
tên_biến = giá_trị_mới;
```

Ví dụ:

```java
int soNguyen = 10;
soNguyen = 20;  // Gán lại giá trị mới cho biến soNguyen

double soThuc = 20.5;
soThuc = 15.75;  // Gán lại giá trị mới cho biến soThuc

char kyTu = 'C';
kyTu = 'D';  // Gán lại giá trị mới cho biến kyTu

boolean laDung = true;
laDung = false;  // Gán lại giá trị mới cho biến laDung
```

### Quy tắc Đặt Tên Biến

* Tên biến phải bắt đầu bằng một chữ cái, dấu gạch dưới `_`, hoặc dấu đô la `$`.
* Các ký tự tiếp theo có thể là chữ cái, chữ số, dấu gạch dưới, hoặc dấu đô la.
* Tên biến có phân biệt chữ hoa và chữ thường (ví dụ: `tuoi` và `Tuoi` là hai biến khác nhau).
* Không được sử dụng từ khóa của Java làm tên biến.

Ví dụ:

```java
int soLuong;
double luongCoBan;
char kyTuDacBiet;
boolean isTrue;
```

### Bài Tập Thực Hành

#### Bài Tập 1: Khai báo và Khởi tạo Biến

Khai báo các biến sau và khởi tạo chúng với các giá trị tương ứng:

* Một biến số nguyên `namSinh` với giá trị 1990.
* Một biến số thực `diemTrungBinh` với giá trị 8.5.
* Một biến ký tự `kyTuDauTien` với giá trị 'H'.
* Một biến boolean `laSinhVien` với giá trị true.

<details>

<summary>Bài giải</summary>

```java
public class Main {
    public static void main(String[] args) {
        int namSinh = 1990;
        double diemTrungBinh = 8.5;
        char kyTuDauTien = 'H';
        boolean laSinhVien = true;
    }
}
```



</details>

#### Bài Tập 2: In ra Giá trị của Biến

Viết chương trình in ra giá trị của các biến đã khai báo và khởi tạo ở bài tập 1.

<details>

<summary>Bài giải</summary>

```java
public class Main {
    public static void main(String[] args) {
        int namSinh = 1990;
        double diemTrungBinh = 8.5;
        char kyTuDauTien = 'H';
        boolean laSinhVien = true;

        System.out.println("Nam Sinh: " + namSinh);
        System.out.println("Diem Trung Binh: " + diemTrungBinh);
        System.out.println("Ky Tu Dau Tien: " + kyTuDauTien);
        System.out.println("La Sinh Vien: " + laSinhVien);
    }
}
```



</details>

### Kết Luận

Biến là một khái niệm cơ bản nhưng rất quan trọng trong lập trình Java. Việc hiểu và sử dụng biến đúng cách giúp bạn quản lý dữ liệu hiệu quả hơn và viết mã dễ hiểu hơn. Thông qua bài giảng này, bạn đã biết cách khai báo, khởi tạo, gán lại giá trị và sử dụng các biến với các kiểu dữ liệu cơ bản cũng như cách làm việc với mảng. Hãy luyện tập thêm để nắm vững kiến thức này!
