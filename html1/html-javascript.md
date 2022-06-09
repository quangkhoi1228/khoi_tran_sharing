---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu sơ về JavaScript trong HTML, các thêm và sử
  dụng của JavaScript
---

# HTML JavaScript

{% hint style="info" %}
Trong bài này chỉ sử mang mục đích giới thiệu khái quát về **JavaScript**. Để tìm hiểu kĩ hơn phần này các bạn vui lòng tham khảo tại phần JS tại đây
{% endhint %}

## JavaScript là gì?

**JavaScript(JS)** là một ngôn ngữ lập trình cho phép chúng ta **thêm các chức năng phức tạp** lên trang web giúp cho việc **xử lý các tương tác của người dùng** dễ dàng và **làm cho trang web trở nên động** hơn.

Ngày trước JS **chỉ được sử dụng cho phía giao diện người dùng** (client side). Nhưng từ khi **NodeJS ra đời**, thì JS cũng được sử dụng như **một ngôn ngữ code phía máy chủ** (server side). Từ đó kỷ nguyên thống trị của JavaScript bắt đầu và cho đến hiện tại JS vẫn luôn là một ngôn ngữ **chưa có đối thủ** nào soán ngôi.

## Cách thêm JS vào trang web

{% hint style="info" %}
Có nhiều cách để sử dụng JS trong trang. Trong bài này sử dụng JS nội bộ(Internal JS)
{% endhint %}

### Thẻ \<script> trong HTML

Thẻ `<script>` trong HTML được sử dụng để **định nghĩa một đoạn mã JS** trong trang. Nó có thể **chứa các đoạn code JS** hoặc **trỏ đến 1 file JS** qua thuộc tính `src`.

```markup
<script>
    document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>
```

```markup
<script src="script.js" />
```

## Ví dụ

```markup
<button id="demo">Hello World!!!</button>
```

Trong ví dụ trên chúng ta có một thẻ `button` chứa cụm từ _hello world!!!_.

**Kết quả:**

\*\*\*\*![](<../.gitbook/assets/image (62).png>)

Giả sử chúng ta muốn chữ trong nút chuyển thành _Hello JavaScript!_ thì chúng ta thêm đoạn code vào như sau:

```markup
<script>
    document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>
```

**Trong đó:**

* Thẻ `<script>` định nghĩa ra các đoạn code JS được thực thi trong trang
* Để chọn một phần tử HTML chúng ta thường dùng `document.getElementById` để chọn phần tử theo thuộc tính `id` của phần tử
* Để thay đổi nội dung của thẻ được chọn chúng ta sử dụng hàm `innerHTML = nội dung mới`

![](<../.gitbook/assets/image (55).png>)

**Full code:**

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <button id="demo">Hello World!!!</button>
    <script>
        document.getElementById("demo").innerHTML = "Hello JavaScript!";
    </script>
</body>

</html>
```

## Một số chức năng mà JS có thể làm khác

```javascript
document.getElementById("demo").style.fontSize = "25px";
document.getElementById("demo").style.color = "red";
document.getElementById("demo").style.backgroundColor = "yellow";
```

## Thẻ \<noscript> trong HTML

Thẻ `<noscript>` là thẻ **quy định một nội dung thay thế** khi **người dùng tắt JS** trên trình duyệt hoặc **trình duyệt web không hỗ trợ JS**

```markup
<script>
    document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>
<noscript>Sorry, your browser does not support JavaScript!</noscript>
```
