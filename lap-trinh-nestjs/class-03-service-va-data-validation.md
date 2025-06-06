# Class 03: Service và Data Validation

### Tách business logic vào Service

#### Mục tiêu

Trong NestJS, **Service** là nơi xử lý **business logic** — logic nghiệp vụ, không nên để trong Controller. Điều này giúp code dễ bảo trì, kiểm thử và mở rộng.

#### Tạo Service

NestJS cho phép bạn tạo service bằng CLI:

```bash
nest generate service users
```

#### Sử dụng Service trong Controller

Giả sử bạn có một service `UsersService` chứa logic xử lý:

```ts
// users.service.ts
import { Injectable } from '@nestjs/common';
import { CreateUserDto } from './dto/create-user.dto';

@Injectable()
export class UsersService {
  private users = [];

  create(user: CreateUserDto) {
    this.users.push(user);
    return user;
  }

  findAll() {
    return this.users;
  }
}
```

Inject service vào controller:

```ts
// users.controller.ts
import { Controller, Post, Body, Get } from '@nestjs/common';
import { UsersService } from './users.service';
import { CreateUserDto } from './dto/create-user.dto';

@Controller('users')
export class UsersController {
  constructor(private readonly usersService: UsersService) {}

  @Post()
  create(@Body() createUserDto: CreateUserDto) {
    return this.usersService.create(createUserDto);
  }

  @Get()
  findAll() {
    return this.usersService.findAll();
  }
}
```

***

### Giới thiệu `class-validator` và `class-transformer`

#### Cài đặt

```bash
npm install class-validator class-transformer
```

#### Mục đích

* `class-validator`: giúp xác thực dữ liệu đầu vào (validate)
* `class-transformer`: chuyển đổi dữ liệu (transform) – ví dụ, từ JSON sang class instance

#### Ví dụ DTO với validate

```ts
// create-user.dto.ts
import { IsEmail, IsNotEmpty, MinLength } from 'class-validator';

export class CreateUserDto {
  @IsNotEmpty({ message: 'Tên không được để trống' })
  name: string;

  @IsEmail({}, { message: 'Email không hợp lệ' })
  email: string;

  @MinLength(6, { message: 'Mật khẩu phải ít nhất 6 ký tự' })
  password: string;
}
```

***

### Áp dụng Pipe để validate đầu vào

NestJS sử dụng **Pipe** để xử lý dữ liệu trước khi vào controller — có thể dùng để validate dữ liệu với DTO.

#### Sử dụng pipe `ValidationPipe` toàn cục

Mở `main.ts`:

```ts
import { ValidationPipe } from '@nestjs/common';
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  app.useGlobalPipes(new ValidationPipe({ transform: true }));
  await app.listen(3000);
}
bootstrap();
```

Hoặc chỉ dùng cho 1 route:

```ts
@Post()
create(@Body(new ValidationPipe()) createUserDto: CreateUserDto) {
  return this.usersService.create(createUserDto);
}
```

#### Các tùy chọn hữu ích của `ValidationPipe`

```ts
new ValidationPipe({
  whitelist: true, // loại bỏ các field không khai báo trong DTO
  forbidNonWhitelisted: true, // báo lỗi nếu có field lạ
  transform: true, // tự động chuyển từ JSON sang class
});
```

***

### Thực hành: Validate dữ liệu người dùng với DTO + Pipe

#### Bước 1: Tạo DTO

```ts
// dto/create-user.dto.ts
import { IsEmail, IsNotEmpty, MinLength } from 'class-validator';

export class CreateUserDto {
  @IsNotEmpty({ message: 'Tên không được để trống' })
  name: string;

  @IsEmail({}, { message: 'Email không hợp lệ' })
  email: string;

  @MinLength(6, { message: 'Mật khẩu tối thiểu 6 ký tự' })
  password: string;
}
```

#### Bước 2: Cập nhật service

```ts
// users.service.ts
import { Injectable } from '@nestjs/common';
import { CreateUserDto } from './dto/create-user.dto';

@Injectable()
export class UsersService {
  private users: CreateUserDto[] = [];

  create(user: CreateUserDto) {
    this.users.push(user);
    return {
      message: 'Tạo người dùng thành công',
      user,
    };
  }

  findAll() {
    return this.users;
  }
}
```

#### Bước 3: Cập nhật controller

```ts
// users.controller.ts
import { Controller, Post, Body, Get, UsePipes, ValidationPipe } from '@nestjs/common';
import { UsersService } from './users.service';
import { CreateUserDto } from './dto/create-user.dto';

@Controller('users')
export class UsersController {
  constructor(private readonly usersService: UsersService) {}

  @Post()
  @UsePipes(new ValidationPipe({ whitelist: true, transform: true }))
  createUser(@Body() createUserDto: CreateUserDto) {
    return this.usersService.create(createUserDto);
  }

  @Get()
  getAllUsers() {
    return this.usersService.findAll();
  }
}
```

#### Bước 4: Kiểm tra bằng Postman hoặc curl

Gửi `POST /users` với body:

```json
{
  "name": "Khôi",
  "email": "khoi@example.com",
  "password": "123456"
}
```

***

### Bài tập thực hành

#### Bài 1: Bổ sung trường `age` vào DTO

* Thêm field `age` kiểu số
* Dùng `@IsInt()` và `@Min(18)` để đảm bảo người dùng từ 18 tuổi trở lên

```ts
@IsInt()
@Min(18)
age: number;
```

#### Bài 2: Tạo DTO mới để cập nhật người dùng (`UpdateUserDto`)

* Sử dụng `PartialType` từ `@nestjs/mapped-types` để kế thừa từ `CreateUserDto`

```ts
import { PartialType } from '@nestjs/mapped-types';
import { CreateUserDto } from './create-user.dto';

export class UpdateUserDto extends PartialType(CreateUserDto) {}
```

#### Bài 3: Xử lý lỗi trả về dưới dạng JSON thân thiện

Sử dụng pipe `ValidationPipe` có cấu hình:

```ts
@UsePipes(new ValidationPipe({
  exceptionFactory: (errors) => {
    return new BadRequestException(
      errors.map(err => ({
        field: err.property,
        errors: Object.values(err.constraints || {}),
      }))
    );
  }
}))
```

***

### Kết luận

Sau bài học này, bạn đã nắm được:

* Cách tách logic nghiệp vụ vào `Service`
* Cách dùng `class-validator`, `class-transformer` để kiểm tra dữ liệu đầu vào
* Cách cấu hình và sử dụng `ValidationPipe` để kiểm tra dữ liệu qua `DTO`
