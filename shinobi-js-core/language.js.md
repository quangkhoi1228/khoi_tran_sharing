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
        Xin chào bạn! Tôi là nội dụng của trang
    </b>
</div>
```

Khi đã có 2 yêu cầu trên, trang của bạn sẽ có giao diện giống với hình bên dưới

![Hình gợi ý code cho Language.js](<../.gitbook/assets/Screenshot from 2022-06-11 15-03-45 (1).png>)

## Thiết lập ngôn ngữ

