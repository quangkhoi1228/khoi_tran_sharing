# GIới thiệu shinobi JS core

## Shinobi JS core là gì?

Shinobi JS core là tập hợp các thư viện JS giúp thực hiện 1 số thao tác nhất định, giúp cho việc phát triển các ứng dụng web nhanh hơn.

## Cách sử dụng

Ví dụ đơn giản:

```markup
<!DOCTYPE html>
<html>
<head>
    <script>
        shinobi = {};
    </script>
    <script
        src="https://www.aladin.finance/static/js/component/mapping.js"></script>
</head>

<body>
    <p id="demo" snb-key="name"></p>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            var json = {
                name: 'Khôi',
                age: 23,
            };
            shinobi.mapping.render('#demo', JSON.stringify(json))
        });

    </script>
</body>
</html>

```

Để sử dụng thư viện của SJC ta cần:

1. Tài liệu HTML5  cơ bản
2. Trên thẻ `head` ta khai báo biến JS `shinobi` trong cặp thẻ `script`
3. Trên thẻ `head` ta khai báo các thư viện cần sử dụng sau phần khai báo biến `shinobi`
4. Trong thẻ `body` ta khai báo JS thực thi và HTML \(nếu có\) để thực hiện tác vụ

{% hint style="info" %}
Lưu ý: code thực thi shinobi JS core phải đặt trong đoạn JS sự kiện Dom content loaded
{% endhint %}

```javascript
document.addEventListener('DOMContentLoaded', () => {
          ...
});
```

