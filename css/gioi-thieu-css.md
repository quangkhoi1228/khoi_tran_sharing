---
description: Trong phần này chúng ta sẽ tìm hiểu về khái niệm CSS và lý do sử dụng CSS
---

# Giới thiệu CSS

## CSS là gì?

* **CSS** là viết tắt của **Cascading Style Sheets**
* CSS **mô tả cách phần tử HTML thể hiện** **trên giao diện** như thế nào?
* CSS giúp chúng ta **tiết kiệm thời gian vì có thể tái sử dụng lại CSS cho nhiều trang khác nhau**.

## Ví dụ

### Không có CSS

![](<../.gitbook/assets/image (2).png>)

### Có CSS

![](<../.gitbook/assets/image (32).png>)

## Vì sao nên sử dụng CSS?

### Giải quyết vấn đề lớn của HTML

**HTML** được tạo ra để **mô tả cấu trúc của trang web** chứ **không phải để làm đẹp** do đó **CSS được ra đời** để giải quyết vấn đề này.

### Cho phép cấu hình hiển thị phần tử

CSS cho phép chúng ta **cấu hình cách hiển thị phần tử HTML tuỳ theo kích thước của thiết bị** do đó CSS đóng vai trò khá quan trọng trong việc thể hiện thông tin cho người dùng.

### CSS tiết kiệm công sức làm việc

CSS có thể lưu trong nhiều file .css và các file này có thể được **sử dụng cho nhiều trang khác nhau** do đó tiết kiệm được nhiều thời gian và công sức làm việc.

Điều đó cũng có nghĩa là chúng ta chỉ cần **chỉnh sửa một file duy nhất** để có thể **thay đổi cách thể hiện của nhiều trang web khác nhau.**

## Cú pháp CSS

Một luật CSS bao gồm selector và một khối khai báo

![](../.gitbook/assets/2.png)

* Selector chỉ ra phần tử HTML muốn chỉnh style
* Khối khai báo chứa một hoặc nhiều khai báo cách nhau bởi dấu chấm phẩy
* Mỗi khai báo bao gồm một thuộc tính CSs và một giá trị cách nhau bởi dấu hai chấm
* Những định nghĩa Css được cách nhau bởi dấu chấm phẩy, và các khối định nghĩa được bao quanh bởi dấu ngoặc nhọn
* Các class trong cùng 1 thẻ được đặt trong thuộc tính class và cách nhau bởi khoảng trắng, chi tiết

```markup
<tagname class="class1 class2 classn"> nội dung </tagname>
```
