---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu về CSS Selector là gì? Cách khai báo và sử
  dụng CSS Selector
---

# CSS Selector

## CSS selector là gì?

**CSS selector** là **phần đầu tiên trong cú pháp khai báo luật CSS**, sử dụng để **chọn ra danh sách một hoặc nhiều phần tử muốn áp dụng luật CSS**.

{% hint style="info" %}
Xem thêm phần cách khai báo luật CSS [tại đây](gioi-thieu-css.md#cu-phap-css)
{% endhint %}

Chúng ta có thể chia CSS selector thành 5 loại chính:

* **Simple selectors**: chọn phần tử dựa trên tên thẻ, id, class
* **Combinator selectors**: chọn phần tử dựa vào mối quan hệ giữa các phần tử với nhau
* **Pseudo-class selectors**: chọn phần tử dựa trên trạng thái
* **Pseudo-elements selectors**: chọn và style các phần tử giả của phần tử gốc
* **Attribute selectors**: chọn phần tử dựa trên thuộc tính HTML

## Cách khai báo selector

* `.class1` : chọn tất cả phần tử chứa `class1`
* `.class1.class2` : chọn tất cả phần tử chứa cả `class1` và `class2`
* `.class1 .class2` : chọn tất cả phần tử chứa `class2` và phần tử đó nằm trong phần tử chứa `class1`
* `#id1` : chọn phần tử đầu tiên chứa `id1`
* `*` : chọn tất cả phần tử
* `p`: chọn tất cả phần tử thẻ `p`
* `.class1,.class2` : chọn tất cả phần tử chứa `class1` và tất cả phần tử chứa `class2`
* `.class1 > .class2` : chọn phần tử chứa `class2` đầu tiên và phần tử đó nằm trong `class1`
* `.class1:hover` : css xảy ra khi phần tử chứa `class1` **được rê chuột vào**
* `img[alt]` : chọn tất cả các thẻ `img` chứa thuộc tính `alt`

Xem thêm: [https://www.w3schools.com/cssref/css\_selectors.asp](https://www.w3schools.com/cssref/css\_selectors.asp)

## Thứ tự ưu tiên của selector

{% hint style="info" %}
Trong trường hợp 1 phần tử HTML bị ảnh hưởng bởi nhiều khai báo CSS thì khai báo CSS nào khai báo rõ ràng hơn sẽ được áp dụng
{% endhint %}

Ví dụ:

```markup
<!DOCTYPE html>
<html>
  <head>
    <style>
      h2 {
        color: red; /* Set text color to red */
      }
      
      div h2 {
        color: blue;
      }
      
    </style>
  </head>
  <body>
    <div>
      <h2>My Heading</h2>
    </div>
    <!-- These paragraphs will be red -->
    <p>Hello World!</p>
    <p>This paragraph is styled with CSS.</p>
    <p>CSS comments are not shown in the output.</p>
  
  </body>
</html>
```

Thẻ `<h2>` sẽ có màu `blue` vì khai báo rõ ràng hơn
