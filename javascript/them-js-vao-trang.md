# Thêm JS vào trang

Để thêm JavaScript vào một trang web, bạn có thể sử dụng một trong các phương pháp sau:

1. **Sử dụng thẻ `<script>` trong HTML:** Bạn có thể thêm mã JavaScript trực tiếp vào trang HTML bằng cách sử dụng thẻ `<script>`. Ví dụ:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Trang Web của Tôi</title>
</head>
<body>
    <!-- Nội dung trang web -->

    <!-- Đoạn mã JavaScript -->
    <script>
        // JavaScript code goes here
        console.log("Hello, world!");
    </script>
</body>
</html>
```

2. **Liên kết một file JavaScript bên ngoài:** Bạn cũng có thể tạo một file JavaScript riêng và sau đó liên kết nó vào trang HTML bằng thẻ `<script>` với thuộc tính `src`. Ví dụ:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Trang Web của Tôi</title>
</head>
<body>
    <!-- Nội dung trang web -->

    <!-- Liên kết file JavaScript bên ngoài -->
    <script src="myscript.js"></script>
</body>
</html>
```

Trong trường hợp này, `myscript.js` là đường dẫn tới file JavaScript bạn muốn liên kết.

3. **Sử dụng các framework hoặc thư viện JavaScript:** Nếu bạn đang sử dụng các framework như React, Angular, hoặc Vue.js, bạn thường sẽ có cách riêng để thêm mã JavaScript vào trang web thông qua các thành phần, directive, hoặc các cách tiếp cận khác được cung cấp bởi framework đó.

Bất kỳ phương pháp nào bạn chọn, JavaScript sẽ được thực thi bởi trình duyệt web khi trang được tải, và mã JavaScript sẽ thực hiện các chức năng và thay đổi tương ứng trên trang web.
