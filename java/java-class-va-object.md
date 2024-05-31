# Java Class và Object

## Java Class và Object

Trong lập trình Java, lớp và đối tượng (Class and Object) là hai khái niệm quan trọng của lập trình hướng đối tượng. Lớp định nghĩa cấu trúc và hành vi của một đối tượng, trong khi đối tượng là một thể hiện cụ thể của một lớp.

### Lớp (Class)

Lớp (Class) là một mẫu (template) hoặc thiết kế mà các đối tượng được tạo ra từ đó. Trong Java, mỗi đối tượng là một thể hiện của một lớp. Để định nghĩa một lớp trong Java, chúng ta sử dụng từ khóa `class`, sau đó là tên của lớp và cặp dấu ngoặc nhọn `{}` để bao quanh nội dung của lớp.

#### Cú pháp:

```java
class TenLop {
    // các thành phần của lớp
}
```

#### Ví dụ:

```java
public class Car {
    // các thuộc tính của ô tô
    String color;
    int maxSpeed;

    // phương thức khởi tạo
    public Car(String color, int maxSpeed) {
        this.color = color;
        this.maxSpeed = maxSpeed;
    }

    // phương thức để hiển thị thông tin của ô tô
    public void displayInfo() {
        System.out.println("Color: " + color);
        System.out.println("Max Speed: " + maxSpeed + " km/h");
    }
}
```

### Đối tượng (Object)

Đối tượng (Object) là một thể hiện cụ thể của một lớp. Khi một lớp được định nghĩa, chúng ta có thể tạo ra nhiều đối tượng từ lớp đó bằng cách sử dụng từ khóa `new`.

#### Cú pháp:

```java
TenLop tenDoiTuong = new TenLop();
```

#### Ví dụ:

```java
public class Main {
    public static void main(String[] args) {
        // Tạo một đối tượng ô tô từ lớp Car
        Car myCar = new Car("Red", 200);
        
        // Gọi phương thức hiển thị thông tin của ô tô
        myCar.displayInfo();
    }
}
```

### Multiple Class và Multiple Object

Trong Java, chúng ta có thể định nghĩa nhiều lớp trong cùng một file và tạo ra nhiều đối tượng từ các lớp đó.

#### Ví dụ:

```java
public class Car {
    // các thuộc tính và phương thức của lớp Car
}

public class Student {
    // các thuộc tính và phương thức của lớp Student
}

public class Main {
    public static void main(String[] args) {
        // Tạo các đối tượng từ các lớp đã được định nghĩa
        Car myCar = new Car();
        Student myStudent = new Student();
        
        // Sử dụng các đối tượng đã được tạo
    }
}
```

#### Ví dụ với Multiple Object:

```java
public class Main {
    public static void main(String[] args) {
        // Tạo một đối tượng ô tô từ lớp Car
        Car car1 = new Car("Blue", 180);
        
        // Tạo một đối tượng ô tô khác từ lớp Car
        Car car2 = new Car("Black", 220);
        
        // Gọi phương thức hiển thị thông tin của ô tô thứ nhất
        car1.displayInfo();
        
        // Gọi phương thức hiển thị thông tin của ô tô thứ hai
        car2.displayInfo();
    }
}
```

### Bài tập thực hành

1. Tạo một lớp "Employee" đại diện cho nhân viên trong một công ty. Lớp này cần có các thuộc tính như tên, tuổi và lương. Đồng thời, cung cấp phương thức để hiển thị thông tin của nhân viên.
2. Tạo một lớp "Circle" đại diện cho hình tròn. Lớp này cần có thuộc tính bán kính và các phương thức để tính diện tích và chu vi của hình tròn.
3. Viết một chương trình Java để tạo ra và hiển thị thông tin của ít nhất hai đối tượng từ mỗi lớp đã được tạo.
