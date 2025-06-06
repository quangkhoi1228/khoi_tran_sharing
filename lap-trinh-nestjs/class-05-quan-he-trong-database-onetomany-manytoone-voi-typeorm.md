# Class 05: Quan hệ trong Database (OneToMany, ManyToOne) với TypeORM

Trong thực tế, dữ liệu thường có mối quan hệ với nhau, ví dụ như **một người dùng có nhiều bài viết**. TypeORM cung cấp cú pháp rõ ràng để định nghĩa các mối quan hệ như `OneToMany`, `ManyToOne`, `OneToOne`, và `ManyToMany`.

***

## Thiết lập quan hệ giữa bảng: user – post

Giả sử chúng ta có hai bảng:

* `User`: người dùng
* `Post`: bài viết (mỗi bài viết thuộc về một người dùng)

### Entity User

```ts
// users/entities/user.entity.ts
import { Entity, PrimaryGeneratedColumn, Column, OneToMany } from 'typeorm';
import { Post } from '../../posts/entities/post.entity';

@Entity()
export class User {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  name: string;

  @OneToMany(() => Post, post => post.user, { cascade: true })
  posts: Post[];
}
```

### Entity Post

```ts
// posts/entities/post.entity.ts
import { Entity, PrimaryGeneratedColumn, Column, ManyToOne } from 'typeorm';
import { User } from '../../users/entities/user.entity';

@Entity()
export class Post {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  title: string;

  @ManyToOne(() => User, user => user.posts, { eager: true })
  user: User;
}
```

### Giải thích cú pháp

* `@OneToMany(() => Post, post => post.user)`: một người dùng có nhiều bài viết
* `@ManyToOne(() => User, user => user.posts)`: một bài viết thuộc về một người dùng
* `{ cascade: true }`: khi tạo `user`, các bài viết có thể tự động lưu
* `{ eager: true }`: khi truy vấn `post`, tự động lấy thông tin `user`

***

## Cascade và Eager Loading

### Cascade

Cascade cho phép lưu/sửa/xoá dữ liệu liên quan tự động. Ví dụ:

```ts
const user = new User();
user.name = 'Nguyễn Văn A';
user.posts = [
  { title: 'Bài viết 1' } as Post,
  { title: 'Bài viết 2' } as Post,
];

await this.userRepository.save(user); // Tự động lưu cả posts
```

> **Lưu ý:** Cần khai báo `cascade: true` trong `@OneToMany`.

### Eager Loading

Eager loading tự động load quan hệ mà không cần `join`. Ví dụ:

```ts
const post = await this.postRepository.findOne({
  where: { id: 1 },
});
// post.user sẽ có sẵn nếu `eager: true`
```

> **Lưu ý:** Nếu không muốn dùng eager, bạn có thể dùng `leftJoinAndSelect` thủ công.

***

## Repository query nâng cao

Nếu không dùng `eager`, bạn có thể truy vấn quan hệ bằng `QueryBuilder` hoặc `find` với `relations`.

### Cách 1: dùng `relations` trong `find`

```ts
const users = await this.userRepository.find({
  relations: ['posts'],
});
```

### Cách 2: dùng `QueryBuilder`

```ts
const users = await this.userRepository
  .createQueryBuilder('user')
  .leftJoinAndSelect('user.posts', 'post')
  .getMany();
```

***

## Thực hành: API lấy user kèm danh sách bài viết

### Mục tiêu

Tạo hệ thống NestJS có 2 module: `users` và `posts` với quan hệ `OneToMany` – `ManyToOne`.

### Yêu cầu

* Tạo `User` và `Post` entity như hướng dẫn trên
* Tạo `UsersService` với hàm `findAllUsersWithPosts()`
* Controller có endpoint: `GET /users` để lấy user cùng bài viết
* Dùng quan hệ `relations` hoặc `join` để trả về đúng cấu trúc

### Gợi ý controller

```ts
// users/users.controller.ts
import { Controller, Get } from '@nestjs/common';
import { UsersService } from './users.service';

@Controller('users')
export class UsersController {
  constructor(private readonly usersService: UsersService) {}

  @Get()
  getUsersWithPosts() {
    return this.usersService.findAllUsersWithPosts();
  }
}
```

### Gợi ý service

```ts
// users/users.service.ts
findAllUsersWithPosts() {
  return this.userRepository.find({
    relations: ['posts'],
  });
}
```

### Output mong muốn

```json
[
  {
    "id": 1,
    "name": "Nguyễn Văn A",
    "posts": [
      { "id": 1, "title": "Bài viết 1" },
      { "id": 2, "title": "Bài viết 2" }
    ]
  }
]
```

***

## Bài tập thực hành

### Mục tiêu

Tự tay cài đặt mối quan hệ `User - Post`, tạo dữ liệu giả và truy xuất.

### Yêu cầu bài tập

* Tạo bảng `User` và `Post` với quan hệ
* Sử dụng `Postman` để thêm dữ liệu:
  * Tạo user
  * Gán nhiều bài viết cho user
* Viết route:
  * `GET /users`: trả về user và danh sách bài viết
  * `GET /posts`: trả về bài viết và user đi kèm
* Dùng cả `relations` và `QueryBuilder` để thực hành truy vấn

***

## Kết luận

Qua bài học này, bạn đã học cách:

* Định nghĩa quan hệ OneToMany – ManyToOne trong TypeORM
* Sử dụng `cascade` để lưu dữ liệu liên kết
* Dùng `eager` để tự động load quan hệ
* Truy vấn dữ liệu liên kết bằng `relations` hoặc `QueryBuilder`

Kỹ năng này rất quan trọng khi bạn xây dựng hệ thống có quan hệ phức tạp, chẳng hạn như blog, diễn đàn, hệ thống thương mại điện tử…
