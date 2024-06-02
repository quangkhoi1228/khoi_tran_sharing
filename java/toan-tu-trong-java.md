---
description: >-
  Trong Java, toán tử được sử dụng để thực hiện các phép tính và thao tác trên
  dữ liệu. Các toán tử có thể là các ký tự đặc biệt hoặc từ khóa được sử dụng để
  thực hiện các phép toán khác nhau.
---

# Toán tử trong Java

## Toán tử số học

<table data-full-width="false"><thead><tr><th width="106">Toán tử</th><th width="152">Tên</th><th>Mô tả</th><th>Ví dụ</th></tr></thead><tbody><tr><td>+</td><td>Addition</td><td>Cộng hai giá trị lại với nhau</td><td>x + y</td></tr><tr><td>-</td><td>Subtraction</td><td>Trừ giá trị thứ hai từ giá trị thứ nhất</td><td>x - y</td></tr><tr><td>*</td><td>Multiplication</td><td>Nhân hai giá trị lại với nhau</td><td>x * y</td></tr><tr><td>/</td><td>Division</td><td>Chia giá trị thứ nhất cho giá trị thứ hai</td><td>x / y</td></tr><tr><td>%</td><td>Modulus</td><td>Trả về phần dư của phép chia</td><td>x % y</td></tr><tr><td>++</td><td>Increment</td><td>Tăng giá trị của biến lên 1 đơn vị</td><td>++x</td></tr><tr><td>--</td><td>Decrement</td><td>Giảm giá trị của biến đi 1 đơn vị</td><td>--x</td></tr></tbody></table>

Toán tử số học được sử dụng để thực hiện các phép tính số học như cộng, trừ, nhân, chia và các phép toán liên quan.

```java
int a = 10;
int b = 5;
int sum = a + b; // Cộng
int difference = a - b; // Trừ
int product = a * b; // Nhân
int quotient = a / b; // Chia
int remainder = a % b; // Phần dư
```

## Toán tử gán

Toán tử gán được sử dụng để gán giá trị cho biến.

<table><thead><tr><th width="118">Toán tử</th><th width="133">Ví dụ</th><th width="283">Ý nghĩa</th><th>Tương tự với</th></tr></thead><tbody><tr><td>=</td><td>x = 5</td><td>Gán</td><td>x = 5</td></tr><tr><td>+=</td><td>x += 3</td><td>Cộng và gán</td><td>x = x + 3</td></tr><tr><td>-=</td><td>x -= 3</td><td>Trừ và gán</td><td>x = x - 3</td></tr><tr><td>*=</td><td>x *= 3</td><td>Nhân và gán</td><td>x = x * 3</td></tr><tr><td>/=</td><td>x /= 3</td><td>Chia và gán</td><td>x = x / 3</td></tr><tr><td>%=</td><td>x %= 3</td><td>Chia lấy dư và gán</td><td>x = x % 3</td></tr><tr><td>&#x26;=</td><td>x &#x26;= 3</td><td>AND bit và gán</td><td>x = x &#x26; 3</td></tr><tr><td>|=</td><td>x |= 3</td><td>OR bit và gán</td><td>x = x | 3</td></tr><tr><td>^=</td><td>x ^= 3</td><td>XOR bit và gán</td><td>x = x ^ 3</td></tr><tr><td>>>=</td><td>x >>= 3</td><td>Dịch phải và gán</td><td>x = x >> 3</td></tr><tr><td>&#x3C;&#x3C;=</td><td>x &#x3C;&#x3C;= 3</td><td>Dịch trái và gán</td><td>x = x &#x3C;&#x3C; 3</td></tr></tbody></table>

## Toán tử so sánh

Toán tử so sánh được sử dụng để so sánh hai giá trị.

```java
int m = 5;
int n = 10;
boolean result = (m > n); // So sánh m lớn hơn n
```

Dưới đây là bảng các toán tử so sánh trong lập trình, cùng với ví dụ:

| Toán tử | Tên               | Ví dụ  |
| ------- | ----------------- | ------ |
| ==      | Bằng              | x == y |
| !=      | Không bằng        | x != y |
| >       | Lớn hơn           | x > y  |
| <       | Nhỏ hơn           | x < y  |
| >=      | Lớn hơn hoặc bằng | x >= y |
| <=      | Nhỏ hơn hoặc bằng | x <= y |

Các toán tử này được sử dụng để so sánh giá trị của các biến trong lập trình, và kết quả của mỗi phép so sánh sẽ là `True` hoặc `False`. Bạn có thể thử các phép toán này trong môi trường lập trình của mình để hiểu rõ hơn.

## Toán tử logic

Toán tử logic được sử dụng để kết hợp các điều kiện logic.

```java
int p = 5;
int q = 10;
boolean condition1 = (p > 3) && (q < 15); // AND logic
boolean condition2 = (p > 3) || (q < 5); // OR logic
boolean condition3 = !(p > 3); // NOT logic
```

Dưới đây là bảng các toán tử logic cùng với mô tả và ví dụ:

<table data-full-width="true"><thead><tr><th width="125">Toán tử</th><th width="149">Tên</th><th width="495">Mô tả</th><th>Ví dụ</th></tr></thead><tbody><tr><td>&#x26;&#x26;</td><td>Và </td><td>Trả về <code>true</code> nếu cả hai câu lệnh đều đúng</td><td>x &#x3C; 5 &#x26;&#x26; x &#x3C; 10</td></tr><tr><td>||</td><td>Hoặc </td><td>Trả về <code>true</code> nếu một trong hai câu lệnh đúng</td><td>x &#x3C; 5 || x &#x3C; 4</td></tr><tr><td>!</td><td>Phủ định </td><td>Đảo ngược kết quả, trả về <code>false</code> nếu kết quả là <code>true</code></td><td>!(x &#x3C; 5 &#x26;&#x26; x &#x3C; 10)</td></tr></tbody></table>

Các toán tử logic được sử dụng để xác định logic giữa các biến hoặc giá trị trong lập trình. Bạn có thể thử các phép toán này trong môi trường lập trình của mình để hiểu rõ hơn.

### Bài tập thực hành

1. Viết một chương trình Java để tính tổng, hiệu, tích và thương của hai số.
2. Viết một chương trình Java để kiểm tra xem một số có phải là số chẵn hay không và in kết quả ra màn hình (Trả về true/false ra console).

### Kết luận

Trên đây là một số loại toán tử phổ biến trong Java cùng với các ví dụ minh họa và bài tập thực hành. Qua việc làm bài tập, bạn sẽ có cơ hội hiểu rõ hơn về cách sử dụng các toán tử trong lập trình Java.
