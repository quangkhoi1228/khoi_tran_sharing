# Class 07: Authentication – JWT

Authentication (xác thực) là bước quan trọng để đảm bảo người dùng truy cập vào hệ thống một cách an toàn và có quyền hạn phù hợp. JWT (JSON Web Token) là một tiêu chuẩn phổ biến để thực hiện xác thực không trạng thái (stateless authentication).

***

## Xác thực với JWT

### JWT là gì?

JWT là một chuỗi gồm 3 phần: header, payload, và signature, dùng để truyền tải thông tin xác thực giữa client và server một cách an toàn. Token này có thể được gửi trong header `Authorization` của HTTP request.

### Quy trình xác thực JWT

* Người dùng đăng nhập (login) bằng username/password.
* Server kiểm tra thông tin, nếu đúng sẽ tạo ra JWT chứa payload (ví dụ userId).
* Client lưu token và gửi trong các request tiếp theo.
* Server dùng secret key để xác thực token, cho phép truy cập tài nguyên bảo vệ.

### Các bước cài đặt JWT trong NestJS

* Cài đặt các package: `@nestjs/jwt`, `passport-jwt`, `bcrypt`

```bash
npm install @nestjs/jwt passport-jwt bcrypt
npm install --save-dev @types/bcrypt
```

***

## Đăng ký, đăng nhập, mã hóa mật khẩu bằng bcrypt

### Mã hóa mật khẩu

* `bcrypt` giúp mã hóa mật khẩu người dùng trước khi lưu vào database.
* Hàm `hash()` tạo mật khẩu mã hóa.
* Hàm `compare()` so sánh mật khẩu người dùng nhập với mật khẩu đã mã hóa.

### Ví dụ mã hóa mật khẩu

```ts
import * as bcrypt from 'bcrypt';

async function hashPassword(password: string): Promise<string> {
  const saltRounds = 10;
  return await bcrypt.hash(password, saltRounds);
}

async function comparePassword(password: string, hash: string): Promise<boolean> {
  return await bcrypt.compare(password, hash);
}
```

### Đăng ký (Register) – lưu user với mật khẩu đã mã hóa

```ts
async registerUser(username: string, password: string) {
  const hashedPassword = await this.hashPassword(password);
  const user = this.userRepository.create({ username, password: hashedPassword });
  await this.userRepository.save(user);
  return user;
}
```

***

## Sử dụng Passport.js với chiến lược JWT

### Passport là gì?

Passport là middleware hỗ trợ đa dạng các chiến lược xác thực (OAuth, JWT, local...). NestJS tích hợp Passport rất tốt, giúp xây dựng hệ thống auth đơn giản và rõ ràng.

### Cấu hình chiến lược JWT với Passport

```ts
// auth/jwt.strategy.ts
import { Injectable } from '@nestjs/common';
import { PassportStrategy } from '@nestjs/passport';
import { ExtractJwt, Strategy } from 'passport-jwt';

@Injectable()
export class JwtStrategy extends PassportStrategy(Strategy) {
  constructor() {
    super({
      jwtFromRequest: ExtractJwt.fromAuthHeaderAsBearerToken(),
      secretOrKey: 'your_jwt_secret_key', // nên để trong biến môi trường
    });
  }

  async validate(payload: any) {
    // payload chứa dữ liệu user đã encode trong token
    return { userId: payload.sub, username: payload.username };
  }
}
```

### Tạo AuthService để xử lý đăng nhập và tạo JWT

```ts
// auth/auth.service.ts
import { Injectable } from '@nestjs/common';
import { JwtService } from '@nestjs/jwt';
import * as bcrypt from 'bcrypt';

@Injectable()
export class AuthService {
  constructor(private jwtService: JwtService) {}

  async validateUser(username: string, pass: string): Promise<any> {
    // Giả sử fetch user từ db
    const user = await this.findUserByUsername(username);
    if (user && (await bcrypt.compare(pass, user.password))) {
      const { password, ...result } = user;
      return result;
    }
    return null;
  }

  async login(user: any) {
    const payload = { username: user.username, sub: user.userId };
    return {
      access_token: this.jwtService.sign(payload),
    };
  }
  
  // Ví dụ giả định
  private async findUserByUsername(username: string) {
    // Tìm user trong db
  }
}
```

### Bảo vệ route bằng Guard Passport JWT

```ts
// auth/jwt-auth.guard.ts
import { Injectable } from '@nestjs/common';
import { AuthGuard } from '@nestjs/passport';

@Injectable()
export class JwtAuthGuard extends AuthGuard('jwt') {}
```

Sử dụng Guard trong controller:

```ts
import { UseGuards } from '@nestjs/common';
import { JwtAuthGuard } from './auth/jwt-auth.guard';

@UseGuards(JwtAuthGuard)
@Get('profile')
getProfile() {
  return { message: 'Đây là dữ liệu bảo vệ bằng JWT' };
}
```

***

## Thực hành: Xây dựng hệ thống auth cơ bản

### Bước 1: Tạo module `auth`

```bash
nest g module auth
nest g service auth
nest g controller auth
```

### Bước 2: Cài đặt và cấu hình JWT module

```ts
// auth/auth.module.ts
import { Module } from '@nestjs/common';
import { JwtModule } from '@nestjs/jwt';
import { PassportModule } from '@nestjs/passport';
import { AuthService } from './auth.service';
import { JwtStrategy } from './jwt.strategy';

@Module({
  imports: [
    PassportModule,
    JwtModule.register({
      secret: 'your_jwt_secret_key', // môi trường thật phải dùng env
      signOptions: { expiresIn: '60m' },
    }),
  ],
  providers: [AuthService, JwtStrategy],
  exports: [AuthService],
})
export class AuthModule {}
```

### Bước 3: Viết Controller xử lý đăng ký, đăng nhập

```ts
// auth/auth.controller.ts
import { Controller, Post, Body, UnauthorizedException } from '@nestjs/common';
import { AuthService } from './auth.service';

@Controller('auth')
export class AuthController {
  constructor(private authService: AuthService) {}

  @Post('register')
  async register(@Body() body: { username: string; password: string }) {
    return this.authService.registerUser(body.username, body.password);
  }

  @Post('login')
  async login(@Body() body: { username: string; password: string }) {
    const user = await this.authService.validateUser(body.username, body.password);
    if (!user) throw new UnauthorizedException('Sai tên đăng nhập hoặc mật khẩu');
    return this.authService.login(user);
  }
}
```

### Bước 4: Bảo vệ route bằng `JwtAuthGuard`

```ts
// users/users.controller.ts
import { Controller, Get, UseGuards } from '@nestjs/common';
import { JwtAuthGuard } from '../auth/jwt-auth.guard';

@Controller('users')
export class UsersController {
  @UseGuards(JwtAuthGuard)
  @Get('profile')
  getProfile() {
    return { message: 'Dữ liệu chỉ dành cho user đã đăng nhập' };
  }
}
```

***

## Bài tập thực hành

* Cài đặt module auth theo hướng dẫn
* Viết endpoint đăng ký (register) và đăng nhập (login)
* Sử dụng bcrypt để mã hóa mật khẩu khi đăng ký
* Sử dụng JWT để tạo token khi đăng nhập thành công
* Viết route bảo vệ bằng `JwtAuthGuard`
* Dùng Postman test:
  * Đăng ký user mới
  * Đăng nhập để lấy token
  * Gửi token trong header `Authorization: Bearer <token>` để truy cập route bảo vệ

***

## Tổng kết

* JWT là chuẩn xác thực phổ biến, hỗ trợ xây dựng hệ thống auth không trạng thái
* `bcrypt` mã hóa mật khẩu giúp bảo mật thông tin người dùng
* NestJS tích hợp Passport.js giúp dễ dàng tạo chiến lược JWT
* Cần kết hợp middleware, guard để đảm bảo an toàn cho API
