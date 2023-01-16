# Cấu hình và lấy SSH key

## SSH key là gì?

SSH key là một phương thức xác thực VPS/Server thay cho mật khẩu vì khi dùng mật khẩu bảo mật sẽ rất kém do mật khẩu bị lộ khi gõ hoặc hacker sử dụng tool để dò mật khẩu.

SSH key là 1 private key được sinh ra và lưu trữ trên máy tính của bạn. Chúng ta copy private key này bỏ vào server để khi chúng ta truy cập thì sẽ gửi kèm private key này cho server kiểm tra. Nếu trùng khớp thì cho phép máy tính chúng ta truy cập.

## Cấu hình SSH key

### MacOS, Ubuntu or Other Linux-based OS

Khởi tạo SSH key bằng cách chạy câu lệnh sau trên terminal

```shell
ssh-keygen -t rsa
```

Sau khi chạy câu lệnh OS sẽ hỏi lưu SSH key tại đâu. Mặc định nó sẽ lưu vào **/home/user/.ssh**. Bạn có thể để trống và Enter.

{% hint style="info" %}
Chúng ta có thể đổi vị trí lưu tuy nhiên theo kinh nghiệm cá nhân thì chúng ta không nên thay đổi đường dẫn mặc định.
{% endhint %}

Tiếp tục nó sẽ hỏi bạn có muốn thiết lập keypharse không, nếu muốn thì nhập keypharse cần thiết lập vào rồi Enter.

{% hint style="warning" %}
keypharse (dạng string, cần ghi nhớ) – Mật khẩu để mở private key, khi đăng nhập vào server nó sẽ hỏi cái này.
{% endhint %}

Sau khi cấu hình keypharse(có thể để trống) xong chúng ta đã hoàn tất việc cấu hình SSH key.

## Lấy SSH key

### MacOS, Ubuntu or Other Linux-based OS

```bash
cat ~/.ssh/id_rsa.pub
```

{% hint style="info" %}
Đây là câu lệnh cho vị trí lưu SSH key là mặc định trong trường hợp thay đổi đường dẫn lúc khởi tạo chúng ta phải thay đổi đường dẫn đến file id\_ras.pub cho phù hợp
{% endhint %}

## Cấu hình SSH key trên server

### Lấy SSH key tại máy tính

Dựa theo hướng dẫn[ tại đây](cau-hinh-va-lay-ssh-key.md#lay-ssh-key) để lấy SSH key

### Cấu hình SSH key trên server

1. Chỉnh sửa file authorized\_key trên server
