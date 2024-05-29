---
description: >-
  CSS spacing dùng để chỉ các thuộc tính giúp tăng khoảng cách của các thành
  phần trong phần tử hoặc giữa các phần tử với nhau
---

# CSS Spacing

## CSS Margin

**Margin** dùng để **tạo một khoảng cách bao xung quanh phần tử tính từ border**, hiểu đơn giản `margin` **là khoảng cách lề** của phần tử

{% hint style="info" %}
**Margin** sử dụng tất cả các giá trị có [đơn vị hợp lệ](broken-reference)
{% endhint %}

### Cú pháp&#x20;

Với CSS chúng ta có thể cấu hình `margin` cho từng cạnh hoặc có thể tuỳ chỉnh tất cả cùng lúc bằng cú pháp shorthand

```css
margin-top: value;
margin-bottom: value;
margin-right: value;
margin-left: value;

# shorthand
margin: all-side-value; 
margin: top-bottom right-left;
margin: top left-right bottom;
margin: top right bottom left;
```

### Ví dụ

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

### Margin: auto

Khi sử dụng `margin: auto;` phần tử sẽ tự động canh giữa phần tử container chứa nó theo chiều ngang.

Khoảng cách sẽ chia đều bên trái và bên phải của phần tử

```css
margin: auto;
```

<figure><img src="../.gitbook/assets/image (2) (3).png" alt=""><figcaption></figcaption></figure>

### Margin: inherit

Khi gán giá trị `margin: inherit` phần tử sẽ thừa hưởng giá trị `margin` từ thẻ cha của mình.

Trong ví dụ này class `ex1` có `margin-left 100px` giống với thẻ `div`(thẻ cha của `ex1`)

<figure><img src="../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

### Margin Collapse

Khi 2 phần tử kế nhau đều có khai báo `margin` của mình và 2 khai báo này đè lên nhau thì đôi khi sẽ có trường hợp 2 phần tử này sẽ cách nhau với khoảng cách đúng bằng khoảng cách margin của phần tử có margin khai báo lớn hơn.&#x20;

{% hint style="info" %}
Trường hợp này chỉ xảy ra cho trường hợp top-bottom chứ không có left-right
{% endhint %}

Ở đây chúng ta thấy `h1` có `margin-bottom: 50px` còn `h2` có `margin-top: 20px`. Lúc này cả 2 sẽ cách nhau 1 khoảng bằng `50px`(phần màu vàng) chứ không phải bằng `70px` hoặc bằng `20px` ==> trường hợp này chính là **Margin collapse**.

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

## CSS Padding

**Padding** dùng để tạo **1 khoảng cách nằm giữa nội dung và border** của phần tử. Nói cách khác `padding` chính **là khoảng cách biên** của phần tử.

{% hint style="info" %}
`Padding` sử dụng tất cả các giá trị có [đơn vị hợp lệ](broken-reference)
{% endhint %}

### Cú pháp&#x20;

Với CSS chúng ta có thể cấu hình `padding` cho từng cạnh hoặc có thể tuỳ chỉnh tất cả cùng lúc bằng cú pháp shorthand

```css
padding-top: value;
padding-bottom: value;
padding-right: value;
padding-left: value;

# shorthand
padding: all-side-value; 
padding: top-bottom right-left;
padding: top left-right bottom;
padding: top right bottom left;
```

### Ví dụ

<figure><img src="../.gitbook/assets/image (3) (3).png" alt=""><figcaption></figcaption></figure>
