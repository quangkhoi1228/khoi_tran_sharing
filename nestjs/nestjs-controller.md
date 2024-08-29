# NestJS controller

#### NestJS **Controller** là gì?

**Controller** trong NestJS là một thành phần chịu trách nhiệm xử lý các yêu cầu HTTP từ phía client và gửi phản hồi tương ứng. Controller xác định các tuyến đường (routes) và ánh xạ chúng đến các phương thức tương ứng để xử lý dữ liệu, gọi dịch vụ (service), và trả về kết quả cho client.

**1. Chức năng của Controller**

* **Tiếp nhận yêu cầu HTTP**: Controller tiếp nhận các yêu cầu HTTP từ client (GET, POST, PUT, DELETE, v.v.).
* **Xử lý yêu cầu**: Sau khi nhận yêu cầu, Controller sẽ gọi đến các service để xử lý logic nghiệp vụ.
* **Trả về phản hồi**: Sau khi xử lý xong, Controller trả về phản hồi cho client.

Controller chủ yếu đóng vai trò là cầu nối giữa tầng **presentation** (giao diện người dùng) và tầng **service** (logic kinh doanh).

**2. Định nghĩa Controller trong NestJS**

Controller trong NestJS được định nghĩa bằng cách sử dụng decorator `@Controller()` để chỉ định rằng đây là một controller. Trong decorator này, chúng ta có thể chỉ định đường dẫn (route) mà controller sẽ xử lý.

Dưới đây là một ví dụ về một controller đơn giản:

```typescript
import { Controller, Get } from '@nestjs/common';

@Controller('cats')  // Định nghĩa route /cats
export class CatsController {
  @Get()  // Định nghĩa phương thức GET cho route /cats
  findAll(): string {
    return 'This action returns all cats';
  }
}
```

* **`@Controller('cats')`**: Xác định route là `/cats`. Tất cả các yêu cầu bắt đầu bằng `/cats` sẽ được xử lý trong `CatsController`.
* **`@Get()`**: Định nghĩa rằng phương thức này sẽ xử lý yêu cầu HTTP GET cho route `/cats`.

**3. Các Decorator HTTP trong Controller**

NestJS cung cấp nhiều decorator tương ứng với các phương thức HTTP:

* **`@Get()`**: Xử lý yêu cầu HTTP GET.
* **`@Post()`**: Xử lý yêu cầu HTTP POST.
* **`@Put()`**: Xử lý yêu cầu HTTP PUT.
* **`@Delete()`**: Xử lý yêu cầu HTTP DELETE.
* **`@Patch()`**: Xử lý yêu cầu HTTP PATCH.

Ví dụ, nếu bạn muốn tạo các phương thức cho các hành động khác nhau (POST, PUT, DELETE):

```typescript
@Controller('cats')
export class CatsController {
  @Get()
  findAll(): string {
    return 'This action returns all cats';
  }

  @Post()
  create(): string {
    return 'This action adds a new cat';
  }

  @Put(':id')
  update(@Param('id') id: string): string {
    return `This action updates a #${id} cat`;
  }

  @Delete(':id')
  remove(@Param('id') id: string): string {
    return `This action removes a #${id} cat`;
  }
}
```

**4. Kết hợp với Service**

Controller thường không trực tiếp xử lý logic nghiệp vụ mà sẽ gọi tới các service để xử lý. Các service sẽ chịu trách nhiệm thực hiện logic phức tạp, còn controller chỉ tập trung vào điều phối yêu cầu và trả về phản hồi.

Ví dụ:

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

Trong ví dụ này:

* `CatsController` sử dụng `CatsService` để lấy dữ liệu về "cats".
* Controller chỉ định nghĩa các route và phương thức, còn logic xử lý sẽ nằm trong `CatsService`.

**5. Định tuyến tham số (Route Parameters)**

NestJS hỗ trợ xử lý các route với tham số bằng cách sử dụng `@Param()`.

Ví dụ:

```typescript
@Controller('cats')
export class CatsController {
  @Get(':id')
  findOne(@Param('id') id: string): string {
    return `This action returns a #${id} cat`;
  }
}
```

Khi có yêu cầu đến `/cats/1`, phương thức `findOne()` sẽ nhận tham số `id` là `1`.

**6. Kết luận**

* **Controller** trong NestJS đóng vai trò điều phối các yêu cầu HTTP và xử lý dữ liệu từ client.
* Chúng giúp định nghĩa các route và ánh xạ chúng đến các phương thức tương ứng.
* Controller kết hợp với service để tách biệt phần logic xử lý nghiệp vụ và phần điều phối yêu cầu, giúp mã nguồn dễ bảo trì và phát triển.
