# Thuộc tính color

## Tổng quan

Thuộc tính color trong CSS dùng để thay đổi màu chữ của thẻ. Giá trị của color có thể là tên màu hoặc theo các chuẩn khai báo RGB, HEX, HSL, RGBA, HSLA.

## Cách sử dụng&#x20;

### Cú pháp

```css
color: value;
```

### Ví dụ

```markup
<h1 style="color:Tomato;">Hello World</h1>
<p style="color:DodgerBlue;">Lorem ipsum...</p>
<p style="color:MediumSeaGreen;">Ut wisi enim...</p>
```

![](<../.gitbook/assets/image (34).png>)

## Các giá trị của color

### Sử dụng tên màu

Trong CSS chúng ta có thể sử dụng tên của màu sắc để quy định giá trị CSS color

```markup
<h1 style="background-color:Tomato;">Tomato</h1>
<h1 style="background-color:Orange;">Orange</h1>
<h1 style="background-color:DodgerBlue;">DodgerBlue</h1>
<h1 style="background-color:MediumSeaGreen;">MediumSeaGreen</h1>
<h1 style="background-color:Gray;">Gray</h1>
<h1 style="background-color:SlateBlue;">SlateBlue</h1>
<h1 style="background-color:Violet;">Violet</h1>
<h1 style="background-color:LightGray;">LightGray</h1>
```

![](<../.gitbook/assets/image (68).png>)

{% hint style="info" %}
Tham khảo danh sách các tên màu hợp lệ [tại đây](https://www.w3schools.com/colors/colors\_names.asp)
{% endhint %}

### Giá trị RGB

#### Tổng quan&#x20;

{% hint style="info" %}
Tất cả các màu sắc đều được cấu thành từ 3 màu chính là:

* R: Red (màu đỏ)
* G: Green (màu xanh lá cây)
* B: Blue (màu xanh lam)
{% endhint %}

Giá trị RGB thể hiện cho giá trị của 3 thành phần này trong màu hiển thị

```css
rgb(red, green, blue)
```

Một số lưu ý khi sử dụng RGB:

* Mỗi tham số (red, green, blue) định nghĩa cường độ màu từ 0 đến 255
* Để biểu diễn màu đen thì giá trị của RGB là rgb(0, 0, 0)
* Để biểu diễn màu trắng thì giá trị của RGB là rgb(255, 255, 255)
* Để biểu diễn màu đỏ thì chúng ta định nghĩa rgb(255, 0, 0), tương tự với xanh lá và xanh dương

#### Ví dụ

```markup
<h2 style="background-color:rgb(255, 0, 0);">rgb(255, 0, 0)</h2>
<h2 style="background-color:rgb(0, 0, 255);">rgb(0, 0, 255)</h2>
<h2 style="background-color:rgb(60, 179, 113);">rgb(60, 179, 113)</h2>
<h2 style="background-color:rgb(238, 130, 238);">rgb(238, 130, 238)</h2>
<h2 style="background-color:rgb(255, 165, 0);">rgb(255, 165, 0)</h2>
<h2 style="background-color:rgb(106, 90, 205);">rgb(106, 90, 205)</h2>
```

![](<../.gitbook/assets/image (20).png>)

#### Giá trị RGBA

Giá trị RGBA cũng tương tự như RGB tuy nhiên có thêm 1 thông số thứ 4 là alpha thể hiện cho alpha channel của màu để quy định độ trong suốt.

```css
rgba(red, green, blue, alpha)
```

Giá trị alpha nằm trong khoảng 0 và 1:

* 0: trong suốt
* 1: Không trong suốt

```markup
<h2 style="background-color:rgba(255, 99, 71, 0);">rgba(255, 99, 71, 0)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.2);">rgba(255, 99, 71, 0.2)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.4);">rgba(255, 99, 71, 0.4)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.6);">rgba(255, 99, 71, 0.6)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.8);">rgba(255, 99, 71, 0.8)</h2>
<h2 style="background-color:rgba(255, 99, 71, 1);">rgba(255, 99, 71, 1)</h2>
```

![](<../.gitbook/assets/image (51).png>)

