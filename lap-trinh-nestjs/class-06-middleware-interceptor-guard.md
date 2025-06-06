# Class 06: Middleware, Interceptor, Guard

NestJS là một framework mạnh mẽ của Node.js hỗ trợ nhiều tính năng của kiến trúc ứng dụng backend hiện đại. Ba thành phần quan trọng trong NestJS để kiểm soát luồng xử lý yêu cầu và bảo mật là: **Middleware**, **Interceptor**, và **Guard**.

***

## Middleware là gì? Ứng dụng trong logging và xác thực

### Middleware là gì?

Middleware là một hàm được gọi trước khi request được xử lý bởi bất kỳ route handler nào. Có thể dùng để:

* Ghi log các request
* Kiểm tra token
* Chặn IP
* Sửa đổi request

### Ví dụ: Tạo middleware ghi log request

```ts
// common/middleware/logger.middleware.ts
import { Injectable, NestMiddleware } from '@nestjs/common';
import { Request, Response, NextFunction } from 'express';

@Injectable()
export class LoggerMiddleware implements NestMiddleware {
  use(req: Request, res: Response, next: NextFunction) {
    console.log(`[${new Date().toISOString()}] ${req.method} ${req.url}`);
    next();
  }
}
```

### Áp dụng middleware

```ts
// app.module.ts
import { MiddlewareConsumer, Module, NestModule } from '@nestjs/common';
import { LoggerMiddleware } from './common/middleware/logger.middleware';
import { UsersModule } from './users/users.module';

@Module({
  imports: [UsersModule],
})
export class AppModule implements NestModule {
  configure(consumer: MiddlewareConsumer) {
    consumer.apply(LoggerMiddleware).forRoutes('*');
  }
}
```

***

## Interceptor: response transformation, timeout, logging

### Interceptor là gì?

Interceptor là lớp trung gian dùng để **can thiệp vào luồng xử lý request và response**. Có thể dùng để:

* Biến đổi dữ liệu trả về
* Thêm timeout cho request
* Log thời gian xử lý
* Cache

### Ví dụ: Interceptor thêm metadata

```ts
// common/interceptors/transform.interceptor.ts
import {
  Injectable,
  NestInterceptor,
  ExecutionContext,
  CallHandler,
} from '@nestjs/common';
import { map } from 'rxjs/operators';
import { Observable } from 'rxjs';

@Injectable()
export class TransformInterceptor implements NestInterceptor {
  intercept(context: ExecutionContext, next: CallHandler): Observable<any> {
    return next.handle().pipe(
      map(data => ({
        statusCode: 200,
        timestamp: new Date().toISOString(),
        data,
      })),
    );
  }
}
```

### Áp dụng interceptor toàn cục

```ts
// main.ts
import { TransformInterceptor } from './common/interceptors/transform.interceptor';
app.useGlobalInterceptors(new TransformInterceptor());
```

***

## Guard: phân quyền, bảo vệ route

### Guard là gì?

Guard quyết định **có cho phép request đi tiếp hay không**, thường dùng cho:

* Kiểm tra quyền (role)
* Kiểm tra xác thực JWT
* Chặn IP

### Ví dụ: Guard đơn giản kiểm tra header `x-api-key`

```ts
// common/guards/api-key.guard.ts
import { CanActivate, ExecutionContext, Injectable } from '@nestjs/common';
import { Request } from 'express';

@Injectable()
export class ApiKeyGuard implements CanActivate {
  canActivate(context: ExecutionContext): boolean {
    const request: Request = context.switchToHttp().getRequest();
    const apiKey = request.headers['x-api-key'];
    return apiKey === '123456'; // kiểm tra khóa đơn giản
  }
}
```

### Áp dụng guard cho controller hoặc method

```ts
// users/users.controller.ts
import { UseGuards } from '@nestjs/common';
import { ApiKeyGuard } from '../common/guards/api-key.guard';

@UseGuards(ApiKeyGuard)
@Get('protected')
getProtectedData() {
  return { message: 'Chỉ truy cập khi có API key đúng' };
}
```

***

## Thực hành: Tạo Middleware kiểm tra request, Guard chặn IP

### Mục tiêu

* Middleware kiểm tra nếu header `x-custom-header` không tồn tại thì log cảnh báo
* Guard chặn truy cập từ IP nằm trong danh sách đen

### Bước 1: Middleware kiểm tra header

```ts
// common/middleware/check-header.middleware.ts
import { Injectable, NestMiddleware } from '@nestjs/common';
import { Request, Response, NextFunction } from 'express';

@Injectable()
export class CheckHeaderMiddleware implements NestMiddleware {
  use(req: Request, res: Response, next: NextFunction) {
    if (!req.headers['x-custom-header']) {
      console.warn('Thiếu x-custom-header!');
    }
    next();
  }
}
```

### Bước 2: Guard chặn IP

```ts
// common/guards/ip-block.guard.ts
import { CanActivate, ExecutionContext, Injectable } from '@nestjs/common';
import { Request } from 'express';

@Injectable()
export class IPBlockGuard implements CanActivate {
  private readonly blockedIps = ['127.0.0.2'];

  canActivate(context: ExecutionContext): boolean {
    const request: Request = context.switchToHttp().getRequest();
    const ip = request.ip;
    return !this.blockedIps.includes(ip);
  }
}
```

### Bước 3: Sử dụng guard

```ts
// users/users.controller.ts
import { UseGuards } from '@nestjs/common';
import { IPBlockGuard } from '../common/guards/ip-block.guard';

@UseGuards(IPBlockGuard)
@Get('safe')
getData() {
  return { message: 'Chỉ IP hợp lệ mới được vào' };
}
```

***

## Bài tập thực hành

### Mục tiêu

Thực hành xây dựng Middleware, Interceptor và Guard như sau:

#### Yêu cầu

1. **Middleware**: kiểm tra `x-auth-token` có tồn tại trong header. Nếu không có, log ra cảnh báo.
2. **Interceptor**: bọc dữ liệu trả về theo định dạng `{ success: true, data: ..., time: ... }`
3. **Guard**: chặn truy cập từ IP `192.168.0.100`
4. Áp dụng:
   * Middleware toàn cục
   * Interceptor toàn cục
   * Guard cho một route nhất định

#### Gợi ý test với Postman

* Dùng `GET /users/safe` để kiểm tra guard chặn IP
* Dùng `GET /users` không có `x-auth-token` để test middleware
* Xem định dạng response khi áp dụng Interceptor

***

## Kết luận

Bạn đã học cách:

* Viết và dùng Middleware để can thiệp trước xử lý controller
* Dùng Interceptor để biến đổi dữ liệu trả về
* Tạo Guard để kiểm tra phân quyền, IP hoặc token

Các khái niệm này là nền tảng để bảo mật và kiểm soát request trong ứng dụng NestJS quy mô lớn.
