# CSS Responsive



## Responsive Web Design là gì?

Responsive Web Design là một phương pháp thiết kế web nhằm tạo ra trải nghiệm người dùng tốt nhất trên mọi thiết bị và kích thước màn hình, từ máy tính để bàn đến điện thoại di động. Kỹ thuật này thích ứng với kích thước màn hình bằng cách thay đổi và điều chỉnh cấu trúc và kiểu dáng của trang web.

## Cách thực hiện CSS Responsive

#### 1. Sử dụng Đơn vị Tương Đối

Sử dụng đơn vị tương đối như `%`, `em`, `rem` thay vì đơn vị tuyệt đối như `px` để xác định kích thước và khoảng cách, giúp các phần tử tự động thích ứng với kích thước màn hình.

```css
.container {
  width: 80%; /* Chiếm 80% chiều rộng của phần tử cha */
  margin: 0 auto; /* Canh giữa phần tử */
}
```

#### 2. Sử dụng Media Queries

Sử dụng Media Queries để xác định các điều kiện và áp dụng CSS khác nhau dựa trên kích thước màn hình. Điều này giúp điều chỉnh kiểu dáng và cấu trúc của trang web tùy theo thiết bị và kích thước màn hình.

```css
/* Thiết lập kiểu dáng cho màn hình có độ rộng lớn hơn hoặc bằng 768px */
@media screen and (min-width: 768px) {
  .menu {
    display: block; /* Hiển thị menu dạng block */
  }
}

/* Thiết lập kiểu dáng cho màn hình có độ rộng nhỏ hơn 768px */
@media screen and (max-width: 767px) {
  .menu {
    display: none; /* Ẩn menu */
  }
}
```

## Bài tập thực hành

1. Tạo một trang web đơn giản và sử dụng các đơn vị tương đối để thiết kế giao diện sao cho tự động thích ứng với kích thước màn hình.
2. Sử dụng Media Queries để điều chỉnh kiểu dáng của trang web khi màn hình thu nhỏ hoặc phóng to.
