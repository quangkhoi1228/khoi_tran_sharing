# Java Modifier

## Java Modifier

Trong lập trình Java, modifier (từ khóa sửa đổi) là các từ khóa đặc biệt được sử dụng để thay đổi các tính chất của lớp, phương thức hoặc thuộc tính. Modifier giúp xác định quyền truy cập, trạng thái, và các thuộc tính khác của thành phần trong chương trình.

### Các loại Modifier trong Java

Có hai loại modifier chính trong Java:

1. **Access Modifiers (Từ khóa truy cập)**
2. **Non-Access Modifiers (Từ khóa không truy cập)**

### Access Modifiers

Access Modifiers được sử dụng để thiết lập quyền truy cập cho các lớp, phương thức, và thuộc tính. Các loại Access Modifiers bao gồm:

#### `public`

Từ khóa `public` cho phép truy cập từ bất kỳ đâu.

#### Ví dụ:

```java
public class Car {
    public String color;
    public int maxSpeed;

    public Car(String color, int maxSpeed) {
        this.color = color;
        this.maxSpeed = maxSpeed;
    }

    public void displayInfo() {
        System.out.println("Color: " + color);
        System.out.println("Max Speed: " + maxSpeed + " km/h");
    }
}
```

#### `private`

Từ khóa `private` chỉ cho phép truy cập từ bên trong lớp đó.

#### Ví dụ:

```java
public class Car {
    private String color;
    private int maxSpeed;

    public Car(String color, int maxSpeed) {
        this.color = color;
        this.maxSpeed = maxSpeed;
    }

    public void displayInfo() {
        System.out.println("Color: " + color);
        System.out.println("Max Speed: " + maxSpeed + " km/h");
    }
}
```

#### `protected`

Từ khóa `protected` cho phép truy cập từ các lớp con và các lớp trong cùng một gói.

#### Ví dụ:

```java
public class Car {
    protected String color;
    protected int maxSpeed;

    public Car(String color, int maxSpeed) {
        this.color = color;
        this.maxSpeed = maxSpeed;
    }

    public void displayInfo() {
        System.out.println("Color: " + color);
        System.out.println("Max Speed: " + maxSpeed + " km/h");
    }
}
```

#### (default)

Nếu không sử dụng từ khóa truy cập nào, quyền truy cập sẽ là mặc định (default), chỉ cho phép truy cập từ các lớp trong cùng một gói.

#### Ví dụ:

```java
class Car {
    String color;
    int maxSpeed;

    public Car(String color, int maxSpeed) {
        this.color = color;
        this.maxSpeed = maxSpeed;
    }

    public void displayInfo() {
        System.out.println("Color: " + color);
        System.out.println("Max Speed: " + maxSpeed + " km/h");
    }
}
```

### Non-Access Modifiers

Non-Access Modifiers được sử dụng để xác định các thuộc tính khác của lớp, phương thức, và thuộc tính. Các loại Non-Access Modifiers bao gồm:

#### `static`

Từ khóa `static` cho phép thuộc tính hoặc phương thức thuộc về lớp, thay vì đối tượng của lớp.

#### Ví dụ:

```java
public class Car {
    public static int numberOfCars;

    public Car() {
        numberOfCars++;
    }

    public static void displayNumberOfCars() {
        System.out.println("Number of cars: " + numberOfCars);
    }
}
```

#### `final`

Từ khóa `final` được sử dụng để chỉ định rằng thuộc tính không thể thay đổi, phương thức không thể ghi đè, hoặc lớp không thể kế thừa.

#### Ví dụ:

```java
public final class Car {
    public final String color;

    public Car(String color) {
        this.color = color;
    }

    public final void displayInfo() {
        System.out.println("Color: " + color);
    }
}
```

#### `abstract`

Từ khóa `abstract` được sử dụng để chỉ định rằng lớp không thể tạo đối tượng và có thể chứa các phương thức trừu tượng (abstract methods).

#### Ví dụ:

```java
public abstract class Animal {
    public abstract void makeSound();

    public void eat() {
        System.out.println("This animal eats food.");
    }
}

public class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Woof");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound();
        dog.eat();
    }
}
```

### Bài tập thực hành

### **Tạo lớp Student**

* Tạo một lớp `Student` với các thuộc tính `name`, `age`, và `studentId`.
* Sử dụng các từ khóa `public`, `private`, và `protected` để thiết lập quyền truy cập cho các thuộc tính và phương thức.

<details>

<summary>Bài giải</summary>

```java
public class Student {
    private String name;
    protected int age;
    public String studentId;

    public Student(String name, int age, String studentId) {
        this.name = name;
        this.age = age;
        this.studentId = studentId;
    }

    public void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Student ID: " + studentId);
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    protected int getAge() {
        return age;
    }

    protected void setAge(int age) {
        this.age = age;
    }
}

public class Main {
    public static void main(String[] args) {
        Student student = new Student("John Doe", 20, "S12345");
        student.displayInfo();
        student.setName("Jane Doe");
        student.displayInfo();
    }
}
```



</details>

### **Tạo lớp Employee**

* Tạo một lớp `Employee` với các thuộc tính `employeeId`, `name`, và `salary`.
* Sử dụng từ khóa `static` để đếm số lượng nhân viên được tạo.
* Sử dụng từ khóa `final` để đảm bảo rằng `employeeId` không thể thay đổi.

<details>

<summary>Bài giải </summary>

```java
public class Employee {
    private static int count = 0;
    public final String employeeId;
    private String name;
    private double salary;

    public Employee(String employeeId, String name, double salary) {
        this.employeeId = employeeId;
        this.name = name;
        this.salary = salary;
        count++;
    }

    public void displayInfo() {
        System.out.println("Employee ID: " + employeeId);
        System.out.println("Name: " + name);
        System.out.println("Salary: $" + salary);
    }

    public static int getCount() {
        return count;
    }
}

public class Main {
    public static void main(String[] args) {
        Employee emp1 = new Employee("E001", "Alice", 50000);
        Employee emp2 = new Employee("E002", "Bob", 60000);
        
        emp1.displayInfo();
        emp2.displayInfo();
        
        System.out.println("Total Employees: " + Employee.getCount());
    }
}
```



</details>

Hãy thực hiện các bài tập để làm quen với việc sử dụng các modifier trong Java.
