# Giới thiệu shinobi JS core

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

## Thuật ngữ liên quan

### Shinobi server API response

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

* result: kết quả của API, thành công: success, thất bại: fail
* content: nội dung của API hoặc nội dung khi bị lỗi

### Dữ liệu dạng findDataList

Nếu 1 Shinobi server API response có nội dung JSON key content theo format:

{% tabs %}
{% tab title="Only result content key" %}
```css
{
    data: [{…},{…},{…},{…},{…},{…},{…},{…},{…},{…}],//list JSON
    pageNum: 1,//number
    pageTotal: 60,//number
    recordPerPage: 10, //number
    rowTotal: 598,//number
}
```
{% endtab %}

{% tab title="Full result" %}
```
{
    result : true,
    content : {
        data: [{…},{…},{…},{…},{…},{…},{…},{…},{…},{…}],//list JSON
        pageNum: 1,//number
        pageTotal: 60,//number
        recordPerPage: 10, //number
        rowTotal: 598,//number
    }    
}
```
{% endtab %}
{% endtabs %}

Diễn giải:

* `data`: thể hiện danh sách dữ liệu
* `pageNum`: thể hiện số thứ tự trang 
* `pageTotal`: thể hiện tổng số trang
* `recordPerPage`: số dòng mỗi trang
* `rowTotal`: tổng số dòng dữ liệu

{% hint style="info" %}
Sở dĩ cái tên Dữ liệu dạng findDataList vì shinobi server core hỗ trợ hàm findDataList dùng để trả về dữ liệu dạng này
{% endhint %}

### Filter object

đối với api dạng `findDataList` đôi khi ta cần cấu hình thêm thuộc tính `filters` trong `request` hoặc trong `shinobiComponentObject`.

`filter object`là 1 JSON có cấu trúc như sau:

```css
{
    colname : colnameValue,// name,age,...
    operator: operatorValue,//=,like
    value: value,//Khôi,23
}
```

`filters` là 1 mảng các đối tượng `filter` \(filter object\)

### Sort object

đối với api dạng `findDataList` đôi khi ta cần cấu hình thêm thuộc tính `sorts` trong `request` hoặc trong `shinobiComponentObject`.

`sort object`là 1 JSON có cấu trúc như sau:

```css
{
    colname : colnameValue,// name,age,...
    operator: operatorValue,//asc,desc
}
```

`sorts` là 1 mảng các đối tượng `sort` \(sort object\)

