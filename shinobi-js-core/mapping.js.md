# Mapping.js

## Mapping.js là gì?

mapping.js là một thư viện đơn giản để tương tác với giao diện dựa trên dữ liệu kiểu JSON và một số thao tác khác như:

* Gán dữ liệu từ dữ liệu định dạng JSON lên giao diện
* Lấy dữ liệu từ giao diện trả về giá trị theo định dạng JSON
* Chuyển các element form HTML thành element dạng text HTML
* Xóa dữ liệu trên giao diện

## Cách dùng

### Gán dữ liệu lên giao diện

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



## API

### render \(element, json\)

Dùng để đưa dữ liệu JSON lên giao diện

```markup
shinobi.mapping.render(element,json)
```







