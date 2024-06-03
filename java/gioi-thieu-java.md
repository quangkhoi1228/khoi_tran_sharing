# Giới thiệu Java

## Java là gì?

Java là một ngôn ngữ lập trình bậc cao, mạnh mẽ và bảo mật cao, được phát triển bởi Sun Microsystems vào năm 1995 (nay thuộc Oracle). Java được thiết kế để có thể chạy trên nhiều nền tảng khác nhau nhờ vào Java Virtual Machine (JVM), cho phép viết một lần, chạy mọi nơi ("Write Once, Run Anywhere").

#### Đặc điểm chính của Java

1. **Đa nền tảng (Cross-Platform)**: Chương trình Java có thể chạy trên nhiều hệ điều hành khác nhau như Windows, MacOS, và Linux mà không cần thay đổi mã nguồn nhờ vào JVM.
2. **Hướng đối tượng (Object-Oriented)**: Java hỗ trợ lập trình hướng đối tượng, giúp tổ chức mã nguồn thành các lớp và đối tượng, tăng khả năng tái sử dụng và bảo trì mã.
3. **Bảo mật (Security)**: Java có các cơ chế bảo mật mạnh mẽ, bao gồm kiểm soát truy cập và bảo mật dữ liệu, giúp bảo vệ ứng dụng khỏi các mối đe dọa tiềm ẩn.
4. **Đa luồng (Multithreading)**: Java hỗ trợ xử lý đa luồng, cho phép thực hiện nhiều tác vụ đồng thời, cải thiện hiệu suất và khả năng đáp ứng của ứng dụng.
5. **Thu gom rác (Garbage Collection)**: Java tự động quản lý bộ nhớ và thu hồi những vùng nhớ không còn sử dụng, giúp giảm bớt công việc của lập trình viên trong việc quản lý bộ nhớ.

### JVM là gì?

Java Virtual Machine (JVM) là một thành phần cốt lõi của nền tảng Java, chịu trách nhiệm thực thi các chương trình Java. JVM tạo ra một môi trường chạy cho mã bytecode Java, đảm bảo rằng chương trình Java có thể chạy trên bất kỳ hệ điều hành nào mà không cần thay đổi mã nguồn.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

## Cài đặt và cấu hình môi trường phát triển Java

#### Bước 1: Cài đặt JDK

Để phát triển ứng dụng Java, bạn cần cài đặt Java Development Kit (JDK). Bạn có thể tải JDK từ trang web của Oracle hoặc OpenJDK. JDK bao gồm tất cả các công cụ cần thiết để biên dịch, chạy và gỡ lỗi các ứng dụng Java.

#### Bước 2: Cấu hình biến môi trường

Sau khi cài đặt JDK, bạn cần cấu hình biến môi trường `JAVA_HOME` và thêm thư mục `bin` của JDK vào biến môi trường `PATH` để có thể chạy các công cụ Java từ dòng lệnh.

#### Bước 3: Kiểm tra cài đặt

Mở cửa sổ dòng lệnh và nhập lệnh sau để kiểm tra phiên bản Java đã cài đặt:

```bash
java --version
```

Nếu cài đặt thành công, bạn sẽ thấy thông tin về phiên bản Java đã cài đặt.
