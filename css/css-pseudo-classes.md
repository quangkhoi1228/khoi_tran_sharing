# CSS Pseudo-classes

## CSS Pseudo-classes

### Pseudo-classes là gì?

Pseudo-classes là các lớp ảo trong CSS được sử dụng để áp dụng các kiểu dáng hoặc hiệu ứng cho các phần tử trong một trạng thái hoặc tình huống cụ thể, mà không cần sử dụng JavaScript. Các pseudo-classes thường được kí hiệu bằng ký tự hai chấm (`:`) sau tên của phần tử hoặc lớp.

### Các Pseudo-classes phổ biến

#### 1. :hover

Pseudo-class `:hover` được kích hoạt khi con trỏ chuột di chuyển qua phần tử.

```css
.button:hover {
  background-color: #ff0000; /* Màu nền đỏ khi hover */
}
```

#### 2. :active

Pseudo-class `:active` được kích hoạt khi phần tử đang được nhấn bằng chuột hoặc bàn phím.

```css
.button:active {
  transform: translateY(2px); /* Dịch chuyển phần tử xuống 2px khi được nhấn */
}
```

#### 3. :focus

Pseudo-class `:focus` được kích hoạt khi phần tử đang được trỏ đến hoặc tập trung vào bằng bàn phím.

```css
.input:focus {
  border-color: #00ff00; /* Viền của input sẽ có màu xanh khi được focus */
}
```

### Bài tập thực hành

1. Tạo một nút hoặc phần tử HTML và áp dụng pseudo-class `:hover` để thay đổi kiểu dáng của nó khi con trỏ chuột di chuyển qua.
2. Tạo một biểu mẫu đơn giản với các ô input và áp dụng pseudo-class `:focus` để thay đổi kiểu dáng của ô input khi được tập trung vào.
