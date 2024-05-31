# Java Class method

## Java Class Method

Trong lập trình Java, method (phương thức) là các hàm hoặc thủ tục được định nghĩa bên trong một lớp và thực hiện các hành động hoặc thao tác trên đối tượng. Method có thể nhận tham số đầu vào và trả về kết quả đầu ra.

### Khai báo Method

Method được khai báo bên trong một lớp. Cú pháp để khai báo một method như sau:

```java
accessModifier returnType methodName(parameterList) {
    // body of method
}
```

* `accessModifier`: Là từ khóa xác định quyền truy cập vào method, như `public`, `private`, hoặc `protected`.
* `returnType`: Là kiểu dữ liệu của giá trị trả về từ method, nếu method không trả về giá trị thì sử dụng từ khóa `void`.
* `methodName`: Là tên của method.
* `parameterList`: Là danh sách các tham số mà method nhận vào (có thể rỗng).

#### Ví dụ:

```java
public class Car {
    // Attribute
    private String color;
    private int maxSpeed;

    // Constructor
    public Car(String color, int maxSpeed) {
        this.color = color;
        this.maxSpeed = maxSpeed;
    }

    // Method để hiển thị thông tin của ô tô
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

### Truyền tham số vào Method

Method có thể nhận các tham số đầu vào để thực hiện các thao tác khác nhau dựa trên giá trị của các tham số này. Tham số được khai báo trong danh sách tham số (parameter list) của method.

#### Ví dụ:

```java
public class MathOperations {
    // Method để cộng hai số nguyên
    public int add(int a, int b) {
        return a + b;
    }

    // Method để trừ hai số nguyên
    public int subtract(int a, int b) {
        return a - b;
    }
}

public class Main {
    public static void main(String[] args) {
        MathOperations math = new MathOperations();
        
        // Gọi phương thức add
        int sum = math.add(5, 3);
        System.out.println("Sum: " + sum);
        
        // Gọi phương thức subtract
        int difference = math.subtract(5, 3);
        System.out.println("Difference: " + difference);
    }
}
```

### Method trả về giá trị

Method có thể trả về một giá trị sau khi thực hiện các thao tác. Kiểu dữ liệu của giá trị trả về được khai báo trong phần `returnType` của method. Để trả về giá trị, sử dụng từ khóa `return`.

#### Ví dụ:

```java
public class Circle {
    // Attribute
    private double radius;

    // Constructor
    public Circle(double radius) {
        this.radius = radius;
    }

    // Method để tính diện tích hình tròn
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}

public class Main {
    public static void main(String[] args) {
        Circle circle = new Circle(5.0);
        
        // Gọi phương thức calculateArea
        double area = circle.calculateArea();
        System.out.println("Area: " + area);
    }
}
```

### Method Overloading

Method overloading là khả năng của một lớp để có nhiều method cùng tên nhưng khác nhau về danh sách tham số (số lượng tham số hoặc kiểu dữ liệu của tham số). Java hỗ trợ method overloading để tăng tính linh hoạt và tiện lợi khi gọi method.

#### Ví dụ:

```java
public class MathOperations {
    // Method để cộng hai số nguyên
    public int add(int a, int b) {
        return a + b;
    }

    // Method để cộng ba số nguyên
    public int add(int a, int b, int c) {
        return a + b + c;
    }

    // Method để cộng hai số thực
    public double add(double a, double b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        MathOperations math = new MathOperations();
        
        // Gọi các phương thức add khác nhau
        int sum1 = math.add(5, 3);
        int sum2 = math.add(5, 3, 2);
        double sum3 = math.add(5.5, 3.2);
        
        System.out.println("Sum1: " + sum1);
        System.out.println("Sum2: " + sum2);
        System.out.println("Sum3: " + sum3);
    }
}
```

### Bài tập thực hành

#### **Tạo lớp Calculator**

* Tạo một lớp `Calculator` với các phương thức `add`, `subtract`, `multiply`, và `divide`.
* Các phương thức này nhận hai tham số đầu vào và trả về kết quả tương ứng.

<details>

<summary>Bài giải</summary>

<pre class="language-java"><code class="lang-java"><strong>public class Calculator {
</strong>    public int add(int a, int b) {
        return a + b;
    }
    
    public int subtract(int a, int b) {
        return a - b;
    }
    
    public int multiply(int a, int b) {
        return a * b;
    }
    
    public double divide(int a, int b) {
        if (b != 0) {
            return (double) a / b;
        } else {
            throw new IllegalArgumentException("Division by zero is not allowed.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        
        int sum = calc.add(10, 5);
        int difference = calc.subtract(10, 5);
        int product = calc.multiply(10, 5);
        double quotient = calc.divide(10, 5);
        
        System.out.println("Sum: " + sum);
        System.out.println("Difference: " + difference);
        System.out.println("Product: " + product);
        System.out.println("Quotient: " + quotient);
    }
}
</code></pre>

</details>

#### **Method Overloading**

* Mở rộng lớp `Calculator` để hỗ trợ các phương thức `add`, `subtract`, `multiply`, và `divide` cho cả số nguyên và số thực.

<details>

<summary>Bài giải</summary>

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }
    
    public double add(double a, double b) {
        return a + b;
    }
    
    public int subtract(int a, int b) {
        return a - b;
    }
    
    public double subtract(double a, double b) {
        return a - b;
    }
    
    public int multiply(int a, int b) {
        return a * b;
    }
    
    public double multiply(double a, double b) {
        return a * b;
    }
    
    public double divide(int a, int b) {
        if (b != 0) {
            return (double) a / b;
        } else {
            throw new IllegalArgumentException("Division by zero is not allowed.");
        }
    }
    
    public double divide(double a, double b) {
        if (b != 0.0) {
            return a / b;
        } else {
            throw new IllegalArgumentException("Division by zero is not allowed.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        
        int sumInt = calc.add(10, 5);
        double sumDouble = calc.add(10.5, 5.5);
        int differenceInt = calc.subtract(10, 5);
        double differenceDouble = calc.subtract(10.5, 5.5);
        int productInt = calc.multiply(10, 5);
        double productDouble = calc.multiply(10.5, 5.5);
        double quotientInt = calc.divide(10, 5);
        double quotientDouble = calc.divide(10.5, 5.5);
        
        System.out.println("Sum (int): " + sumInt);
        System.out.println("Sum (double): " + sumDouble);
        System.out.println("Difference (int): " + differenceInt);
        System.out.println("Difference (double): " + differenceDouble);
        System.out.println("Product (int): " + productInt);
        System.out.println("Product (double): " + productDouble);
        System.out.println("Quotient (int): " + quotientInt);
        System.out.println("Quotient (double): " + quotientDouble);
    }
}
```



</details>

Hãy thực hiện các bài tập để làm quen với việc sử dụng method trong Java.
