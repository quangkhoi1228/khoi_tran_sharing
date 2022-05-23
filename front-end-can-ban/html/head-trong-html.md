---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu về thẻ head trong HTML về khái niệm, chức
  năng, các phần tử quan trọng nhất mà nó có thể chứa và sự ảnh hưởng của các
  phần tử này đến trang
---

# Head trong HTML

## Head là gì?

Head là một phần trong văn bản HTML, nó sẽ không hiển thị trên trình duyệt khi load trang nhưng sẽ cung cấp một số các thông tin thêm như: tiêu đề trang, đường dẫn đến các file CSS/JS, favicon hay metadata.

Metadata là dữ liệu về trang như tác giả, các từ khoá quan trọng để mô tả văn bản hoặc thông tin về cách hiển thị của văn bản.

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

Trong trường hợp này Tiêu để của trang sẽ thanh đổi thành "My test page"

## Thẻ \<title>

Thẻ \<title> là một thẻ HTML dùng để định nghĩa tiêu để của trang. Tiêu để này sẽ được thể hiện trên tab của trình duyệt khi load trang.

\<title> là thẻ được yêu cầu trong văn bản HTML và rất quan trọng trong việc tối ưu công cụ tìm kiếm (SEO)

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

Kết quả:

![](<../../.gitbook/assets/image (70).png>)

