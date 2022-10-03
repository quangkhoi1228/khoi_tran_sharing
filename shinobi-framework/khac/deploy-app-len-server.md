---
description: Trong bài này chúng ta sẽ học cách deploy một ứng dụng shinobi lên server
---

# Deploy app lên server

## Bản chất của deployment

Về bản chất việc ứng dụng web được chạy lúc phát triển trên máy tính của dev và ứng dụng web chạy trên server là giống nhau.

Việc deploy website/web app lên server là việc chúng ta sử dụng một máy tính chuyên dụng(server) để chạy thay cho máy tính của dev lúc phát triển vì server được thiết kế để chạy trong thời gian dài, tránh các lỗi về đường truyền và chi phí thấp hơn.

{% hint style="warning" %}
Tuy nói giống nhau về cách vận hành tuy nhiên việc  chạy web app trên server có thể khác 1 xíu so với việc chạy trên máy tính của dev
{% endhint %}

## Tổng quan về deploy web app shinobi

Web app shinobi(WAS) khi chạy trên IDE là một ứng dụng Java sử dụng Maven để quản lý các library sử dụng trong dự án. Tuy nhiên khi deploy WAS được chạy dưới dạng ứng dụng Java portable sử dụng JDK Java kích hoạt file ứng dụng .jar và một số thư viện của maven để chạy web app.

**Ví dụ về các file có trên server khi deploy WAS (athena website)**

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Trong ảnh trên chia thành các nhóm chính sau:

1. athenaweb.jar: File web app nén dưới dạng java archive file
2. athenaweb\_lib/: Thư mục chứa danh sách các thư viện trong project
3. athena.tar.gz: File này là file tạm lúc copy file lên server(không tham gia quá trình chạy app)
4. Các file config: web.properties, s3.properties, dbconfig.properties,...
5. web/: Thư mục chứa phần giao diện của web app (phần này có hay không tuỳ thuộc vào web app có sử dụng giao diện hay không)

## Hướng dẫn Deploy

### Yêu cầu

1. Java JDK portable. Download [tại đây](https://drive.google.com/file/d/14THaCJBWqbnYYSiNORPwF0vlE1dNUXBS/view?usp=sharing)
2. Eclipse&#x20;

### Quy trình deploy





![](<../../.gitbook/assets/image (1).png>)





