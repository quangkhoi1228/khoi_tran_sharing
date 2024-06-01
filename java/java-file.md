# Java File

## Java File

Trong Java, việc xử lý file là một kỹ năng quan trọng, giúp bạn đọc, ghi, và thao tác với các file trên hệ thống. Java cung cấp nhiều lớp và phương thức để thực hiện các thao tác này, bao gồm `File`, `FileReader`, `FileWriter`, `BufferedReader`, `BufferedWriter`, và nhiều lớp khác.

### Ví dụ các Hàm để tương tác với file

<table data-full-width="true"><thead><tr><th width="212">Phương thức</th><th width="180">Kiểu trả về</th><th>Mô tả</th></tr></thead><tbody><tr><td>canRead()</td><td>Boolean</td><td>Kiểm tra xem file có thể đọc được hay không</td></tr><tr><td>canWrite()</td><td>Boolean</td><td>Kiểm tra xem file có thể ghi được hay không</td></tr><tr><td>createNewFile()</td><td>Boolean</td><td>Tạo một file trống</td></tr><tr><td>delete()</td><td>Boolean</td><td>Xóa một file</td></tr><tr><td>exists()</td><td>Boolean</td><td>Kiểm tra xem file có tồn tại hay không</td></tr><tr><td>getName()</td><td>String</td><td>Trả về tên của file</td></tr><tr><td>getAbsolutePath()</td><td>String</td><td>Trả về đường dẫn tuyệt đối của file</td></tr><tr><td>length()</td><td>Long</td><td>Trả về kích thước của file tính bằng byte</td></tr><tr><td>list()</td><td>String[]</td><td>Trả về một mảng các file trong thư mục</td></tr><tr><td>mkdir()</td><td>Boolean</td><td>Tạo một thư mục</td></tr></tbody></table>

### Lớp File

Lớp `File` trong Java được sử dụng để đại diện cho các file và thư mục. Bạn có thể sử dụng lớp này để kiểm tra xem file hoặc thư mục có tồn tại hay không, tạo mới, xóa, và lấy thông tin về file hoặc thư mục.

#### Khởi Tạo File

Để khởi tạo một đối tượng `File`, bạn chỉ cần cung cấp đường dẫn của file hoặc thư mục:

```java
import java.io.File;

public class FileExample {
    public static void main(String[] args) {
        File file = new File("example.txt");
        
        if (file.exists()) {
            System.out.println("File exists.");
        } else {
            System.out.println("File does not exist.");
        }
    }
}
```

### Đọc File

#### Sử Dụng FileReader và BufferedReader

`FileReader` và `BufferedReader` được sử dụng để đọc dữ liệu từ file.

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadFileExample {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("example.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### Sử Dụng Scanner

Lớp `Scanner` cũng có thể được sử dụng để đọc dữ liệu từ file.

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class ScannerExample {
    public static void main(String[] args) {
        try {
            File file = new File("example.txt");
            Scanner scanner = new Scanner(file);
            
            while (scanner.hasNextLine()) {
                String line = scanner.nextLine();
                System.out.println(line);
            }
            scanner.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

### Ghi File

#### Sử Dụng FileWriter và BufferedWriter

`FileWriter` và `BufferedWriter` được sử dụng để ghi dữ liệu vào file.

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class WriteFileExample {
    public static void main(String[] args) {
        try (BufferedWriter bw = new BufferedWriter(new FileWriter("example.txt", true))) {
            bw.write("Hello, world!");
            bw.newLine();
            bw.write("Java File I/O is interesting.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### Sử Dụng PrintWriter

Lớp `PrintWriter` cung cấp các phương thức để ghi dữ liệu định dạng vào file.

```java
import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintWriter;

public class PrintWriterExample {
    public static void main(String[] args) {
        try (PrintWriter pw = new PrintWriter(new FileWriter("example.txt"))) {
            pw.println("Hello, world!");
            pw.printf("Pi: %.2f", Math.PI);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### Xoá File

Lớp `File` cung cấp phương thức `delete()` để xoá file hoặc thư mục.

```java
import java.io.File;

public class DeleteFileExample {
    public static void main(String[] args) {
        File file = new File("example.txt");
        
        if (file.delete()) {
            System.out.println("File deleted successfully.");
        } else {
            System.out.println("Failed to delete the file.");
        }
    }
}
```

### Bài Tập Thực Hành

#### Bài Tập 1: Đọc File và Hiển Thị Nội Dung

Tạo một chương trình để đọc nội dung của file `input.txt` và hiển thị nội dung ra màn hình.

<details>

<summary>Bài giải</summary>

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class Exercise1 {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("input.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```



</details>

#### Bài Tập 2: Ghi Dữ Liệu Vào File

Tạo một chương trình để ghi dữ liệu vào file `output.txt`.

<details>

<summary>Bài giải</summary>

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class Exercise2 {
    public static void main(String[] args) {
        try (BufferedWriter bw = new BufferedWriter(new FileWriter("output.txt"))) {
            bw.write("Java file I/O is powerful.");
            bw.newLine();
            bw.write("You can read and write files easily.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```



</details>

#### Bài Tập 3: Đếm Số Từ Trong File

Tạo một chương trình để đếm số từ trong file `input.txt`.

<details>

<summary>Bài giải</summary>

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class Exercise3 {
    public static void main(String[] args) {
        int wordCount = 0;
        try (BufferedReader br = new BufferedReader(new FileReader("input.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                String[] words = line.split("\\s+");
                wordCount += words.length;
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
        System.out.println("Word count: " + wordCount);
    }
}
```



</details>

#### Bài Tập 4: Sao Chép File

Tạo một chương trình để sao chép nội dung từ file `source.txt` sang file `destination.txt`.

<details>

<summary>Bài giải</summary>

```java
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class Exercise4 {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("source.txt"));
             BufferedWriter bw = new BufferedWriter(new FileWriter("destination.txt"))) {

            String line;
            while ((line = br.readLine()) != null) {
                bw.write(line);
                bw.newLine();
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```



</details>

#### Bài Tập 5: Đảo Ngược Nội Dung File

Tạo một chương trình để đọc nội dung từ file `input.txt` và ghi nội dung đảo ngược vào file `reversed.txt`.

<details>

<summary>Bài giải</summary>

```java
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class Exercise5 {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("input.txt"));
             BufferedWriter bw = new BufferedWriter(new FileWriter("reversed.txt"))) {

            String line;
            while ((line = br.readLine()) != null) {
                bw.write(new StringBuilder(line).reverse().toString());
                bw.newLine();
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```



</details>

Qua các bài tập trên, hy vọng các bạn đã hiểu rõ hơn về cách xử lý file trong Java, bao gồm cách đọc, ghi và thao tác với file. Hãy tiếp tục thực hành để nâng cao kỹ năng lập trình của mình.
