# Language.js

## Language.js là gì?

Language.js là thư viện dùng để cấu hình ngôn ngữ mong muốn và sử dụng để hỗ trợ thay đổi ngôn ngữ cho hệ thống.&#x20;

## Cách sử dụng

#### Thanh lựa chọn

Để tuỳ chỉnh ngôn ngữ, ta cần một thanh chọn ngôn ngữ trước, đây là code mẫu cho HTML:

```html
<div class="select">
    <select id="selectLangcode">
        <option value="VN">VN</option>
        <option value="EN">EN</option>
    </select>
</div>
```

#### Phần nội dụng

Sau khi đã có code cho thanh lựa chọn, ta tiếp tục với code của nội dung cần thay đổi ngôn ngữ:

```html
<div>
    <b snb-lang="PAGECODE_WELCOMECONTENT">
        Xin chào bạn! Tôi là nội dụng của trang.
    </b>
</div>
```

Khi đã có 2 yêu cầu trên, trang của bạn sẽ có giao diện tương tự với hình bên dưới

![Hình gợi ý code cho Language.js](<../.gitbook/assets/Screenshot from 2022-06-11 15-03-45 (1).png>)

## Thiết lập ngôn ngữ

Chúng ta sẽ cấu hình ngôn ngữ cho nội dung hệ thống vừa đặt bằng cách Chọn "System" trong trang hệ thống Admin, sau đó chọn "Resourcebundle".

![Thanh menu của hệ thống Admin](<../.gitbook/assets/image (1).png>)

Một hệ thống bảng sẽ hiển thị như sau

![Hệ thống bảng Resourcebundle hệ thống Admin](<../.gitbook/assets/image (9).png>)

Điền đầy đủ thông tin với các dữ liệu như sau:

* Resourcename: Giá trị của thuộc tính snb-lang trong code\
  Ví dụ: "PAGECODE\_WELCOMECONTENT"\

* Langcode: Ngôn ngữ cần thiết lập\
  Ví dụ: "VN"\

* Resourcevalue: Nội dung dữ liệu của thuộc tính snb-lang\
  Ví dụ: "Xin chào bạn! Tôi là nội dụng của trang."

_<mark style="color:orange;">Lưu ý</mark>_<mark style="color:orange;">: Cần thiết lập cả Langcode cho "VN" và "EN" cho dữ liệu đang cần được thiết lập</mark>

<img src="../.gitbook/assets/image (20).png" alt="" data-size="original">![](<../.gitbook/assets/image (6).png>)

Sau khi đã điền đầy đủ thông tin dữ liệu cần thiết, nhấn nút "Tạo mới" để thêm mới dữ liệu, hoặc "Cập nhật" để chỉnh sửa lại dữ liệu hiện có.\
\
Sau khi tạo mới thành công hoặc chỉnh sửa thành công, nhấn nút "reloadResourceBundle", Bảng dữ liệu sẽ có xuất hiện 2 dữ liệu mới bạn vừa thêm.

![Bảng dữ liệu thiết lập Ngôn ngữ](<../.gitbook/assets/image (5).png>)

Sau khi đã hoàn thành thiết lập ngôn ngữ bên hệ thống Admin, vậy là trang của chúng ta đã có thể thay đổi dựa vào thanh chọn ngôn ngữ rồi!! Chúc bạn thành công.

![](<../.gitbook/assets/image (10).png>)
