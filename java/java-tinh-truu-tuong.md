# Java Tính trừu tượng

## Java Giới Thiệu Abstraction

Abstraction (Trừu tượng hóa) là một trong những tính chất cơ bản của lập trình hướng đối tượng (OOP). Nó cho phép chúng ta tập trung vào những gì một đối tượng làm thay vì cách nó làm. Abstraction giúp giảm thiểu sự phức tạp bằng cách ẩn đi các chi tiết triển khai không cần thiết và chỉ hiển thị các thuộc tính và phương thức cần thiết của đối tượng.

### Abstraction là gì?

Abstraction trong lập trình hướng đối tượng là quá trình ẩn đi các chi tiết cụ thể và chỉ hiển thị những phần quan trọng của đối tượng. Trong Java, abstraction được thực hiện thông qua các lớp trừu tượng (abstract classes) và giao diện (interfaces).

#### Lớp trừu tượng (Abstract Class)

Lớp trừu tượng là lớp không thể tạo đối tượng trực tiếp và có thể chứa các phương thức trừu tượng (phương thức không có phần triển khai). Một lớp con phải kế thừa lớp trừu tượng và cung cấp triển khai cho các phương thức trừu tượng này.

**Cú pháp lớp trừu tượng**

```java
abstract class Animal {
    // Phương thức trừu tượng
    abstract void sound();

    // Phương thức không trừu tượng
    void sleep() {
        System.out.println("Animal is sleeping");
    }
}
```

**Ví dụ về lớp trừu tượng**

```java
abstract class Animal {
    abstract void sound();

    void sleep() {
        System.out.println("Animal is sleeping");
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

public class AbstractClassExample {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound();
        dog.sleep();

        Animal cat = new Cat();
        cat.sound();
        cat.sleep();
    }
}
```

Trong ví dụ trên, lớp `Animal` là lớp trừu tượng với một phương thức trừu tượng `sound()`. Các lớp con `Dog` và `Cat` kế thừa từ `Animal` và cung cấp triển khai cho phương thức `sound()`.

#### Giao diện (Interface)

Giao diện trong Java là một tập hợp các phương thức trừu tượng. Các lớp có thể triển khai nhiều giao diện, cho phép chúng có thể thực hiện nhiều hành vi khác nhau.

**Cú pháp giao diện**

```java
interface Animal {
    void sound();
    void sleep();
}
```

**Ví dụ về giao diện**

```java
interface Animal {
    void sound();
    void sleep();
}

class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }

    @Override
    public void sleep() {
        System.out.println("Dog is sleeping");
    }
}

class Cat implements Animal {
    @Override
    public void sound() {
        System.out.println("Cat meows");
    }

    @Override
    public void sleep() {
        System.out.println("Cat is sleeping");
    }
}

public class InterfaceExample {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound();
        dog.sleep();

        Animal cat = new Cat();
        cat.sound();
        cat.sleep();
    }
}
```

Trong ví dụ trên, giao diện `Animal` định nghĩa hai phương thức trừu tượng `sound()` và `sleep()`. Các lớp `Dog` và `Cat` triển khai giao diện này và cung cấp triển khai cho các phương thức.

### Sự khác nhau giữa Abstract Class và Interface

* **Kế thừa**: Một lớp có thể kế thừa một lớp trừu tượng, nhưng có thể triển khai nhiều giao diện.
* **Phương thức**: Lớp trừu tượng có thể chứa cả phương thức trừu tượng và không trừu tượng, trong khi giao diện chỉ chứa các phương thức trừu tượng (trước Java 8).
* **Trường**: Lớp trừu tượng có thể có các trường (variables), còn giao diện chỉ có các hằng số (final variables).

### Bài tập thực hành

#### Bài tập 1: Abstract Class

Tạo một lớp trừu tượng `Shape` với phương thức trừu tượng `area()`. Tạo các lớp con `Circle` và `Rectangle` kế thừa từ `Shape` và cung cấp triển khai cho phương thức `area()`.

<details>

<summary>Bài giải</summary>

```java
abstract class Shape {
    abstract double area();
}

class Circle extends Shape {
    double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    @Override
    double area() {
        return Math.PI * radius * radius;
    }
}

class Rectangle extends Shape {
    double length, width;

    Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    @Override
    double area() {
        return length * width;
    }
}

public class Exercise1 {
    public static void main(String[] args) {
        Shape circle = new Circle(5);
        System.out.println("Area of Circle: " + circle.area());

        Shape rectangle = new Rectangle(4, 6);
        System.out.println("Area of Rectangle: " + rectangle.area());
    }
}
```



</details>

#### Bài tập 2: Interface

Tạo một giao diện `Vehicle` với phương thức `start()` và `stop()`. Tạo các lớp `Car` và `Bike` triển khai giao diện `Vehicle`.

<details>

<summary>Bài giải</summary>

```java
interface Vehicle {
    void start();
    void stop();
}

class Car implements Vehicle {
    @Override
    public void start() {
        System.out.println("Car is starting");
    }

    @Override
    public void stop() {
        System.out.println("Car is stopping");
    }
}

class Bike implements Vehicle {
    @Override
    public void start() {
        System.out.println("Bike is starting");
    }

    @Override
    public void stop() {
        System.out.println("Bike is stopping");
    }
}

public class Exercise2 {
    public static void main(String[] args) {
        Vehicle car = new Car();
        car.start();
        car.stop();

        Vehicle bike = new Bike();
        bike.start();
        bike.stop();
    }
}
```



</details>

Qua các bài tập trên, hy vọng các bạn đã hiểu rõ hơn về khái niệm Abstraction trong Java, cách sử dụng các lớp trừu tượng và giao diện. Hãy tiếp tục thực hành để nâng cao kỹ năng lập trình của mình.
