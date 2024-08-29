# NestJS module

#### Giới thiệu về **NestJS Module**

**Module** là một trong những khái niệm cốt lõi của NestJS. Nó giúp tổ chức mã nguồn một cách hiệu quả và rõ ràng, đồng thời hỗ trợ chia nhỏ các thành phần của ứng dụng để dễ quản lý, bảo trì và mở rộng.

**1. Định nghĩa NestJS Module**

Trong NestJS, một **module** là một đơn vị tổ chức logic của mã nguồn, đóng vai trò là một tập hợp các thành phần liên quan như controller, service, và provider. Mọi ứng dụng NestJS đều có ít nhất một module chính, được gọi là **root module** (thường là `AppModule`), và có thể có nhiều module khác để chia tách các chức năng.

Mục tiêu chính của module là nhóm các thành phần lại với nhau để giữ cho mã nguồn được tách biệt và dễ dàng quản lý.

**2. Cấu trúc một Module**

Module trong NestJS được định nghĩa bằng cách sử dụng **decorator** `@Module()`. Cấu trúc cơ bản của một module bao gồm:

* **Controllers**: Các controller chịu trách nhiệm xử lý các yêu cầu HTTP và trả về dữ liệu tương ứng.
* **Providers**: Các dịch vụ hoặc logic kinh doanh của ứng dụng được khai báo trong provider.
* **Imports**: Các module khác mà module hiện tại phụ thuộc vào.
* **Exports**: Các provider hoặc service mà module hiện tại cung cấp cho các module khác.

```typescript
import { Module } from '@nestjs/common';
import { CatsController } from './cats.controller';
import { CatsService } from './cats.service';

@Module({
  imports: [],            // Các module mà module này phụ thuộc vào
  controllers: [CatsController],  // Các controller của module này
  providers: [CatsService],  // Các service hoặc provider của module này
  exports: [CatsService],    // Các provider mà module này chia sẻ cho các module khác
})
export class CatsModule {}
```

**3. Module Root**

Mọi ứng dụng NestJS đều có một **root module** – đây là điểm bắt đầu của ứng dụng. Root module thường là `AppModule`:

```typescript
import { Module } from '@nestjs/common';
import { CatsModule } from './cats/cats.module';

@Module({
  imports: [CatsModule],  // Đưa module khác vào để sử dụng
})
export class AppModule {}
```

**4. Tính năng của Module trong NestJS**

* **Tái sử dụng**: Các module có thể được tái sử dụng và import vào các module khác.
* **Tách biệt logic**: Module giúp tách biệt các phần khác nhau của ứng dụng (như module cho người dùng, sản phẩm, đặt hàng).
* **Tính mô-đun hóa**: Tạo nên sự linh hoạt và dễ quản lý cho ứng dụng lớn bằng cách chia thành nhiều module nhỏ, độc lập.
* **Scope (Phạm vi)**: Mỗi module có thể có phạm vi riêng, nghĩa là các provider chỉ có sẵn trong module đó nếu không được export ra ngoài.

**5. Ví dụ cụ thể về việc sử dụng module**

Dưới đây là một ví dụ về việc tạo một module `CatsModule` với một controller và một service:

* **cats.module.ts**:

```typescript
import { Module } from '@nestjs/common';
import { CatsController } from './cats.controller';
import { CatsService } from './cats.service';

@Module({
  controllers: [CatsController],
  providers: [CatsService],
})
export class CatsModule {}
```

* **cats.controller.ts**:

```typescript
import { Controller, Get } from '@nestjs/common';
import { CatsService } from './cats.service';

@Controller('cats')
export class CatsController {
  constructor(private readonly catsService: CatsService) {}

  @Get()
  findAll(): string {
    return this.catsService.findAll();
  }
}
```

* **cats.service.ts**:

```typescript
import { Injectable } from '@nestjs/common';

@Injectable()
export class CatsService {
  findAll(): string {
    return 'This action returns all cats';
  }
}
```

#### 6. **Kết luận**

NestJS **module** là một cách tổ chức và quản lý mã nguồn hiệu quả, hỗ trợ tính mô-đun hóa, dễ bảo trì và mở rộng. Bằng cách chia nhỏ ứng dụng thành các module, lập trình viên có thể tổ chức mã một cách dễ dàng, rõ ràng và có khả năng tái sử dụng cao.
