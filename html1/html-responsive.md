# HTML Responsive

## HTML Responsive <a href="#html-responsive" id="html-responsive"></a>

Responsive web design nói về việc tạo một trang web nhìn ổn trên mọi thiết bị‌

Một trang web thiết kế responsive sẽ tự động điều chỉnh cho các màn hình hay các khung nhìn khác nhau.‌

trang web thiết kế responsive sử dụng HTML và CSS để tự động chỉnh kích thước, ẩn, co lại hoặc phóng to các phần tử trong trang để trang web nhìn ổn trên tất cả thiết bị(máy tính, máy tính bảng hoặc điện thoại)

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GnKec9asHVp9\_G%2F6.jpeg?alt=media)

## Responsive Web Design‌

### Set viewport - Khung nhìn <a href="#set-viewport-khung-nhin" id="set-viewport-khung-nhin"></a>

```markup
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Thẻ meta sẽ đặt giá trị viewport cho trang, nó sẽ hướng dẫn trình duyệt cách kiểm soát chiều và việc điều chỉnh việc co/dãn của trang‌

Ví dụ:‌

Không có set viewport

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GoDS7aeCfm1ODR%2F7.png?alt=media)‌

Có set viewport

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GpbNkQnx4VCIh5%2F8.png?alt=media)‌

### Các đơn vị <a href="#cac-don-vi" id="cac-don-vi"></a>

Cách code responsive đơn giản nhất là code theo các đơn vị tương đối:‌

* % theo phần trăm
* rem : bằng kích thước font-size của thẻ html
* em : bằng kích thước thẻ cha của phần tử
* vw : viewport width theo kích cỡ width viewport
* vh: viewport height theo kích cỡ height viewport

Các đơn vị tuyệt đối:‌

* px: bằng 1 điểm ảnh pixel màn hình
* pt: bằng 1 point: 1inch = 72 point

### Media Queries <a href="#media-queries" id="media-queries"></a>

Một cách chặt chẽ và chi tiết hơn là sử dụng media query để code css theo từng width cụ thể:

```markup
‌<style>
    .left,
    .right {
        float: left;
        width: 20%;
        /* The width is 20%, by default */
    }

    ​ .main {
        float: left;
        width: 60%;
        /* The width is 60%, by default */
    }

    ​

    /* Use a media query to add a breakpoint at 800px: */
    @media screen and (max-width: 800px) {

        ​ .left,
        .main,
        .right {
            width: 100%;
            /* The width is 100%, when the viewport is 800px or smaller */
        }
    }
</style>
```

Các thư viện dùng để responsive: Bulma, Bootstrap, Tailwind,...‌
