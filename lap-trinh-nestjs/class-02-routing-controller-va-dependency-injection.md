# Class 02: Routing, Controller và Dependency Injection

### Tổng quan bài học

Trong bài này, chúng ta sẽ học cách xây dựng các route trong NestJS thông qua `Controller`, truyền và nhận dữ liệu qua `DTO`, và hiểu cơ chế **Dependency Injection (DI)** – một trong những đặc điểm nổi bật của NestJS giúp quản lý các thành phần và tăng khả năng mở rộng của ứng dụng.

***

### Controller và Route trong NestJS

#### Controller là gì?

Trong NestJS, **Controller** chịu trách nhiệm xử lý các **request** từ client và trả về **response** tương ứng. Mỗi controller sẽ định nghĩa các route như `GET`, `POST`, `PUT`, `DELETE`.

#### Cú pháp khai báo Controller

```ts
import { Controller, Get } from '@nestjs/common';

@Controller('hello') // Prefix route: /hello
export class HelloController {
  @Get() // Route: GET /hello
  getHello(): string {
    return 'Xin chào từ NestJS!';
  }
}
```

#### Các decorator xử lý route:

| Decorator   | HTTP Method | Mô tả                       |
| ----------- | ----------- | --------------------------- |
| `@Get()`    | GET         | Lấy dữ liệu                 |
| `@Post()`   | POST        | Thêm dữ liệu mới            |
| `@Put()`    | PUT         | Cập nhật toàn bộ dữ liệu    |
| `@Patch()`  | PATCH       | Cập nhật một phần dữ liệu   |
| `@Delete()` | DELETE      | Xóa dữ liệu                 |
| `@Param()`  |             | Lấy giá trị từ URL          |
| `@Body()`   |             | Lấy dữ liệu từ body request |
| `@Query()`  |             | Lấy dữ liệu từ query string |

#### Ví dụ đầy đủ:

```ts
import { Controller, Get, Post, Put, Delete, Body, Param } from '@nestjs/common';

@Controller('users')
export class UserController {
  @Get()
  findAll(): string {
    return 'Lấy danh sách người dùng';
  }

  @Get(':id')
  findOne(@Param('id') id: string): string {
    return `Lấy người dùng có id: ${id}`;
  }

  @Post()
  create(@Body() body: any): string {
    return `Tạo người dùng với dữ liệu: ${JSON.stringify(body)}`;
  }

  @Put(':id')
  update(@Param('id') id: string, @Body() body: any): string {
    return `Cập nhật người dùng ${id} với dữ liệu: ${JSON.stringify(body)}`;
  }

  @Delete(':id')
  remove(@Param('id') id: string): string {
    return `Xóa người dùng có id: ${id}`;
  }
}
```

***

## DTO (Data Transfer Object)

DTO là các class đơn giản dùng để định nghĩa cấu trúc dữ liệu truyền vào/từ controller. Ở bài này, bạn chỉ cần tạo DTO mà **không cần validation**.

```ts
tsCopyEdit// users/dto/create-user.dto.ts
export class CreateUserDto {
  name: string;
  age: number;
}
```

```ts
tsCopyEdit// users/dto/update-user.dto.ts
export class UpdateUserDto {
  name?: string;
  age?: number;
}
```

***

## Giới thiệu Dependency Injection

NestJS sử dụng Dependency Injection (DI) để quản lý các phụ thuộc giữa các class (như Service, Repository…). Thay vì tự tạo instance của service, NestJS sẽ inject tự động khi ta khai báo trong constructor.

### Tạo Service

```bash
bashCopyEditnest generate service users
```

Tạo ra file `users.service.ts`:

```ts
tsCopyEditimport { Injectable } from '@nestjs/common';

@Injectable()
export class UsersService {
  private users = [];

  findAll() {
    return this.users;
  }

  findOne(id: number) {
    return this.users.find((u) => u.id === id);
  }

  create(user: any) {
    const newUser = { id: Date.now(), ...user };
    this.users.push(newUser);
    return newUser;
  }

  update(id: number, data: any) {
    const index = this.users.findIndex((u) => u.id === id);
    if (index === -1) return null;
    this.users[index] = { ...this.users[index], ...data };
    return this.users[index];
  }

  remove(id: number) {
    const index = this.users.findIndex((u) => u.id === id);
    if (index === -1) return null;
    const removed = this.users.splice(index, 1);
    return removed[0];
  }
}
```

### Sử dụng Service trong Controller

```ts
tsCopyEditimport { Controller, Get, Post, Put, Delete, Param, Body } from '@nestjs/common';
import { UsersService } from './users.service';
import { CreateUserDto } from './dto/create-user.dto';
import { UpdateUserDto } from './dto/update-user.dto';

@Controller('users')
export class UsersController {
  constructor(private readonly usersService: UsersService) {}

  @Get()
  findAll() {
    return this.usersService.findAll();
  }

  @Get(':id')
  findOne(@Param('id') id: string) {
    return this.usersService.findOne(Number(id));
  }

  @Post()
  create(@Body() body: CreateUserDto) {
    return this.usersService.create(body);
  }

  @Put(':id')
  update(@Param('id') id: string, @Body() body: UpdateUserDto) {
    return this.usersService.update(Number(id), body);
  }

  @Delete(':id')
  remove(@Param('id') id: string) {
    return this.usersService.remove(Number(id));
  }
}
```

***

## Bài tập thực hành

### Mục tiêu

Tạo một module `users` đơn giản để quản lý danh sách người dùng bao gồm các API sau:

* `GET /users` – Lấy danh sách người dùng
* `GET /users/:id` – Lấy thông tin người dùng theo ID
* `POST /users` – Tạo người dùng mới (gồm name, age)
* `PUT /users/:id` – Cập nhật người dùng
* `DELETE /users/:id` – Xoá người dùng

### Yêu cầu

* Sử dụng `Service` để quản lý dữ liệu người dùng (lưu trữ trong mảng đơn giản)
* Tạo 2 DTO: `CreateUserDto`, `UpdateUserDto` (không cần dùng `class-validator`)
* Không cần kết nối cơ sở dữ liệu

***

## Gợi ý mở rộng

Sau khi hoàn thành, bạn có thể mở rộng:

* Thêm logic kiểm tra người dùng tồn tại trước khi cập nhật/xoá
* Sử dụng `Map` thay vì mảng
* Bổ sung tính năng tìm kiếm người dùng theo tên
