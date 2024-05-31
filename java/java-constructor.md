# Java Constructor

## Java Constructor

Trong lập trình Java, constructor (hàm dựng) là một phương thức đặc biệt được sử dụng để khởi tạo đối tượng của lớp. Constructor có cùng tên với lớp và không có kiểu trả về, kể cả `void`.

### Khai báo Constructor

Khi bạn tạo một đối tượng từ lớp, constructor sẽ được gọi để khởi tạo các giá trị cho các thuộc tính của đối tượng đó.

#### Cú pháp:

```java
class ClassName {
    // Constructor
    ClassName(parameterList) {
        // body of constructor
    }
}
```

* `ClassName`: Là tên của lớp.
* `parameterList`: Là danh sách các tham số mà constructor nhận vào (có thể rỗng).

#### Ví dụ:

```java
public class Car {
    private String color;
    private int maxSpeed;

    // Constructor
    public Car(String color, int maxSpeed) {
        this.color = color;
        this.maxSpeed = maxSpeed;
    }

    // Phương thức để hiển thị thông tin của ô tô
    public void displayInfo() {
        System.out.println("Color: " + color);
        System.out.println("Max Speed: " + maxSpeed + " km/h");
    }
}

public class Main {
    public static void main(String[] args) {
        // Tạo một đối tượng ô tô từ lớp Car
        Car myCar = new Car("Red", 200);
        
        // Gọi phương thức hiển thị thông tin của ô tô
        myCar.displayInfo();
    }
}
```

Trong ví dụ trên, lớp `Car` có một constructor nhận hai tham số `color` và `maxSpeed`. Khi tạo một đối tượng `Car`, constructor này sẽ được gọi để khởi tạo các giá trị cho các thuộc tính của đối tượng.

### Constructor Mặc Định

Nếu bạn không định nghĩa constructor nào cho lớp, Java sẽ tự động tạo ra một constructor mặc định không tham số. Constructor này sẽ không làm gì cả và các thuộc tính của đối tượng sẽ được khởi tạo với giá trị mặc định của chúng (0, null, false, v.v.).

#### Ví dụ:

```java
public class Dog {
    private String name;
    private int age;

    // Constructor mặc định do Java tự động tạo
    public Dog() {
    }

    // Phương thức để hiển thị thông tin của chó
    public void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age + " years");
    }
}

public class Main {
    public static void main(String[] args) {
        // Tạo một đối tượng chó từ lớp Dog
        Dog myDog = new Dog();
        
        // Gọi phương thức hiển thị thông tin của chó
        myDog.displayInfo();
    }
}
```

Trong ví dụ trên, mặc dù không định nghĩa constructor nào cho lớp `Dog`, Java vẫn tạo ra một constructor mặc định không tham số.

### Constructor Overloading

Constructor overloading là khả năng của một lớp để có nhiều constructor với các tham số khác nhau. Điều này cho phép bạn khởi tạo đối tượng theo nhiều cách khác nhau.

#### Ví dụ:

```java
public class Rectangle {
    private double length;
    private double width;

    // Constructor không tham số
    public Rectangle() {
        this.length = 1.0;
        this.width = 1.0;
    }

    // Constructor với một tham số
    public Rectangle(double side) {
        this.length = side;
        this.width = side;
    }

    // Constructor với hai tham số
    public Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    // Phương thức để tính diện tích hình chữ nhật
    public double calculateArea() {
        return length * width;
    }

    // Phương thức để hiển thị thông tin của hình chữ nhật
    public void displayInfo() {
        System.out.println("Length: " + length);
        System.out.println("Width: " + width);
        System.out.println("Area: " + calculateArea());
    }
}

public class Main {
    public static void main(String[] args) {
        // Tạo các đối tượng hình chữ nhật từ lớp Rectangle
        Rectangle rect1 = new Rectangle();
        Rectangle rect2 = new Rectangle(5.0);
        Rectangle rect3 = new Rectangle(4.0, 6.0);
        
        // Gọi phương thức hiển thị thông tin của hình chữ nhật
        rect1.displayInfo();
        rect2.displayInfo();
        rect3.displayInfo();
    }
}
```

Trong ví dụ trên, lớp `Rectangle` có ba constructor với các tham số khác nhau. Điều này cho phép bạn tạo đối tượng `Rectangle` theo nhiều cách khác nhau.

### Bài tập thực hành

### **Tạo lớp Person**

* Tạo một lớp `Person` với các thuộc tính `name` (tên) và `age` (tuổi).
* Cung cấp ba constructor: constructor mặc định, constructor với một tham số `name`, và constructor với hai tham số `name` và `age`.
* Viết thêm phương thức `displayInfo` để hiển thị thông tin của người.

<details>

<summary>Bài giải</summary>

```java
public class Person {
    private String name;
    private int age;

    // Constructor mặc định
    public Person() {
        this.name = "Unknown";
        this.age = 0;
    }

    // Constructor với một tham số
    public Person(String name) {
        this.name = name;
        this.age = 0;
    }

    // Constructor với hai tham số
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Phương thức để hiển thị thông tin của người
    public void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age + " years");
    }
}

public class Main {
    public static void main(String[] args) {
        // Tạo các đối tượng từ lớp Person
        Person person1 = new Person();
        Person person2 = new Person("Alice");
        Person person3 = new Person("Bob", 25);
        
        // Gọi phương thức hiển thị thông tin của người
        person1.displayInfo();
        person2.displayInfo();
        person3.displayInfo();
    }
}
```



</details>

### **Tạo lớp BankAccount**

* Tạo một lớp `BankAccount` với các thuộc tính `accountNumber` (số tài khoản) và `balance` (số dư).
* Cung cấp ba constructor: constructor mặc định, constructor với một tham số `accountNumber`, và constructor với hai tham số `accountNumber` và `balance`.
* Viết thêm phương thức `displayInfo` để hiển thị thông tin của tài khoản.

<details>

<summary>Bài giải</summary>

```java
public class BankAccount {
    private String accountNumber;
    private double balance;

    // Constructor mặc định
    public BankAccount() {
        this.accountNumber = "000000";
        this.balance = 0.0;
    }

    // Constructor với một tham số
    public BankAccount(String accountNumber) {
        this.accountNumber = accountNumber;
        this.balance = 0.0;
    }

    // Constructor với hai tham số
    public BankAccount(String accountNumber, double balance) {
        this.accountNumber = accountNumber;
        this.balance = balance;
    }

    // Phương thức để hiển thị thông tin của tài khoản
    public void displayInfo() {
        System.out.println("Account Number: " + accountNumber);
        System.out.println("Balance: $" + balance);
    }
}

public class Main {
    public static void main(String[] args) {
        // Tạo các đối tượng từ lớp BankAccount
        BankAccount account1 = new BankAccount();
        BankAccount account2 = new BankAccount("123456");
        BankAccount account3 = new BankAccount("789012", 1000.0);
        
        // Gọi phương thức hiển thị thông tin của tài khoản
        account1.displayInfo();
        account2.displayInfo();
        account3.displayInfo();
    }
}
```



</details>

### **Bài tập thêm**

* Tạo thêm một số đối tượng từ các lớp `Person` và `BankAccount`, sau đó hiển thị thông tin của từng đối tượng.
* Thử thay đổi giá trị của các thuộc tính thông qua constructor và kiểm tra kết quả.

Hãy thực hiện các bài tập để làm quen với việc sử dụng constructor trong Java.
