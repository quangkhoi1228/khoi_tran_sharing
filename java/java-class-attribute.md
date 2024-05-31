# Java Class attribute

## Java Class Attribute

Trong lập trình Java, attribute (thuộc tính) là các biến được định nghĩa bên trong một lớp và dùng để lưu trữ trạng thái của đối tượng. Các attribute định nghĩa thông tin chi tiết về một đối tượng cụ thể và xác định các đặc điểm của đối tượng đó. Bài giảng này sẽ hướng dẫn bạn cách khai báo, truy cập và sử dụng các attribute trong Java.

### Khai báo Attribute

Khai báo attribute trong Java được thực hiện bên trong một lớp. Một attribute có thể có các đặc tính như quyền truy cập, kiểu dữ liệu và tên.

#### Cú pháp:

```java
accessModifier dataType attributeName;
```

* `accessModifier`: Là từ khóa xác định quyền truy cập vào attribute, như `public`, `private`, hoặc `protected`.
* `dataType`: Là kiểu dữ liệu của attribute, như `int`, `double`, `String`, hoặc kiểu dữ liệu tùy chỉnh.
* `attributeName`: Là tên của attribute.

#### Ví dụ:

```java
public class Car {
    // Attribute
    private String color;
    private int maxSpeed;
}
```

Trong ví dụ trên, lớp `Car` có hai attribute là `color` và `maxSpeed`, mỗi attribute có kiểu dữ liệu tương ứng.

### Truy cập Attribute

Có thể truy cập vào attribute của một đối tượng thông qua các phương thức của lớp đó. Đối với các attribute có access modifier là `private`, chúng ta cần sử dụng các phương thức getter và setter để đọc và ghi giá trị của attribute đó.

#### Getter và Setter

Getter là phương thức dùng để đọc giá trị của attribute, còn setter là phương thức dùng để gán giá trị cho attribute. Cú pháp của getter và setter như sau:

```java
public dataType getAttributeName() {
    return attributeName;
}

public void setAttributeName(dataType attributeName) {
    this.attributeName = attributeName;
}
```

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

    // Getter cho color
    public String getColor() {
        return color;
    }

    // Setter cho color
    public void setColor(String color) {
        this.color = color;
    }

    // Getter cho maxSpeed
    public int getMaxSpeed() {
        return maxSpeed;
    }

    // Setter cho maxSpeed
    public void setMaxSpeed(int maxSpeed) {
        this.maxSpeed = maxSpeed;
    }
}

public class Main {
    public static void main(String[] args) {
        // Tạo một đối tượng ô tô từ lớp Car
        Car myCar = new Car("Red", 200);
        
        // Gọi phương thức hiển thị thông tin của ô tô
        System.out.println("Color: " + myCar.getColor());
        System.out.println("Max Speed: " + myCar.getMaxSpeed());
        
        // Thay đổi giá trị của các thuộc tính thông qua setter
        myCar.setColor("Blue");
        myCar.setMaxSpeed(220);
        
        // Hiển thị lại thông tin sau khi thay đổi
        System.out.println("Updated Color: " + myCar.getColor());
        System.out.println("Updated Max Speed: " + myCar.getMaxSpeed());
    }
}
```

### Khởi tạo Attribute

Các attribute thường được khởi tạo thông qua constructor của lớp. Constructor là một phương thức đặc biệt được gọi khi một đối tượng của lớp được tạo ra. Nó thường được sử dụng để khởi tạo các giá trị cho các attribute.

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

    // Các phương thức getter và setter như trên
}
```

### Bài tập thực hành

### **Tạo lớp Book**

* Tạo một lớp `Book` với các attribute `title` (tiêu đề), `author` (tác giả), và `pages` (số trang).
* Cung cấp các phương thức getter và setter cho mỗi attribute.
* Viết thêm một method để hiển thị thông tin của sách.

<details>

<summary>Bài giải</summary>

```java
public class Book {
    private String title;
    private String author;
    private int pages;

    public Book(String title, String author, int pages) {
        this.title = title;
        this.author = author;
        this.pages = pages;
    }

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

    public int getPages() {
        return pages;
    }

    public void setPages(int pages) {
        this.pages = pages;
    }

    public void displayInfo() {
        System.out.println("Title: " + title);
        System.out.println("Author: " + author);
        System.out.println("Pages: " + pages);
    }
}

public class Main {
    public static void main(String[] args) {
        Book myBook = new Book("1984", "George Orwell", 328);
        myBook.displayInfo();

        myBook.setTitle("Animal Farm");
        myBook.setAuthor("George Orwell");
        myBook.setPages(112);
        myBook.displayInfo();
    }
}
```



</details>

### **Tạo lớp Student**

* Tạo một lớp `Student` với các attribute `name` (tên), `age` (tuổi), và `major` (ngành học).
* Cung cấp các phương thức getter và setter cho mỗi attribute.
* Viết thêm một method để hiển thị thông tin của sinh viên.

<details>

<summary>Bài giải</summary>

```java
public class Student {
    private String name;
    private int age;
    private String major;

    public Student(String name, int age, String major) {
        this.name = name;
        this.age = age;
        this.major = major;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getMajor() {
        return major;
    }

    public void setMajor(String major) {
        this.major = major;
    }

    public void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Major: " + major);
    }
}

public class Main {
    public static void main(String[] args) {
        Student student1 = new Student("Alice", 20, "Computer Science");
        Student student2 = new Student("Bob", 22, "Mechanical Engineering");
        
        student1.displayInfo();
        student2.displayInfo();
    }
}
```



</details>

### **Bài tập thêm**

* Tạo ít nhất hai đối tượng từ mỗi lớp `Book` và `Student`, sau đó hiển thị thông tin của từng đối tượng.
* Thay đổi một số giá trị của các attribute thông qua setter và hiển thị lại thông tin sau khi thay đổi.

Hãy thực hiện các bài tập để làm quen với việc sử dụng attribute và method trong Java.
