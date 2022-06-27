---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu về thuộc tính id trong HTML, cách khai báo
  và các cách sử dụng của id
---

# Id trong HTML

## Tổng quan

`id` là **thuộc tính của HTML** được sử dụng để **định nghĩa một mã id duy nhất** cho **một phần tử** **HTML**

**Không thể** định nghĩa **hai phần tử HTML** có **cùng id** trong **một văn bản HTML**

## Cách khai báo

Thuộc tính `id` được **khai báo** trong **thẻ bắt đầu** của phần tử HTML

```markup
<div id="demo">Hello world!</div>
```

`id` thường được sử dụng để **xác định** **phần tử HTML** cần chọn

{% hint style="info" %}
khai báo tên `id` có **phân biệt hoa thường**
{% endhint %}

{% hint style="info" %}
tên `id` phải có **ít nhất một ký tự**, **không thể bắt đầu bằng số** và **không chứa khoảng trắng** như là tab, khoảng trắng, vv
{% endhint %}

## Sử dụng id để định danh thẻ trong CSS

Thuộc tính `id` có thể được sử dụng để **định danh** phần tử bạn muốn **chỉnh sửa cách thể hiện**.

### Cú pháp

```css
#id {
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
      #myHeader {
        background-color: lightblue;
        color: black;
        padding: 40px;
        text-align: center;
      }
    </style>
  </head>
  <body>
  
    <h1 id="myHeader">My Header</h1>
    <h1>Another Header</h1>
  
  </body>
</html>
```

Trong ví dụ này chúng ta có 2 thẻ `h1` nhưng chỉ có thẻ `h1` có gán `id` **myHeader** thì mới được áp dụng khai báo CSS

## Đánh dấu (bookmark) HTML bằng id và link

Đánh dấu HTML cho phép người dùng **di chuyển** đến **1 phần chỉ định** của trang. Điều này rất tiện lợi cho người dùng trong trường hợp trang có nội dung dài.

### Quy trình thực hiện:

#### Đánh dấu vị trí cần di chuyển đến bằng thuộc tính id

```markup
<h2 id="C4">Chapter 4</h2>
```

#### Tạo 1 đường link để dẫn đến vị trí đã được bookmark

* Nếu trong cùng trang ta có thể chỉ cần chỉ định bookmark bằng cú pháp: **# + id**

```markup
<a href="#C4">Jump to Chapter 4</a>
```

* Trong trường hợp khác trang ta phải chỉ định cả đường dẫn bằng cú pháp: **url + # + id**

```markup
<a href="index.html#C4">Jump to Chapter 4</a>
```

{% hint style="info" %}
Khi click vào link ta sẽ thấy trang mới mở sẽ được nhảy xuống đúng vị trí của phần tử chứa `id`
{% endhint %}

## Sử dụng JavaScript với id

Thuộc tính `id` có thể được dùng để định danh một phần tử HTML để thực thi một số tác vụ trên phần tử này.

JavaScript có thể truy xuất đến phần tử thông qua `id` bằng cú pháp sau:

```javascript
document.getElementById(id)
```

**trong đó:**

* `document.getElementById()` là hàm dùng để **truy xuất phần tử qua id**
* `id` là `id` của **phần tử cần truy xuất**

### Ví dụ

```markup
<script>
    document.getElementById("myHeader").innerHTML = "Have a nice day!";
</script>
```

Trong ví dụ này chúng ta sẽ thay đổi nội dung của phần tử có `id` la **myHeader** sang nội dung mới.

## Tổng kết

* Thuộc tính `id` được sử dụng để **định nghĩa** một mã `id` cho phần tử HTML
* `id` **phân biệt hoa thường**, **không được bắt đầu bằng số** và **chứa khoảng trắng**
* Trong một văn bản **không được có 2 phần tử khai báo cùng id** do giá trị của **id là duy nhất**
* `id` được sử dụng bởi **CSS** để **tuỳ chỉnh hiển thị phần tử**
* `id` cũng được **sử dụng để làm bookmark** cho nội dung trang
* **JS** có thể chọn phần tử HTML bằng hàm `document.getElementById()`
