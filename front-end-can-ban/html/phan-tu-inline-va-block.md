---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu phần tử Inline và Block là gì? Sự khác nhau
  của chúng và một số thẻ của mỗi loại
---

# Phần tử Inline và Block

## Thuộc tính display

Thuộc tính `display` là **một thuộc tính của CSS quy định cách mà phần tử đó thể hiện trên giao diện** như thế nào.

Thuộc tính `display` là một thuộc tính quan trọng của CSS **giúp cho việc phân bổ bố cục trang web một cách dễ dàng hơn**

## Tổng quan

* Mỗi phần tử HTML đều có giá trị của thuộc tính `display` mặc định **tuỳ vào loại phần tử đó là** gì?&#x20;
* Có 2 giá trị mặc định hiện tại là: `Block` và `Inline`

## Phần tử Block

Phần tử `Block` luôn luôn **bắt đầu 1 dòng mới**, và trình duyệt sẽ tự động thêm 1 số khoảng cách vào trước và sau phần tử.

Phần tử `Block` luôn luôn **chiếm hết chiều dài khả dụng** tức là chúng sẽ cố gắng kéo dài sang trái và phải nhiều nhất có thể.

Hai phần tử phổ biến nhất là `<p>` and `<div>`

![](<../../.gitbook/assets/image (69).png>)

```markup
<p>Hello World</p>
<div>Hello World</div>
```

&#x20;Một số phần tử Block khác:

![Các thẻ HTML Block](<../../.gitbook/assets/image (68) (1).png>)

## Phần tử Inline

Phần tử `Inline` **không tạo dòng mới** và chỉ lấy số lượng **chiều dài(width) tối thiểu** mà chúng cần.

Thẻ `Inline` hay gặp là thẻ `<span>`

![](<../../.gitbook/assets/image (58) (1).png>)

```markup
<span>Hello World</span>
```

Đây là 1 số thẻ Inline:

![](<../../.gitbook/assets/image (52).png>)

{% hint style="info" %}
Lưu ý: Phần tử `Inline` không thể chứa phần tử `Block`
{% endhint %}

