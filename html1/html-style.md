---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu cách thay đổi hiển thị của phần tử trong
  trang bằng thuộc tính style của thẻ HTML
---

# HTML Style

## HTML style là gì? <a href="#html-styles" id="html-styles"></a>

`style` là thuộc tính của HTML được sử dụng để trang trí một phần tử, chẳng hạn như màu sắc, phông chữ, kích thước của phần tử đó.

Cú pháp:

```markup
 <tagname style="property:value;">
```

`Property` là 1 `CSS property‌`

`Value` là 1 `Css value‌`

Ví dụ:

```markup
<h1 style="background-color:powderblue;">This is a heading</h1>
<p style="background-color:tomato;">This is a paragraph.</p>
```

‌

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GimvGV1q5eQaXL%2F1.png?alt=media)

## Một số thuộc tính cơ bản <a href="#html-javascript" id="html-javascript"></a>

### Background-color

Thuộc tính `background-color` định nghĩa màu nền của một phần tử

```markup
<body style="background-color:powderblue;">

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
```

### Color

Thuộc tính `color` quy định màu chữ của một phần tử

```markup
<h1 style="color:blue;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>
```

### Font-family

Thuộc tính `font-family` quy định font chữ của phần tử

```markup
<h1 style="font-family:verdana;">This is a heading</h1>
<p style="font-family:courier;">This is a paragraph.</p>
```

### Font-size

Thuộc tính `font-size` quy định kích cỡ chữ của phần tử

```markup
<h1 style="font-size:300%;">This is a heading</h1>
<p style="font-size:160%;">This is a paragraph.</p>
```

### Text-align

Trong CSS, thuộc tính `text-align` được sử dụng để điều chỉnh vị trí ngang của nội dung trong một phần tử HTML. Thuộc tính này có thể được áp dụng cho các phần tử chứa nội dung văn bản như đoạn văn, tiêu đề, đoạn mã, và nhiều phần tử khác.

Có các giá trị sau cho thuộc tính `text-align`:

1. `left`: Căn lề văn bản về phía trái.
2. `right`: Căn lề văn bản về phía phải.
3. `center`: Căn lề văn bản ra giữa.
4. `justify`: Căn đều cả hai mép của văn bản, tạo ra các đoạn văn bản có độ dài các dòng bằng nhau.
5. `initial`: Thiết lập giá trị mặc định của thuộc tính.
6. `inherit`: Kế thừa giá trị của thuộc tính từ phần tử cha.

Ví dụ:

```css
p {
  text-align: center;
}

h1 {
  text-align: right;
}
```

Trong ví dụ trên, tất cả các đoạn văn bản trong thẻ `<p>` sẽ được căn giữa, còn các tiêu đề `<h1>` sẽ được căn lề về phía phải.

### **Margin**

Thuộc tính `margin` được sử dụng để tạo ra khoảng cách giữa các phần tử và phần tử xung quanh. Khoảng cách này là khoảng trống không gian ở bên ngoài phần tử và có thể ảnh hưởng đến việc xếp chồng các phần tử lên nhau hoặc cách chúng tương tác.

Có thể áp dụng các giá trị cho `margin` như sau:

* `margin-top`: Khoảng cách từ phía trên.
* `margin-right`: Khoảng cách từ phía phải.
* `margin-bottom`: Khoảng cách từ phía dưới.
* `margin-left`: Khoảng cách từ phía trái.

Ví dụ:

```css
div {
  margin: 10px; /* Áp dụng margin 10px cho tất cả các phía của phần tử div */
  margin-top: 20px; /* Áp dụng margin 20px cho phía trên của phần tử div */
}
```

### **Padding**

Thuộc tính `padding` được sử dụng để tạo khoảng cách giữa nội dung của phần tử và viền ngoài cùng của phần tử đó. Khoảng cách này ảnh hưởng đến khoảng cách giữa nội dung và các phần tử xung quanh.

Cũng tương tự như `margin`, `padding` cũng có các giá trị áp dụng cho từng phía của phần tử:

* `padding-top`: Khoảng cách từ phía trên.
* `padding-right`: Khoảng cách từ phía phải.
* `padding-bottom`: Khoảng cách từ phía dưới.
* `padding-left`: Khoảng cách từ phía trái.

Ví dụ:

```css
div {
  padding: 15px; /* Áp dụng padding 15px cho tất cả các phía của phần tử div */
  padding-left: 30px; /* Áp dụng padding 30px cho phía trái của phần tử div */
}
```

### Border

`border` là một thuộc tính được sử dụng để thêm viền vào xung quanh phần tử HTML. Viền này bao gồm các đường đẻo theo các cạnh của phần tử, tạo ra một ranh giới xác định giữa phần tử và các phần tử xung quanh hoặc để tạo ra mục tiêu thẩm mỹ.

Cú pháp cơ bản của thuộc tính `border` là:

```css
element {
  border: [border-width] [border-style] [border-color];
}
```

Trong đó:

* `[border-width]` xác định độ dày của viền, có thể là giá trị như `1px`, `2px`,...
* `[border-style]` xác định kiểu viền, có thể là `solid` (đường thẳng liền), `dotted` (chấm), `dashed` (đường nét đứt), v.v.
* `[border-color]` xác định màu sắc của viền, có thể là tên màu hoặc mã màu.

Ví dụ:

```css
div {
  border: 2px solid #000;
}
```

Trong ví dụ trên, một viền độ dày 2px, kiểu `solid`, và màu đen (#000) sẽ được thêm vào xung quanh phần tử `<div>`.

Ngoài ra, bạn cũng có thể điều chỉnh các phần tử viền riêng lẻ như sau:

```css
div {
  border-top: 1px dashed #999;
  border-right: 2px dotted #555;
  border-bottom: 1px solid #333;
  border-left: 0;
}
```

Trong ví dụ này, mỗi cạnh của phần tử `<div>` sẽ có một loại viền, một màu sắc và một độ dày riêng biệt.





{% hint style="info" %}
Chi tiết các thuộc tính tham khảo thêm ở đây: [https://cssreference.io/](https://cssreference.io/)
{% endhint %}
