---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu về comment trong HTML và các cách sử dụng
  cơ bản của nó
---

# Comment trong HTML

## Comment là gì?

**Comment** có nghĩa **là** những dòng **code** mà ta muốn tạo ra để ghi chú hoặc giải thích cho một đoạn **code** khác, và vì đây **là** ghi chú nên khi biên dịch thì compiler sẽ bỏ qua các dòng đó.

**Trong HTML** thì comment sẽ **không được hiển thị lên trình duyệt**. Lợi dụng tính chất này chúng ta có thể sử dụng comment để có thể **ghi chú lại** các nội dung ngay trong file code hoặc **lưu trữ lại các đoạn code tạm thời chưa được sử dụng** trong thời điểm hiện tại.

## Cú pháp

Cú pháp comment trong HTML được định nghĩa như sau:

```markup
<!-- Write your comments here -->
```

{% hint style="info" %}
Lưu ý **dấu chấm than (!)** chỉ có ở phần mở thẻ chứ không có trong phần đóng thẻ.
{% endhint %}

## Các chức năng chính

### Ghi chú code

Với comment chúng ta **có thể ghi chú** để **giải thích** hoặc **cảnh báo** cho đoạn code của chúng ta

```markup
<!-- This is a comment -->

<p>This is a paragraph.</p>

<!-- Remember to add more information here -->
```

### Ẩn nội dung

Với comment chúng ta cũng có thể **ẩn các đoạn code** hiện không được sử dụng hoặc được tạm bỏ qua trong quá trình chạy code.

```markup
<p>This is a paragraph.</p>

<!-- <p>This is another paragraph </p> -->

<p>This is a paragraph too.</p>
```

Chúng ta có thể **ẩn nhiều dòng code** bằng cách bọc chúng bằng thẻ mở và thẻ đóng của comment HTML

```markup
<p>This is a paragraph.</p>
<!--
<p>Look at this cool image:</p>
<img border="0" src="pic_trulli.jpg" alt="Trulli">
-->
<p>This is a paragraph too.</p>
```

Chúng ta cũng có thể **ẩn một phần nội dung** bên trong thẻ như sau:

```markup
<p>This <!-- great text --> is a paragraph.</p>
```
