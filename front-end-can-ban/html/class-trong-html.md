---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu về thuộc tính class trong HTML, cách khai
  báo và các cách sử dụng của class
---

# Class trong HTML

## Tổng quan

`class` là một thuộc tính của HTML được sử dụng để **định nghĩa một lớp(class)** cho phần tử HTML&#x20;

**Nhiều phần tử HTML** có thể **có chung class với nhau**

Thuộc tính `class` thường được dùng để **trỏ đến một khai báo CSS** của class hoặc **JS có thể truy xuất nhiều phần tử HTML** có **chứa cùng class**.&#x20;

## Cách khai báo

Thuộc tính `class` được **khai báo** trong **thẻ bắt đầu** của phần tử HTML

```markup
<div class="demo">Hello world!</div>
```

{% hint style="info" %}
Khai báo tên **class** có **phân biệt hoa thường**
{% endhint %}

{% hint style="info" %}
`class` có thể sử dụng cho mọi phần tử HTML
{% endhint %}

## Sử dụng class để định danh thẻ trong CSS

`class` có thể được sử dụng để **định danh** các phần tử bạn muốn **chỉnh sửa cách thể hiện**.

### Cú pháp

Chúng ta sử dụng dấu chấm **. + tên class** để **xác định** các phần tử bị **ảnh hưởng bởi class**&#x20;

Các cặp thuộc tính CSS sẽ được **đặt trong dấu {}** và để **kế sau cú pháp khai báo class**&#x20;

```css
.class-name {
    property1: value1;
    property2: value2;
}
```

### Ví dụ

```markup
<!DOCTYPE html>
<html>
  <head>
    <style>
      .city {
        background-color: tomato;
        color: white;
        border: 2px solid black;
        margin: 20px;
        padding: 20px;
      }
    </style>
  </head>
  <body>
  
    <div class="city">
      <h2>London</h2>
      <p>London is the capital of England.</p>
    </div>
    
    <div class="city">
      <h2>Paris</h2>
      <p>Paris is the capital of France.</p>
    </div>
    
    <div class="city">
      <h2>Tokyo</h2>
      <p>Tokyo is the capital of Japan.</p>
    </div>
    
    <div class="city">
      <h2>Tokyo</h2>
      <p>Tokyo is the capital of Japan.</p>
    </div>
  
  </body>
</html>
```

Trong ví dụ này chúng ta có 4 thẻ `div` nhưng chỉ có thẻ `div` có gán `class` **city** thì mới được áp dụng khai báo CSS

## Khai báo nhiều class trong một phần tử

Phần tử có thể **chứa nhiều** `class` khác nhau trong giá trị của thuộc tính `class`

Để định nghĩa nhiều `class` chúng ta sẽ **ngăn cách** tên các `class` trong giá trị của thuộc tính class **bằng khoảng cách**

```markup
<h2 class="city main">London</h2>
<h2 class="city">Paris</h2>
<h2 class="city">Tokyo</h2>
```

Phần tử chứa **nhiều `class`** sẽ bị **ảnh hưởng bởi các `class`** đó

## Khai báo cùng class trên các phần tử khác nhau

Các **phần tử HTML khác nhau** có thể **khai báo cùng `class`**

```markup
<h2 class="city">Paris</h2>
<p class="city">Paris is the capital of France</p>
```

Trong ví dụ này chúng ta có 2 thẻ `<h2>` và `<p>` khác nhau nhưng chúng có thể **thêm cùng class** là `city` và có **cùng cách thể hiện**.

## Sử dụng class trong JavaScript

**JavaScript** **sử dụng class** như một cách để **xác định các phần tử trong trang** và thực hiện các thao tác lên chúng.

```markup
<script>
  var x = document.getElementsByClassName("city");
  for (var i = 0; i < x.length; i++) {
    x[i].style.display = "none";
  }
</script>
```

trong ví dụ này chúng ta sẽ lấy ra các phần tử có `class` là **city** sau đó ẩn các phần tử này đi.

## Tổng kết

* Thuộc tính `class` được sử dụng để **định nghĩa** một hay nhiều class cho phần tử HTML
* `class` được **CSS** sử dụng để **áp dụng style cho nhiều phần tử**&#x20;
* `class` được **JS** sử dụng để **chọn ra các phần tử** thông qua hàm `document.getElementsByClassName(className)`
* `class` có thể được sử dụng **cho mọi phần tử**
* `class` **phân biệt hoa thường**
* **Nhiều phần tử khác nhau** có thể **dùng chung một class**
