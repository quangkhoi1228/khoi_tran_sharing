# 2. Import/Export component

### Giới thiệu

Trong React, để có thể sử dụng một component ở nhiều nơi, chúng ta cần **export (xuất)** component từ một file và **import (nhập)** component đó vào file cần dùng. Việc sử dụng đúng cú pháp `export` và `import` giúp tổ chức code rõ ràng, dễ tái sử dụng và bảo trì lâu dài.

***

### Export component mặc định (default export)

Khi một component được export mặc định, ta chỉ được phép export **duy nhất một giá trị mặc định** trong mỗi file.

#### Cú pháp

```tsx
// app/components/Header.tsx
'use client';

const Header = () => {
  return <header>Đây là header</header>;
};

export default Header;
```

#### Cách import component mặc định

```tsx
// app/page.tsx
import Header from './components/Header';

export default function HomePage() {
  return (
    <div>
      <Header />
    </div>
  );
}
```

#### Lưu ý

* Khi import default, **có thể đặt tên tùy ý** cho component (nhưng nên giữ tên gốc để dễ hiểu).
* `Header` có thể đổi thành `MyHeader` hay gì khác:

```tsx
import MyHeader from './components/Header';
```

***

### Export component theo tên (named export)

Cho phép export **nhiều component** trong cùng một file.

#### Cú pháp

```tsx
// app/components/Buttons.tsx
'use client';

export const PrimaryButton = () => {
  return <button className="bg-blue-500 text-white p-2">Primary</button>;
};

export const SecondaryButton = () => {
  return <button className="bg-gray-300 p-2">Secondary</button>;
};
```

#### Cách import component theo tên

```tsx
// app/page.tsx
import { PrimaryButton, SecondaryButton } from './components/Buttons';

export default function HomePage() {
  return (
    <div>
      <PrimaryButton />
      <SecondaryButton />
    </div>
  );
}
```

#### Lưu ý

* Khi dùng `named export`, bạn **phải giữ đúng tên** khi import.
* Nếu muốn đổi tên khi import:

```tsx
import { PrimaryButton as MainButton } from './components/Buttons';
```

***

### Kết hợp default và named export

Bạn có thể vừa export mặc định một component chính, vừa export các component phụ trong cùng file.

#### Ví dụ

```tsx
// app/components/Form.tsx
'use client';

const Form = () => {
  return <form>Đây là form chính</form>;
};

export const InputField = () => {
  return <input type="text" placeholder="Nhập gì đó..." />;
};

export const SubmitButton = () => {
  return <button type="submit">Gửi</button>;
};

export default Form;
```

#### Cách import

```tsx
// app/page.tsx
import Form, { InputField, SubmitButton } from './components/Form';

export default function HomePage() {
  return (
    <div>
      <Form />
      <InputField />
      <SubmitButton />
    </div>
  );
}
```

***

### Tổ chức component bằng thư mục

Tạo thư mục chứa nhiều component con và có một file `index.ts` để gom tất cả export.

#### Cấu trúc thư mục

```
app/
└── components/
    └── layout/
        ├── Header.tsx
        ├── Footer.tsx
        └── index.ts
```

#### Nội dung từng file

```tsx
// Header.tsx
'use client';
export const Header = () => <header>Header</header>;

// Footer.tsx
'use client';
export const Footer = () => <footer>Footer</footer>;
```

```ts
// index.ts
export * from './Header';
export * from './Footer';
```

#### Import từ `index.ts`

```tsx
import { Header, Footer } from './components/layout';
```

#### Lợi ích

* Giúp code ngắn gọn, sạch sẽ.
* Có thể import nhiều component từ một thư mục duy nhất.

***

### Import component từ thư viện bên ngoài

Ngoài component nội bộ, ta có thể import component từ thư viện như Material UI, Tailwind UI, ShadCN UI, v.v.

```tsx
import { Button } from '@/components/ui/button'; // dùng ShadCN UI
```

***

### Bài tập thực hành cho học viên

#### Bài tập 1: Tạo 3 component và export theo kiểu named export

* Tạo file `MyWidgets.tsx` trong `app/components`
* Tạo 3 component: `ClockWidget`, `WeatherWidget`, `NewsWidget`
* Mỗi component hiển thị một đoạn văn bản mô phỏng (chưa cần logic)
* Export cả 3 bằng `export` theo tên

```tsx
// app/components/MyWidgets.tsx
'use client';

export const ClockWidget = () => <div>Đồng hồ: 12:00</div>;
export const WeatherWidget = () => <div>Thời tiết: Nắng đẹp</div>;
export const NewsWidget = () => <div>Tin tức: React 19 sắp ra mắt!</div>;
```

* Import các widget vào `app/page.tsx` và hiển thị chúng.

***

#### Bài tập 2: Tạo thư mục `common` chứa nhiều component và dùng `index.ts`

* Tạo thư mục `app/components/common/`
* Thêm 2 file: `Title.tsx`, `Divider.tsx`
* Trong `index.ts`, export tất cả các component
* Import từ `common` trong `page.tsx`

***

#### Bài tập 3: Tạo một file component chính có default export, thêm một component phụ dùng named export

* File `Notification.tsx`:
  * Default export: `NotificationBox`
  * Named export: `CloseButton`
* Import và sử dụng trong `page.tsx`

***

### Tổng kết

* **Default export** dùng để export một giá trị chính trong file, dễ rename khi import.
* **Named export** cho phép export nhiều giá trị trong cùng một file, phải dùng đúng tên khi import.
* Có thể kết hợp cả hai cách export.
* Sử dụng `index.ts` giúp gom các export từ nhiều file, tiện quản lý và import.
* Đây là kỹ năng **bắt buộc** để tái sử dụng component hiệu quả trong dự án React lớn.

