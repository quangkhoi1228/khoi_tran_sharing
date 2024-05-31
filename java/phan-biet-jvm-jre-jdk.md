# Phân biệt JVM, JRE, JDK

Trong lập trình Java, việc hiểu rõ về JVM, JRE, và JDK là rất quan trọng. Đây là những thành phần cơ bản và cần thiết để phát triển và chạy ứng dụng Java. Chúng ta sẽ cùng tìm hiểu chi tiết từng khái niệm, cũng như mối quan hệ giữa chúng.

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

### JVM (Java Virtual Machine)

#### Mô tả

JVM (Java Virtual Machine) là một máy ảo chạy các bytecode Java. Nó cung cấp một môi trường chạy cho các chương trình Java, bất kể hệ điều hành nào. JVM chịu trách nhiệm chuyển đổi bytecode (mã trung gian) thành mã máy, giúp chương trình Java có thể chạy trên bất kỳ hệ điều hành nào mà không cần phải biên dịch lại.

#### Các thành phần chính của JVM

* **Class Loader**: Tải các lớp (class) Java vào bộ nhớ.
* **Execution Engine**: Thực thi mã bytecode của các lớp đã được tải.
  * **Interpreter**: Chuyển đổi bytecode thành mã máy và thực thi.
  * **JIT Compiler (Just-In-Time Compiler)**: Biên dịch bytecode thành mã máy khi cần thiết, giúp tăng hiệu suất thực thi.
* **Runtime Data Area**: Khu vực dữ liệu trong thời gian chạy, bao gồm Heap, Stack, Method Area, và các vùng bộ nhớ khác.
  * **Heap**: Nơi lưu trữ các đối tượng.
  * **Stack**: Lưu trữ các khung ngăn xếp cho mỗi phương thức đang thực thi.
  * **Method Area**: Chứa thông tin về các lớp đã tải.

#### Ví dụ

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

Khi bạn biên dịch mã Java trên, file `HelloWorld.class` sẽ được tạo ra. JVM sẽ đọc file này và chuyển đổi bytecode thành mã máy để thực thi.

### JRE (Java Runtime Environment)

#### Mô tả

JRE (Java Runtime Environment) là một tập hợp các công cụ cần thiết để chạy các ứng dụng Java. JRE bao gồm JVM và các thư viện lớp chuẩn (standard class libraries), mà JVM sử dụng trong quá trình thực thi ứng dụng Java.

#### Các thành phần chính của JRE

* **JVM**: Như đã mô tả ở trên.
* **Core Libraries**: Các thư viện lõi Java như Collections Framework, File I/O, Networking, v.v.
* **Supporting Files**: Các tệp hỗ trợ cần thiết khác để chạy các ứng dụng Java.

#### Ví dụ

Khi bạn cài đặt JRE trên hệ thống, bạn có thể chạy các ứng dụng Java mà không cần công cụ phát triển. Ví dụ:

```bash
java HelloWorld
```

Lệnh trên sẽ sử dụng JRE để thực thi chương trình `HelloWorld`.

### JDK (Java Development Kit)

#### Mô tả

JDK (Java Development Kit) là bộ công cụ phát triển phần mềm để phát triển các ứng dụng Java. JDK bao gồm JRE và các công cụ phát triển khác như trình biên dịch (javac), trình gỡ lỗi (jdb), và các công cụ khác cần thiết để phát triển các ứng dụng Java.

#### Các thành phần chính của JDK

* **JRE**: Như đã mô tả ở trên.
* **Development Tools**: Các công cụ phát triển phần mềm, bao gồm:
  * **javac**: Trình biên dịch Java, chuyển mã nguồn Java thành bytecode.
  * **jdb**: Trình gỡ lỗi Java.
  * **javap**: Trình phân tích mã bytecode.
  * **javadoc**: Công cụ tạo tài liệu từ mã nguồn Java.

#### Ví dụ

Để phát triển và chạy một ứng dụng Java, bạn cần sử dụng JDK. Ví dụ:

```bash
javac HelloWorld.java
java HelloWorld
```

Lệnh `javac` sẽ biên dịch mã nguồn Java thành bytecode. Lệnh `java` sẽ chạy bytecode bằng JRE.



