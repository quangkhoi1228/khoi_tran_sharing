# JS

## JS là gì?

JavaScript là ngôn ngữ lập trình phổ biến nhất thế giới

JavaScript là ngôn ngữ lập trình cho website

JavaScript rất dễ để học

## Thêm JS vào trang

Tham khảo HTML javascript: [Cách thêm JavaScript](https://app.gitbook.com/@quangkhoi1228/s/front-end-guide/~/drafts/-MY3PD3alRQ69Ywet0ra/front-end-can-ban/html#html-javascript)

## Biến

biến được khai báo bằng từ khóa `var`

### Tổng quan

```javascript
//khai báo biến
var x = 5;
var y = 6;
var z = x + y;

//nhiều biến 1 dòng
var person = "John Doe", carName = "Volvo", price = 200;

//nhiều biến nhiều dòng
var person = "John Doe",
carName = "Volvo",
price = 200;

//Giá trị mặc định của biến là undefined
var carName;
//undefined

//khai báo lại biến không làm mất dữ liệu biến
var carName = "Volvo";
var carName;
//Volvo
```

### 

### Sử dụng **let** và **const** \(ES6\)

Trước 2015 để khai báo biến trong JS chỉ có duy nhất từ khóa `var` 

Từ [JavaScript \(ES6\)](https://www.w3schools.com/js/js_es6.asp) phiên bản 2015 JS chấp nhận từ khóa `const`  để khai báo 1 biến không thể khai báo lại và `let` để hạn chế phạm vi hoạt động của biến.

### Kiểu dữ liệu

Biến JS có thể chứa các dữ liệu kiểu String, Number, Object vân vân

```javascript
var length = 16;                               // Number
var lastName = "Johnson";                      // String
var x = {firstName:"John", lastName:"Doe"};   //object
```

## Hàm

Một hàm JS là một khối code được thiết kế để thực thi 1 tác vụ nào đó

Một hàm JS được thực thi khi nó được gọi

### Cú pháp

```javascript
function name(parameter1, parameter2, parameter3) {
  // code to be executed
}

//example
function myFunction(p1, p2) {
  return p1 * p2; 
} 
```

### return giá trị

Khi hàm thực thi tới từ khóa `return`  hàm sẽ dừng và trả giá trị về cho nơi gọi nó

```javascript
var x = myFunction(4, 3);   // Function is called, return value will end up in x

function myFunction(a, b) {
  return a * b;             // Function returns the product of a and b
}
//12
```

## Đối tượng\(Object\)

Object trong JS được định nghĩa theo cấu trúc JSON tìm hiểu thêm [tại đây](https://app.gitbook.com/@quangkhoi1228/s/front-end-guide/~/drafts/-MY3kpB8BWsP7tWZQ1b8/shinobi-js-core/cac-khai-niem/json)

## Sự kiện\(Event\)

Sự kiện trong JS có thể là 1 thứ gì đó trình duyệt web hoặc người dùng vừa thực hiện như: 

* Trang tải xong
* Người dùng thao tác với phần tử trong trang
* ...

Ví dụ:

```markup
<element event="some JavaScript">

<button onclick="alert('Hello')">Click me.</button>
```

Một số sự kiện

| Sự kiện | Diễn giải |
| :--- | :--- |
| onchange | Một phần tử HTML vừa thay đổi |
| onclick | Người dùng click vào phần tử |
| onmouseover | Người dùng rê chuột vào phần tử |
| onmouseout | Người dùng rê chuột ra khỏi phần tử |
| onkeydown | Người dùng nhấn 1 nút |
| onload | Trình duyệt web load xong trang |

Xem thêm  các sự kiện [tại đây](https://www.w3schools.com/jsref/dom_obj_event.asp)

## Điều kiện\(Condition\)

### Câu lệnh if

Dùng câu lệnh `if` để xác định khối code thực thi nếu điều kiện bằng `true`

```javascript
if (condition) {
  //  block of code to be executed if the condition is true
}
```

Ví dụ:

```javascript
if (hour < 18) {
  greeting = "Good day";
}
//Good day
```

### Câu lệnh else

Dùng câu lệnh `else`  để xác định khối code thực thi nếu điều kiện bằng `false`

```javascript
if (condition) {
  //  block of code to be executed if the condition is true
} else {
  //  block of code to be executed if the condition is false
}
```

Ví dụ:

```javascript
if (hour < 18) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
//Good day
```

### Câu lệnh else if

Sử dụng câu lệnh `else if` để định nghĩa 1 điều kiện mới điều kiện đầu tiên `false`

```javascript
if (condition1) {
  //  block of code to be executed if condition1 is true
} else if (condition2) {
  //  block of code to be executed if the condition1 is false and condition2 is true
} else {
  //  block of code to be executed if the condition1 is false and condition2 is false
}
```

Ví dụ:

```javascript
if (time < 10) {
  greeting = "Good morning";
} else if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
//Good day
```

### Câu lệnh switch

Sử dụng câu lệnh `switch` để chọn 1 trong nhiều khối code để thực thi

```javascript
switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}
```

#### Cách hoạt động

* Biểu thức `switch` được đánh giá 1 lần
* Giá trị của biểu thức sẽ được so sánh với giá trị của mỗi `case` 
* Nếu khớp, khối code liên kết với `case` đó sẽ được thực thi
* Nếu không có trường hợp nào khớp, khối code `default` sẽ được thực thi 

Ví dụ:

```javascript
//new Date().getDay() lấy về thứ tự hiện tại của ngày trong tuần 
//từ 0 đến 6
switch (new Date().getDay()) {
  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
     day = "Tuesday";
    break;
  case 3:
    day = "Wednesday";
    break;
  case 4:
    day = "Thursday";
    break;
  case 5:
    day = "Friday";
    break;
  case 6:
    day = "Saturday";
}
//"Monday"
```

#### Từ khóa `break`

* Khi JS thực thi tới từ khóa `break`, khối code switch đang thực thi sẽ dừng và thoát khỏi câu lệnh `switch`
* Nếu khối code trong `case` đó được thực thi nhưng không có từ khóa `break` để thoát thì khối code trong `case` tiếp theo sẽ được kích hoạt cho dù có khớp với giá trị của điều kiện hay không và cứ thế đi đến hết các `case` của `switch`
* Không cần `break` khối code cuối cùng vì đường nào khối code đó cũng sẽ dừng

