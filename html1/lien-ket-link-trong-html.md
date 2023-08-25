---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu cách tạo liên kết trong HTML và cách sử
  dụng chúng
---

# Liên kết(link) trong HTML

## Liên kết là gì?

**Liên kết(Link) trong HTML** là các **siêu liên kết (Hyperlink)**, thường được dùng với thẻ `<a>` để **chuyển giữa các trang** khi người dùng **click vào**.

## Cú pháp

Liên kết trong HTML thường được quy định trong thuộc tính `href` của thẻ `<a>`

```markup
<a href="url">link text</a>
```

Trong đó:

* `href` là **thuộc tính HTML** của thẻ `<a>`
* `url` là **đường dẫn đích** của liên kết khi **click vào**
* **link text** là **nội dung hiển thị** trên website

{% hint style="info" %}
Khi click vào thẻ này trang sẽ chuyển sang liên kết có giá trị là `url`
{% endhint %}

## Thuộc tính target

**Mặc định** khi **click vào Link** trang sẽ chuyển cửa sổ hiện tại sang **trang đích của liên kết**. Để **thay đổi điều này** chúng ta có thể sử dụng thuộc tính target của thẻ `<a>` để làm.

Thuộc tính `target` **quy định nơi mở trang đích** của liên kết. Các giá trị có thể có như sau:

* `_self` :Mặc định, mở tại tab/cửa sổ hiện tại
* `_blank` :Mở ở tab mới
* `_parent` :Mở trang mới tại trang cha của `iframe` (chỉ hiển thị nội dung trang đích nằm trong kích thước mà thẻ `<iframe>` được đặt)
* `_top` :mở trang đích ngay tại tab hiện tại, bất kể có nằm trong thẻ `<iframe>` hay không

## Đường dẫn tương đối và tuyệt đối

{% hint style="info" %}
Xem thêm tại phần [Đường dẫn file trong HTML](../huong-dan-khac/duong-dan-file-trong-html.md)
{% endhint %}

## Gửi email bằng link

Để mở cửa sổ gửi mail của một ứng dụng chúng ta sử dụng thuộc tính `mailto:` trong thuộc tính `href`

```markup
<a href="mailto:someone@example.com">Send email</a>
```

## Gọi điện bằng link

Chúng ta có thể gọi đến một số nếu có chức năng đó trên thiết bị bằng cách sử dụng `tel:` trong `href`

```markup
<a href="tel:09987655433">Send email</a>
```

## Tạo Link bằng JS

Chúng ta có thể tạo một Link cho một HTML element bất kỳ bằng cách thêm sự kiện `onclick` và hàm `window.location.href="url"`

```markup
<button onclick="window.location.href='https://google.com'">
    HTML Tutorial
</button>
```

Trong đó:

* `onclick` là thuộc tính của HTML, có thể thêm vào bất kỳ HTML element nào
* `window.location.href` là hàm JS dùng để chuyển trang đến giá trị `url` truyền vào
