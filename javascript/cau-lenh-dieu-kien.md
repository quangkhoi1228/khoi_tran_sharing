---
description: >-
  Trong bài học này, chúng ta sẽ tìm hiểu về câu lệnh điều kiện trong
  JavaScript, bao gồm if, else if, và else.
---

# Câu lệnh điều kiện

## I. Câu Lệnh `if`

Câu lệnh `if` được sử dụng để thực thi một khối mã nếu một điều kiện được đánh giá là đúng.

**Ví dụ:**

```javascript
var age = 20;
if (age >= 18) {
    console.log("Bạn đã trưởng thành.");
}
```

## II. Câu Lệnh `else if`

Câu lệnh `else if` được sử dụng để thêm điều kiện kiểm tra tiếp theo nếu điều kiện trước đó là không đúng.

**Ví dụ:**

```javascript
var temperature = 25;
if (temperature < 0) {
    console.log("Nhiệt độ dưới 0 độ C.");
} else if (temperature >= 0 && temperature <= 10) {
    console.log("Nhiệt độ từ 0 đến 10 độ C.");
} else {
    console.log("Nhiệt độ trên 10 độ C.");
}
```

## III. Câu Lệnh `else`

Câu lệnh `else` được sử dụng để thực thi một khối mã nếu không có điều kiện nào trong các điều kiện trước đó là đúng.

**Ví dụ:**

```javascript
var isRainy = true;
if (isRainy) {
    console.log("Mang ô khi ra ngoài.");
} else {
    console.log("Không cần mang ô khi ra ngoài.");
}
```

## IV. Bài Tập Thực Hành

1. Viết một chương trình kiểm tra xem một số có phải là số chẵn hay không.
2. Viết một chương trình kiểm tra xem một năm có phải là năm nhuận hay không.
3. Viết một chương trình kiểm tra điểm số của một học sinh và in ra thông báo về thành tích của học sinh đó (giỏi, khá, trung bình, yếu).
