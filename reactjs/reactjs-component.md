# ReactJS Component

### Giới thiệu về Component trong React

**Component** là khối xây dựng cơ bản nhất trong React. Mỗi component đại diện cho một phần của giao diện người dùng (UI) và có thể được tái sử dụng ở nhiều nơi.

Trong Next.js App Router, component có thể được sử dụng trong các route như `app/page.tsx` hoặc trong các component UI tái sử dụng trong thư mục `components`.

***

### Cách tạo Function Component bằng TypeScript

#### Cú pháp cơ bản

```tsx
// app/components/Hello.tsx
'use client';

import React from 'react';

const Hello = () => {
  return <h1>Chào mừng đến với React + TypeScript + Next.js!</h1>;
};

export default Hello;
```

#### Lưu ý

* Trong App Router, các file client-side cần có dòng `'use client'` ở đầu file nếu sử dụng state, event, hoặc effect.
* Tên component **phải viết hoa chữ cái đầu** (`Hello`), nếu không sẽ không được React hiểu là một component.
* File có đuôi `.tsx` cho phép viết JSX kết hợp TypeScript.

***

### Tạo Component có Props với TypeScript

Props là **cách truyền dữ liệu vào component** từ nơi sử dụng nó. Ta định nghĩa kiểu của props bằng `type` hoặc `interface`.

#### Ví dụ component nhận props

```tsx
// app/components/Greeting.tsx
'use client';

type GreetingProps = {
  name: string;
  age?: number; // tuỳ chọn
};

const Greeting = ({ name, age }: GreetingProps) => {
  return (
    <div>
      <h2>Xin chào {name}!</h2>
      {age && <p>Bạn {age} tuổi.</p>}
    </div>
  );
};

export default Greeting;
```

#### Cách sử dụng component có props

```tsx
// app/page.tsx
import Greeting from './components/Greeting';

export default function HomePage() {
  return (
    <div>
      <Greeting name="Khôi" age={25} />
      <Greeting name="Mai" />
    </div>
  );
}
```

***

### Truyền `children` cho Component

Một prop đặc biệt trong React là `children`, dùng để **nhúng nội dung con** vào component cha.

#### Ví dụ component layout dùng `children`

```tsx
// app/components/Card.tsx
'use client';

type CardProps = {
  children: React.ReactNode;
};

const Card = ({ children }: CardProps) => {
  return <div className="border p-4 rounded shadow">{children}</div>;
};

export default Card;
```

#### Cách sử dụng

```tsx
<Card>
  <h3>Thông báo</h3>
  <p>Đây là nội dung bên trong thẻ Card.</p>
</Card>
```

***

### Tái sử dụng Component qua danh sách `.map()`

Bạn có thể render nhiều component cùng loại với dữ liệu từ mảng.

#### Ví dụ hiển thị danh sách sản phẩm

```tsx
// app/components/ProductItem.tsx
'use client';

type Product = {
  id: number;
  name: string;
  price: number;
};

type ProductItemProps = {
  product: Product;
};

const ProductItem = ({ product }: ProductItemProps) => {
  return (
    <div>
      <h4>{product.name}</h4>
      <p>Giá: {product.price.toLocaleString()} VND</p>
    </div>
  );
};

export default ProductItem;
```

```tsx
// app/page.tsx
import ProductItem from './components/ProductItem';

const products = [
  { id: 1, name: 'Áo thun', price: 150000 },
  { id: 2, name: 'Quần jeans', price: 320000 },
];

export default function HomePage() {
  return (
    <div>
      {products.map((p) => (
        <ProductItem key={p.id} product={p} />
      ))}
    </div>
  );
}
```

***

### Bài tập thực hành cho học viên

#### Bài tập 1: Tạo component `ProfileCard`

* Nhận props: `avatar: string`, `fullName: string`, `bio: string`
* Hiển thị ảnh đại diện, tên, mô tả ngắn gọn
* Dùng CSS Module để căn chỉnh layout, bo tròn ảnh

#### Bài tập 2: Tạo component `Button` có thể tái sử dụng

* Nhận props: `onClick: () => void`, `label: string`, `variant: 'primary' | 'secondary'`
* Khi click thì `console.log('Clicked!')`

***

### Tổng kết

* Component là phần tử cơ bản nhất của UI trong React
* Props là cách truyền dữ liệu vào component, nên dùng `type` để khai báo rõ ràng
* `children` giúp truyền nội dung lồng vào trong component
* CSS Module giúp style độc lập, dễ tái sử dụng
* App Router yêu cầu `'use client'` nếu dùng tương tác
