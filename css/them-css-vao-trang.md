# Thêm CSS vào trang

## Tổng quan

CSS được tạo ra để hỗ trợ HTML do đó khi trình duyệt đọc đến phần khai báo CSS, trình duyệt sẽ format lại cách thể hiện của trang dựa vào phần CSS đó.&#x20;

Có 3 cách để thêm CSS vào trang cụ thể như sau:

## Inline CSS (thêm trực tiếp vào thẻ)

Inline CSS là cách khai báo CSS giống cách khai báo giá trị của thuộc tính style của HTML

{% hint style="info" %}
các bạn có thể tham khảo thêm [tại đây](../html1/html-css.md)
{% endhint %}

Inline CSS được sử dụng để thêm CSS cho một thẻ HTML  bằng cách thêm thuộc tính style cho thẻ đó và giá trị chính là các cặp `property: value` ngăn cách bởi dấu chấm phẩy (;) thể hiện CSS muốn thêm.

```markup
<!DOCTYPE html>
<html>
    <body>
    
        <h1 style="color:blue;text-align:center;">This is a heading</h1>
        <p style="color:red;">This is a paragraph.</p>
    
    </body>
</html>
```

## Internal CSS(CSS nội bộ)

Internal CSS(CSS nội bộ) được sử dụng để thêm CSS vào một trang cụ thể. Tất cả các khai báo CSS được đặt trong thẻ \<style> và thẻ \<style> này được đặt trong thẻ \<head> của trang.

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
