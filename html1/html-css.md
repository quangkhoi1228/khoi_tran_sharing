---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu CSS là gì? Cách khai báo luật CSS và làm
  bài tập thực hành với CSS
---

# HTML CSS

## CSS là gì?

* **CSS** viết tắt của **Cascading Style Sheets**
* CSS **miêu tả phần tử HTML** được hiển thị như thế nào trên màn hình
* CSS giúp **tiết kiệm công sức** bởi vì có thể **kiểm soát bố cục** của **nhiều trang web** chỉ cần một lần thao tác
* Danh sách các style có thể được **lưu trong nhiều file CSS**

{% hint style="info" %}
Trong bài này chỉ sử mang mục đích giới thiệu khái quát về CSS. Để tìm hiểu kĩ hơn phần này các bạn vui lòng tham khảo tại phần CSS [tại đây](../css/)
{% endhint %}

## Cách viết các luật CSS (CSS rule)

**Một luật CSS** bao gồm **selector** và **một khối khai báo**

![](../../.gitbook/assets/2.png)

* **Selector** chỉ ra **phần tử HTML muốn chỉnh style**
* **Khối khai báo** chứa **một hoặc nhiều khai báo** cách nhau bởi **dấu chấm phẩy(;)**
* **Mỗi khai báo** bao gồm **một thuộc tính** CSS và **một giá trị** cách nhau bởi **dấu hai chấm(:)**
* Những **định nghĩa Css** được cách nhau bởi **dấu chấm phẩy**, và các khối định nghĩa được bao quanh bởi **dấu ngoặc nhọn({})**

## Cách sử dụng CSS

{% hint style="info" %}
Có nhiều cách để sử dụng CSS trong trang. Trong bài này sử dụng Css nội bộ(Internal CSS)
{% endhint %}

Tại thẻ `head` của trang chúng ta tạo thẻ `style` để chứa các khai báo CSS của trang như sau:

```markup
<!DOCTYPE html>
<html>
    <head>
        <style>
            body {background-color: powderblue;}
            h1   {color: blue;}
            p    {color: red;}
        </style>
    </head>
    <body>
    
        <h1>This is a heading</h1>
        <p>This is a paragraph.</p>
    
    </body>
</html>
```

Kết quả:&#x20;

![Kết quả](<../../.gitbook/assets/image (66) (1).png>)

