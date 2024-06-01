# Java User Input

## Java User Input

Trong lập trình, việc nhận đầu vào từ người dùng là một kỹ năng quan trọng. Java cung cấp nhiều cách để đọc dữ liệu từ người dùng, phổ biến nhất là sử dụng lớp `Scanner`. Lớp `Scanner` thuộc gói `java.util` và cho phép chúng ta đọc dữ liệu từ nhiều nguồn khác nhau như bàn phím, file, hoặc chuỗi.

### Sử Dụng Lớp Scanner

Lớp `Scanner` cung cấp các phương thức để đọc các loại dữ liệu khác nhau như chuỗi, số nguyên, số thực, v.v.

#### Khởi Tạo Scanner

Để sử dụng `Scanner` để đọc đầu vào từ bàn phím, chúng ta cần khởi tạo một đối tượng của lớp `Scanner` với `System.in`:

```java
import java.util.Scanner;

public class UserInputExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter your name:");
        String name = scanner.nextLine();
        
        System.out.println("Enter your age:");
        int age = scanner.nextInt();

        System.out.println("Hello, " + name + ". You are " + age + " years old.");
        
        scanner.close();
    }
}
```

#### Đọc Chuỗi

Phương thức `nextLine()` được sử dụng để đọc một dòng văn bản từ người dùng.

```java
import java.util.Scanner;

public class ReadStringExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter a sentence:");
        String sentence = scanner.nextLine();
        
        System.out.println("You entered: " + sentence);
        
        scanner.close();
    }
}
```

#### Đọc Số Nguyên

Phương thức `nextInt()` được sử dụng để đọc một số nguyên từ người dùng.

```java
import java.util.Scanner;

public class ReadIntExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter a number:");
        int number = scanner.nextInt();
        
        System.out.println("You entered: " + number);
        
        scanner.close();
    }
}
```

#### Đọc Số Thực

Phương thức `nextDouble()` được sử dụng để đọc một số thực từ người dùng.

```java
import java.util.Scanner;

public class ReadDoubleExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter a floating-point number:");
        double number = scanner.nextDouble();
        
        System.out.println("You entered: " + number);
        
        scanner.close();
    }
}
```

#### Đọc Ký Tự

Phương thức `next().charAt(0)` được sử dụng để đọc một ký tự từ người dùng.

```java
import java.util.Scanner;

public class ReadCharExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter a character:");
        char character = scanner.next().charAt(0);
        
        System.out.println("You entered: " + character);
        
        scanner.close();
    }
}
```

### Bài Tập Thực Hành

#### Bài Tập 1: Đọc Tên và Tuổi

Tạo một chương trình để đọc tên và tuổi của người dùng và hiển thị thông tin đó.

<details>

<summary>Bài giải</summary>

```java
import java.util.Scanner;

public class Exercise1 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter your name:");
        String name = scanner.nextLine();
        
        System.out.println("Enter your age:");
        int age = scanner.nextInt();

        System.out.println("Hello, " + name + ". You are " + age + " years old.");
        
        scanner.close();
    }
}
```



</details>

#### Bài Tập 2: Tính Tổng Hai Số Nguyên

Tạo một chương trình để đọc hai số nguyên từ người dùng và tính tổng của chúng.

<details>

<summary>Bài giải</summary>

```java
import java.util.Scanner;

public class Exercise2 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the first number:");
        int num1 = scanner.nextInt();
        
        System.out.println("Enter the second number:");
        int num2 = scanner.nextInt();

        int sum = num1 + num2;
        System.out.println("The sum is: " + sum);
        
        scanner.close();
    }
}
```



</details>

#### Bài Tập 3: Đọc và In Số Thực

Tạo một chương trình để đọc một số thực từ người dùng và hiển thị số đó với hai chữ số thập phân.

<details>

<summary>Bài giải</summary>

```java
import java.util.Scanner;

public class Exercise3 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter a floating-point number:");
        double number = scanner.nextDouble();

        System.out.printf("You entered: %.2f%n", number);
        
        scanner.close();
    }
}
```



</details>

#### Bài Tập 4: Đọc Ký Tự và Hiển Thị Mã ASCII

Tạo một chương trình để đọc một ký tự từ người dùng và hiển thị mã ASCII của ký tự đó.

<details>

<summary>Bài giải</summary>

```java
import java.util.Scanner;

public class Exercise4 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter a character:");
        char character = scanner.next().charAt(0);

        int ascii = (int) character;
        System.out.println("The ASCII value of " + character + " is " + ascii);
        
        scanner.close();
    }
}
```



</details>

#### Bài Tập 5: Kiểm Tra Số Chẵn Lẻ

Tạo một chương trình để đọc một số nguyên từ người dùng và kiểm tra xem số đó là chẵn hay lẻ.

<details>

<summary>Bài giải</summary>

```java
import java.util.Scanner;

public class Exercise5 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter an integer:");
        int number = scanner.nextInt();

        if (number % 2 == 0) {
            System.out.println("The number is even.");
        } else {
            System.out.println("The number is odd.");
        }
        
        scanner.close();
    }
}
```



</details>

Qua các bài tập trên, hy vọng các bạn đã hiểu rõ hơn về cách nhận đầu vào từ người dùng trong Java, bao gồm việc đọc chuỗi, số nguyên, số thực và ký tự. Hãy tiếp tục thực hành để nâng cao kỹ năng lập trình của mình.
