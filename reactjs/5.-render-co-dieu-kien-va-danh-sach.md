# 5. Render có điều kiện và danh sách

### Khái niệm render có điều kiện trong React

Trong React, bạn có thể **hiển thị hoặc ẩn một phần giao diện** dựa trên điều kiện logic. Điều này giúp UI linh hoạt hơn theo trạng thái ứng dụng.

Có hai cách phổ biến để render có điều kiện trong JSX:

#### Sử dụng if-else (ngoài JSX)

Bạn không thể dùng trực tiếp `if` bên trong JSX, nhưng có thể viết biến bên ngoài rồi dùng trong JSX.

```tsx
'use client';

import { useState } from 'react';

export default function Example() {
  const [isShow, setIsShow] = useState(true);

  let content;
  if (isShow) {
    content = <p>Đây là nội dung được hiển thị.</p>;
  } else {
    content = <p>Nội dung bị ẩn.</p>;
  }

  return (
    <div>
      {content}
      <button onClick={() => setIsShow(!isShow)}>Toggle</button>
    </div>
  );
}
```

#### Sử dụng toán tử 3 ngôi trong JSX

Toán tử 3 ngôi cho phép viết gọn hơn ngay trong JSX:

```tsx
<p>{isShow ? 'Hiển thị nội dung' : 'Ẩn nội dung'}</p>
```

Hoặc để render một component/element:

```tsx
{isShow ? <ComponentA /> : <ComponentB />}
```

#### Toán tử AND (`&&`) trong JSX

Dùng để hiển thị khi điều kiện đúng, không hiển thị gì khi sai:

```tsx
{isShow && <p>Chỉ hiển thị khi isShow = true</p>}
```

### Render danh sách với `Array.map()`

Để hiển thị nhiều phần tử từ mảng, React thường dùng `map`:

```tsx
const fruits = ['Táo', 'Cam', 'Xoài'];

return (
  <ul>
    {fruits.map((fruit, index) => (
      <li key={index}>{fruit}</li>
    ))}
  </ul>
);
```

#### Tại sao phải có `key`?

* `key` giúp React **nhận biết từng phần tử riêng biệt** khi render lại.
* Giúp tối ưu cập nhật UI, tránh render lại toàn bộ danh sách.
* `key` nên là giá trị **duy nhất**, ví dụ: `id` hoặc `uuid`.
* Không nên dùng `index` nếu danh sách có thể thay đổi thứ tự hoặc thêm/xóa.

Ví dụ chuẩn hơn với id:

```tsx
type Product = {
  id: number;
  name: string;
};

const products: Product[] = [
  { id: 1, name: 'Laptop' },
  { id: 2, name: 'Điện thoại' },
];

return (
  <ul>
    {products.map(product => (
      <li key={product.id}>{product.name}</li>
    ))}
  </ul>
);
```

### Ví dụ thực tế: Danh sách sản phẩm với toggle hiện/ẩn chi tiết

```tsx
'use client';

import { useState } from 'react';

type Product = {
  id: number;
  name: string;
  price: number;
  description: string;
};

const productList: Product[] = [
  { id: 1, name: 'Laptop Dell', price: 2000, description: 'Laptop cấu hình mạnh, pin lâu.' },
  { id: 2, name: 'Điện thoại Samsung', price: 1000, description: 'Điện thoại màn hình lớn, camera đẹp.' },
  { id: 3, name: 'Tai nghe Sony', price: 300, description: 'Tai nghe chống ồn, chất lượng cao.' },
];

export default function ProductList() {
  const [showDetailsId, setShowDetailsId] = useState<number | null>(null);

  const toggleDetails = (id: number) => {
    if (showDetailsId === id) {
      setShowDetailsId(null);
    } else {
      setShowDetailsId(id);
    }
  };

  return (
    <div>
      <h1>Danh sách sản phẩm</h1>
      <ul>
        {productList.map(product => (
          <li key={product.id} style={{ marginBottom: '1rem' }}>
            <div style={{ cursor: 'pointer' }} onClick={() => toggleDetails(product.id)}>
              <strong>{product.name}</strong> - ${product.price}
              {' '}
              <button>{showDetailsId === product.id ? 'Ẩn chi tiết' : 'Xem chi tiết'}</button>
            </div>
            {showDetailsId === product.id && (
              <p>Mô tả: {product.description}</p>
            )}
          </li>
        ))}
      </ul>
    </div>
  );
}
```

Giải thích:

* Dùng `map` để render danh sách sản phẩm.
* Dùng `key={product.id}` để React nhận diện từng phần tử.
* Dùng state `showDetailsId` để lưu id sản phẩm đang hiển thị chi tiết.
* Khi click vào tên hoặc nút, gọi hàm `toggleDetails` để bật/tắt chi tiết sản phẩm.
* Dùng toán tử 3 ngôi và điều kiện để render chi tiết khi id trùng.

***

## Bài tập thực hành

1. Tạo một danh sách học viên với các trường: `id`, `name`, `age`.
2. Hiển thị danh sách này bằng `map`.
3. Thêm nút "Xem chi tiết" để toggle hiển thị tuổi học viên (tương tự ví dụ sản phẩm).
4. Dùng toán tử 3 ngôi hoặc AND để render có điều kiện.
5. Đảm bảo mỗi phần tử có `key` duy nhất.

