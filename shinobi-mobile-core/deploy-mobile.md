# Deploy mobile

## Build android và IOS build

### Kiểm tra version 

Kiểm tra version trong file `pubspec.yaml` và tăng version nếu cần

```yaml
version: 2021.04.162+162
```

### Kiểm tra global config 

Kiểm tra và chuyển `mode` trong file `GlobalConfig.dart` sang `aladin` 

```dart
  static String mode = 'aladin';
```

### Chạy file build

sử dụng teminal để chạy dòng lệnh thực file file `deploy_build.sh`

```bash
sh deploy_build.sh
```

## Deploy IOS

### Mở XCode

Mở Xcode và chọn aladin mobile project

![](../.gitbook/assets/image%20%2846%29.png)

### Archive app

Bước 1: Chọn `Runner` chuyển target sang `Any IOS Device`

![](../.gitbook/assets/image%20%2847%29.png)

Bước 2: Chọn `product` ==&gt; `Archive`

![](../.gitbook/assets/image%20%2844%29.png)

### Validate app\(optional\)



### Distribute app

## 

