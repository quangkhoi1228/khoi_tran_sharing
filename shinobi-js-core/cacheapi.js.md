# Cacheapi.js

## Lý do sử dụng cacheapi.js?

Mỗi khi gọi 1 API bằng api.js server phải đi xử lý và tốn tài nguyên và tốn thời gian để chờ server trả về dữ liệu, nhưng không phải dữ liệu nào cũng thay đổi theo thời gian thực nên đối với dữ liệu dạng này ta có thể lưu\(cache\) lại phía client để giảm tải cho server mà vẫn đảm bảo dữ liệu phía client được đúng và không tốn thời gian chờ khi gọi API.

==&gt; **Lúc đó cacheapi.js ra đời để giải quyết vấn đề này**

{% tabs %}
{% tab title="Cú pháp" %}
```javascript
shinobi.cacheapi.request(url,bodyParamString,callback,options)
```
{% endtab %}

{% tab title="code" %}
```javascript
var url = '/api/UserApi/getAllUserInfo';
var bodyParam = {
    "username": "686"
};
var callback = function (response) {
    console.log(response);
}
shinobi.cacheapi.request(url, JSON.stringify(bodyParam), callback);
```
{% endtab %}

{% tab title="Ví dụ" %}
```markup
<!DOCTYPE html>
<html>

<head>
    <script>
        shinobi = {};
    </script>
    <script src="https://naruto.finance/static/js/component/api.js"></script>
</head>

<body>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            var url = '/api/UserApi/getAllUserInfo';
            var bodyParam = {
                "username": "686"
            };
            var callback = function (response) {
                console.log(response);
            }
            shinobi.cacheapi.request(url, JSON.stringify(bodyParam), callback);
        });

    </script>
</body>

</html>
```
{% endtab %}

{% tab title="Kết quả" %}
![](../.gitbook/assets/image%20%2831%29.png)

![](../.gitbook/assets/image%20%2832%29.png)
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Ta thấy gọi cacheapi 2 lần đều trả về dữ liệu nhưng api chỉ được gọi trong lần call đầu tiên.
{% endhint %}

## Cơ chế

phía client sẽ tạo 1 biến JS là `shinobi.cacheapi.cache` dạng 1 JSON, khi gọi api lần đầu với cacheapi.js client sẽ tự động lưu kết quả trả về vào biến `shinobi.cacheapi.cache` theo format:

```javascript
{
    url_bodyParamString : serverResponse
}
```

Trong những lần gọi cacheapi.js tiếp theo nếu `url` và `bodyParamString` khớp với key nào trong `shinobi.cacheapi.cache` dữ liệu sẽ lấy giá trị value của key đó để trả về.

## Cách dùng

### Lấy dữ liệu từ API

{% tabs %}
{% tab title="Cú pháp" %}
```javascript
shinobi.cacheapi.request(url,bodyParamString,callback,options)
```
{% endtab %}

{% tab title="code" %}
```javascript
var url = '/api/UserApi/getAllUserInfo';
var bodyParam = {
    "username": "686"
};
var callback = function (response) {
    console.log(response);
}
shinobi.cacheapi.request(url, JSON.stringify(bodyParam), callback);
```
{% endtab %}

{% tab title="Ví dụ" %}
```markup
<!DOCTYPE html>
<html>

<head>
    <script>
        shinobi = {};
    </script>
    <script src="https://naruto.finance/static/js/component/api.js"></script>
</head>

<body>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            var url = '/api/UserApi/getAllUserInfo';
            var bodyParam = {
                "username": "686"
            };
            var callback = function (response) {
                console.log(response);
            }
            shinobi.cacheapi.request(url, JSON.stringify(bodyParam), callback);
        });

    </script>
</body>

</html>
```
{% endtab %}

{% tab title="Kết quả" %}
![](../.gitbook/assets/image%20%2831%29.png)

![](../.gitbook/assets/image%20%2832%29.png)
{% endtab %}
{% endtabs %}

Các thuộc tính options:

|  |  |
| :--- | :--- |
|  |  |





