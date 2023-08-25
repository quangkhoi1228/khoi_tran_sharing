---
description: >-
  Trong HTML, thẻ <table> được sử dụng để tạo các bảng dữ liệu trong trang web.
  Bảng dữ liệu này có thể chứa các hàng và cột, giúp bạn tổ chức và hiển thị
  thông tin một cách có cấu trúc.
---

# HTML Table

## Cú pháp

```html
<table>
  <tr>
    <th>Tiêu đề cột 1</th>
    <th>Tiêu đề cột 2</th>
    <th>...</th>
  </tr>
  <tr>
    <td>Dữ liệu hàng 1, cột 1</td>
    <td>Dữ liệu hàng 1, cột 2</td>
    <td>...</td>
  </tr>
  <tr>
    <td>Dữ liệu hàng 2, cột 1</td>
    <td>Dữ liệu hàng 2, cột 2</td>
    <td>...</td>
  </tr>
  <!-- ... Các hàng khác ... -->
</table>
```

Trong đó:

* `<table>` là thẻ bao bọc toàn bộ bảng.
* `<tr>` là thẻ dùng để tạo hàng trong bảng.
* `<th>` là thẻ dùng để định nghĩa các tiêu đề cột. Thường được đặt trong hàng đầu tiên và có thể căn lề và làm nổi bật văn bản.
* `<td>` là thẻ dùng để chứa dữ liệu của từng ô trong bảng.

Ví dụ:

```html
<table>
  <tr>
    <th>Tên</th>
    <th>Tuổi</th>
  </tr>
  <tr>
    <td>John</td>
    <td>25</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>30</td>
  </tr>
</table>
```

Trong ví dụ trên, chúng ta tạo một bảng với hai cột ("Tên" và "Tuổi") và hai hàng chứa dữ liệu tương ứng.

Thẻ `<table>` trong HTML rất hữu ích để hiển thị dữ liệu dưới dạng bảng và có thể được tùy chỉnh thông qua CSS để phù hợp với thiết kế trang web.
