---
description: Trong trang này chúng ta sẽ tìm hiểu về các cách thêm CSS vào trang.
---

# Thêm CSS vào trang

## Tổng quan

CSS được tạo ra để hỗ trợ HTML do đó khi trình duyệt đọc đến phần khai báo CSS, trình duyệt sẽ format lại cách thể hiện của trang dựa vào phần CSS đó.&#x20;

**Có 3 cách để thêm CSS vào trang cụ thể như sau:**

## Inline CSS (thêm trực tiếp vào thẻ)

**Inline CSS** là cách khai báo CSS **giống cách khai báo giá trị của thuộc tính style của HTML**

{% hint style="info" %}
các bạn có thể tham khảo thêm [tại đây](../html1/html-css.md)
{% endhint %}

**Inline CSS** được sử dụng để thêm CSS cho một thẻ HTML  bằng cách **thêm thuộc tính style cho thẻ** đó và **giá trị chính là các cặp** `property: value` **ngăn cách bởi dấu chấm phẩy (;)** thể hiện CSS muốn thêm.

```markup
<!DOCTYPE html>
<html>
    <body>
    
        <h1 style="color:blue;text-align:center;">This is a heading</h1>
        <p style="color:red;">This is a paragraph.</p>
    
    </body>
</html>
```

![](<../.gitbook/assets/image (32).png>)

## Internal CSS(CSS nội bộ)

**Internal CSS(CSS nội bộ)** được sử dụng để thêm CSS vào một trang cụ thể. Tất cả các khai báo CSS được đặt trong thẻ `<style>` và thẻ `<style>` này được đặt trong thẻ `<head>` của trang.

```markup
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-color: linen;
    }
    
    h1 {
      color: maroon;
      margin-left: 40px;
    }
  </style>
</head>
<body>

  <h1>This is a heading</h1>
  <p>This is a paragraph.</p>
  
</body>
</html>
```

![](<../.gitbook/assets/image (20) (1).png>)

## External CSS(Thêm file .css)

**External CSS** được hiểu là chúng ta sẽ tạo các file `.css` chứa các khai báo CSS sau đó import các file này vào trang cần áp dụng. Điều này cho phép chúng ta chỉ cần chỉnh sửa 1 chỗ duy nhất (file `.css`) để thay đổi ở nhiều trang.

### Cách sử dụng

Đầu tiên chúng ta phải tại file `.css` để chứa các luật CSS

file **mystyle.css**

```css
body {
  background-color: lightblue;
}

h1 {
  color: navy;
  margin-left: 20px;
}
```

Để thêm file `.css` vào trang chúng ta sẽ sử dụng thẻ `<link>` và đặt thẻ này vào thẻ `<head>` của trang

```markup
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="mystyle.css">
    </head>
    <body>
    
        <h1>This is a heading</h1>
        <p>This is a paragraph.</p>
        
    </body>
</html>
```

![](<../.gitbook/assets/image (20).png>)

## Lưu ý thứ tự khai báo

### Khái niệm

Thứ tự khai báo của của **Internal CSS** và **External CSS** khá quan trọng trong việc CSS nào sẽ được khai báo.

{% hint style="info" %}
Trong trang nếu CSS của **Internal CSS/External CSS** nào **được khai báo sau** thì khai báo đó được áp dụng trong trang
{% endhint %}

### Ví dụ

file: **mystyle.css**

```css
h1 {
  color: navy;
}
```

**Internal CSS**

```css
h1 {
  color: orange;   
}
```

#### Internal CSS khai báo sau External CSS

```markup
<head>
  <link rel="stylesheet" type="text/css" href="mystyle.css">
  <style>
    h1 {
      color: orange;
    }
  </style>
</head>
```

Kết quả là `<h1>` có màu `orange`

![](<../.gitbook/assets/image (3).png>)

#### External CSS khai báo sau Internal CSS

```markup
<head>
  <style>
    h1 {
      color: orange;
    }
  </style>
  <link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```



Kết quả là `<h1>` có màu `navy`

![](<../.gitbook/assets/image (34).png>)

## Thứ tự ưu tiên

Trong trường hợp trang có nhiều cách khai báo CSS cho cùng một `selector` trong trang thì thứ tự ưu tiên sẽ có quy định như sau:

1. Inline CSS
2. Internal CSS/External CSS
3. CSS mặc định của Browser

{% hint style="info" %}
**CSS inline** sẽ có độ ưu tiên cao nhất ==> **CSS Internal** hoặc **CSS external** nằm trong `<head>` ==> CSS mặc định của trình duyệt
{% endhint %}

