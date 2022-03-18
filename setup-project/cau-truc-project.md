---
description: Mô tả cấu trúc project
---

# Cấu trúc project

```python
project_name
├── src/    # chứa source code backend
├── web/    # chứa source các phần liên quan đến frontend
|   ├── optimize/   # chứa thông tin tối ưu web site - build resource 
|   └── webdir/     # chứa source code frontend
|       ├── fragment/   # chứa các fragment/các phần html sử dụng lại trong trang như header, sidebar, ...
|       ├── public/     # chứa các trang không cần đăng nhập vẫn vào được như login, signup, home, ... 
|       ├── private/    # chứa các trang cần đăng nhập như userinfo, userdashboard, ... 
|       ├── static/     # chứa các phần về resource tĩnh như CSS, JS, SASS, image, ...
|       |   ├── css/    # chứa các phần về CSS
|       |   |   ├── component/  # các thư viện CSS tự viết
|       |   |   ├── library/    # các thư viện CSS sử dụng bên thứ 3
|       |   |   └── render/     # các file CSS viết riêng cho từng trang
|       |   ├── image/  # chứa các phần về hình ảnh
|       |   ├── js/     # chứa các phần về JS
|       |   |   ├── component/  # các thư viện JS tự viết
|       |   |   ├── library/    # các thư viện JS sử dụng bên thứ 3
|       |   |   └── render/     # các file JS viết riêng cho từng trang
|       |   |   └── template/   # các file JS viết riêng cho từng template của trang
|       |   ├── media/  # chứa các phần về media như âm thanh, video
|       |   ├── production/     # chứa các file js, css đã được tối ưu và được import sử dụng trong trang
|       |   └── sass/   # chứa các phần về sass
|       ├── system  #  chứa các trang của admin như user, group, ... 
|       ├── systemfragment/     # chứa các fragment/các phần html sử dụng lại trong trang như header, sidebar, ... nhưng của trang admin
|       ├── systemtemplate/     # chứa các template trang admin
|       └── template    # chứa các template trang nhưng của người dùng
├── project_file.log    # file log của project
├── web.properties  # file lưu thông tin của website như port, api,...
├── dbconfig.properties     # file lưu thông tin cấu hình database
├── pom.xml     # file lưu thông tin cấu hình maven
└── ...     # các file .properties khác
```

Hình ảnh

![](<../.gitbook/assets/image (67).png>)
