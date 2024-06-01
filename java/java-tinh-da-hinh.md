# Java Tính đa hình

## Giới Thiệu Polymorphism

Polymorphism (Đa hình) là một trong những khái niệm cơ bản và quan trọng trong lập trình hướng đối tượng (OOP). Nó cho phép một đối tượng có thể thực hiện các hành động khác nhau dựa trên ngữ cảnh cụ thể. Polymorphism giúp mã nguồn linh hoạt và dễ bảo trì hơn.

### Polymorphism là gì?

Polymorphism có nghĩa là "nhiều hình thái". Trong Java, Polymorphism cho phép một phương thức hoặc một đối tượng có thể hành xử khác nhau tùy thuộc vào cách chúng được gọi. Có hai loại Polymorphism chính trong Java:

* Compile-time Polymorphism (Đa hình khi biên dịch): Được thực hiện thông qua Method Overloading (Nạp chồng phương thức).
* Runtime Polymorphism (Đa hình khi chạy): Được thực hiện thông qua Method Overriding (Ghi đè phương thức).

### Compile-time Polymorphism

Compile-time Polymorphism hay Method Overloading xảy ra khi nhiều phương thức trong cùng một lớp có cùng tên nhưng khác nhau về tham số (số lượng hoặc kiểu dữ liệu).

#### Cú pháp Method Overloading

```java
class MathOperation {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

#### Ví dụ minh họa Method Overloading

```java
public class OverloadingExample {
    public static void main(String[] args) {
        MathOperation math = new MathOperation();

        System.out.println("Sum of two integers: " + math.add(5, 3));
        System.out.println("Sum of two doubles: " + math.add(5.5, 3.2));
        System.out.println("Sum of three integers: " + math.add(1, 2, 3));
    }
}
```

Trong ví dụ trên, lớp `MathOperation` có ba phương thức `add()` với cùng tên nhưng khác nhau về tham số.

### Runtime Polymorphism

Runtime Polymorphism hay Method Overriding xảy ra khi một lớp con cung cấp cách triển khai cụ thể cho một phương thức đã được định nghĩa trong lớp cha. Điều này cho phép một đối tượng lớp con được xử lý như thể nó là đối tượng của lớp cha.

#### Cú pháp Method Overriding

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}
```

#### Ví dụ minh họa Method Overriding

```java
public class OverridingExample {
    public static void main(String[] args) {
        Animal a;

        a = new Dog();
        a.sound(); // Gọi phương thức của lớp Dog

        a = new Cat();
        a.sound(); // Gọi phương thức của lớp Cat
    }
}
```

Trong ví dụ trên, phương thức `sound()` được ghi đè trong các lớp con `Dog` và `Cat`.

### Lợi ích của Polymorphism

Polymorphism giúp tăng tính linh hoạt và mở rộng của ứng dụng bằng cách cho phép một đối tượng thực hiện các hành động khác nhau dựa trên ngữ cảnh cụ thể. Điều này giúp mã nguồn dễ bảo trì và mở rộng hơn.

#### Ví dụ minh họa

```java
class Shape {
    void draw() {
        System.out.println("Drawing a shape");
    }
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle");
    }
}

class Rectangle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a rectangle");
    }
}

public class PolymorphismExample {
    public static void main(String[] args) {
        Shape s;

        s = new Circle();
        s.draw(); // Gọi phương thức của lớp Circle

        s = new Rectangle();
        s.draw(); // Gọi phương thức của lớp Rectangle
    }
}
```

Trong ví dụ này, phương thức `draw()` được ghi đè trong các lớp con `Circle` và `Rectangle`. Đối tượng `Shape` có thể tham chiếu đến đối tượng của lớp con và gọi phương thức ghi đè tương ứng.

### Bài tập thực hành

#### Bài tập 1: Method Overloading

Tạo một lớp `Calculator` với các phương thức `multiply()` để nhân hai số nguyên, hai số thực và ba số nguyên.

<details>

<summary>Bài giải</summary>

```java
class Calculator {
    int multiply(int a, int b) {
        return a * b;
    }

    double multiply(double a, double b) {
        return a * b;
    }

    int multiply(int a, int b, int c) {
        return a * b * c;
    }
}

public class Exercise1 {
    public static void main(String[] args) {
        Calculator calc = new Calculator();

        System.out.println("Product of two integers: " + calc.multiply(4, 5));
        System.out.println("Product of two doubles: " + calc.multiply(4.5, 5.5));
        System.out.println("Product of three integers: " + calc.multiply(2, 3, 4));
    }
}
```



</details>

#### Bài tập 2: Method Overriding

Tạo hai lớp `Bird` và `Sparrow` kế thừa từ lớp `Bird`. Ghi đè phương thức `fly()` trong lớp `Sparrow`.

<details>

<summary>Bài giải</summary>

```java
class Bird {
    void fly() {
        System.out.println("Bird is flying");
    }
}

class Sparrow extends Bird {
    @Override
    void fly() {
        System.out.println("Sparrow is flying");
    }
}

public class Exercise2 {
    public static void main(String[] args) {
        Bird b = new Sparrow();
        b.fly(); // Gọi phương thức của lớp Sparrow
    }
}
```



</details>

#### Bài tập 3: Polymorphism với kế thừa

Tạo ba lớp `Employee`, `Manager`, và `Developer`. Lớp `Employee` có phương thức `work()`. Ghi đè phương thức này trong các lớp `Manager` và `Developer`.

<details>

<summary>Bài giải</summary>

```java
class Employee {
    void work() {
        System.out.println("Employee is working");
    }
}

class Manager extends Employee {
    @Override
    void work() {
        System.out.println("Manager is managing");
    }
}

class Developer extends Employee {
    @Override
    void work() {
        System.out.println("Developer is developing");
    }
}

public class Exercise3 {
    public static void main(String[] args) {
        Employee e;

        e = new Manager();
        e.work(); // Gọi phương thức của lớp Manager

        e = new Developer();
        e.work(); // Gọi phương thức của lớp Developer
    }
}
```



</details>

Qua các bài tập trên, hy vọng các bạn đã hiểu rõ hơn về khái niệm Polymorphism trong Java, cách sử dụng các từ khóa và các phương thức liên quan. Hãy tiếp tục thực hành để nâng cao kỹ năng lập trình của mình.
