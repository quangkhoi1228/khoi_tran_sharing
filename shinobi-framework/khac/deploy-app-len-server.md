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

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Trong ảnh trên chia thành các nhóm chính sau:

1. athenaweb.jar: File web app nén dưới dạng java archive file
2. athenaweb\_lib/: Thư mục chứa danh sách các thư viện trong project
3. athena.tar.gz: File này là file tạm lúc copy file lên server(không tham gia quá trình chạy app)
4. Các file config: web.properties, s3.properties, dbconfig.properties,...
5. web/: Thư mục chứa phần giao diện của web app (phần này có hay không tuỳ thuộc vào web app có sử dụng giao diện hay không)

## Yêu cầu

1. Java JDK portable. Download [tại đây](https://drive.google.com/file/d/14THaCJBWqbnYYSiNORPwF0vlE1dNUXBS/view?usp=sharing)
2. Eclipse&#x20;
3. Chạy được Web App bằng Eclipse

## Quy trình deploy

### Tạo thư mục chứa các file deploy

{% hint style="info" %}
Tạo folder `deploy` để chứa các file phục vụ mục đích deploy. Thư mục này thường đặt trong thư mục của Project và ngang hàng với thư mục `git`
{% endhint %}

<figure><img src="https://lh6.googleusercontent.com/Z66c36XtkYZhFODji-KdrNaJ0UFqQIYSNXzhTLvWmSrg4rbEGrvjOLV-okWlJyDAp0LTW5uJ2Re0gjHQpsZmHi26pRARRxmZhl-nv-dtb4cGwFgtsvC_zssEjfWn2i49eLB4Wcch7WE5IR8zWkoJ3w0VpBeRB6hWcbBo7KX4RA1qRJu1Y7LSneXL" alt=""><figcaption></figcaption></figure>

### Export file nén và thư mục chứa các library của project

1.  Chuột phải project -> Export\


    <figure><img src="https://lh6.googleusercontent.com/mB3nkfwc9vtt0IgGnXEbjTc2O6CzhmJShj7xHzdjRg7Mgpb_f31KLBztxTbSE0LTj1KB3Z6ZR0czH6LjpAWgdUHYPLyNtYHtdHpxklcys12AiST1YEC7FZvYU5_pBM_37oPqbNtL6o8rL84zs6yNAAuLzTN1yqxUnnYeIlq6qFdc9OvxcXtvbBlG" alt=""><figcaption></figcaption></figure>
2.  Chọn Runnable JAR file\


    <figure><img src="https://lh4.googleusercontent.com/gfVPQa9IJlzo6kRivCUfHJn2VSZEcNYJxyvmUIFg4_FpOlbnTv51zNCkFe9n_BsKAn6JSTwdjSQNrU7KAXSIRanYnrgChl4q61yKWG-XBdMcmPGUSYAY8LowTUcNhRMDNgaARJdawHuCKTKAyH-LGRv1As0zkhPs2yPLuCiRrmZ35Xuwsd7JR1vm" alt=""><figcaption></figcaption></figure>
3. Điền các thông số\
   ![](https://lh6.googleusercontent.com/YoC\_8hKdSgk4S-fptk\_G-oVbIiqlFZI5PYSHl1xGMJjHV\_lmCZmWRHsxd3AhUxZ1ow9CH5UyspWw1IIAmlVo5ol3mushxrPs5MNStSL\_dVf-zY-mHQKEdCc-yJr2TW\_GLADVIrSRbHUrUBH1BhNWyj6XIrMTxsNTTB6KG4ywDHo9rhuzRrwXx2FS)\


{% hint style="info" %}
1. Launch configuration: trỏ đến run as configuration của project&#x20;
2. Export destination: trỏ đến thư mục deploy vừa tạo và đặt tên file là ${project-name}.jar’
3. Library handling: chọn cái 3&#x20;
4. Tích vào save as ANT script (Nhớ cài ant script vào máy trước)&#x20;
5. ANT script location: trỏ đến thư mục deploy và đặt tên build\_${project-name}.xml&#x20;
{% endhint %}

**Kết quả**

<figure><img src="https://lh4.googleusercontent.com/9HwIQOUjZsm2fFZDV8OfwtltNmWF7lakBDqzUXc8RSHSS1E08sAi_IH1yj-5L1KU-TP9h2xENqUnD___bVX23pfXExPD5Vlee_pBb1nZo_MKw1NY7lW7uyY9n0vQT3tuet8oYNn0m7SWAyC6nyP08TpCkLyPfq_8GQrAsZN7HU8KwQi9UzPwMrBf" alt=""><figcaption></figcaption></figure>



####





