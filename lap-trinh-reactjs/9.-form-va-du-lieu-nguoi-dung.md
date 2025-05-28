# 9. Form và dữ liệu người dùng

### Controlled component là gì?

Trong React, một **Controlled Component** là các phần tử form (input, textarea, select...) mà giá trị của chúng được **quản lý bởi state của React**.

Điều này nghĩa là:

* Giá trị input được gán trực tiếp từ state.
* Mỗi khi người dùng thay đổi giá trị, ta gọi hàm xử lý sự kiện để cập nhật state.
* React kiểm soát hoàn toàn dữ liệu và giao diện của input.

Ví dụ Controlled Input:

```tsx
'use client';

import { useState } from 'react';

export default function ControlledInput() {
  const [name, setName] = useState('');

  const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    setName(e.target.value);
  };

  return (
    <div>
      <label>
        Tên:
        <input type="text" value={name} onChange={handleChange} />
      </label>
      <p>Bạn đã nhập: {name}</p>
    </div>
  );
}
```

#### Ưu điểm Controlled Components

* Dễ dàng validate dữ liệu khi nhập.
* Dữ liệu luôn đồng bộ giữa UI và state.
* Dễ dàng xử lý các thao tác phức tạp như reset, submit form.

***

### Quản lý nhiều input với một state

Khi có nhiều input, thay vì tạo nhiều state riêng lẻ, ta có thể dùng **1 state là object** lưu toàn bộ dữ liệu form.

Ví dụ:

```tsx
'use client';

import { useState } from 'react';

type FormData = {
  name: string;
  email: string;
  password: string;
};

export default function MultiInputForm() {
  const [formData, setFormData] = useState<FormData>({
    name: '',
    email: '',
    password: '',
  });

  const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    const { name, value } = e.target;

    // Gộp dữ liệu cũ và cập nhật trường mới
    setFormData(prev => ({
      ...prev,
      [name]: value,
    }));
  };

  return (
    <form>
      <label>
        Tên:
        <input name="name" type="text" value={formData.name} onChange={handleChange} />
      </label>

      <label>
        Email:
        <input name="email" type="email" value={formData.email} onChange={handleChange} />
      </label>

      <label>
        Mật khẩu:
        <input name="password" type="password" value={formData.password} onChange={handleChange} />
      </label>

      <pre>{JSON.stringify(formData, null, 2)}</pre>
    </form>
  );
}
```

#### Giải thích

* `formData` là object chứa tất cả trường input.
* Thuộc tính `name` trên mỗi input trùng với key trong `formData`.
* Khi người dùng thay đổi input, `handleChange` dùng `e.target.name` để xác định trường nào đang thay đổi, và cập nhật state tương ứng.
* Dùng spread operator `...prev` để giữ các trường khác không đổi.

***

### Gộp form data vào 1 object

Đây là cách phổ biến để xử lý form trong React, nhất là với form phức tạp nhiều trường.

Ưu điểm:

* Quản lý dễ dàng, chỉ cần một state duy nhất.
* Dễ dàng gửi dữ liệu lên server dưới dạng object.
* Dễ dàng reset form: chỉ cần gán lại object mặc định.

***

### Ví dụ thực hành: Tạo form đăng ký

Yêu cầu: tạo form đăng ký gồm các input: tên, email, password, quản lý dữ liệu bằng một state object và hiển thị dữ liệu vừa nhập.

```tsx
'use client';

import { useState } from 'react';

type RegisterFormData = {
  name: string;
  email: string;
  password: string;
};

export default function RegisterForm() {
  const [formData, setFormData] = useState<RegisterFormData>({
    name: '',
    email: '',
    password: '',
  });

  const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    const { name, value } = e.target;
    setFormData(prev => ({
      ...prev,
      [name]: value,
    }));
  };

  const handleSubmit = (e: React.FormEvent<HTMLFormElement>) => {
    e.preventDefault();
    alert(`Đăng ký thành công!\nTên: ${formData.name}\nEmail: ${formData.email}`);
    // Xử lý gửi dữ liệu lên server ở đây nếu cần
  };

  return (
    <form onSubmit={handleSubmit} style={{ display: 'flex', flexDirection: 'column', maxWidth: 400, gap: '1rem' }}>
      <label>
        Tên:
        <input
          type="text"
          name="name"
          value={formData.name}
          onChange={handleChange}
          required
          placeholder="Nhập tên của bạn"
        />
      </label>

      <label>
        Email:
        <input
          type="email"
          name="email"
          value={formData.email}
          onChange={handleChange}
          required
          placeholder="Nhập email"
        />
      </label>

      <label>
        Mật khẩu:
        <input
          type="password"
          name="password"
          value={formData.password}
          onChange={handleChange}
          required
          placeholder="Nhập mật khẩu"
          minLength={6}
        />
      </label>

      <button type="submit">Đăng ký</button>

      <pre>{JSON.stringify(formData, null, 2)}</pre>
    </form>
  );
}
```

***

## Bài tập thực hành

1. Tạo form đăng nhập với 2 input: email, password. Quản lý bằng một object state.
2. Hiển thị dữ liệu form nhập vào realtime dưới dạng JSON.
3. Thêm nút submit, khi submit thì hiển thị alert thông báo đã đăng nhập thành công cùng dữ liệu email.
4. Bổ sung validation bắt buộc và minlength cho mật khẩu.
5. Thử mở rộng thêm input checkbox "Ghi nhớ đăng nhập" và quản lý trong cùng state.
