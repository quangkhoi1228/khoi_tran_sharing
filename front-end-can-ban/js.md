# JS

## JS là gì?

JavaScript là ngôn ngữ lập trình phổ biến nhất thế giới

JavaScript là ngôn ngữ lập trình cho website

JavaScript rất dễ để học

## Thêm JS vào trang

Tham khảo HTML javascript: [Cách thêm JavaScript](https://app.gitbook.com/@quangkhoi1228/s/front-end-guide/~/drafts/-MY3PD3alRQ69Ywet0ra/front-end-can-ban/html#html-javascript)

## Biến\(variables\)

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

Trong JS có 5 loại kiểu dữ liệu có thể chứa giá trị

* `string`
* `number`
* `boolean`
* `object`
* `function`

Có 6 loại dữ liệu thuộc đối tượng

* `Object`
* `Date`
* `Array`
* `String`
* `Number`
* `Boolean`

và 2 loại dữ liệu không chứa giá trị

* `null`
* `undefined`

```javascript
var length = 16;                               // Number
var lastName = "Johnson";                      // String
var x = {firstName:"John", lastName:"Doe"};   //object
```

## Hàm\(Function\)

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

#### Từ khóa `default`

* Từ khóa `default` định nghĩa khối code thực thi khi không có trường hợp nào khớp với giá trị của điều kiện
* Không nhất thiết phải đặt `default` cuối cùng của `switch`nhưng lúc đó phải có `break` trong khối code `default` 

## Vòng lặp\(Loop\)

Ta thường dùng vòng lặp nếu cần thực thi khối code lại nhiều lần nhưng chỉ khác thông số đầu vào.

Trong JS ta có các kiểu lặp phổ biến sau:

* `for` -  lặp lại một khối code với số lần lặp xác định trước
* `for/in` - lặp qua các thuộc tính\(properties\) của 1 đối tượng\(object\)
* `for/of` - lặp qua các giá trị của đối tượng có thể lặp lại
* `while` - lặp qua một khối code khi điều kiện bằng `true`
* `do/while` - lặp qua một khối code khi điều kiện bằng `true`

### Vòng lặp for

```javascript
for (statement 1; statement 2; statement 3) {
  // code block to be executed
}
```

**Statement 1** được thực thi \(1 lần\) trước khi thực thi khối code

**Statement 2** định nghĩa điều kiện cho việc thực thi khối code

**Statement 3** được thực thi\(mỗi lần\) sau khi khối code được thực hiện xong

Ví dụ:

```javascript
for (i = 0; i < 5; i++) {
  text += "The number is " + i + "<br>";
}
//The number is 0
//The number is 1
//The number is 2
//The number is 3
//The number is 4
```

### Vòng lặp for/in

#### For/in các thuộc tính của Object

```javascript
for (key in object) {
  // code block to be executed
}
```

Ví dụ:

```javascript
var person = {fname:"John", lname:"Doe", age:25};

var text = "";
var x;
for (x in person) {
  text += person[x];
}
//John Doe 25
```

#### For/in các phần tử của mảng

```javascript
for (variable in array) {
  code
}
```

Ví dụ:

```javascript
var txt = "";
var numbers = [45, 4, 9, 16, 25];
var x;
for (x in numbers) {
  txt += numbers[x] +  " "; 
}
console.log(txt)
//45 4 9 16 25 
```

> Lưu ý không sử dụng for/in nếu quan tâm đến thứ tự duyệt phần tử, nếu index duyệt mảng quan trọng hãy sử dụng forEach để thay thế

#### forEach trong mảng

Dùng forEach để duyệt các phần tử trong mảng 1 lần

```javascript
var txt = "";
var numbers = [45, 4, 9, 16, 25];
var x;
numbers.forEach(function(item) {
  txt += item +  " "; 
})
console.log(txt)
//45 4 9 16 25 
```

### Vòng lặp for/of 

Vòng lăp for/of có thể duyệt qua các phần tử của một đối tượng có thể lặp lại như Arrays, Strings, Maps, NodeLists, vân vân

```javascript
for (variable of iterable) {
  // code block to be executed
}
```

Ví dụ:

```javascript
let language = "JavaScript";
let text = "";

for (let x of language) {
  text += x + "-";
}
console.log(text);
//J-a-v-a-S-c-r-i-p-t-
```

### Vòng lặp while

```javascript
while (condition) {
  // code block to be executed
}
```

Ví dụ:

```javascript
var i = 0;
while (i < 5) {
    console.log("The number is " + i);
  i++;
}
//The number is 0
//The number is 1
//The number is 2
//The number is 3
//The number is 4
```

### Vòng lặp do/while

Vòng lặp `do/while` là một biến thể của lặp `while` vòng lặp sẽ thực thi khối code 1 lần trước khi check điều kiện là `true`, và sẽ lặp lại trong khi điều kiện là `true`

```javascript
do {
  // code block to be executed
}
while (condition);
```

Ví dụ:

```javascript
var i = 0;

do {
  console.log("The number is " + i);
  i++;
}
while (i < 5);  
//The number is 0
//The number is 1
//The number is 2
//The number is 3
//The number is 4
```

### Xử lý lỗi try/catch/throw/finally

Mệnh đề `try` sẽ cố thực thi để tìm ra lỗi trong khối code

Mệnh đề `catch` sẽ giúp xử lý lỗi

Mệnh đề `throw` giúp tùy chỉnh lỗi 

Mệnh đề `finally` giúp thực thi code sau khi try và catch bất kể kết quả là gì

```javascript
try {
 // Block of code to try
}
catch(err) {
//  Block of code to handle errors
}
finally {
  //Block of code to be executed regardless of the try / catch result
}
```

Ví dụ:

```markup
<!DOCTYPE html>
<html>
<body>

<p>Please input a number between 5 and 10:</p>

<input id="demo" type="text">
<button type="button" onclick="myFunction()">Test Input</button>

<p id="p01"></p>

<script>
function myFunction() {
  var message, x;
  message = document.getElementById("p01");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try { 
    if(x == "")  throw "is empty";
    if(isNaN(x)) throw "is not a number";
    x = Number(x);
    if(x > 10)   throw "is too high";
    if(x < 5)  throw "is too low";
  }
  catch(err) {
    message.innerHTML = "Input " + err;
  }
  finally {
    document.getElementById("demo").value = "";
  }
}
</script>

</body>
</html>

```

[chi tiết chạy](https://www.w3schools.com/js/tryit.asp?filename=tryjs_finally_error)















