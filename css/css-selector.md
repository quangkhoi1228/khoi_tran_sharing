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

