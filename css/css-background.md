---
description: Trong bài này chúng ta sẽ tìm hiểu về các thuộc tính liên quan đến background
---

# CSS Background

{% hint style="info" %}
**Các thuộc tính Background** dùng để **cấu hình hình nền** cho **các phần tử trong trang**. Trong bài này chúng ta sẽ học các thuộc tính sau:

* `background-color`
* `background-image`
* `background-repeat`
* `background-position`
* `background-attachment`
* `background` (shorthand property)
{% endhint %}

## Background-color

Thuộc tính `background-color` **quy định màu nền của một phần tử**.

### Cú pháp

```css
background-color: value;
```

### Ví dụ

```css
body {
  background-color: red;
}
```

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Giá trị của `background-color` là các [Màu sắc trong CSS](mau-sac-trong-css.md)
{% endhint %}

{% hint style="info" %}
`background-color` bị ảnh hưởng bởi [`opacity`](https://app.gitbook.com/s/-MC5-BglfKHq4hM84twh/\~/changes/PH4IuTiLOf69YLLByT9o/css/css-opacity)``
{% endhint %}

## Background-image

Thuộc tính `background-image` **quy định ảnh nền** của **một phần tử bằng một hình ảnh**.

**Mặc định ảnh nền** sẽ **lặp lại** để làm sao **bao phủ toàn bộ phần tử**.

### Cú pháp

```css
background-image: url(image-url);
```

### Ví dụ

```css
body {
  background-image: url("paper.gif");
}
```

<figure><img src="../.gitbook/assets/image (11) (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Khi sử dụng **hình ảnh làm hình nền** thì nên **tránh** các ảnh nền **có màu sắc làm rối nội dung** của trang
{% endhint %}

<figure><img src="../.gitbook/assets/image (2) (3).png" alt=""><figcaption></figcaption></figure>

## Background-repeat

### Cú pháp

```css
background-repeat: value;
```

### Bài toán

Mặc định `background-image` sẽ tự động lặp lại theo chiều ngang và chiều dọc để có thể bao phủ được hết phần tử tuy nhiên trong một vài trường hợp ảnh nền chỉ được lặp lại theo 1 trong 2 chiều vì chiều còn lại đã đủ kích thước gây ra kết quả chúng ta không mong muốn lắm như ảnh dưới.

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

Trong trường hợp này nếu ảnh có thể lặp lại theo chiều ngang có thể sẽ ổn hơn, lúc này ta sẽ dùng `background-repeat: repeat-x;` để thực hiện yêu cầu này.

<figure><img src="../.gitbook/assets/image (1) (3) (1).png" alt=""><figcaption></figcaption></figure>

### Repeat

Giá trị `background-repeat: repeat;` là **giá trị mặc định**, giá trị này sẽ làm cho hình nền **lặp lại theo cả chiều ngang và dọc**.

```css
body {
  background-image: url("img_tree.png");
  background-repeat: repeat;
}
```

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

### No-repeat

Giá trị `background-repeat: no-repeat;` sẽ làm cho hình nền sẽ **hiển thị 1 lần** và **không lặp lại theo hướng nào cả**.

```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
}
```

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

### Repeat-x

Giá trị `background-repeat: repeat-x;` sẽ làm cho hình nền **lặp lại theo chiều ngang (trục x).**

```css
body {
  background-image: url("img_tree.png");
  background-repeat: repeat-x;
}
```

<figure><img src="../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

### Repeat-y

Giá trị `background-repeat: repeat-y;`  sẽ làm cho hình nền **lặp lại theo chiều dọc (trục y).**

```css
body {
  background-image: url("img_tree.png");
  background-repeat: repeat-y;
}
```

<figure><img src="../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

### Space

Giá trị `background-repeat: space;`  cũng khá giống với `repeat` được liệt kê như sau:

* Giống:
  * Cả `repeat` và `space` đều **lặp theo 2 chiều.**
* Khác:
  * `Space` sẽ cố gắng lặp nhiều nhất có thể nhưng sẽ **không làm cho hình bị cắt xén**(mất một phần)
  * Sau khi cố gắng xong thì **khoảng trắng** sẽ được **chia đều giữa các hình nền được lặp**

```css
body {
  background-image: url("img_tree.png");
  background-repeat: space;
}
```

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

### Round

Giá trị `background-repeat: round;` cũng khá giống với `space` về việc ảnh nền sẽ không bị cắt nhưng khác `space` ở chỗ ảnh nền khi `round` **sẽ bị kéo dài, thu nhỏ để không còn khoảng trống nào**.

```css
body {
  background-image: url("img_tree.png");
  background-repeat: round;
}
```

<figure><img src="../.gitbook/assets/image (6) (2).png" alt=""><figcaption></figcaption></figure>

## Background-position

Thuộc tính `background-position` dùng để quy định **vị trí của ảnh nền**.

### Cú pháp

```css
background-position: value;
```

### Ví dụ

```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-position: right top;
}
```

<figure><img src="../.gitbook/assets/image (11) (3).png" alt=""><figcaption></figcaption></figure>

### Giá trị

| Giá trị                                                                                                                                                                                                                                                         | Mô tả                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p><code>left top</code><br><code>left center</code><br><code>left bottom</code><br><code>right top</code><br><code>right center</code><br><code>right bottom</code><br><code>center top</code><br><code>center center</code><br><code>center bottom</code></p> | <p>Chúng ta có thể sử dụng tên để đặt giá trị.</p><p></p><p>Nếu có duy nhất một giá trị, giá trị còn lại mặc định là <code>center</code> </p>                                                                                                                                                                                                                                                                                                                                                                |
| _x% y%_                                                                                                                                                                                                                                                         | <p>Chúng ta có thể dùng đơn vị % để gán giá trị.</p><p></p><p>Giá trị đầu tiên là vị trí theo trục x và giá trị thứ 2 là theo trục y.</p><ul><li>Góc top left là 0% 0% </li><li>Góc right bottom là 100% 100%</li><li>Nếu chỉ có 1 giá trị thì giá trị còn lại mặc định là 50%</li><li>Mặc định giá trị là 0% 0%</li></ul>                                                                                                                                                                                   |
| _xpos ypos_                                                                                                                                                                                                                                                     | <p>Chúng ta có thể sử dụng đơn vị tuyệt đối để làm giá trị </p><p></p><p>Giá trị đầu tiên là vị trí theo trục x và giá trị thứ 2 là theo trục y.</p><ul><li>Góc top left là 0 0</li><li>Đơn vị  có thể là px hoặc bất cứ <a href="https://app.gitbook.com/s/-MC5-BglfKHq4hM84twh/~/changes/hgI8rSryYsZI6EeXv0xS/css/don-vi-do-unit-trong-css">đơn vị hợp lệ</a> nào.</li><li>Nếu chỉ có 1 giá trị thì giá trị còn lại mặc định là 50%</li><li>Bạn có thể phối hợp % và giá trị tuyệt đối với nhau.</li></ul> |
|                                                                                                                                                                                                                                                                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

## Background-attachment

Trong một vài trường hợp nội dung dài thì trình duyệt sẽ xuất hiện một thanh cuộn, lúc này mặc định ảnh nền sẽ tự động chạy theo nội dung khi cuộn. Để giữ cho ảnh nền đứng yên khi cuộn lúc này chúng ta dùng thuộc tính `background-attachment` dùng để quy định background sẽ cuộn theo nội dung hay sẽ đứng yên khi nội dung di chuyển.

### Cú pháp

```css
background-attachment: value;
```

### Scroll

```css
background-attachment: scroll;
```

Giá trị mặc định, ảnh nền sẽ cuộn theo nội dung

<figure><img src="../.gitbook/assets/postion-attachment-scroll.gif" alt=""><figcaption></figcaption></figure>

### Fixed

```css
background-attachment: fixed;
```

Background sẽ đứng yên khi cuộn nội dung

<figure><img src="../.gitbook/assets/posiotion-attachment-fixed.gif" alt=""><figcaption></figcaption></figure>

## Background shorthand&#x20;

Cú pháp **shorthand** hay viết tắt giúp chúng ta **viết nhiều cấu hình về background** cho một phần tử cùng lúc **thay vì chúng ta viết từng thuộc tính riêng biệt**.&#x20;

### Ví dụ

Thay vì viết

```css
body {
  background-color: #ffffff;
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-position: right top;
}
```

Chúng ta có thể viết tắt như sau:

```css
body {
  background: #ffffff url("img_tree.png") no-repeat right top;
}
```

### Cú pháp

{% code overflow="wrap" %}
```css
background: background-color background-image background-repeat 
    background-attachment background-position;
```
{% endcode %}

{% hint style="info" %}
Chúng ta có thể viết thiếu giá trị cho một vài thuộc tính miễn là theo đúng thứ tự được quy định theo cú pháp
{% endhint %}

{% hint style="info" %}
Thuộc tính `background-attachment` sẽ không áp dụng được trong cú pháp shorthand
{% endhint %}
