---
description: des
---

# Phân quyền user

## URL là gì?

**URL** là **một đường dẫn** giúp cho người dùng có thể **lấy được các resource của trang**&#x20;

**Các loại URL thường gặp:**

* File&#x20;
* Api
* Trang&#x20;
* ...

## Hệ phân quyền&#x20;

**Phân quyền user** là chức năng cho phép hệ thống **quy định được user** nào sẽ được **truy cập vào URL nào.**

**Các thành phần trong hệ phân quyền:**

### URL

đã được đề cập ở trên

### User

**user** là **người dùng trên hệ thống** có thể đăng nhập thông qua mật khẩu và tên đăng nhập.&#x20;

Một số thông tin quan trọng của user(tbuser):

| Tên trường    | Diễn giải                              | Kiểu dữ liệu | ví dụ         |
| ------------- | -------------------------------------- | ------------ | ------------- |
| id            | mã id tự sinh của user                 | number       | 1             |
| username      | tên tài khoản                          | string       | user1         |
| loginusername | tên đăng nhập (dùng để đăng nhập)      | string       | loginuser1    |
| password      | mật khẩu (dùng để đăng nhập)           | string       | passworduser1 |
| isvalidated   | trạng thái có được đăng nhập hay không | boolean      | true          |

#### Minh hoạ

![](<../.gitbook/assets/image (68).png>)

### Group

**group** quy định **nhóm người dùng** trên hệ thống.&#x20;

Một số thông tin quan trọng của group(tbgroup):

| Tên trường       | Diễn giải               | Kiểu dữ liệu | ví dụ   |
| ---------------- | ----------------------- | ------------ | ------- |
| id               | mã id tự sinh của group | number       | 1       |
| groupname        | tên group               | string       | group1  |
| groupdescription | mô tả                   | string       | mô tả 1 |

#### Minh hoạ

![](<../.gitbook/assets/image (58).png>)

**Admin có thể quy định:**

* Một user có thể ở nhiều nhóm
* Một nhóm có thể chứa nhiều user&#x20;

Dựa vào bảng **tbusergroup** - bảng này **quy định user nào thuộc group nào**.

Một số thông tin quan trọng của user group(tbusergroup):

| Tên trường | Diễn giải                                       | Kiểu dữ liệu | ví dụ  |
| ---------- | ----------------------------------------------- | ------------ | ------ |
| groupname  | tên group - trùng với groupname của group       | string       | group1 |
| username   | username - trùng với cột username của tài khoản | string       | user1  |

#### Minh hoạ

![](<../.gitbook/assets/image (59).png>)

### Role

**role** là một **luật quy định group** nào **được/không được truy cập vào URL**

Một số thông tin quan trọng của group(tbgroup):

| Tên trường  | Diễn giải                        | Kiểu dữ liệu | ví dụ  |
| ----------- | -------------------------------- | ------------ | ------ |
| id          | mã id tự sinh                    | number       | 1      |
| groupname   | tên group                        | string       | group1 |
| resourceurl | url                              | string       | /api/1 |
| roletype    | quy định được hay không được vào | allow/deny   | allow  |

#### Minh hoạ

![](<../.gitbook/assets/image (60).png>)

{% hint style="info" %}
Từ các thuật ngữ trên ta thấy:

1. user thuộc group
2. group được phép truy cập/từ chối vào các URL dựa vào Role

\==> user được phân quyền URL
{% endhint %}

## Menu động

### Module

**Module** được ví như **một chức vụ trong hệ thống** như admin, contentcreater,..&#x20;

**Module** sẽ **quy định group nào** sẽ **được quyền truy cập vào các module nào**

Một số trường quan trọng của tbmodule:

| Tên trường | Diễn giải                                                                     | Kiểu dữ liệu | ví dụ   |
| ---------- | ----------------------------------------------------------------------------- | ------------ | ------- |
| id         | mã id tự sinh                                                                 | number       | 1       |
| modulename | tên module                                                                    | string       | module1 |
| groupname  | tên group                                                                     | string       | group1  |
| priority   | Độ ưu tiên, quy định thứ tự của module này khi lấy danh sách module của group | number       | 1       |

### Cây menu&#x20;

cây **menu** là một tính năng cho phép chúng ta **tạo và tuỳ chỉnh menu.**

Cây menu được **quy định theo từng modulename**

Tham khảo /system/menumoduleconfig

![](<../.gitbook/assets/image (56).png>)

{% hint style="info" %}
Từ đây chúng ta hiểu như sau:

1. Group có thể truy cập vào nhiều module
2. Mỗi module như một chức vụ và có 1 menu đi kèm
3. Menu có thể tuỳ chỉnh băng admin
4. User thuộc group

\==> Từ đó chúng ta có thể quy định được user có thể xem được nhiều menu khác nhau và menu này có thể tuỳ chỉnh được
{% endhint %}
