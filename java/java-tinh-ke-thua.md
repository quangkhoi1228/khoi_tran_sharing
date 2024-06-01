# Java Tính kế thừa

## Java Inheritance

Java Inheritance (Kế thừa trong Java) là một khái niệm quan trọng trong lập trình hướng đối tượng (OOP), cho phép một lớp (class) thừa hưởng các thuộc tính và phương thức của một lớp khác. Điều này giúp tái sử dụng mã nguồn, tăng tính linh hoạt và mở rộng của ứng dụng.

### Khái niệm kế thừa trong Java

Kế thừa là quá trình mà một lớp (được gọi là lớp con hoặc lớp dẫn xuất) kế thừa các thuộc tính và phương thức từ một lớp khác (được gọi là lớp cha hoặc lớp cơ sở). Lớp con có thể sử dụng và mở rộng các thành phần của lớp cha mà không cần phải viết lại mã nguồn.

#### Cú pháp cơ bản

```java
class ParentClass {
    // Các thuộc tính và phương thức của lớp cha
}

class ChildClass extends ParentClass {
    // Các thuộc tính và phương thức của lớp con
}
```

#### Ví dụ minh họa

```java
// Lớp cha
class Animal {
    void eat() {
        System.out.println("Animal is eating");
    }
}

// Lớp con
class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking");
    }
}

public class InheritanceExample {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat(); // Gọi phương thức của lớp cha
        d.bark(); // Gọi phương thức của lớp con
    }
}
```

Trong ví dụ trên, lớp `Dog` kế thừa từ lớp `Animal`, vì vậy nó có thể sử dụng phương thức `eat()` của lớp cha.

### Từ khóa `super`

Từ khóa `super` được sử dụng để gọi trực tiếp các phương thức và thuộc tính của lớp cha từ lớp con.

#### Cú pháp `super`

```java
class ParentClass {
    void parentMethod() {
        System.out.println("This is a parent method");
    }
}

class ChildClass extends ParentClass {
    void childMethod() {
        super.parentMethod(); // Gọi phương thức của lớp cha
        System.out.println("This is a child method");
    }
}
```

#### Ví dụ minh họa

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Cat extends Animal {
    void sound() {
        super.sound(); // Gọi phương thức của lớp cha
        System.out.println("Cat meows");
    }
}

public class SuperExample {
    public static void main(String[] args) {
        Cat c = new Cat();
        c.sound(); // Gọi phương thức của lớp con
    }
}
```

### Kế thừa nhiều cấp (Multilevel Inheritance)

Kế thừa nhiều cấp xảy ra khi một lớp con kế thừa từ một lớp con khác, tức là có nhiều cấp kế thừa.

#### Ví dụ minh họa

```java
class Animal {
    void move() {
        System.out.println("Animal is moving");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking");
    }
}

class Puppy extends Dog {
    void play() {
        System.out.println("Puppy is playing");
    }
}

public class MultilevelInheritanceExample {
    public static void main(String[] args) {
        Puppy p = new Puppy();
        p.move(); // Phương thức của lớp cha
        p.bark(); // Phương thức của lớp con
        p.play(); // Phương thức của lớp cháu
    }
}
```

### Ghi đè phương thức (Method Overriding)

Ghi đè phương thức cho phép một lớp con cung cấp cách triển khai cụ thể cho một phương thức đã được định nghĩa trong lớp cha.

#### Cú pháp ghi đè phương thức

```java
class ParentClass {
    void display() {
        System.out.println("Parent class method");
    }
}

class ChildClass extends ParentClass {
    @Override
    void display() {
        System.out.println("Child class method");
    }
}
```

#### Ví dụ minh họa

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}

public class OverridingExample {
    public static void main(String[] args) {
        Animal a = new Cat();
        a.sound(); // Gọi phương thức ghi đè
    }
}
```

### Từ khóa `final`

Từ khóa `final` trong Java có thể được sử dụng để khai báo biến, phương thức và lớp với các ý nghĩa khác nhau:

#### `final` với biến

Một biến được khai báo là `final` không thể thay đổi giá trị sau khi đã được gán.

```java
final int MAX_VALUE = 100;

public class FinalVariableExample {
    public static void main(String[] args) {
        final int x = 10;
        // x = 20; // Lỗi: Không thể gán lại giá trị cho biến final
        System.out.println("x = " + x);
    }
}
```

#### `final` với phương thức

Một phương thức được khai báo là `final` không thể bị ghi đè bởi các lớp con.

```java
class ParentClass {
    final void finalMethod() {
        System.out.println("This is a final method");
    }
}

class ChildClass extends ParentClass {
    // void finalMethod() {
    //     // Lỗi: Không thể ghi đè phương thức final
    // }
}
```

#### `final` với lớp

Một lớp được khai báo là `final` không thể được kế thừa.

```java
final class FinalClass {
    // Nội dung của lớp final
}

// class SubClass extends FinalClass {
//     // Lỗi: Không thể kế thừa lớp final
// }
```

#### Ví dụ minh họa

```java
final class Constants {
    static final double PI = 3.14159;
}

class Circle {
    double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    void displayArea() {
        double area = Constants.PI * radius * radius;
        System.out.println("Area of the circle: " + area);
    }
}

public class FinalExample {
    public static void main(String[] args) {
        Circle c = new Circle(5);
        c.displayArea();
    }
}
```

Trong ví dụ này, lớp `Constants` và biến `PI` được khai báo là `final`, nghĩa là giá trị của `PI` không thể thay đổi và lớp `Constants` không thể được kế thừa.

### Bài tập thực hành

#### Bài tập 1: Kế thừa cơ bản

Tạo hai lớp `Vehicle` và `Car`. Lớp `Vehicle` có thuộc tính `color` và phương thức `move()`. Lớp `Car` kế thừa từ lớp `Vehicle` và thêm phương thức `turnOnLights()`.

<details>

<summary>Bài giải</summary>

```java
class Vehicle {
    String color;

    void move() {
        System.out.println("Vehicle is moving");
    }
}

class Car extends Vehicle {
    void turnOnLights() {
        System.out.println("Car is turning on lights");
    }
}

public class Exercise1 {
    public static void main(String[] args) {
        Car car = new Car();
        car.color = "Red";
        car.move();
        car.turnOnLights();
    }
}
```



</details>

#### Bài tập 2: Ghi đè phương thức

Tạo hai lớp `Shape` và `Circle`. Lớp `Shape` có phương thức `calculateArea()`. Lớp `Circle` kế thừa từ lớp `Shape` và ghi đè phương thức `calculateArea()` để tính diện tích hình tròn.

<details>

<summary>Bài giải</summary>

```java
class Shape {
    double radius;

    void calculateArea() {
        System.out.println("Area of shape is not defined");
    }
}

class Circle extends Shape {
    Circle(double radius) {
        this.radius = radius;
    }

    @Override
    void calculateArea() {
        double area = Math.PI * radius * radius;
        System.out.println("Area of circle: " + area);
    }
}

public class Exercise2 {
    public static void main(String[] args) {
        Circle c = new Circle(5);
        c.calculateArea();
    }
}
```



</details>

#### Bài tập 3: Kế thừa nhiều cấp

Tạo ba lớp `Employee`, `AdministrativeEmployee`, và `TechnicalEmployee`. Lớp `Employee` có phương thức `work()`. Lớp `AdministrativeEmployee` kế thừa từ `Employee` và thêm phương thức `attendMeeting()`. Lớp `TechnicalEmployee` kế thừa từ `AdministrativeEmployee` và thêm phương thức `repairMachine()`.

<details>

<summary>Bài giải</summary>

```java
class Employee {
    void work() {
        System.out.println("Employee is working");
    }
}

class AdministrativeEmployee extends Employee {
    void attendMeeting() {
        System.out.println("Administrative employee is attending a meeting");
    }
}

class TechnicalEmployee extends AdministrativeEmployee {
    void repairMachine() {
        System.out.println("Technical employee is repairing a machine");
    }
}

public class Exercise3 {
    public static void main(String[] args) {
        TechnicalEmployee te = new TechnicalEmployee();
        te.work();
        te.attendMeeting();
        te.repairMachine();
    }
}
```



</details>

Qua các bài tập trên, hy vọng các bạn đã hiểu rõ hơn về khái niệm kế thừa trong Java, cách sử dụng các từ khóa và các phương thức liên quan. Hãy tiếp tục thực hành

để nâng cao kỹ năng lập trình của mình.
