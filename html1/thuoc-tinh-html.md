---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu về thuộc tính của thẻ trong HTML và làm
  quen với một số thuộc tính cơ bản
---

# Thuộc tính HTML

## Thuộc tính HTML là gì? <a href="#thuoc-tinh-html" id="thuoc-tinh-html"></a>

* Tất cả các phần tử HTML có thể **có nhiều thuộc tính**
* Các thuộc tính **cung cấp thông tin bổ sung** về các phần tử
* Các thuộc tính luôn được c**hỉ định trong thẻ bắt đầu**
* Các thuộc tính được quy định bằng các cặp tên / giá trị như: **name = "value"**

## Thuộc tính href

thuộc tính `href` của `<a>` quy định cụ thể URL của trang liên kết đi vào khi click vào thẻ

```markup
<a href="https://quangkhoi1228.gitbook.io/">Quangkhoi1228</a>
```

## Thuộc tính src

Thuộc tính `src` của `<img>` quy định cụ thể đường dẫn đến hình ảnh sẽ được hiển thị

```markup
<img src="img_girl.jpg">
```

## Thuộc tính width và height

Thuộc tính `width` và `height` cung cấp thông tin kích thước cho hình ảnh `<img>`

```markup
<img src="img_girl.jpg" width="500" height="600">
```

## Thuộc tính alt

Thuộc tính `alt` của `<img>` cung cấp một văn bản thay thế cho hình ảnh trong trường hợp không tải được ảnh hoặc những người sử dụng không thể nhìn màn hình cùng có thể biết vị trí này thể hiện gì.

```markup
<img src="img_girl.jpg" alt="Girl with a jacket">
```

## Thuộc tính style

Thuộc tính `style` được sử dụng để thêm phong cách cho một yếu tố, chẳng hạn như màu sắc, font chữ, kích thước, và nhiều hơn nữa

```markup
<p style="color:red;">This is a red paragraph.</p>
```

## Thuộc tính lang

Thuộc tính lang của `<html>` tuyên bố ngôn ngữ của trang web

```markup
<!DOCTYPE html>
<html lang="en">
<body>
...
</body>
</html>
```

\*Xem thêm chi tiết các thuộc tính của HTML tại đây: [https://www.w3schools.com/tags/ref\_attributes.asp](https://www.w3schools.com/tags/ref\_attributes.asp)
