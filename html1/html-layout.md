---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu về HTML layout, các cách để thực hiện HTML
  layout và cách sử dụng chúng.
---

# HTML Layout

## HTML Layout <a href="#html-layout" id="html-layout"></a>

HTML layout là một thuật ngữ nói về việc bố cục các phần tử HTML được sắp xếp trong trang. Trong  trang web thường hiển thị nội dung theo nhiều phần và mỗi phần có nhiều cột‌.&#x20;

Ví dụ về trang youtube được bố trí theo hàng và cột

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GlAbXJ8w3E\_D9G%2F4.png?alt=media)

## Phần tử HTML layout <a href="#phan-tu-html-layout" id="phan-tu-html-layout"></a>

HTML có 1 vài phần tử ngữ nghĩa dùng để định nghĩa sự khác nhau giữa các phần trong trang web

![](<../.gitbook/assets/image (2).png>)

Trong đó:

* `<header>` - định nghĩa một header cho một trang hoặc một phần
* `<nav>` - Định nghĩa một bộ các đường dẫn điều hướng
* `<section>` - định nghĩa một phần của văn bản
* `<article>` - định nghĩa một phần tử độc lập hoặc phần tử chứa nội dung
* `<aside>` - Định nghĩa nội dung nằm ngoài nội dung chính(như là một thanh bên - sidebar )
* `<footer>` - định nghĩa phần chân của trang hoặc một phần của trang
* `<details>` - định nghĩa một phần nội dung chi tiết, người dùng có thể mở hoặc đóng tùy nhu cầu
* `<summary>` - định nghĩa phần đầu của thẻ `<details>`

Có thể xem thêm các thẻ khác tại đây [HTML Semantics](https://www.w3schools.com/html/html5\_semantic\_elements.asp)



## Kỹ thuật chia Layout <a href="#ky-thuat-chia-layout" id="ky-thuat-chia-layout"></a>

Có 4 kỹ thuật chính để tạo layout có nhiều cột, mỗi cách đều có ưu và nhược điểm khác nhau:‌

* CSS framework
* CSS float property
* CSS flexbox
* CSS grid

## CSS framework

### CSS framework là gì?

CSS framework dùng để chỉ các bộ CSS được định nghĩa sẵn cung cấp các tính năng như định nghĩa các component như nút, tiêu đề, header, card,... hoặc cung cấp tính năng responsive. Chúng được đưa vào thành một hoặc nhiều file CSS - được gọi là CSS framework.

Khi sử dụng CSS framework chúng ta chỉ đơn giản là gọi ra các CSS được định nghĩa sẳn và sử dụng từ đó dẫn đến tốc độ phát triển giao diện của chúng ta sẽ tăng lên.

Ưu điểm:&#x20;

* Tốc độ phát triển nhanh hơn do các tính năng đã được viết sẵn
* Hạn chế code lặp lại&#x20;
* Các framework đã được đông đảo developer sử dụng nên hạn chế các lỗi phát sinh
* Chức năng ngày càng được phát triển nhiều hơn

Nhược điểm:

* Framework thường có kích thước lớn dẫn đến việc trang bị nặng hơn khi load
* Muốn thành thạo framework thì cần rất nhiều thời gian
* Các framework đều có quy tắc lõi nhất định do đó không thể sửa đổi

### Một số CSS framework phổ biến

Hiện nay có một số CSS framework được sử dụng phổ biến như:

* Bootstrap
* Tailwind
* Bulma
* Ant design
* ...

## CSS float layout

### Float layout là gì?

Float layout được hiểu là việc chúng ta sử dụng thuộc tính float của CSS để quy định phần tử thể hiện trên trang.&#x20;

Ưu điểm:

* Thuộc tính float rất đơn giản để học, các bạn chỉ cần nắm rõ quy tắc sử dụng thuộc tính float và clear được.&#x20;

Nhược điểm:

* khi phần tử sử dụng thuộc tính float vẫn bị ảnh hưởng bởi nội dung của thẻ do đó có thể ảnh hưởng đến sự linh hoạt của bố cục trang.

### Cách sử dụng

{% hint style="info" %}
Các bạn tham khảo thêm phần CSS float và CSS clear để hiểu rõ hơn phần này.
{% endhint %}

Thuộc tính float của CSS có nhiệm vụ dồn các phần tử được gán thuộc tính float sang bên trái hay phải dựa theo value được cấu hình là left hay right

Ví dụ:&#x20;

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<title>CSS Template</title>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
* {
  box-sizing: border-box;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* Style the header */
header {
  background-color: #666;
  padding: 30px;
  text-align: center;
  font-size: 35px;
  color: white;
}

/* Create two columns/boxes that floats next to each other */
nav {
  float: left;
  width: 30%;
  height: 300px; /* only for demonstration, should be removed */
  background: #ccc;
  padding: 20px;
}

/* Style the list inside the menu */
nav ul {
  list-style-type: none;
  padding: 0;
}

article {
  float: left;
  padding: 20px;
  width: 70%;
  background-color: #f1f1f1;
  height: 300px; /* only for demonstration, should be removed */
}

/* Clear floats after the columns */
section::after {
  content: "";
  display: table;
  clear: both;
}

/* Style the footer */
footer {
  background-color: #777;
  padding: 10px;
  text-align: center;
  color: white;
}

/* Responsive layout - makes the two columns/boxes stack on top of each other instead of next to each other, on small screens */
@media (max-width: 600px) {
  nav, article {
    width: 100%;
    height: auto;
  }
}
</style>
</head>
<body>

<h2>CSS Layout Float</h2>
<p>In this example, we have created a header, two columns/boxes and a footer. On smaller screens, the columns will stack on top of each other.</p>
<p>Resize the browser window to see the responsive effect (you will learn more about this in our next chapter - HTML Responsive.)</p>

<header>
  <h2>Cities</h2>
</header>

<section>
  <nav>
    <ul>
      <li><a href="#">London</a></li>
      <li><a href="#">Paris</a></li>
      <li><a href="#">Tokyo</a></li>
    </ul>
  </nav>
  
  <article>
    <h1>London</h1>
    <p>London is the capital city of England. It is the most populous city in the  United Kingdom, with a metropolitan area of over 13 million inhabitants.</p>
    <p>Standing on the River Thames, London has been a major settlement for two millennia, its history going back to its founding by the Romans, who named it Londinium.</p>
  </article>
</section>

<footer>
  <p>Footer</p>
</footer>

</body>
</html>
```

![](<../.gitbook/assets/image (3).png>)

Ở đây các phần \<nav> và \<article> được dồn sang trái vì có thuộc tính float: left

## CSS flexbox layout

### CSS flexbox layout là gì?

CSS flexbox layout được hiểu là chúng ta sử dụng thuộc tính CSS để có thể đoán trước được cách các phần tử thể hiện trên trang và chúng sẽ bị ảnh hưởng bởi kích thước màn hình từ đó chúng ta có thể xây dựng các trang web.&#x20;

### Cách sử dụng

{% hint style="info" %}
CSS flexbox là một phần rất lớn do đó các bạn nên tham khảo phần CSS về flexbox để hiểu rõ hơn
{% endhint %}

## CSS grid layout

### CSS grid layout là gì?

CSS grid layout là một kĩ thuật dựa trên việc chia trang web thành các hàng và cột từ đó chúng ta có thể chia bố cục cột cách rõ ràng mà không cần dùng đến thuộc tính float hay position.

### Cách sử dụng

{% hint style="info" %}
CSS grid là một phần rất lớn do đó các bạn nên tham khảo phần CSS về grid để hiểu rõ hơn
{% endhint %}
