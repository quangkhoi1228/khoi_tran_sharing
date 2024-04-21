# CSS Flexbox

## **Giới thiệu về Flexbox**

CSS Flexible Box Layout (hay còn gọi là Flexbox) là một công cụ mạnh mẽ cho việc xây dựng bố cục linh hoạt và đáp ứng trong thiết kế web. Với Flexbox, bạn có thể dễ dàng điều chỉnh và điều hướng các phần tử HTML theo các hướng khác nhau mà không cần sử dụng các kỹ thuật truyền thống như float hoặc position.

## **Các thuộc tính cơ bản của Flexbox**

#### 1. `display: flex;`

Thuộc tính `display: flex;` biến một container thành một flex container và các phần tử con bên trong sẽ trở thành các flex item. Điều này cho phép bạn sử dụng các thuộc tính Flexbox khác để điều chỉnh bố cục.

**Ví dụ:**

```css
.container {
  display: flex;
}
```

#### 2. `flex-direction`

Thuộc tính `flex-direction` xác định hướng các flex item trong flex container.

* `row`: Các phần tử con sẽ được sắp xếp theo chiều ngang từ trái sang phải (mặc định).
* `row-reverse`: Các phần tử con sẽ được sắp xếp theo chiều ngang từ phải sang trái.
* `column`: Các phần tử con sẽ được sắp xếp theo chiều dọc từ trên xuống dưới.
* `column-reverse`: Các phần tử con sẽ được sắp xếp theo chiều dọc từ dưới lên trên.

**Ví dụ:**

```css
.container {
  flex-direction: column;
}
```

#### 3. `justify-content`

Thuộc tính `justify-content` xác định cách phân phối các flex item theo hướng trục chính của flex container.

* `flex-start`: Các flex item sẽ được căn bên trái (hoặc bên trên theo trục dọc).
* `flex-end`: Các flex item sẽ được căn bên phải (hoặc bên dưới theo trục dọc).
* `center`: Các flex item sẽ được căn giữa.
* `space-between`: Các flex item sẽ được phân bố sao cho khoảng cách giữa chúng là như nhau, và cạnh mép đầu và cuối sẽ giữ khoảng trống.
* `space-around`: Các flex item sẽ được phân bố sao cho khoảng cách giữa chúng và cạnh mép đầu và cuối đều là như nhau.

**Ví dụ:**

```css
.container {
  justify-content: center;
}
```

#### 4. `align-items`

Thuộc tính `align-items` xác định cách phân phối các flex item theo hướng trục phụ của flex container.

* `flex-start`: Các flex item sẽ được căn lề đầu (trên cùng nếu theo trục dọc).
* `flex-end`: Các flex item sẽ được căn lề cuối (dưới cùng nếu theo trục dọc).
* `center`: Các flex item sẽ được căn giữa theo trục phụ.
* `baseline`: Các flex item sẽ được căn theo baseline của chúng.
* `stretch`: Các flex item sẽ căn theo chiều dài tối đa của flex container.

**Ví dụ:**

```css
.container {
  align-items: center;
}
```

#### 5. `flex`

Thuộc tính `flex` xác định tỷ lệ mở rộng của các flex item so với nhau.

**Ví dụ:**

```css
.item {
  flex: 1; /* mọi flex item có cùng kích thước */
}
```

#### 6. `flex-wrap`

Thuộc tính `flex-wrap` xác định xem các flex item có được phép xuống dòng hay không.

* `nowrap`: Các flex item sẽ không được phép xuống dòng.
* `wrap`: Các flex item sẽ được phép xuống dòng nếu cần.
* `wrap-reverse`: Các flex item sẽ được phép xuống dòng theo chiều ngược lại.

**Ví dụ:**

```css
.container {
  flex-wrap: wrap;
}
```

Đây là một số ví dụ cơ bản về cách sử dụng các thuộc tính cơ bản của Flexbox. Bạn có thể kết hợp chúng để tạo ra các bố cục phức tạp hơn.

## **Thực hành**

Hãy xem xét một ví dụ cụ thể về việc sử dụng Flexbox để tạo một bố cục linh hoạt:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flexbox Example</title>
  <style>
    .flex-container {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
    }
    .flex-item {
      width: 100px;
      height: 100px;
      background-color: #3498db;
      margin: 10px;
    }
  </style>
</head>
<body>
  <div class="flex-container">
    <div class="flex-item"></div>
    <div class="flex-item"></div>
    <div class="flex-item"></div>
  </div>
</body>
</html>
```

**IV. Kết luận**

Flexbox là một công cụ mạnh mẽ để tạo bố cục linh hoạt trong thiết kế web. Bằng cách hiểu và sử dụng các thuộc tính cơ bản của nó, bạn có thể tạo ra giao diện web hiệu quả và dễ bảo trì.
