# Api.js

## Api.js là gì?

api.js là một thư viện dùng để gọi dữ liệu từ API, cụ thể hơn api.js sẽ tạo 1 request dạng POST đến server và xử lý dữ liệu trả về

{% tabs %}
{% tab title="Cú pháp" %}
```diff
shinobi.api.request(url,bodyParamString,callback,options)
```
{% endtab %}

{% tab title="Code" %}
```javascript
var url = '/api/UserApi/getAllUserInfo';
var bodyParam = {
    "username": "686"
};
var callback = function (response) {
    console.log(response);
}
shinobi.api.request(url, JSON.stringify(bodyParam), callback);
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
            shinobi.api.request(url, JSON.stringify(bodyParam), callback);
        });

    </script>
</body>

</html>
```
{% endtab %}

{% tab title="Kết quả" %}
![](../.gitbook/assets/image%20%2825%29.png)
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Khi shinobi server response có result:

* fail: không chạy hàm `callback` mà hiển thị thông báo lỗi theo nội dung trả về
* success: chạy hàm `callback` với thông số là content của API response
{% endhint %}

## Diễn giải 

### url

Là đường dẫn lấy dữ liệu

### bodyParamString

là chuỗi chứa nội dung là JSON chứa body param của request POST

### callback

là hàm được gọi sau khi dữ liệu được trả về, có tham số đầu vào là shinobi server response content khi result = success

{% tabs %}
{% tab title="Cú pháp callback" %}
```javascript
function(responseContent){
    ...
}
```
{% endtab %}
{% endtabs %}

### options

| Thuộc tính | Mặc định | diễn giải |
| :--- | :--- | :--- |
| responseHandleFunction | null | khai báo hàm này để cấu hình một hàm xử lý khi nhận được response trả về |

```javascript
function({
    data: data,
    url: url,
    request: param,
    callback: callback,
    options: options,
})
```

