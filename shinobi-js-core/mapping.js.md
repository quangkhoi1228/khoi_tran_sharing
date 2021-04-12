---
description: Thư viện đơn giản để tương tác với giao diện dựa trên dữ liệu kiểu JSON
---

# Mapping.js

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







