---
description: Border dùng để thêm 1 đường viền bao xung quanh phần tử
---

# CSS Border

## Border style

Border style dùng để thay đổi cách hiển thị của border thông qua thuộc tính border-style

### Cú pháp

```css
border-style: value;
```

### Giá trị

| Giá trị | Diễn giải                                                                                                                                                                                                                                          |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| solid   | solid là giá trị mặc định, border sẽ có dạng một đường thẳng liền nét  và không bị đứt đoạn                                                                                                                                                        |
| dashed  | border được tạo ra bởi các dấu gạch ngang                                                                                                                                                                                                          |
| dotted  | border được tạo ra bởi các dấu chấm                                                                                                                                                                                                                |
| double  | <p>border được tạo ra bằng 2 border solid nhưng 2 đường này sẽ mỏng hơn và được ngăn cách bởi một khoảng trắng.<br>Độ dày của 2 line border và khoảng trắng là bằng nhau và bằng 1/3 của <a href="css-border.md#border-width">border-width</a></p> |
| groove  | groove dịch ra là đường rãnh do đó khi giá trị là groove thì border sẽ có dạng 3d của một chiếc đường rãnh, hiệu ứng sẽ dựa vào màu sắc của thuộc tính [border-color](css-border.md#border-color)                                                  |
| ridge   | ridge dịch ra là chóp(tương tự kim tự tháp ai cập) do đó khi giá trị là ridge thì border sẽ có dạng 3d của một hình chóp, hiệu ứng sẽ dựa vào màu sắc của thuộc tính [border-color](css-border.md#border-color)                                    |
| inset   | Border sẽ tạo ra hiệu ứng đổ bóng, bạn cứ tưởng tượng phần tử giống như một chiếc miệng giếng và ánh sáng sẽ chiếu từ góc bottom-right lên top-left, hiệu ứng sẽ dựa vào màu sắc của thuộc tính [border-color](css-border.md#border-color)         |
| outset  | Border cũng sẽ tạo ra hiệu ứng đổ bóng nhưng ánh sáng sẽ chiếu từ góc top-left xuống bottom-right , hiệu ứng sẽ dựa vào màu sắc của thuộc tính [border-color](css-border.md#border-color)                                                          |
| none    | Phần tử sẽ không có đường viền                                                                                                                                                                                                                     |
| hidden  | Giống none nhưng thường sẽ được dùng cho table                                                                                                                                                                                                     |

### Mix border-style

Một phẩn tử có 4 cạnh do đó chúng ta có thể khai báo từng cạnh một kiểu border theo cú pháp sau:

```css
border-style: top right bottom left;
```

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Để dễ hình dung hơn các bạn có thể xem hình dưới khi có kết hợp với color và width:

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

## Border-width

## Border-color
