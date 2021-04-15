# Api.js

## Shinobi server API response

Shinobi server trả dữ liệu API có dạng JSON string theo format 

{% tabs %}
{% tab title="Cú pháp" %}
```javascript
`{
    result: resultValue,
    content: contentValue
}`
```
{% endtab %}

{% tab title="Ví dụ" %}
```
'{result: "success", content: "null"}'
```
{% endtab %}
{% endtabs %}

* result: kết quả của API, thành công : success, thất bại: fail
* content: nội dung của API

## Api.js là gì?

api.js là một thư viện dùng để gọi dữ liệu từ API, cụ thể hơn api.js sẽ tạo 1 request dạng POST đến server và xử lý dữ liệu trả về

{% tabs %}
{% tab title="Cú pháp" %}
```diff
shinobi.api.request(url,bodyParamString,callback)
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
![](../.gitbook/assets/image%20%2824%29.png)
{% endtab %}
{% endtabs %}

## Diễn giải 

### url

Là đường dẫn lấy dữ liệu

### bodyParamString

là chuỗi chứa nội dung là JSON chứa body param của request POST

### callback

là hàm được gọi sau khi dữ liệu được trả về, có tham số đầu vào 

