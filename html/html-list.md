---
description: >-
  Trong HTML, danh sách (list) là một cách để hiển thị một nhóm các mục liên
  quan hoặc có cùng loại trong một dạng cấu trúc cụ thể.
---

# HTML List

Trong HTML, có hai loại danh sách phổ biến: danh sách không thứ tự (unordered list) và danh sách có thứ tự (ordered list). Danh sách cho phép bạn xếp sắp thông tin hoặc mục vào một cấu trúc dễ đọc hơn. Dưới đây là cách tạo và sử dụng danh sách trong HTML:

## **Danh sách không thứ tự (Unordered List):**

* Danh sách không thứ tự được sử dụng để hiển thị danh sách các mục mà không cần thứ tự cụ thể. Mỗi mục trong danh sách không thứ tự thường được hiển thị bằng một dấu đầu dòng (bullets) hoặc biểu tượng tùy chọn.

```html
<ul>
  <li>Mục 1</li>
  <li>Mục 2</li>
  <li>Mục 3</li>
</ul>
```

Trong đoạn mã trên, `<ul>` là thẻ bao bọc danh sách không thứ tự và `<li>` là thẻ sử dụng để định nghĩa các mục trong danh sách.

## **Danh sách có thứ tự (Ordered List):**

* Danh sách có thứ tự được sử dụng để hiển thị danh sách các mục theo một thứ tự cụ thể. Mỗi mục trong danh sách có thứ tự thường được hiển thị bằng số hoặc chữ cái.

```html
<ol>
  <li>Mục 1</li>
  <li>Mục 2</li>
  <li>Mục 3</li>
</ol>
```

Trong đoạn mã trên, `<ol>` là thẻ bao bọc danh sách có thứ tự và `<li>` được sử dụng để định nghĩa các mục trong danh sách.

## **Danh sách định nghĩa (Definition List):**

* Danh sách định nghĩa được sử dụng để xác định các thuộc tính hoặc định nghĩa cho mỗi mục. Danh sách này sử dụng các thẻ `<dl>` (danh sách định nghĩa), `<dt>` (mục tiêu định nghĩa), và `<dd>` (nội dung định nghĩa).

```html
<dl>
  <dt>Thuật ngữ 1</dt>
  <dd>Định nghĩa thuật ngữ 1</dd>
  <dt>Thuật ngữ 2</dt>
  <dd>Định nghĩa thuật ngữ 2</dd>
</dl>
```

Trong đoạn mã trên, `<dl>` là thẻ bao bọc danh sách định nghĩa, `<dt>` được sử dụng để định nghĩa mục tiêu và `<dd>` được sử dụng để định nghĩa nội dung của mục tiêu.

{% hint style="info" %}
Danh sách là một phần quan trọng trong HTML, giúp cải thiện tổ chức và hiển thị thông tin trên trang web của bạn.
{% endhint %}
