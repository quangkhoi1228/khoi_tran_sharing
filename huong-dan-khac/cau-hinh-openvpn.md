---
description: Cách cấu hình OpenVPN trên các hệ điều hành
---

# Cấu hình OpenVPN

## Cấu hình OpenVPN

### MacOS

Sử dụng TunnelBlick để kết nối

### Linux

Sử dụng OpenVpn command line để cấu hình&#x20;

#### Không có username và password

1. Tạo folder chứa cấu hình VPN. Tất cả các thao tác file sau bước 1 đều nằm trong thư mục này
2. Tạo file chứa username + password. Ví dụ: pass.txt
3. Start openvpn

`sudo "computer password" | sudo -S openvpn --config /duong_dan_den_open_vpn_file/ten_file_vpn.ovpn`

#### Có username và password

1. Tạo folder chứa cấu hình VPN. Tất cả các thao tác file sau bước 1 đều nằm trong thư mục này
2. Tạo file chứa username + password. Ví dụ: pass.txt
3. Start OpenVPN

`sudo "computer password" | sudo -S openvpn --config /duong_dan_den_open_vpn_file/ten_file_vpn.ovpn --auth-user-pass pass.txt`

{% hint style="info" %}
Fix lỗi routines::ca md too weak

[https://superuser.com/questions/1737052/openssl-error0a00018essl-routinesca-md-too-weak](https://superuser.com/questions/1737052/openssl-error0a00018essl-routinesca-md-too-weak)
{% endhint %}
