# Java Comment

### Giới thiệu

Trong lập trình, comments (chú thích) là các đoạn mã mà trình biên dịch hoặc thông dịch bỏ qua và không thực thi. Chúng được sử dụng để giải thích mã, làm cho mã dễ hiểu hơn cho người khác hoặc cho chính bạn trong tương lai.

Trong Java, có ba loại comments chính:

1. Single-line comments (chú thích một dòng)
2. Multi-line comments (chú thích nhiều dòng)
3. Documentation comments (chú thích tài liệu)

### Single-line Comments

#### Cú pháp

Single-line comments bắt đầu bằng hai dấu gạch chéo `//`. Mọi thứ sau `//` trên cùng một dòng sẽ được coi là comment và bị bỏ qua khi chương trình chạy.

#### Ví dụ

```java
public class Main {
    public static void main(String[] args) {
        // Đây là một comment một dòng
        System.out.println("Hello, World!"); // In ra màn hình dòng chữ Hello, World!
    }
}
```

#### Giải thích

Trong ví dụ trên, `// Đây là một comment một dòng` và `// In ra màn hình dòng chữ Hello, World!` đều là comments. Chúng không ảnh hưởng đến việc thực thi chương trình.

### Multi-line Comments

#### Cú pháp

Multi-line comments bắt đầu bằng `/*` và kết thúc bằng `*/`. Mọi thứ giữa `/*` và `*/` sẽ được coi là comment.

#### Ví dụ

```java
public class Main {
    public static void main(String[] args) {
        /* 
         * Đây là một comment nhiều dòng.
         * Bạn có thể viết chú thích trên nhiều dòng.
         */
        System.out.println("Hello, World!");
    }
}
```

#### Giải thích

Trong ví dụ trên, đoạn văn bản giữa `/*` và `*/` là một comment nhiều dòng. Nó không ảnh hưởng đến việc thực thi chương trình.

### Documentation Comments

#### Cú pháp

Documentation comments bắt đầu bằng `/**` và kết thúc bằng `*/`. Chúng thường được sử dụng để tạo tài liệu cho mã nguồn bằng công cụ Javadoc.

#### Ví dụ

```java
/**
 * Đây là lớp Main.
 * Lớp này chứa phương thức main để chạy chương trình.
 */
public class Main {

    /**
     * Đây là phương thức main.
     * @param args Đối số dòng lệnh
     */
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

#### Giải thích

Trong ví dụ trên, các đoạn văn bản giữa `/**` và `*/` là documentation comments. Chúng có thể được sử dụng để tạo tài liệu tự động cho mã nguồn.

### Bài Tập Thực Hành

1. Tạo một lớp Java có tên là `CommentExample` và thêm phương thức `main` vào.
2. Sử dụng single-line comments để giải thích từng bước trong phương thức `main`.
3. Thêm một multi-line comment ở đầu lớp để giải thích mục đích của lớp.
4. Sử dụng documentation comments để mô tả lớp và phương thức `main`.

#### Gợi ý

```java
/**
 * Lớp CommentExample
 * Lớp này dùng để minh họa cách sử dụng comments trong Java.
 */
public class CommentExample {

    /**
     * Phương thức main
     * @param args Đối số dòng lệnh
     */
    public static void main(String[] args) {
        // In ra màn hình dòng chữ "Hello, Java!"
        System.out.println("Hello, Java!");

        // Tính tổng của hai số
        int a = 5; // Số thứ nhất
        int b = 10; // Số thứ hai
        int sum = a + b; // Tính tổng
        System.out.println("Tổng của a và b là: " + sum); // In kết quả
    }
}
```

Trong bài tập này, bạn sẽ sử dụng các loại comments khác nhau để làm cho mã của bạn dễ hiểu hơn. Hãy chắc chắn rằng bạn đã hiểu rõ cách sử dụng từng loại comment và thực hành viết comments cho mã của mình.
