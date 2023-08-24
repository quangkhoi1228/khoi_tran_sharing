# Phần tử HTML

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

### Phân tích chi tiết một phần tử HTML

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

## Phần tử HTML lồng nhau

Trong HTML, bạn có thể lồng nhau các phần tử bên trong nhau để tạo thành cấu trúc phức tạp hơn. Điều này cho phép bạn xây dựng các thành phần web phong phú và có cấu trúc hơn.

```markup
<p>My cat is <strong>very grumpy.</strong></p>
```

## Phần tử rỗng

Trong HTML, có một số phần tử được gọi là "phần tử rỗng" hoặc "phần tử tự đóng" (self-closing elements). Điều này có nghĩa là bạn không cần phải cung cấp cặp thẻ mở và thẻ đóng cho các phần tử này, mà chỉ cần sử dụng một thẻ duy nhất để đại diện cho phần tử đó. Thường thì bạn sẽ sử dụng dấu gạch chéo sau thẻ mở để đóng phần tử.

```markup
<img
  src="https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png"
  alt="Firefox icon" />
```

