---
description: >-
  CSS cho phép sử dụng nhiều loại đơn vị để xác định kích thước và khoảng cách
  của các phần tử trên trang web. Dưới đây là một số đơn vị đo phổ biến:
---

# Đơn vị đo trong CSS

### Đơn Vị Đo trong CSS

#### 1. Đơn vị Đo Tuyệt Đối

* **px (pixels):** Đơn vị đo tuyệt đối, cố định và không thay đổi dù kích thước màn hình có thay đổi.

```css
.element {
  width: 200px;
  height: 100px;
}
```

#### 2. Đơn vị Đo Tương Đối

* **em:** Đơn vị đo tương đối, thường sử dụng để xác định kích thước dựa trên font-size của phần tử cha gần nhất.

```css
.element {
  font-size: 16px;
  padding: 1em; /* tương đương với 16px */
}
```

* **rem:** Giống như em nhưng dựa trên font-size của phần tử gốc (root element), thường là `<html>`.

```css
.element {
  font-size: 16px;
}

.child-element {
  padding: 2rem; /* tương đương với 32px (2 * 16px) */
}
```

#### 3. Đơn vị Đo Tương Đối với Viewport

* **vw (viewport width):** Tương đương với 1% của chiều rộng của viewport.

```css
.element {
  width: 50vw; /* chiếm 50% chiều rộng của viewport */
}
```

* **vh (viewport height):** Tương đương với 1% của chiều cao của viewport.

```css
.element {
  height: 50vh; /* chiếm 50% chiều cao của viewport */
}
```

### Tham khảo

{% embed url="https://www.w3schools.com/cssref/css_units.php" %}

### Bài tập thực hành

1. Tạo một trang web đơn giản chứa một số phần tử HTML và sử dụng các đơn vị đo khác nhau để xác định kích thước và khoảng cách của chúng.
2. Thay đổi kích thước của trình duyệt và quan sát sự thay đổi trong kích thước của các phần tử sử dụng đơn vị đo tuyệt đối và đơn vị đo tương đối.
3. Thử sử dụng đơn vị đo viewport để tạo ra một layout linh hoạt có thể điều chỉnh kích thước theo kích thước của trình duyệt.
