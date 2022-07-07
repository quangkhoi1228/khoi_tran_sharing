---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu comment trong CSS và cách sử dụng comment
  CSS
---

# Comment trong CSS

## Tổng quan

{% hint style="info" %}
Trình thông dịch của trình duyệt giúp cho trình duyệt hiểu được `CSS` và  thể hiện trên giao diện.
{% endhint %}

**Comment CSS** là một thuật ngữ dùng để chỉ việc chúng ta làm cho một số đoạn **nội dung khai báo trong CSS được bỏ qua bởi trình thông dịch của trình duyệt**.

Nhờ vào đặc tính trên mà **comment** thường **được sử dụng** để **mô tả hoặc ghi chú trong code** để sau này chúng ta xem lại có thể **biết được thêm thông tin**.

## Cách sử dụng

Comment trong CSS được đặt trong thẻ `<style>` hoặc trong file `.css` . Bắt đầu bởi `/*` và kết thúc bằng `*/`

Một vài cách sử dụng như sau:

#### Comment một dòng

```css
/* This is a single-line comment */
p {
  color: red;
}
```

#### Comment tất cả mọi vị trí

```css
p {
  color: red;  /* Set text color to red */
}
```

#### Comment nhiều dòng

```css
/* This is
a multi-line
comment */

p {
  color: red;
}
```

{% hint style="info" %}
Comment trong CSS khác cú pháp với comment trong HTML các bạn có thể tham khảo comment trong HTML [tại đây](../html1/comment-trong-html.md)
{% endhint %}
