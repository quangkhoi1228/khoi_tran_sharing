---
description: Deploy Wordpress trên nền ubuntu
---

# Deploy with ubuntu

## Update + Upgrade packages

```bash
sudo apt update && sudo apt upgrade
```

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

## Install Apache&#x20;

```bash
sudo apt install apache2
```

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Kiểm tra apache có chạy không ta dùng

```bash
sudo systemctl status apache2
```

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Sau khi cài ok chúng ta có thể truy cập đường dẫn để xem kết quả

```markdown
https://ip-address
```

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

## Install MySql

```bash
sudo apt install mysql-server
```

Để chắc chắn sql server chạy chúng ta dùng lệnh

```bash
sudo systemctl start mysql.service
```



## Install PHP

```bash
sudo apt install php php-mysql
```

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Để kiểm tra PHP được cài đặt hay chưa chúng ta tạo file info.php

```bash
sudo nano /var/www/html/info.php
```

Thêm nội dung này và save lại

```php
<?php
phpinfo();
?>
```

Truy cập vào link để xem thông tin&#x20;

```url
https://ip-address/info.php
```

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>



## Tạo database&#x20;
