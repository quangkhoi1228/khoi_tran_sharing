# HTML

## HTML là gì? <a href="#html-la-gi" id="html-la-gi"></a>

* HTML là viết tắt của Hyper Text Markup Language
* HTML là ngôn ngữ đánh dấu tiêu chuẩn để tạo ra các trang Web
* HTML bao gồm một loạt các phần tử
* Các phần tử HTML cho trình duyệt biết cách hiển thị nội dung
* Các phần tử HTML gắn nhãn các phần nội dung như "đây là một tiêu đề", "đây là một đoạn văn", "đây là một liên kết", v.v.
* HTML mô tả cấu trúc của một trang Web

## Phần tử HTML(Thẻ HTML) là gì? <a href="#phan-tu-html-la-gi" id="phan-tu-html-la-gi"></a>

Phần tử HTML được xác định bởi thẻ bắt đầu, một số nội dung và thẻ kết thúc:

```markup
<tagname> Nội dung </tagname>
```

Phần tử HTML là tất cả mọi thứ từ thẻ bắt đầu đến thẻ kết thúc:

```markup
<h1> Tiêu đề </h1>
<p> Đoạn văn </p>‌
```

Lưu ý: Một số phần tử HTML không có nội dung (như phần tử `<br>`). Các phần tử này được gọi là phần tử rỗng. Các phần tử trống không có thẻ kết thúc!‌

### Các thẻ HTML căn bản <a href="#cac-the-html-can-ban" id="cac-the-html-can-ban"></a>

`<h1>` đến `<h6>`: tiêu đề‌

`<p>`: đoạn văn bản‌

`<a>`: đường dẫn‌

\*Chi tiết các thẻ: [https://htmlreference.io/](https://htmlreference.io)​‌

\*Các thẻ HTML không phân biệt hoa thường `<H1>` giống với `<h1>` nhưng khuyến khích viết chữ thường‌

## Ví dụ HTML đơn giản <a href="#vi-du-html-don-gian" id="vi-du-html-don-gian"></a>

```markup
‌<!DOCTYPE html>
<html>​

<head>
    <title>Page Title</title>
</head>​

<body>
    <h1>This is a Heading</h1>
    <p>This is a paragraph.</p>
</body>​

</html>
```

* `<!DOCTYPE html>` chỉ ra rằng tài liệu này là một tài liệu HTML5
* `<html>` là phần tử gốc của một trang HTML
* `<head>` chứa thông tin meta về trang HTML
* `<title>` chỉ định tiêu đề cho trang HTML (được hiển thị trong thanh tiêu đề của trình duyệt hoặc trong tab của trang)
* `<body>` xác định nội dung của tài liệu và là vùng chứa tất cả nội dung hiển thị, chẳng hạn như tiêu đề, đoạn văn, hình ảnh, siêu liên kết, bảng, danh sách, v.v.
* `<h1>` xác định một tiêu đề lớn
* `<p>` xác định một đoạn văn

‌

Kết quả:‌

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GhQ1ufeIzGHPLq%2F0.png?alt=media)

## Thuộc tính HTML <a href="#thuoc-tinh-html" id="thuoc-tinh-html"></a>

* Tất cả các phần tử HTML có thể có các thuộc tính
* Các thuộc tính cung cấp thông tin bổ sung về các phần tử
* Các thuộc tính luôn được chỉ định trong thẻ bắt đầu
* Các thuộc tính thường có trong các cặp tên / giá trị như: name = "value"

Ví dụ:‌

* Thuộc tính href của `<a>` quy định cụ thể các URL của trang liên kết đi vào
* Thuộc tính src của `<img>` quy định cụ thể đường dẫn đến hình ảnh sẽ được hiển thị
* Thuộc tính width và height cung cấp thông tin kích thước cho hình ảnh `<img>`
* Thuộc tính alt của `<img>` cung cấp một văn bản thay thế cho hình ảnh
* Thuộc tính style được sử dụng để thêm phong cách cho một yếu tố, chẳng hạn như màu sắc, font chữ, kích thước, và nhiều hơn nữa
* Thuộc tính lang của `<html>` tuyên bố ngôn ngữ của trang web

\*Chi tiết: [https://www.w3schools.com/tags/ref\_attributes.asp](https://www.w3schools.com/tags/ref\_attributes.asp)​‌

### HTML styles <a href="#html-styles" id="html-styles"></a>

Style là thuộc tính HTML được sử dụng để thêm kiểu vào một phần tử, chẳng hạn như màu sắc, phông chữ, kích thước, v.v.‌

Cú pháp:

```markup
 <tagname style="property:value;">
```

Property là 1 CSS property‌

Value là 1 Css value‌

Ví dụ:

```markup
<h1 style="background-color:powderblue;">This is a heading</h1>
<p style="background-color:tomato;">This is a paragraph.</p>
```

‌

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GimvGV1q5eQaXL%2F1.png?alt=media)

### HTML CSS <a href="#html-css" id="html-css"></a>

* CSS là viết tắt của Cascading Style Sheets.
* CSS tiết kiệm rất nhiều công việc. Nó có thể kiểm soát bố cục của nhiều trang web cùng một lúc.
* Tìm hiểu chi tiết hơn tại phần Css

Ví dụ:

```markup
‌<!DOCTYPE html>
<html>​

<head>
    <style>
        body {
            background-color: powderblue;
        }

        ​ h1 {
            color: blue;
        }

        ​ p {
            color: red;
        }
    </style>
</head>​

<body>
    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>
</body>​

</html>
```

### HTML JavaScript <a href="#html-javascript" id="html-javascript"></a>

JavaScript làm cho các trang HTML trở nên động và tương tác hơn.‌

Ví dụ:

```markup
‌<!DOCTYPE html>
<html>​

<body>
    <h1>My First JavaScript</h1> <button type="button"
        onclick="document.getElementById('demo').innerHTML = Date()"> Click me
        to display Date and Time.</button>
    <p id="demo"></p>
</body>​

</html>
```

## HTML Layout <a href="#html-layout" id="html-layout"></a>

Trang web thường hiển thị nội dung theo nhiều phần và mỗi phần có nhiều cột‌

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GlAbXJ8w3E\_D9G%2F4.png?alt=media)

### Phần tử HTML layout <a href="#phan-tu-html-layout" id="phan-tu-html-layout"></a>

HTML có 1 vài phần tử ngữ nghĩa để định nghĩa sự khác nhau giữa các phần trong trang web

![HTML5 Semantic Elements](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7Gmxi\_3wgIzX-NW%2F5.gif?generation=1618053992301174\&alt=media)

| <ul><li><code>&#x3C;header></code> - định nghĩa một header cho một trang hoặc một phần</li><li><code>&#x3C;nav></code> - Định nghĩa một bộ các đường dẫn điều hướng</li><li><code>&#x3C;section></code> - định nghĩa một phần của văn bản</li><li><code>&#x3C;article></code> - định nghĩa một phần tử độc lập hoặc phần tử chứa nội dung</li><li><code>&#x3C;aside></code> - Định nghĩa nội dung nằm ngoài nội dung chính(như là một thanh bên - sidebar )</li><li><code>&#x3C;footer></code> - định nghĩa phần chân của trang hoặc một phần của trang</li><li><code>&#x3C;details></code> - định nghĩa một phần nội dung chi tiết, người dùng có thể mở hoặc đóng tùy nhu cầu</li><li><code>&#x3C;summary></code> - định nghĩa phần đầu của thẻ <code>&#x3C;details></code></li></ul><p>Có thể xem thêm các thẻ khác tại đây <a href="https://www.w3schools.com/html/html5_semantic_elements.asp">HTML Semantics</a></p> |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### Kỹ thuật chia Layout <a href="#ky-thuat-chia-layout" id="ky-thuat-chia-layout"></a>

Có 4 kỹ thuật chính để tạo layout có nhiều cột, mỗi cách đều có ưu và nhược điểm khác nhau:‌

* CSS framework: Bulma, Bootstrap, Tailwind,...
* CSS float property
* CSS flexbox
* CSS grid

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

## Bài tập <a href="#bai-tap" id="bai-tap"></a>

Bài 1: code giao diện

‌

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7Gq2nR49VO20D2u%2F9.png?alt=media)

Bài 2: Code giao diện cho desktop và mobile

‌

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7Gre0ICUaLP3S7S%2F10.png?alt=media)

Bài 3: code giao diện(chỉ có hình của 1 chiếc lá bên trái chứ không hình chiếc lá bên phải)‌

​

![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GsSR-R2cYQ7VMU%2F11.png?generation=1618053992337288\&alt=media)
