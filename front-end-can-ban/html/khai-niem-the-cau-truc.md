---
description: >-
  Trong bài này chúng ta sẽ tìm trả lời các câu hỏi sau: HTML là gì? Phần tử
  HTML là gì? và cấu trúc của một file HTML như thế nào?
---

# Khái niệm/Thẻ/Cấu trúc

## HTML là gì? <a href="#html-la-gi" id="html-la-gi"></a>

* HTML viết tắt của Hyper Text Markup Language
* HTML là ngôn ngữ tiêu chuẩn để tạo ra giao diện của trang web
* HTML mô tả cấu trúc của một trang Web bằng cách gắn nhãn các phần nội dung như "đây là một tiêu đề", "đây là một đoạn văn", "đây là một liên kết", v.v.
* Các phần tử HTML có cách hiển thị trên giao diện khác nhau do đó giúp cho trình duyệt hiểu cách hiển thị nội dung trên giao diện

## Phần tử HTML(Thẻ HTML) là gì? <a href="#phan-tu-html-la-gi" id="phan-tu-html-la-gi"></a>

Phần tử HTML là đơn vị nhỏ nhất của HTML và được xác định bởi **thẻ bắt đầu**, **một số nội dung** và **thẻ kết thúc**:

```markup
<tagname> Nội dung </tagname>
```

Phần tử HTML là tất cả mọi thứ từ thẻ bắt đầu đến thẻ kết thúc:

```markup
<h1> Tiêu đề </h1>
<p> Đoạn văn </p>‌
```

Lưu ý: Một số phần tử HTML không có nội dung (như phần tử `<br>`). Các phần tử này được gọi là phần tử rỗng hay phần tử trống. phần tử trống không có thẻ kết thúc!‌

### Các thẻ HTML căn bản <a href="#cac-the-html-can-ban" id="cac-the-html-can-ban"></a>

`<h1>` đến `<h6>`: tiêu đề‌

`<p>`: đoạn văn bản‌

`<a>`: đường dẫn‌

\*Chi tiết các thẻ: [https://htmlreference.io/](https://htmlreference.io)​‌

\*Các thẻ HTML không phân biệt hoa thường `<H1>` giống với `<h1>` nhưng khuyến khích viết chữ thường‌

## Cấu trúc file HTML đơn giản <a href="#vi-du-html-don-gian" id="vi-du-html-don-gian"></a>

File HTML là tập hợp các thẻ HTML nhưng được tổ chức theo một trật tự giúp cho trình duyệt hiểu và truyền tải lên giao diện một cách chính xác.

Dưới đây là mô tả một file HTML đơn giản:

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
