---
description: Deploy Wordpress trên nền ubuntu
---

# Deploy with ubuntu

## Update + Upgrade packages

```bash
sudo apt update && sudo apt upgrade
```

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

## Install Apache&#x20;

```bash
sudo apt install apache2
```

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Kiểm tra apache có chạy không ta dùng

```bash
sudo systemctl status apache2
```

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Sau khi cài ok chúng ta có thể truy cập đường dẫn để xem kết quả

```markdown
https://ip-address
```

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## Install MySql

```bash
sudo apt install mysql-server
```

Để chắc chắn sql server chạy chúng ta dùng lệnh

```bash
sudo systemctl start mysql.service
```

