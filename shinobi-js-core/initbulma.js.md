# Initbulma.js

## Initbulma.js là gì?

Initbulma.js là một File Javascript có chức năng để gán các yêu cầu của người sử dụng vào một chức năng nào đó của Bulma, hoặc những chức năng người dùng tự thêm vào liên quan đến Bulma

## Cách thiết l

#### Các chức năng từ thư viện Bulma

Ví dụ về cách thêm tuỳ chỉnh vào chức năng của thư viện Bulma (Thư viện bulmaCalender):

```javascript
var selector = '[type="date"]:not(.is-init-bulma-false)';

var options = {
    dateFormat: 'DD/MM/YYYY',
};

if (typeof bulmaCalendar == 'function') {
    shinobi.initbulma.calendars = bulmaCalendar.attach(selector,options);
}
```

#### Các chức năng người dùng thiết lập

Ví dụ về tính năng tuỳ chỉnh của người dùng (Hàm lấy tên miền của trang):

```javascript
getPathNameAppendSearch : function () {
    return window.location.pathname + window.location.search;
},
```

## Cách sử&#x20;

Với các tính năng từ thư viện Bulma, người dùng chỉ cần gọi theo cú pháp đã code sẵn trước đó

```javascript
var selector = "#thisSelector";
var options = {};

shinobi.initbulma.calendars = bulmaCalendar.attach(selector,options);
```

Còn các chức năng mà người dùng tuỳ chỉnh có thể sử dụng như sau:

```javascript
shinobi.initbulma.getPathNameAppendSearch();
```

Initbulma.js chỉ đơn giản như vậy thôi, chúc bạn thực hành thành công nhé!!
