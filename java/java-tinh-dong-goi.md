# Java Tính đóng gói

## Java Encapsulation(Tính đóng gói)

Encapsulation là một trong những nguyên tắc cơ bản của lập trình hướng đối tượng (OOP) trong Java. Encapsulation giúp bảo vệ dữ liệu của đối tượng bằng cách ẩn các chi tiết cụ thể và chỉ cung cấp các phương thức cần thiết để truy cập và thay đổi dữ liệu.

### Khái Niệm Encapsulation

Encapsulation là quá trình đóng gói dữ liệu (các biến) và các phương thức hoạt động trên dữ liệu đó thành một khối duy nhất. Trong Java, điều này được thực hiện bằng cách:

1. Đặt các biến của lớp là `private`.
2. Cung cấp các phương thức `public` getter và setter để truy cập và cập nhật các biến này.

### Lợi Ích của Encapsulation

* **Bảo vệ Dữ liệu**: Ngăn chặn truy cập trái phép và thay đổi dữ liệu từ bên ngoài lớp.
* **Dễ Dàng Bảo Trì**: Thay đổi nội bộ của lớp không ảnh hưởng đến các mã sử dụng lớp đó.
* **Tăng Tính Mô-đun**: Các đối tượng có thể được quản lý một cách độc lập và dễ dàng tái sử dụng.

### Cách Thực Hiện Encapsulation

#### Đặt Biến là Private

Các biến của lớp được khai báo là `private` để ngăn chặn truy cập trực tiếp từ bên ngoài.

#### Cung Cấp Phương Thức Getter và Setter

Phương thức `getter` để truy cập giá trị của biến và phương thức `setter` để thay đổi giá trị của biến. Phương thức `setter` có thể bao gồm các kiểm tra hợp lệ để đảm bảo tính toàn vẹn của dữ liệu.

### Ví Dụ về Encapsulation

```java
public class Student {
    // Biến private
    private String name;
    private int age;

    // Phương thức getter cho name
    public String getName() {
        return name;
    }

    // Phương thức setter cho name
    public void setName(String name) {
        this.name = name;
    }

    // Phương thức getter cho age
    public int getAge() {
        return age;
    }

    // Phương thức setter cho age
    public void setAge(int age) {
        if (age >= 0) {
            this.age = age;
        } else {
            System.out.println("Tuổi không hợp lệ.");
        }
    }
}
```

#### Sử Dụng Lớp Student

```java
public class Main {
    public static void main(String[] args) {
        Student student = new Student();
        student.setName("Nguyễn Văn A");
        student.setAge(20);

        System.out.println("Tên: " + student.getName());
        System.out.println("Tuổi: " + student.getAge());
    }
}
```

### Bài Tập Thực Hành

### **Tạo Lớp Circle**

* Tạo một lớp `Circle` với các biến private `radius` và `color`.
* Cung cấp các phương thức public `getRadius()`, `setRadius(double radius)`, `getColor()`, và `setColor(String color)` để truy cập và cập nhật giá trị của các biến này.
* Đảm bảo rằng bán kính không thể là số âm.

<details>

<summary>Bài giải</summary>

```java
public class Circle {
    private double radius;
    private String color;

    public double getRadius() {
        return radius;
    }

    public void setRadius(double radius) {
        if (radius >= 0) {
            this.radius = radius;
        } else {
            System.out.println("Bán kính không hợp lệ.");
        }
    }

    public String getColor() {
        return color;
    }

    public void setColor(String color) {
        this.color = color;
    }
}

public class Main {
    public static void main(String[] args) {
        Circle circle = new Circle();
        circle.setRadius(5.5);
        circle.setColor("Đỏ");

        System.out.println("Bán kính: " + circle.getRadius());
        System.out.println("Màu sắc: " + circle.getColor());
    }
}
```



</details>

### **Tạo Lớp BankAccount**

* Tạo một lớp `BankAccount` với biến private `balance`.
* Cung cấp các phương thức public `getBalance()`, `deposit(double amount)`, và `withdraw(double amount)` để truy cập và cập nhật số dư tài khoản.
* Đảm bảo rằng không thể rút số tiền lớn hơn số dư hiện tại.

<details>

<summary>Bài giải</summary>

```java
public class BankAccount {
    private double balance;

    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        } else {
            System.out.println("Số tiền gửi không hợp lệ.");
        }
    }

    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        } else {
            System.out.println("Số tiền rút không hợp lệ hoặc không đủ số dư.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        BankAccount account = new BankAccount();
        account.deposit(1000);
        account.withdraw(500);

        System.out.println("Số dư tài khoản: " + account.getBalance());
    }
}
```



</details>

### **Tạo Lớp Book**

* Tạo một lớp `Book` với các biến private `title`, `author`, và `price`.
* Cung cấp các phương thức public `getTitle()`, `getAuthor()`, `getPrice()`, và `setPrice(double price)` để truy cập và cập nhật giá trị của các biến này.
* Đảm bảo rằng giá tiền không thể là số âm.

<details>

<summary>Bài giải</summary>

```java
public class Book {
    private String title;
    private String author;
    private double price;

    public String getTitle() {
        return title;
    }

    public void setTitle(String title) {
        this.title = title;
    }

    public String getAuthor() {
        return author;
    }

    public void setAuthor(String author) {
        this.author = author;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        if (price >= 0) {
            this.price = price;
        } else {
            System.out.println("Giá không hợp lệ.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Book book = new Book();
        book.setTitle("Lập Trình Java");
        book.setAuthor("Nguyễn Văn B");
        book.setPrice(150000);

        System.out.println("Tên sách: " + book.getTitle());
        System.out.println("Tác giả: " + book.getAuthor());
        System.out.println("Giá: " + book.getPrice() + " VND");
    }
}
```



</details>

Hãy thực hiện các bài tập trên để làm quen với Encapsulation trong Java và hiểu rõ hơn về cách sử dụng nó trong lập trình hướng đối tượng.
