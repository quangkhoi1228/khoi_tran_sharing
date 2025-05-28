# 14. Custom Hook

### Tư duy chia logic thành hook

Trong React, Hook giúp chúng ta **chia sẻ logic giữa các component** mà không cần lặp lại code hoặc thay đổi cấu trúc component.

Khi nhiều component cần dùng chung một logic như:

* Lấy kích thước cửa sổ (window size)
* Theo dõi vị trí chuột (mouse position)
* Đồng bộ dữ liệu với localStorage

Thay vì viết lại logic trong từng component, ta có thể tách phần đó thành một **Custom Hook**.

Custom Hook chính là một **hàm bắt đầu bằng từ `use`**, và có thể sử dụng các hook khác như `useState`, `useEffect`, v.v. bên trong.

***

### Quy ước đặt tên `useXxx`

Custom Hook phải:

* Được đặt tên bắt đầu bằng `use`
* Là một hàm có thể gọi trong component hoặc hook khác
* Có thể dùng các hook bên trong như `useState`, `useEffect`, `useRef`,...

Ví dụ: `useWindowSize`, `useMousePosition`, `useForm`,...

Lưu ý: **Không gọi hook trong vòng lặp, điều kiện hoặc hàm lồng nhau** (tuân thủ quy tắc hooks).

***

### Tái sử dụng logic với Custom Hook

Custom Hook giúp:

* Tái sử dụng logic dễ dàng
* Code sạch, dễ bảo trì
* Dễ kiểm thử

Ví dụ, nhiều component cần biết kích thước cửa sổ => tạo `useWindowSize`.

***

### Tạo custom hook `useWindowSize`

Hook này trả về kích thước hiện tại của cửa sổ trình duyệt.

```tsx
// hooks/useWindowSize.ts
'use client';

import { useState, useEffect } from 'react';

type WindowSize = {
  width: number;
  height: number;
};

export function useWindowSize(): WindowSize {
  const [size, setSize] = useState<WindowSize>({
    width: typeof window !== 'undefined' ? window.innerWidth : 0,
    height: typeof window !== 'undefined' ? window.innerHeight : 0,
  });

  useEffect(() => {
    const handleResize = () => {
      setSize({
        width: window.innerWidth,
        height: window.innerHeight,
      });
    };

    window.addEventListener('resize', handleResize);
    return () => window.removeEventListener('resize', handleResize);
  }, []);

  return size;
}
```

#### Sử dụng hook:

```tsx
// app/page.tsx
'use client';

import { useWindowSize } from '@/hooks/useWindowSize';

export default function HomePage() {
  const { width, height } = useWindowSize();

  return (
    <div>
      <h1>Kích thước cửa sổ</h1>
      <p>Chiều rộng: {width}px</p>
      <p>Chiều cao: {height}px</p>
    </div>
  );
}
```

***

### Tạo custom hook `useMousePosition`

Hook này theo dõi vị trí con trỏ chuột.

```tsx
// hooks/useMousePosition.ts
'use client';

import { useState, useEffect } from 'react';

type Position = {
  x: number;
  y: number;
};

export function useMousePosition(): Position {
  const [position, setPosition] = useState<Position>({ x: 0, y: 0 });

  useEffect(() => {
    const updateMouse = (e: MouseEvent) => {
      setPosition({ x: e.clientX, y: e.clientY });
    };

    window.addEventListener('mousemove', updateMouse);
    return () => window.removeEventListener('mousemove', updateMouse);
  }, []);

  return position;
}
```

#### Sử dụng hook:

```tsx
// app/mouse/page.tsx
'use client';

import { useMousePosition } from '@/hooks/useMousePosition';

export default function MousePage() {
  const { x, y } = useMousePosition();

  return (
    <div>
      <h1>Vị trí chuột</h1>
      <p>X: {x}</p>
      <p>Y: {y}</p>
    </div>
  );
}
```

***

## Bài tập thực hành

#### Bài 1: Tạo `useScrollPosition`

Tạo custom hook trả về vị trí cuộn dọc của trình duyệt (scroll Y).

* Dùng `window.addEventListener('scroll', ...)`
* Trả về `{ scrollY: number }`

#### Bài 2: Tạo `useDarkMode`

* Tạo hook lưu chế độ sáng/tối (`isDarkMode`)
* Cho phép toggle giữa 2 chế độ
* Lưu trạng thái vào `localStorage`

Gợi ý trả về object như:

```ts
{
  isDarkMode: boolean;
  toggle: () => void;
}
```

#### Bài 3: Tích hợp

* Tạo trang `/custom-hook-test` sử dụng `useWindowSize`, `useMousePosition` và `useDarkMode`
* Hiển thị vị trí chuột, kích thước màn hình, nút bật/tắt chế độ tối
