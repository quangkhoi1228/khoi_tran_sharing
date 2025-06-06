# Class 08: Authorization – Phân quyền

Authorization (phân quyền) là quá trình xác định xem người dùng đã xác thực có quyền truy cập tài nguyên, thực hiện hành động hay không. Trong nhiều ứng dụng, chúng ta cần phân biệt quyền của user dựa trên vai trò (role) khác nhau.

***

## Gán vai trò (role) cho user

### Vai trò (role) là gì?

Role là nhóm quyền hoặc cấp độ phân quyền gán cho user. Ví dụ:

* `admin`: có quyền toàn bộ hệ thống
* `user`: quyền giới hạn, chỉ truy cập chức năng cơ bản
* `moderator`: quyền trung gian...

### Gán role cho user trong database

Thông thường, trường `role` sẽ được thêm vào entity `User`. Ví dụ:

```ts
// user.entity.ts
import { Entity, PrimaryGeneratedColumn, Column } from 'typeorm';

@Entity()
export class User {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  username: string;

  @Column()
  password: string;

  @Column()
  role: string;  // Ví dụ: 'admin', 'user', 'moderator'
}
```

Khi tạo user, bạn gán role phù hợp:

```ts
const user = this.userRepository.create({
  username: 'khoi',
  password: hashedPassword,
  role: 'admin',
});
await this.userRepository.save(user);
```

***

## Tạo Guard kiểm tra role

### Guard trong NestJS

Guard là lớp dùng để kiểm soát truy cập route, quyết định cho phép hoặc chặn dựa trên logic tùy chỉnh.

### Guard phân quyền theo role

Ta sẽ viết một Guard để kiểm tra role của user từ request đã được xác thực (thông thường user info được lấy từ `request.user` sau khi xác thực JWT).

```ts
// roles.guard.ts
import { Injectable, CanActivate, ExecutionContext } from '@nestjs/common';
import { Reflector } from '@nestjs/core';

@Injectable()
export class RolesGuard implements CanActivate {
  constructor(private reflector: Reflector) {}

  canActivate(context: ExecutionContext): boolean {
    // Lấy danh sách role được phép truy cập từ metadata @Roles
    const roles = this.reflector.get<string[]>('roles', context.getHandler());
    if (!roles) {
      return true; // Nếu không có metadata roles thì cho phép truy cập
    }

    const request = context.switchToHttp().getRequest();
    const user = request.user;

    // Kiểm tra user có role trong danh sách roles được phép hay không
    return user && roles.includes(user.role);
  }
}
```

***

## Custom Decorator cho @Roles

### Metadata trong NestJS

Chúng ta dùng `Reflect.metadata` để gán metadata cho các route handler, dùng `Reflector` lấy ra trong Guard.

### Tạo decorator `@Roles`

```ts
// roles.decorator.ts
import { SetMetadata } from '@nestjs/common';

export const Roles = (...roles: string[]) => SetMetadata('roles', roles);
```

***

## Sử dụng RolesGuard và @Roles trong Controller

```ts
import { Controller, Get, UseGuards } from '@nestjs/common';
import { JwtAuthGuard } from '../auth/jwt-auth.guard';
import { RolesGuard } from './roles.guard';
import { Roles } from './roles.decorator';

@Controller('admin')
@UseGuards(JwtAuthGuard, RolesGuard)
export class AdminController {
  @Get('dashboard')
  @Roles('admin')
  getAdminDashboard() {
    return { message: 'Chỉ admin mới có thể xem được trang này' };
  }

  @Get('profile')
  @Roles('admin', 'moderator')
  getAdminOrModProfile() {
    return { message: 'Admin hoặc moderator mới truy cập được' };
  }
}
```

Ở ví dụ trên:

* `JwtAuthGuard` sẽ kiểm tra xác thực JWT và thêm thông tin user vào request.
* `RolesGuard` sẽ kiểm tra vai trò user với decorator `@Roles`.

***

## Ví dụ đầy đủ về phần auth có role

```ts
// auth.service.ts
async validateUser(username: string, pass: string): Promise<any> {
  const user = await this.userRepository.findOne({ where: { username } });
  if (user && (await bcrypt.compare(pass, user.password))) {
    const { password, ...result } = user;
    return result;
  }
  return null;
}
```

Giả sử `result` trả về có `{ id, username, role }` thì trong `JwtStrategy` ta trả về thông tin này làm payload token:

```ts
async validate(payload: any) {
  return { userId: payload.sub, username: payload.username, role: payload.role };
}
```

Khi user gửi request kèm token, NestJS sẽ gán `request.user` có đủ trường `role` để `RolesGuard` dùng.

***

## Bài tập thực hành

1. Thêm trường `role` trong entity User (vd: 'admin', 'user', 'moderator').
2. Viết custom decorator `@Roles` để gán role cho route.
3. Viết `RolesGuard` để kiểm tra quyền user truy cập.
4. Bảo vệ route `/admin/dashboard` chỉ cho phép `admin` truy cập.
5. Bảo vệ route `/admin/profile` cho phép `admin` và `moderator` truy cập.
6. Test thử với các user có role khác nhau qua Postman hoặc curl.
7. (Optional) Tạo route `/user/profile` cho tất cả user đã đăng nhập đều truy cập được.

***

## Tổng kết

* Phân quyền là bước tiếp theo sau xác thực, giúp giới hạn truy cập theo vai trò người dùng
* Custom decorator và Guard giúp xây dựng hệ thống phân quyền gọn, tái sử dụng cao
* Thực hiện phân quyền dễ dàng với NestJS nhờ `Reflector` và metadata
* Cần kết hợp tốt giữa xác thực (Auth) và phân quyền (Authorization)
