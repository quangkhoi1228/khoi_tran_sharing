# Mapping.js

## Mapping.js là gì?

mapping.js là một thư viện đơn giản để tương tác với giao diện dựa trên dữ liệu kiểu JSON và một số thao tác khác như:

* Gán dữ liệu từ dữ liệu định dạng JSON lên giao diện
* Lấy dữ liệu từ giao diện trả về giá trị theo định dạng JSON
* Chuyển các element form HTML thành element dạng text HTML
* Xóa dữ liệu trên giao diện

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
'{"name":"Khôi","age":23}'
```

### element

Phần tử HTML

```markup
<div>Tôi là phần tử HTML</div>
```

### snbKey

thuộc tính của thẻ HTML, trong mapping.js snbKey giúp quy định giá trị được áp dụng cho thẻ hoặc đăng ký thẻ là một phần tử bị ảnh hưởng bởi mapping.js

```markup
<div snb-key="key1">Tôi là phần tử HTML</div>
```

### callback

hàm sẽ được gọi sau khi thực hiện 1 số xử lý gì đó

```javascript
var callback = function(){
    console.log('Tôi là 1 hàm callback');
}
```

### options

một biến kiểu JSON quy định một số khai báo phụ của hàm

```typescript
{
    checkNull: true,
    callback: function(){
        console.log('Tôi là một callback');
    } 
}
```

### snbKeyValue

giá trị của phần tử

```javascript
12
'Giá trị'
```

## Gán dữ liệu lên giao diện

### render/renderElement

{% tabs %}
{% tab title="code" %}
```markup
<p id="demo" snb-key="name"></p>
<p class="demo1" snb-key="age"></p>
<script>
    document.addEventListener('DOMContentLoaded', () => {
        var json = {
            name: 'Khôi',
            age: 23,
        };
        shinobi.mapping.render('#demo', JSON.stringify(json));
        shinobi.mapping.renderElement('.demo1',json);
    });
</script>
```
{% endtab %}

{% tab title="ví dụ" %}
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
    <p class="demo1" snb-key="age"></p>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            var json = {
                name: 'Khôi',
                age: 23,
            };
            shinobi.mapping.render('#demo', JSON.stringify(json));
            shinobi.mapping.renderElement('.demo1', json);

        });

    </script>
</body>

</html>
```
{% endtab %}

{% tab title="kết quả" %}
![](../.gitbook/assets/image%20%283%29.png)
{% endtab %}
{% endtabs %}

hàm `render` và hàm `renderElement` giống nhau cách sử dụng và các cấu hình, chỉ khác nhau input đầu vào của hàm.

hai hàm này đều có nhiệm vụ đưa dữ liệu dạng JSON lên giao diện cụ thể hơn các cặp key-value của `json` sẽ được đưa vào các thẻ con của phần tử `selector` hoặc `element` khai báo tại input của hàm

### snb-key

thuộc tính này dùng để xác định giá trị `value` thuộc `key` nào của `json` sẽ được gán vào giao diện

{% tabs %}
{% tab title="code" %}
```markup
<div id="container">
    <p>Giá trị của key "name": <span snb-key="name"></span></p>
    <p>Giá trị của key "age": <span snb-key="age"></span></p>
</div>
```
{% endtab %}

{% tab title="ví dụ" %}
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
    <div id="container">
        <p>Giá trị của key "name": <span snb-key="name"></span></p>
        <p>Giá trị của key "age": <span snb-key="age"></span></p>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            var json = {
                name: 'Khôi',
                age: 23,
            };
            shinobi.mapping.render('#container', JSON.stringify(json));
        });

    </script>
</body>

</html>
```
{% endtab %}

{% tab title="kết quả" %}
![](../.gitbook/assets/image.png)
{% endtab %}
{% endtabs %}

### snb-format

thuộc tính này dùng để format giá trị dạng số



















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

### getValue\(selector,callback,options\)

Lấy dữ liệu có thể có trong tập con của phần tử và trả về dữ liệu dạng JSON

```julia
shinobi.mapping.getValue(selector,callback,options)
```

### getValueElement\(element,callback,options\)

Lấy dữ liệu có thể có trong tập con của phần tử và trả về dữ liệu dạng JSON

```julia
shinobi.mapping.getValueElement(element,callback,options)
```

### handleOptionMapping\(element,snbKeyValue,options\)

áp dụng các thay đổi lên phần tử dựa theo các `options` được khai báo

```javascript
shinobi.mapping.handleOptionMapping(element,snbKeyValue,options)
```

### getValueMappingNormalTag\(element,options\)

lấy giá trị của element HTML

```javascript
shinobi.mapping.getValueMappingNormalTag(element,options)
```

### replaceFormWithLabel\(selector\)

đổi các phần tử con của phần tử `selector` từ form HTML thành dạng text HTML

```javascript
shinobi.mapping.replaceFormWithLabel(selector)
```

### replaceFormWithLabelElement\(element\)

đổi các phần tử con của phần tử `element` từ form HTML thành dạng text HTML

```javascript
shinobi.mapping.replaceFormWithLabelElement(element)
```

### replaceFormWithLabelSnbKey\(element\)

đổi phần tử form HTML thành dạng text HTML

```javascript
shinobi.mapping.replaceFormWithLabelSnbKey(element)
```

### checkPreProcess\(element,options\)

biến đổi dữ liệu trả về tùy vào các thuộc tính `options`

```javascript
shinobi.mapping.checkPreProcess(element,options)
```

### getValueShinobiEditor\(element,options\)

lấy dữ liệu từ phần tử dạng editor dựa vào các thuộc tính `options`

```javascript
shinobi.mapping.getValueShinobiEditor(element,options)
```

### clear\(selector,callback,options\)

xóa dữ liệu các phần tử có chứa snbKey dựa vào các cấu hình `options`

```javascript
shinobi.mapping.clear(selector,callback,options)
```

### clearElement\(element,callback,options\)

xóa dữ liệu các phần tử có chứa snbKey dựa vào các cấu hình `options`

```javascript
shinobi.mapping.clearElement(element,callback,options)
```





