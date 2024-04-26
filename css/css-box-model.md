# CSS Box Model

## Giới thiệu về CSS Box Model

#### CSS Box Model là gì?

CSS Box Model là một khái niệm cơ bản trong CSS, quy định cách mà các phần tử HTML được cấu trúc và hiển thị trên trình duyệt. Box Model bao gồm các thành phần: Content, Padding, Border và Margin.

<figure><img src="../.gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure>

### Các thành phần trong CSS Box Model

#### 1. Content (Nội dung)

Là phần chứa nội dung của phần tử HTML, được xác định bởi `width` (chiều rộng) và `height` (chiều cao).

```html
<div class="content-box">
  Nội dung của box.
</div>
```

```css
.content-box {
  width: 200px;
  height: 100px;
  background-color: lightblue;
}
```

#### 2. Padding

Là khoảng cách giữa nội dung và đường viền, xác định bằng thuộc tính `padding`.

```html
<div class="padding-box">
  Nội dung với padding.
</div>
```

```css
.padding-box {
  width: 200px;
  height: 100px;
  background-color: lightblue;
  padding: 20px;
}
```

#### 3. Border

Là đường viền xung quanh phần tử, xác định bằng thuộc tính `border`.

```html
<div class="border-box">
  Nội dung với border.
</div>
```

```css
.border-box {
  width: 200px;
  height: 100px;
  background-color: lightblue;
  padding: 20px;
  border: 2px solid black;
}
```

#### 4. Margin

Là khoảng cách giữa đường viền của phần tử và các phần tử khác, xác định bằng thuộc tính `margin`.

```html
<div class="margin-box">
  Nội dung với margin.
</div>
```

```css
.margin-box {
  width: 200px;
  height: 100px;
  background-color: lightblue;
  padding: 20px;
  border: 2px solid black;
  margin: 20px;
}
```

### Bài tập thực hành

1. Tạo một trang web đơn giản chứa một số phần tử HTML và áp dụng CSS Box Model để căn chỉnh chúng.
2. Thay đổi kích thước, màu sắc và kiểu border của các phần tử để thấy được sự ảnh hưởng của CSS Box Model.
3. Tạo một layout đơn giản sử dụng CSS Box Model để sắp xếp các phần tử trên trang theo ý muốn của bạn.
