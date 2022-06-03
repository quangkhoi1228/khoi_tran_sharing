# Phân quyền user

##

## URL là gì?

URL là một đường dẫn giúp cho người dùng có thể lấy được các resource của trang&#x20;

Các loại URL thường gặp:

* File&#x20;
* Api
* Trang&#x20;
* ...

## Hệ phân quyền&#x20;

Phân quyền user là chức năng cho phép hệ thống quy định được user nào sẽ được truy cập vào URL nào.

Các thành phần trong hệ phân quyền:

### URL

đã được đề cập ở trên

### User

user là người dùng trên hệ thống có thể đăng nhậ thông qua mật khẩu và tên đăng nhập.&#x20;

Một số thông tin quan trọng của user(tbuser):

| Tên trường    | Diễn giải                              | Kiểu dữ liệu | ví dụ         |
| ------------- | -------------------------------------- | ------------ | ------------- |
| id            | mã id tự sinh của user                 | number       | 1             |
| username      | tên tài khoản                          | string       | user1         |
| loginusername | tên đăng nhập (dùng để đăng nhập)      | string       | loginuser1    |
| password      | mật khẩu (dùng để đăng nhập)           | string       | passworduser1 |
| isvalidated   | trạng thái có được đăng nhập hay không | boolean      | true          |

![](<../.gitbook/assets/image (68).png>)

### Group

group quy định nhóm người dùng trên hệ thống.&#x20;

Một số thông tin quan trọng của group(tbgroup):

| Tên trường       | Diễn giải               | Kiểu dữ liệu | ví dụ   |
| ---------------- | ----------------------- | ------------ | ------- |
| id               | mã id tự sinh của group | number       | 1       |
| groupname        | tên group               | string       | group1  |
| groupdescription | mô tả                   | string       | mô tả 1 |

![](<../.gitbook/assets/image (56).png>)

**Admin có thể quy định:**

* Một user có thể ở nhiều nhóm
* Một nhóm có thể chứa nhiều user&#x20;

Dựa vào bảng tbusergroup - bảng này quy định user nào thuộc group nào.

Một số thông tin quan trọng của user group(tbusergroup):

| Tên trường | Diễn giải                                       | Kiểu dữ liệu | ví dụ  |
| ---------- | ----------------------------------------------- | ------------ | ------ |
| groupname  | tên group - trùng với groupname của group       | string       | group1 |
| username   | username - trùng với cột username của tài khoản | string       | user1  |

![](<../.gitbook/assets/image (58).png>)

### Role

role là một luật quy định group nào được/không được truy cập vào URL

Một số thông tin quan trọng của group(tbgroup):

| Tên trường  | Diễn giải                        | Kiểu dữ liệu | ví dụ  |
| ----------- | -------------------------------- | ------------ | ------ |
| id          | mã id tự sinh                    | number       | 1      |
| groupname   | tên group                        | string       | group1 |
| resourceurl | url                              | string       | /api/1 |
| roletype    | quy định được hay không được vào | allow/deny   | allow  |

![](<../.gitbook/assets/image (56).png>)

###
