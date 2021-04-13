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

## Thuật ngữ/Khái niệm

### selector

DOM query selector đầu vào của hàm `document.querySelector` hoặc `document.querySelectorAll`

```markup
#id1
.class1
.class1.class2
```

### json

dữ liệu có định dạng JSON

```css
{
    name : "Khôi",
    age: 23,
}
```

### jsonString

chuỗi chứa nội dung có định dạng JSON

```javascript
''
```

## Các hàm hỗ trợ

### render \(selector, jsonString\)

Đưa dữ liệu lên giao diện

```
shinobi.mapping.render(selector,jsonString)
```

### renderElement\(element,json\)

Đưa dữ liệu lên giao diện

```javascript
shinobi.mapping.renderElement(element,json)
```

### renderSelector\(element,json,snbKey\)

Đưa dữ liệu vài phần tử

```javascript
shinobi.mapping.renderSelector(element,json,snbKey)
```

### 





















