# Class 09: File Upload & Configuration

## Cấu hình NestJS với @nestjs/config

`@nestjs/config` giúp quản lý biến môi trường (environment variables) và cấu hình dự án một cách linh hoạt.

### Cài đặt

```bash
npm install @nestjs/config
```

### Tạo file `.env` ở thư mục gốc dự án

```env
PORT=3000
UPLOAD_DIR=./public/uploads
```

### Cấu hình `ConfigModule` trong `app.module.ts`

```ts
import { Module } from '@nestjs/common';
import { ConfigModule } from '@nestjs/config';

@Module({
  imports: [
    ConfigModule.forRoot({
      isGlobal: true,  // cho phép sử dụng config ở toàn bộ module
    }),
  ],
})
export class AppModule {}
```

***

## Upload file với Multer (ảnh đại diện người dùng)

NestJS tích hợp Multer để xử lý upload file multipart/form-data rất tiện lợi qua `FileInterceptor`.

### Cài đặt platform-express

```bash
npm install @nestjs/platform-express
```

### Tạo controller xử lý upload ảnh đại diện

```ts
import { Controller, Post, UploadedFile, UseInterceptors, BadRequestException } from '@nestjs/common';
import { FileInterceptor } from '@nestjs/platform-express';
import { diskStorage } from 'multer';
import { extname } from 'path';
import { ConfigService } from '@nestjs/config';

@Controller('users')
export class UsersController {
  constructor(private configService: ConfigService) {}

  @Post('upload-avatar')
  @UseInterceptors(
    FileInterceptor('avatar', {
      storage: diskStorage({
        destination: (req, file, cb) => {
          // Lấy thư mục upload từ biến môi trường, default './public/uploads'
          const uploadPath = this.configService.get<string>('UPLOAD_DIR') || './public/uploads';
          cb(null, uploadPath);
        },
        filename: (req, file, cb) => {
          // Đặt tên file upload dạng avatar-<timestamp>-<random>.<ext>
          const uniqueSuffix = Date.now() + '-' + Math.round(Math.random() * 1e9);
          const ext = extname(file.originalname);
          cb(null, `avatar-${uniqueSuffix}${ext}`);
        },
      }),
      fileFilter: (req, file, cb) => {
        // Chỉ chấp nhận ảnh jpg, jpeg, png
        if (!file.mimetype.match(/\/(jpg|jpeg|png)$/)) {
          return cb(new BadRequestException('Chỉ chấp nhận file ảnh có định dạng jpg, jpeg, png!'), false);
        }
        cb(null, true);
      },
      limits: { fileSize: 2 * 1024 * 1024 }, // giới hạn kích thước 2MB
    }),
  )
  uploadAvatar(@UploadedFile() file: Express.Multer.File) {
    if (!file) {
      throw new BadRequestException('Không có file được gửi lên!');
    }
    const host = `http://localhost:${process.env.PORT || 3000}`;
    const imageUrl = `${host}/uploads/${file.filename}`;
    return {
      message: 'Upload ảnh đại diện thành công',
      filename: file.filename,
      url: imageUrl,
    };
  }
}
```

***

## Xử lý lưu trữ file tạm trong thư mục static

Để truy cập được file upload từ trình duyệt, ta cần cấu hình serve thư mục `public` làm static.

### Cài đặt ServeStaticModule

```bash
npm install @nestjs/serve-static
```

### Cấu hình `ServeStaticModule` trong `app.module.ts`

```ts
import { Module } from '@nestjs/common';
import { ServeStaticModule } from '@nestjs/serve-static';
import { join } from 'path';

@Module({
  imports: [
    ServeStaticModule.forRoot({
      rootPath: join(__dirname, '..', 'public'), // thư mục public nằm ngoài src
      serveRoot: '/uploads', // truy cập file qua http://localhost:3000/uploads/filename
    }),
    // Các module khác
  ],
})
export class AppModule {}
```

***

## Giải thích chi tiết

* **@nestjs/config**: Đọc biến môi trường, tránh hardcode cấu hình, dễ thay đổi môi trường khác nhau.
* **FileInterceptor**: Middleware xử lý file upload, nhận key form data `avatar`.
* **diskStorage**: Thiết lập thư mục lưu và tên file lưu.
* **fileFilter**: Lọc file theo định dạng, đảm bảo chỉ ảnh hợp lệ được upload.
* **limits**: Giới hạn kích thước file upload.
* **ServeStaticModule**: Cho phép truy cập file upload qua URL, phục vụ file tĩnh.

***

## Bài tập thực hành cho học viên

* Tạo file `.env` với `UPLOAD_DIR=./public/uploads`.
* Cài đặt và cấu hình `@nestjs/config` theo hướng dẫn.
* Tạo controller với route POST `/users/upload-avatar` để upload file ảnh đại diện.
* Giới hạn file upload chỉ nhận `jpg, jpeg, png`, kích thước tối đa 2MB.
* Lưu file vào thư mục public/uploads theo cấu hình.
* Cấu hình serve static thư mục `public` để truy cập file upload qua URL.
* Sử dụng Postman hoặc frontend test upload file.
* Kiểm tra upload thành công, trả về URL file, truy cập URL ảnh trên trình duyệt.
* Thử upload file không phải ảnh hoặc quá lớn để kiểm tra lỗi.
