# Class 04: Kết nối Database với TypeORM

NestJS tích hợp rất tốt với TypeORM – một ORM mạnh mẽ cho TypeScript hỗ trợ PostgreSQL, MySQL, SQLite... Bài học này sẽ giúp bạn biết cách cấu hình cơ bản, tạo `Entity`, `Repository`, thực hiện `Migration`, và truy vấn dữ liệu thực tế với bảng `users`.

***

## Cấu hình kết nối cơ sở dữ liệu PostgreSQL/MySQL với TypeORM

### Cài đặt package

Chạy lệnh sau tùy vào CSDL bạn chọn:

**PostgreSQL:**

```bash
npm install --save @nestjs/typeorm typeorm pg
```

**MySQL:**

```bash
npm install --save @nestjs/typeorm typeorm mysql2
```

### Cấu hình TypeORM module

Trong file `app.module.ts`, thêm:

```ts
import { Module } from '@nestjs/common';
import { TypeOrmModule } from '@nestjs/typeorm';
import { UsersModule } from './users/users.module';

@Module({
  imports: [
    TypeOrmModule.forRoot({
      type: 'postgres', // hoặc 'mysql'
      host: 'localhost',
      port: 5432, // với MySQL là 3306
      username: 'postgres', // hoặc 'root' với MySQL
      password: 'password',
      database: 'testdb',
      autoLoadEntities: true,
      synchronize: true, // chỉ dùng trong phát triển, KHÔNG dùng production
    }),
    UsersModule,
  ],
})
export class AppModule {}
```

### Giải thích các tuỳ chọn

* `type`: Loại CSDL (`postgres`, `mysql`, `sqlite`, v.v.)
* `autoLoadEntities`: Tự động load các entity từ module
* `synchronize`: Tự động tạo bảng khi khởi động (chỉ dùng cho dev)
* `entities`: Có thể dùng thủ công để khai báo entity

***

## Tạo Entity và Repository

### Tạo Entity `User`

```ts
// users/entities/user.entity.ts
import { Entity, PrimaryGeneratedColumn, Column } from 'typeorm';

@Entity()
export class User {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  name: string;

  @Column()
  age: number;
}
```

### Đăng ký Entity vào Module

```ts
// users/users.module.ts
import { Module } from '@nestjs/common';
import { TypeOrmModule } from '@nestjs/typeorm';
import { UsersService } from './users.service';
import { UsersController } from './users.controller';
import { User } from './entities/user.entity';

@Module({
  imports: [TypeOrmModule.forFeature([User])],
  controllers: [UsersController],
  providers: [UsersService],
})
export class UsersModule {}
```

### Sử dụng Repository trong Service

```ts
// users/users.service.ts
import { Injectable } from '@nestjs/common';
import { InjectRepository } from '@nestjs/typeorm';
import { Repository } from 'typeorm';
import { User } from './entities/user.entity';

@Injectable()
export class UsersService {
  constructor(
    @InjectRepository(User)
    private readonly userRepo: Repository<User>,
  ) {}

  findAll() {
    return this.userRepo.find();
  }

  findOne(id: number) {
    return this.userRepo.findOne({ where: { id } });
  }

  create(data: Partial<User>) {
    const newUser = this.userRepo.create(data);
    return this.userRepo.save(newUser);
  }

  update(id: number, data: Partial<User>) {
    return this.userRepo.update(id, data);
  }

  async remove(id: number) {
    const user = await this.findOne(id);
    return this.userRepo.remove(user);
  }
}
```

***

## Migration cơ bản với TypeORM CLI

### Cài đặt CLI

```bash
npm install --save-dev typeorm ts-node
```

Thêm file `ormconfig.ts`:

```ts
// ormconfig.ts
import { DataSource } from 'typeorm';
import { User } from './src/users/entities/user.entity';

export default new DataSource({
  type: 'postgres',
  host: 'localhost',
  port: 5432,
  username: 'postgres',
  password: 'password',
  database: 'testdb',
  entities: [User],
  migrations: ['src/migrations/*.ts'],
  synchronize: false,
});
```

Thêm script vào `package.json`:

```json
"scripts": {
  "migration:generate": "typeorm migration:generate -d ormconfig.ts src/migrations/Init",
  "migration:run": "typeorm migration:run -d ormconfig.ts"
}
```

### Tạo và chạy migration

```bash
npm run migration:generate
npm run migration:run
```

Migration giúp bạn kiểm soát schema DB một cách chặt chẽ, nhất là khi dùng trong production.

***

## Bài tập thực hành

### Mục tiêu

Xây dựng một module quản lý người dùng (`users`) kết nối với cơ sở dữ liệu PostgreSQL hoặc MySQL.

### Yêu cầu

* Cấu hình kết nối với database
* Tạo `User` entity có `id`, `name`, `age`
* Viết service với các chức năng:
  * Thêm người dùng mới
  * Lấy danh sách người dùng
  * Lấy người dùng theo `id`
  * Cập nhật thông tin người dùng
  * Xoá người dùng
* Thêm route tương ứng trong controller
* Viết một migration tạo bảng `users`

### Gợi ý

* Dùng `Postman` để test các API
* Dùng `typeorm migration:generate` để tạo migration
* Nếu rảnh, thêm trường `email`, `createdAt`
