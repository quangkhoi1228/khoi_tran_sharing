---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu về HTML responsive và cách code website
  responsive
---

# HTML Responsive

## Responsive Web Design‌

Responsive web design nói về việc tạo một trang web nhìn ổn trên mọi thiết bị‌ được hiểu là trang web sẽ tự động điều chỉnh so cho trên các màn hình có kích thước khác nhau đều có thể hiển thị tốt cho người dùng.‌

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GnKec9asHVp9\_G%2F6.jpeg?alt=media)

{% hint style="info" %}
Trong bài này chỉ nếu khái niệm cơ bản về Responsive web design để hiểu rõ hơn các bạn vui lòng tham khảo mục CSS
{% endhint %}

## Set viewport - Khung nhìn <a href="#set-viewport-khung-nhin" id="set-viewport-khung-nhin"></a>

```markup
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Việc đầu tiên chúng ta cần làm khi muốn thiết kế web có responsive là phải thêm một thẻ \<meta> để quy định kích thước của viewport chúng ta sẽ như thế nào so với kích thước hiện tại của thiết bị.

Nó sẽ hướng dẫn trình duyệt cách kiểm soát chiều và việc điều chỉnh việc co/dãn của trang‌

Ví dụ:‌

**Không có set viewport**

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GoDS7aeCfm1ODR%2F7.png?alt=media)‌

**Có set viewport**

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GpbNkQnx4VCIh5%2F8.png?alt=media)‌

## Các đơn vị <a href="#cac-don-vi" id="cac-don-vi"></a>

### Các đơn vị tương đối:‌

* % theo phần trăm
* rem : bằng kích thước font-size của thẻ html
* em : bằng kích thước thẻ cha của phần tử
* vw : viewport width theo kích cỡ width viewport
* vh: viewport height theo kích cỡ height viewport

### Các đơn vị tuyệt đối:‌

* px: bằng 1 điểm ảnh pixel màn hình
* pt: bằng 1 point: 1inch = 72 point

{% hint style="info" %}
Cách code responsive đơn giản nhất là code theo đơn vị tương đối
{% endhint %}
