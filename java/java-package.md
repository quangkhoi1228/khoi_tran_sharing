# Java Package

## Java Package

Trong Java, một **package** (gói) là một cách để tổ chức các lớp và các gói lớp liên quan đến nhau. Package giúp quản lý và tổ chức mã nguồn một cách cấu trúc và có tổ chức hơn, đặc biệt khi dự án của bạn trở nên lớn và phức tạp.

### Khái niệm về Package

Một package trong Java là một tập hợp các lớp liên quan đến nhau, các interface, và các thư viện. Nó được sử dụng để đóng gói code liên quan lại với nhau và giữ cho code dễ quản lý và tái sử dụng.

#### Tại sao sử dụng Package?

* **Tổ chức code**: Package giúp tổ chức code của bạn thành các phần nhỏ, dễ quản lý.
* **Quản lý tên**: Package cho phép bạn sử dụng các tên lớp trùng nhau từ các gói khác nhau mà không gây ra xung đột.
* **Tái sử dụng code**: Bạn có thể tái sử dụng các lớp và gói lớp ở nhiều dự án khác nhau bằng cách sử dụng package.

#### Cách sử dụng Package

Trong Java, một class hoặc một interface có thể được đặt trong một package. Để đặt một class vào một package, bạn cần sử dụng từ khóa `package` ở đầu file mã nguồn Java.

Ví dụ:

```java
package com.example.myapp;

public class MyClass {
    // code của class
}
```

Trong đoạn mã trên, class `MyClass` được đặt trong package `com.example.myapp`.

### Tạo và Sử dụng Package

#### Tạo Package

Để tạo một package mới, bạn cần tạo một thư mục mới trong cấu trúc thư mục của dự án của bạn và đặt các file mã nguồn Java vào trong thư mục đó. Tên của thư mục sẽ là tên của package.

Ví dụ: Tạo package có tên là `com.example.myapp`:

```
src/
    └── com/
        └── example/
            └── myapp/
                └── MyClass.java
```

#### Sử dụng Package

Để sử dụng các class và gói lớp từ một package khác, bạn cần sử dụng từ khóa `import`.

Ví dụ:

```java
import com.example.myapp.MyClass;

public class AnotherClass {
    // code của class
}
```

Trong đoạn mã trên, class `AnotherClass` sử dụng class `MyClass` từ package `com.example.myapp`.

Đôi khi, bạn cũng có thể sử dụng các class từ các package được cung cấp bởi Java hoặc các thư viện bên thứ ba. Để làm điều này, bạn cần import package từ bên ngoài.

Ví dụ:

```java
import java.util.Scanner;

public class MyClass {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Nhập một số nguyên: ");
        int number = scanner.nextInt();
        System.out.println("Bạn vừa nhập: " + number);
        scanner.close();
    }
}
```

Trong đoạn mã trên, chúng ta import package `java.util` để sử dụng class `Scanner` để nhập dữ liệu từ người dùng.

### Bài tập thực hành

1. Tạo một package có tên là `utilities` và trong đó tạo một class có tên là `MathHelper`. Trong class này, viết một phương thức `sum` nhận vào hai số nguyên và trả về tổng của chúng.
2. Tạo một package mới và sử dụng class `MathHelper` từ package `utilities` để tính tổng của hai số và in ra kết quả.
3. Import package `java.util` và sử dụng class `Scanner` để nhập một số nguyên từ người dùng và in ra số đó.

<details>

<summary>Bài giải</summary>

#### 1. Tạo Package và Class Utility

1. Tạo một package có tên là `utilities`.
2. Trong package `utilities`, tạo một class có tên là `MathHelper`.
3. Trong class `MathHelper`, viết một phương thức có tên là `sum` nhận vào hai số nguyên và trả về tổng của chúng.

```java
package utilities;

public class MathHelper {
    public static int sum(int a, int b) {
        return a + b;
    }
}

```

#### 2. Sử dụng Class Utility

1. Tạo một package mới và đặt tên là `app`.
2. Trong package `app`, tạo một class có tên là `Main`.
3. Trong class `Main`, sử dụng class `MathHelper` từ package `utilities` để tính tổng của hai số và in ra kết quả.

```java
package app;

import utilities.MathHelper;

public class Main {
    public static void main(String[] args) {
        int a = 10;
        int b = 20;
        int sum = MathHelper.sum(a, b);
        System.out.println("Tổng của " + a + " và " + b + " là: " + sum);
    }
}

```

#### 3. Sử dụng Scanner

1. Trong class `Main`, import package `java.util.Scanner`.
2. Sử dụng class `Scanner` để nhập một số nguyên từ người dùng và in ra số đó.

```java
package app;

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Nhập một số nguyên: ");
        int number = scanner.nextInt();
        System.out.println("Bạn vừa nhập: " + number);
        scanner.close();
    }
}

```

</details>

Bạn có thể thực hiện bài tập trên để làm quen với việc tạo và sử dụng các package trong Java.
