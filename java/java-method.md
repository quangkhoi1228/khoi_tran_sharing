# Java Method

## Giới thiệu về Phương Thức (Method) trong Java

Phương thức (method) trong Java là một khối mã thực hiện một nhiệm vụ cụ thể và có thể được gọi lại nhiều lần trong chương trình. Phương thức giúp chia chương trình thành các phần nhỏ hơn và dễ quản lý hơn.

## **Cú Pháp của Phương Thức**

Cú pháp chung của một phương thức trong Java như sau:

```java
modifier kiểu_trả_về tên_phương_thức (danh_sách_tham_số) {
    // Khối mã
}
```

* `modifier`: Là các từ khóa như `public`, `private`, `protected` hoặc không có (default).
* `kiểu_trả_về`: Kiểu dữ liệu mà phương thức trả về. Nếu phương thức không trả về giá trị, sử dụng `void`.
* `tên_phương_thức`: Tên của phương thức, nên đặt tên sao cho có ý nghĩa.
* `danh_sách_tham_số`: Danh sách các tham số được truyền vào phương thức, ngăn cách bởi dấu phẩy. Nếu không có tham số, để trống.

## **Ví Dụ về Phương Thức**

Dưới đây là ví dụ về một phương thức tính tổng hai số nguyên:

```java
public class Main {
    // Phương thức tính tổng hai số nguyên
    public static int tinhTong(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int x = 5;
        int y = 10;
        int tong = tinhTong(x, y);
        System.out.println("Tổng của " + x + " và " + y + " là: " + tong);
    }
}
```

## **Phương Thức Không Trả Về Giá Trị (void)**

Nếu phương thức không trả về giá trị, sử dụng kiểu dữ liệu `void`:

```java
public class Main {
    // Phương thức in thông báo
    public static void inThongBao() {
        System.out.println("Đây là một thông báo!");
    }

    public static void main(String[] args) {
        inThongBao();
    }
}
```

## **Phương Thức với Tham Số**

Phương thức có thể nhận nhiều tham số:

```java
public class Main {
    // Phương thức tính hiệu hai số nguyên
    public static int tinhHieu(int a, int b) {
        return a - b;
    }

    public static void main(String[] args) {
        int ketQua = tinhHieu(20, 5);
        System.out.println("Hiệu của 20 và 5 là: " + ketQua);
    }
}
```

## **Gọi Phương Thức**

Để gọi một phương thức, bạn chỉ cần sử dụng tên phương thức cùng với các tham số (nếu có).

Ví dụ:

```java
public class Main {
    public static void inLoiChao() {
        System.out.println("Xin chào!");
    }

    public static void main(String[] args) {
        inLoiChao(); // Gọi phương thức inLoiChao
    }
}
```

## **Phương Thức Nạp Chồng (Method Overload)**

Phương thức nạp chồng cho phép tạo nhiều phương thức cùng tên trong cùng một lớp, nhưng khác nhau về danh sách tham số.

Ví dụ:

```java
public class Main {
    public static int cong(int a, int b) {
        return a + b;
    }

    public static double cong(double a, double b) {
        return a + b;
    }

    public static void main(String[] args) {
        int tongSoNguyen = cong(5, 10);
        double tongSoThuc = cong(5.5, 10.5);

        System.out.println("Tổng số nguyên: " + tongSoNguyen);
        System.out.println("Tổng số thực: " + tongSoThuc);
    }
}
```

## **Hàm Đệ Quy (Recursive Method)**

Hàm đệ quy là hàm gọi lại chính nó trong quá trình thực thi. Đệ quy thường được sử dụng để giải quyết các bài toán phân rã lặp lại.

Ví dụ tính giai thừa bằng đệ quy:

```java
public class Main {
    public static int tinhGiaiThua(int n) {
        if (n <= 1) { // Điều kiện dừng
            return 1;
        } else {
            return n + tinhGiaiThua(n - 1); // Gọi lại chính nó
        }
    }

    public static void main(String[] args) {
        int n = 5;
        int ketQua = tinhGiaiThua(n);
        System.out.println("Giai thừa của " + n + " là: " + ketQua);
    }
}
```

## **Bài Tập Thực Hành**

1. Viết một phương thức `tinhTich` nhận hai số nguyên làm tham số và trả về tích của chúng. Sau đó gọi phương thức này trong phương thức `main` và in ra kết quả.
2. Viết một phương thức `inChuoi` nhận một chuỗi làm tham số và in ra chuỗi đó. Gọi phương thức này trong phương thức `main`.
3. Viết phương thức nạp chồng `cong` với ba tham số kiểu int và kiểu double. Gọi các phương thức này trong `main` và in ra kết quả.
4. Viết một phương thức đệ quy `tinhTongDaySo` để tính tổng của dãy số từ 1 đến n. Gọi phương thức này trong `main` và in ra kết quả.

## **Kết Luận**

Phương thức là một phần quan trọng trong lập trình Java, giúp chia chương trình thành các phần nhỏ hơn, dễ quản lý hơn và tái sử dụng mã. Hiểu và sử dụng đúng cách phương thức, bao gồm nạp chồng và đệ quy, sẽ giúp bạn viết các chương trình Java hiệu quả và linh hoạt hơn.
