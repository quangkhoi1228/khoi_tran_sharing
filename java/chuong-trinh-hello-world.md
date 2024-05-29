# Chương trình Hello world

### Tạo dự án Java mới

1. Từ màn hình chào đón, nhấp vào "Create New Project".
2. Chọn "Java" từ danh sách các loại dự án.
3. Đảm bảo rằng JDK đã được cấu hình. Nếu chưa, bạn có thể nhấp vào "New..." để tải và cài đặt JDK hoặc trỏ tới thư mục chứa JDK hiện có.
4. Nhấp vào "Next" và đặt tên cho dự án của bạn.
5. Chọn thư mục lưu trữ dự án và nhấp vào "Finish".

### Viết và chạy chương trình Java đầu tiên của bạn

1. Trong cửa sổ Project, nhấp chuột phải vào thư mục `src` và chọn `New` -> `Java Class`.
2. Đặt tên cho lớp mới, ví dụ: `HelloWorld`.
3. Thêm mã nguồn Java vào lớp `HelloWorld`:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

4. Nhấp chuột phải vào tệp `HelloWorld.java` và chọn `Run 'HelloWorld.main()'` để chạy chương trình của bạn.
5. Kết quả sẽ được hiển thị trong cửa sổ console ở dưới cùng của IntelliJ IDEA.

## Cấu trúc của một chương trình Java

Một chương trình Java cơ bản gồm các thành phần chính như sau:

1. **Lớp (Class)**: Mỗi chương trình Java được định nghĩa trong một lớp.
2. **Phương thức chính (main method)**: Phương thức `main` là điểm bắt đầu của chương trình Java.

#### Ví dụ: Chương trình Hello World

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

#### Giải thích chương trình

* **public class HelloWorld**: Định nghĩa một lớp công khai tên là `HelloWorld`.
* **public static void main(String\[] args)**: Phương thức chính của chương trình, nơi bắt đầu thực thi mã.
* **System.out.println("Hello, World!");**: In ra dòng chữ "Hello, World!" trên màn hình.



Chúc mừng, bạn đã cài đặt và sử dụng IntelliJ IDEA để viết chương trình Java đầu tiên của mình!
