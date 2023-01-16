---
description: Trong bài này chúng ta sẽ tìm hiểu về các giá trị màu và ứng dụng của chúng
---

# Màu sắc trong CSS

## Tổng quan

**Màu sắc** là một phần **rất quan trọng trong CSS** cùng với việc thiết kế layout để **tạo ra sự khác biệt giữa các trang web** với nhau. Việc hiểu rõ màu sắc giúp chúng ta có thể nắm được khái niệm và cách khai báo giá trị của chúng

## Các giá trị của màu sắc

### Sử dụng tên màu

Trong CSS chúng ta có thể sử dụng **tên của màu sắc** để quy định giá trị CSS color

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
**Tất cả các màu sắc** đều được cấu thành từ **3 màu chính** là:

* **R**: Red (màu đỏ)
* **G**: Green (màu xanh lá cây)
* **B**: Blue (màu xanh lam)
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

### Giá trị RGBA

#### Tổng quan

**Giá trị RGBA** cũng **tương tự như RGB** tuy nhiên **có thêm 1 thông số thứ 4 là alpha** thể hiện cho alpha channel của màu để **quy định độ trong suốt**.

```css
rgba(red, green, blue, alpha)
```

Giá trị alpha nằm trong khoảng 0 và 1:

* **0**: trong suốt
* **1**: Không trong suốt

#### Ví dụ

```markup
<h2 style="background-color:rgba(255, 99, 71, 0);">rgba(255, 99, 71, 0)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.2);">rgba(255, 99, 71, 0.2)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.4);">rgba(255, 99, 71, 0.4)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.6);">rgba(255, 99, 71, 0.6)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.8);">rgba(255, 99, 71, 0.8)</h2>
<h2 style="background-color:rgba(255, 99, 71, 1);">rgba(255, 99, 71, 1)</h2>
```

![](<../.gitbook/assets/image (51).png>)

{% hint style="info" %}
Thuộc tính alpha này khá hữu dụng trong thực tế để thiết kế các trang web có background có độ mờ ảo hoặc làm hiệu ứng animation
{% endhint %}

### Giá trị HEX

#### Tổng quan

Màu có **giá trị HEX** cũng **khá giống với màu RGB** về việc màu sắc cũng được cấu thành từ 3 giá trị màu Red, Green, Blue tuy nhiên thay vì tách nhau bằng dấu phẩy thì màu **giá trị HEX sẽ viết dính liền nhau** và chúng ta cũng có 2 cú pháp như sau:&#x20;

* Giá trị HEX có **7 ký tự** (6-digit HEX)

```css
#RRGGBB
```

* Giá trị HEX có **4 ký tự** hay còn gọi là "3 Digit HEX"

```css
#RGB
```

#### Giá trị HEX có 7 ký tự

Đây là cách viết cơ bản thể hiện theo quy tắc như sau:

* Dấu `#` thể hiện đây là giá trị màu color HEX
* ký tự 2,3 thể hiển màu red
* Ký tự 4,5 thể hiện màu green
* Ký tự 6,7 thể hiện màu blue

![](<../.gitbook/assets/image (4) (1).png>)![](<../.gitbook/assets/image (1) (2).png>)

{% hint style="info" %}
Để thể hiện **màu đen** ta dùng giá trị `00` --> `#000000`

Để thể hiện **màu trắng** ta dùng giá trị `ff` --> `#ffffff`
{% endhint %}

#### Giá trị HEX 4 ký tự (3 Digit HEX Value)

Giá trị HEX có 4 ký tự là **cú pháp viết tắt của cú pháp 7 ký tự** trong đó:

* Dấu `#` thể hiện giá trị HEX
* ký tự 2 thể hiện màu red
* Ký tự 3 thể hiện màu green
* Ký tự 4 thể hiện màu blue

```css
body {
  background-color: #fc9; /* same as #ffcc99 */
}

h1 {
  color: #f0f; /* same as #ff00ff */
}

p {
  color: #b58; /* same as #bb5588 */
}
```

### Giá trị HSL

#### Tổng quan

**HSL** viết tắt của HSL **hue**, **saturation**, và **lightness**

Giá trị HSL được biểu diễn theo cú pháp:

```css
hsl(hue, saturation, lightness)
```

Trong đó:

1. **Hue** biểu diễn **màu sắc** được biểu điễn theo dạng một bánh xe màu từ 0 --> 360 độ.&#x20;
   1. 0 là màu red
   2. 120 là green
   3. 240 là blue
2. **Saturation** là **độ bão hoà** thể hiện mức độ đậm nhạt của màu sắc từ 0% --> 100%
   1. 0% là một mảng màu xám&#x20;
   2. 100% là thể hiện màu đậm nhất
3. Lightness là **độ sáng** thể hiện mức độ sáng tối của màu
   1. 0% nghĩa là màu sẽ là màu đen
   2. 100% nghĩa là màu sẽ có màu trắng

Các bạn có thể tham khảo hình sau để dễ hình dung hơn:

![](<../.gitbook/assets/image (13).png>)

#### Ví dụ:

<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

### Giá trị HSLA

#### Tổng quan&#x20;

Giá trị **HSLA** t**ương tự như HSL** tuy nhiên có **thêm 1 giá trị alpha** thứ 4 để **biểu diễn độ trong suốt** của màu:

```css
hsla(hue, saturation, lightness, alpha)
```

{% hint style="info" %}
Giá trị Alpha có giá trị từ 0 --> 1

* Với 0 là màu trong suốt hoàn toàn
* Với 1 là màu không có độ trong suốt nào
{% endhint %}

<figure><img src="../.gitbook/assets/image (5) (2).png" alt=""><figcaption></figcaption></figure>

