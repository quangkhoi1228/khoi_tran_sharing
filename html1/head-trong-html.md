---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu về thẻ head trong HTML về khái niệm, chức
  năng, các phần tử quan trọng nhất mà nó có thể chứa và sự ảnh hưởng của các
  phần tử này đến trang
---

# Head trong HTML

## Head là gì?

**Head** là **một phần** trong **văn bản HTML**, nó sẽ **không hiển thị trên trình duyệt** khi load trang nhưng sẽ **cung cấp** một số các **thông tin thêm** như: **tiêu đề trang, đường dẫn đến các file CSS/JS, favicon hay metadata.**

**Metadata** là **dữ liệu về trang** như tác giả, các từ khoá quan trọng để mô tả văn bản hoặc thông tin về cách hiển thị của văn bản.

### Ví dụ

```markup
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```

Trong trường hợp này Tiêu đề của trang sẽ thanh đổi thành _"My test page"_

## Thẻ \<title>

Thẻ `<title>` là một thẻ HTML dùng để **định nghĩa tiêu để của trang**. Tiêu để này sẽ được **thể hiện trên tab của trình duyệt** khi load trang.

`<title>` là thẻ **được yêu cầu trong văn bản HTML** và rất quan trọng trong việc **tối ưu công cụ tìm kiếm (SEO)**

```markup
<!DOCTYPE html>
<html>
<head>
  <title>A Meaningful Page Title</title>
</head>
<body>

The content of the document......

</body>
</html>
```

**Kết quả:**

![](<../.gitbook/assets/image (70).png>)

## Thẻ \<meta>

Thẻ `<meta>` cung cấp các thông tin **metadata** **của trang** như tác giả, mô tả, từ khoá tìm kiếm, cấu hình viewport trang,... Sau đây là một vài ví dụ:

### Định nghĩa bảng mã của trang

```markup
<meta charset="UTF-8">
```

### Định nghĩa từ khoá tìm kiếm

```markup
<meta name="keywords" content="HTML, CSS, JavaScript">
```

### Định nghĩa mô tả của trang

```markup
<meta name="description" content="Free Web tutorials">
```

### Định nghĩa tác giả

```markup
<meta name="author" content="John Doe">
```

### Cấu hình viewport của trang trên nhiều thiết bị

```markup
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Tuỳ chỉnh favicon

```markup
<link rel="icon" href="favicon.ico" type="image/x-icon">
```
