---
description: Border dùng để thêm 1 đường viền bao xung quanh phần tử
---

# CSS Border

## Border style

**Border style** dùng để **thay đổi cách hiển thị của border** thông qua thuộc tính `border-style`

### Cú pháp

```css
border-style: value;
```

### Giá trị

<table><thead><tr><th width="160">Giá trị</th><th>Diễn giải</th></tr></thead><tbody><tr><td><code>solid</code></td><td><code>solid</code> là giá trị mặc định, border sẽ có dạng một đường thẳng liền nét  và không bị đứt đoạn</td></tr><tr><td><code>dashed</code></td><td>border được tạo ra bởi các dấu gạch ngang</td></tr><tr><td><code>dotted</code></td><td>border được tạo ra bởi các dấu chấm</td></tr><tr><td><code>double</code></td><td>border được tạo ra bằng 2 border <code>solid</code> nhưng 2 đường này sẽ mỏng hơn và được ngăn cách bởi một khoảng trắng.<br>Độ dày của 2 line border và khoảng trắng là bằng nhau và bằng 1/3 của <a href="css-border.md#border-width">border-width</a></td></tr><tr><td><code>groove</code></td><td><code>groove</code> dịch ra là đường rãnh do đó khi giá trị là <code>groove</code> thì border sẽ có dạng 3d của một chiếc đường rãnh, hiệu ứng sẽ dựa vào màu sắc của thuộc tính <a href="css-border.md#border-color">border-color</a></td></tr><tr><td><code>ridge</code></td><td><code>ridge</code> dịch ra là chóp(tương tự kim tự tháp ai cập) do đó khi giá trị là <code>ridge</code> thì border sẽ có dạng 3d của một hình chóp, hiệu ứng sẽ dựa vào màu sắc của thuộc tính <a href="css-border.md#border-color">border-color</a></td></tr><tr><td><code>inset</code></td><td>Border sẽ tạo ra hiệu ứng đổ bóng, bạn cứ tưởng tượng phần tử giống như một chiếc miệng giếng và ánh sáng sẽ chiếu từ góc <code>bottom-right</code> lên <code>top-left</code>, hiệu ứng sẽ dựa vào màu sắc của thuộc tính <a href="css-border.md#border-color">border-color</a></td></tr><tr><td><code>outset</code></td><td><code>outset</code> cũng sẽ tạo ra hiệu ứng đổ bóng nhưng ánh sáng sẽ chiếu từ góc <code>top-left</code> xuống <code>bottom-right</code> , hiệu ứng sẽ dựa vào màu sắc của thuộc tính <a href="css-border.md#border-color">border-color</a></td></tr><tr><td><code>none</code></td><td>Phần tử sẽ không có đường viền</td></tr><tr><td><code>hidden</code></td><td>Giống <code>none</code> nhưng thường sẽ được dùng cho <code>table</code></td></tr></tbody></table>

### Mix border-style

Một phẩn tử có 4 cạnh do đó chúng ta có thể khai báo từng cạnh một kiểu border theo cú pháp sau:

```css
border-style: top right bottom left;
```

<figure><img src="../.gitbook/assets/image (10) (2).png" alt=""><figcaption></figcaption></figure>

Để dễ hình dung hơn các bạn có thể xem hình dưới khi có kết hợp với **color** và **width**:

<figure><img src="../.gitbook/assets/image (1) (3).png" alt=""><figcaption></figcaption></figure>

## Border-width

Thuộc tính `border-width` dùng để quy định độ dày của 4 cạnh border.

### Cú pháp

#### Gán giá trị border cho cả 4 góc&#x20;

Đây là cú pháp cơ bản nhất khi bạn muốn gán một giá trị `border-width` áp dụng cho cả 4 cạnh, khi đó ta đưa vào cho `border-width` một giá trị duy nhất.

```css
border-width: value;
```

#### Gán giá trị theo từng cạnh

Trong trường hợp chúng ta muốn gán giá trị khác nhau cho từng cạnh cụ thể thì ta sẽ đưa từng giá trị theo cú pháp sau

```css
border-width: top right bottom left;
```

#### Gán giá trị theo trục

Trong trường hợp chúng ta muốn gán giá trị theo trục x hoặc y, chúng ta sẽ khai báo 2 giá trị

```css
border-width: top-bottom right-left;
```

#### Gán giá trị trục x và tuỳ chỉnh trục 2 chiều của trục y

Việc gán giá trị cho trục x và 2 chiều của trục y hay gặp ở các trường hợp style cho các card có chiều `top`, `bottom` và `left-right` khác nhau

```css
border-width: top right-left bottom;
```

<figure><img src="../.gitbook/assets/image (4) (3) (1).png" alt=""><figcaption></figcaption></figure>

### Giá trị

Giá trị của `border-width` có thể là tất cả các giá trị có [đơn vị hợp lệ](broken-reference) hoặc giá trị cấu hình trước: `thin`, `medium`, và `thick`

<figure><img src="../.gitbook/assets/image (2) (4).png" alt=""><figcaption></figcaption></figure>

## Border-color

Thuộc tính `border-color` dùng để quy định màu sắc của 4 cạnh border.

### Cú pháp

#### Gán giá trị color cho cả 4 góc&#x20;

Đây là cú pháp cơ bản nhất khi bạn muốn gán một giá trị `border-color` áp dụng cho cả 4 cạnh, khi đó ta đưa vào cho `border-color` một giá trị duy nhất.

```css
border-color: value;
```

#### Gán giá trị theo từng cạnh

Trong trường hợp chúng ta muốn gán giá trị khác nhau cho từng cạnh cụ thể thì ta sẽ đưa từng giá trị theo cú pháp sau

```css
border-color: top right bottom left;
```

#### Gán giá trị theo trục

Trong trường hợp chúng ta muốn gán giá trị theo trục x hoặc y, chúng ta sẽ khai báo 2 giá trị

```css
border-color: top-bottom right-left;
```

#### Gán giá trị trục x và tuỳ chỉnh trục 2 chiều của trục y

```css
border-width: top right-left bottom;
```

### Giá trị

Giá trị của `border-color` là [các màu hợp lệ](mau-sac-trong-css.md)

<figure><img src="../.gitbook/assets/image (4) (3).png" alt=""><figcaption></figcaption></figure>

## Border sides

Như chúng ta đã biết 1 phần tử sẽ có 4 cạnh và các khai báo phía trên của `border-style`, `border-width`, `border-color` đều có cú pháp để khai báo từng giá trị của cạnh nhưng nếu chỉ khai báo 1 cạnh thì các cú pháp trên đều chưa đáp ứng được.&#x20;

Do đó border sides ra đời cho phép chúng ta khai báo các thuộc tính của border cho một cạnh cụ thể, chi tiết như sau:&#x20;

### Cú pháp

```css
border-top-style: $style-value; // border top style
border-right-style: $style-value; // border right style
border-bottom-style: $style-value; // border bottom style
border-left-style: $style-value; // border left style

border-top-width: $width-value; // border top width
border-right-width: $width-value; // border right width
border-bottom-width: $width-value; // border bottom width
border-left-width: $width-value; // border left width

border-top-color: $color-value; // border top color
border-right-color: $color-value; // border right color
border-bottom-color: $color-value; // border bottom color
border-left-color: $color-value; // border left color
```

### Ví dụ

<figure><img src="../.gitbook/assets/image (2) (1) (2).png" alt=""><figcaption></figcaption></figure>

## CSS Shorthand border

Shorthand border là cú pháp viết tắt giúp cho chúng ta cấu hình `border-style`, `border-width`, `border-color` trong cùng 1 dòng code

### Cú pháp

```css
border: border-width border-style border-color;
```

{% hint style="info" %}
Trong cú pháp này chỉ có `border-style` là bắt buộc còn lại chúng ta có thể bỏ qua miễn sao theo đúng thứ tự là được
{% endhint %}

### Shorthand border với border sides

Chúng ta có cú pháp shortand border cho 1 cạnh như sau:

```css
border-top: border-width border-style border-color; // top
border-right: border-width border-style border-color; // right
border-bottom: border-width border-style border-color; // bottom
border-left: border-width border-style border-color; // left
```

### Ví dụ

<figure><img src="../.gitbook/assets/image (1) (1) (3).png" alt=""><figcaption></figcaption></figure>

## Rounded border(bo góc)

Khi muốn bo tròn border chúng ta sẽ sử dụng `border-radius` để thao tác

### Cú pháp

```css
border-radius: value;
```

{% hint style="info" %}
`Border-radius` sử dụng các [đơn vị hợp lệ](broken-reference) để làm giá trị
{% endhint %}

{% hint style="info" %}
khi muốn bo tròn luôn ta sẽ gán giá trị `border-radius: 9999px;`
{% endhint %}
