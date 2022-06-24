---
description: >-
  Trong bài này chúng ta sẽ tìm hiểu về HTML layout, các cách để thực hiện HTML
  layout và cách sử dụng chúng.
---

# HTML Layout

## HTML Layout <a href="#html-layout" id="html-layout"></a>

**HTML layout** là một thuật ngữ nói về việc **bố cục các phần tử HTML được sắp xếp trong trang**. Trong  **trang web thường hiển thị** nội dung **theo nhiều phần và mỗi phần có nhiều cột‌.**&#x20;

Ví dụ về trang youtube được bố trí theo hàng và cột

![](https://gblobscdn.gitbook.com/assets%2Fwelcome-to-my-site%2F-MXvWNSrLk9ygm1zzKIA%2F-MXvX7GlAbXJ8w3E\_D9G%2F4.png?alt=media)

## Phần tử HTML layout <a href="#phan-tu-html-layout" id="phan-tu-html-layout"></a>

**HTML** có 1 vài **phần tử ngữ nghĩa** dùng để **định nghĩa sự khác nhau** giữa các **phần trong trang web**

![](<../.gitbook/assets/image (2) (2).png>)

Trong đó:

* `<header>` - định nghĩa một **header cho một trang** hoặc một **phần**
* `<nav>` - Định nghĩa một **bộ các đường dẫn điều hướng**
* `<section>` - định nghĩa **một phần của văn bản**
* `<article>` - định nghĩa **một phần tử độc lập** hoặc **phần tử chứa nội dung**
* `<aside>` - Định nghĩa **nội dung nằm ngoài nội dung chính**(như là một thanh bên - sidebar )
* `<footer>` - định nghĩa **phần chân của trang** hoặc **một phần của trang**
* `<details>` - định nghĩa một phần **nội dung chi tiết**, người dùng **có thể mở hoặc đóng tùy nhu cầu**
* `<summary>` - định nghĩa **phần đầu** của thẻ `<details>`

Có thể xem thêm các thẻ khác tại đây [HTML Semantics](https://www.w3schools.com/html/html5\_semantic\_elements.asp)



## Kỹ thuật chia Layout <a href="#ky-thuat-chia-layout" id="ky-thuat-chia-layout"></a>

Có 4 kỹ thuật chính để tạo layout có nhiều cột, mỗi cách đều có ưu và nhược điểm khác nhau:‌

* CSS framework
* CSS float property
* CSS flexbox
* CSS grid

## CSS framework

### CSS framework là gì?

**CSS framework** dùng để chỉ c**ác bộ CSS được định nghĩa sẵn cung cấp các tính năng** như định nghĩa các component như nút, tiêu đề, header, card,... hoặc cung cấp tính năng responsive. Chúng **được đưa vào thành một hoặc nhiều file CSS** - được gọi là **CSS framework**.

Khi sử dụng CSS framework chúng ta chỉ đơn giản là gọi ra các CSS được định nghĩa sẳn và sử dụng từ đó dẫn đến tốc độ phát triển giao diện của chúng ta sẽ tăng lên.

#### Ưu điểm

Tốc độ phát triển nhanh hơn do các tính năng đã được viết sẵn

* Hạn chế code lặp lại&#x20;
* Các framework đã được đông đảo developer sử dụng nên hạn chế các lỗi phát sinh
* Chức năng ngày càng được phát triển nhiều hơn

#### Nhược điểm

Framework thường có kích thước lớn dẫn đến việc trang bị nặng hơn khi load

* Muốn thành thạo framework thì cần rất nhiều thời gian
* Các framework đều có quy tắc lõi nhất định do đó không thể sửa đổi

### Một số CSS framework phổ biến

Hiện nay có một số CSS framework được sử dụng phổ biến như:

* Bootstrap
* Tailwind
* Bulma
* Ant design
* ...

## CSS float layout

### Float layout là gì?

**Float layout** được hiểu là việc chúng ta **sử dụng thuộc tính `float` của CSS** để **quy định phần tử thể hiện trên trang.**&#x20;

#### Ưu điểm

* Thuộc tính `float` rất đơn giản để học, các bạn chỉ cần nắm rõ quy tắc sử dụng thuộc tính `float` và `clear` được.&#x20;

#### Nhược điểm

* khi phần tử sử dụng thuộc tính `float` vẫn bị ảnh hưởng bởi nội dung của thẻ do đó có thể ảnh hưởng đến sự linh hoạt của bố cục trang.

### Cách sử dụng

{% hint style="info" %}
Các bạn tham khảo thêm phần CSS float và CSS clear để hiểu rõ hơn phần này.
{% endhint %}

Thuộc tính `float` của CSS có nhiệm vụ **dồn các phần tử được gán thuộc tính** `float` **sang bên trái hay phải dựa theo `value` được cấu hình là `left` hay `right`**

## CSS flexbox layout

### CSS flexbox layout là gì?

`CSS flexbox layout` được hiểu là chúng ta sử dụng thuộc tính CSS để có thể đoán trước được cách các phần tử thể hiện trên trang và chúng sẽ bị ảnh hưởng bởi kích thước màn hình từ đó chúng ta có thể xây dựng các trang web.&#x20;

### Cách sử dụng

{% hint style="info" %}
CSS flexbox là một phần rất lớn do đó các bạn nên tham khảo phần CSS về flexbox để hiểu rõ hơn
{% endhint %}

## CSS grid layout

### CSS grid layout là gì?

**CSS grid layout** là một kĩ thuật dựa trên việc **chia trang web thành các hàng và cột** từ đó chúng ta có thể chia bố cục cột cách rõ ràng mà **không cần dùng đến thuộc tính** `float` **hay** `position`.

### Cách sử dụng

{% hint style="info" %}
CSS grid là một phần rất lớn do đó các bạn nên tham khảo phần CSS về grid để hiểu rõ hơn
{% endhint %}
