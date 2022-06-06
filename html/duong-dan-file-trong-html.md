---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu về đường dẫn trong HTML và cách sử dụng
  chúng
---

# Đường dẫn file trong HTML

## Đường dẫn file là gì?

1. Đường dẫn trong HTML dùng để mô tả/trỏ đến vị trí của file trong cấu trúc web.&#x20;
2. Một số loại file mà đường dẫn hay trỏ đến:
   * Trang web
   * Hình ảnh
   * File CSS/JS
   * ...
3. Thường có 2 dạng đường dẫn là đường dẫn tương đối và đường dẫn tuyệt đối

## Đường dẫn tuyệt đối(Absolute path)

Đường dẫn tuyệt đối là một URL đầy đủ của file&#x20;

```markup
<img src="https://www.w3schools.com/images/picture.jpg" alt="Mountain">
```

{% hint style="info" %}
Đường dẫn tuyệt đối có một tính năng quan trọng là cho phép chúng ta lấy file ở cả những website khác.
{% endhint %}

## Đường dẫn tương đối(Relative path)

Đường dẫn tương đối mô tả vị trí của file đích bằng cách chỉ ra mối liên hệ của nó so với file hiện tại. &#x20;

Cụ thể như sau:

#### File đích nằm trong thư mục root của website hiện tại

```markup
<img src="/images/picture.jpg" alt="Mountain">
```

#### File đích nằm trong thư mục mà thư mục đó  nằm cùng thư mục với file hiện tại

```markup
<img src="images/picture.jpg" alt="Mountain">
```

#### File đích nằm trong thư mục cha chứa file hiện tại

```markup
<img src="../images/picture.jpg" alt="Mountain">
```

{% hint style="info" %}
Đường dẫn tương đối thường được sử dụng vì:&#x20;

* Cách viết đôi khi ngắn hơn so với cách viết đường dẫn tuyệt đối
* Tạo ra các trang web động hơn vì không phải hardcode domain của trang web
{% endhint %}
