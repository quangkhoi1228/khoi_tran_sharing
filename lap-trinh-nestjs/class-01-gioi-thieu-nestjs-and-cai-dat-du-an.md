# Class 01: Giới thiệu NestJS & Cài đặt dự án

### Tìm hiểu NestJS là gì? Vì sao chọn NestJS?

**NestJS** là một framework backend viết bằng **TypeScript**, dựa trên **Express.js** (hoặc Fastify) và mang phong cách **OOP (Lập trình hướng đối tượng)**, **FP (Hàm)** và **FRP (Lập trình phản ứng)**.

#### Điểm mạnh:

* Viết bằng TypeScript, hỗ trợ static typing
* Kiến trúc module hóa, dễ bảo trì
* Hỗ trợ Dependency Injection (DI)
* Hỗ trợ REST API, GraphQL, WebSocket, Microservice

#### Đối tượng:

* Lập trình viên backend muốn phát triển hệ thống backend theo cách chuyên nghiệp, scalable, maintainable.

### So sánh với Express.js và các framework khác

| Tiêu chí                  | NestJS              | Express.js   | Koa.js      |
| ------------------------- | ------------------- | ------------ | ----------- |
| Viết = TypeScript         | Tích hợp sẵn        | Hỗ trợ ngoài | Có thể      |
| Kiến trúc module          | Có                  | Tự thiết kế  | Tự thiết kế |
| DI (Dependency Injection) | Có                  | Tự code      | Tự code     |
| GraphQL/WebSocket         | Tích hợp chính thức | Cần plugin   | Cần plugin  |
| Curve learning            | Trung bình          | Dễ           | Dễ          |

NestJS làm cho backend trở nên giống Spring Boot (Java) hoặc ASP.NET Core (C#) nhưng trong ngữ TypeScript.

### Cài đặt Nest CLI và tạo project đầu tiên

#### Cài NestJS CLI

```bash
npm i -g @nestjs/cli
```

#### Tạo project mới

```bash
nest new my-nest-app
```

Chọn **npm** hoặc **yarn** tuỳ thích. Sau khi tạo, thư mục sẽ có cấu trúc mặc định:

### Cấu trúc dự án NestJS

```
my-nest-app/
├── src/
│   ├── app.controller.ts      // Controller chính
│   ├── app.service.ts         // Logic chính
│   ├── app.module.ts          // Module gốc
│   └── main.ts                // File bootstrap
├── test/                      // Thư mục test
├── package.json
└── tsconfig.json
```

* **main.ts**: Điểm khởi chạy chính:

```ts
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}
bootstrap();
```

### Tạo module, controller và service đơn giản

#### Tạo module mới

```bash
nest generate module hello
```

#### Tạo controller

```bash
nest generate controller hello
```

#### Tạo service

```bash
nest generate service hello
```

Sau khi sinh code, NestJS sẽ tự động import module/service/controller vào trong file `hello.module.ts`

#### Code Controller: hello.controller.ts

```ts
import { Controller, Get } from '@nestjs/common';
import { HelloService } from './hello.service';

@Controller('hello')
export class HelloController {
  constructor(private readonly helloService: HelloService) {}

  @Get()
  getHello(): string {
    return this.helloService.getHello();
  }
}
```

#### Code Service: hello.service.ts

```ts
import { Injectable } from '@nestjs/common';

@Injectable()
export class HelloService {
  getHello(): string {
    return 'Xin chào từ NestJS!';
  }
}
```

Khi chạy lệnh `npm run start`, truy cập địa chỉ:

```
GET http://localhost:3000/hello
```

Sẽ nhận kế:

```
Xin chào từ NestJS!
```

### Bài tập thực hành

1. Tạo dự án NestJS mới tên `learn-nest`
2. Tạo module mới tên `greeting`, bao gồm:
   * Controller có route `GET /greeting` trả lời chào
   * Service cung cấp method `getGreeting()` trả về chuỗi "Chào mừng đến với NestJS!"
3. Kiểm tra trên Postman hoặc trình duyệt để nhận kế JSON hoặc text phản hồi.

