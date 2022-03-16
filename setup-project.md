---
description: Setup project là công việc đầu tiên để làm việc với 1 dự án
---

# Setup Project

## Tạo cấu trúc thư mục

![](<.gitbook/assets/image (48) (1).png>)

Thư mục chứa project có cấu trúc thư mục như trên.

{% hint style="info" %}
Trong đó:

* _**project\_name**_ đầu tiên là thư mục chứa dự án và trùng tên với tên của dự án
* _**git**_ là thư mục chứa source code của dự án
* _**project\_name**_ thứ hai là source code của dự án
{% endhint %}

Các bạn có thể sử dụng giao diện để tạo hoặc sử dụng các lệnh sau:

```powershell
mkdir project_name
cd project_name
mkdir git
cd git
```

## Kéo source code từ git

### Clone source

Đầu tiên chúng ta phải có 1 đường dẫn git đến repo của chúng ta ví dụ:

```url
https://gitlab.com/luongdangdung/cmedweb.git
```

Tại thư mục git chúng ta sử dụng câu lệnh sau để kéo source

```bash
git clone https://gitlab.com/luongdangdung/cmedweb.git
```

Khi thành công sẽ có tiến thông báo tiến trình trong terminal và source sẽ được clone về trong thư mục git

```bash
Cloning into 'cmedweb'...
remote: Enumerating objects: 1485, done.
remote: Counting objects: 100% (12/12), done.
remote: Compressing objects: 100% (12/12), done.
remote: Total 1485 (delta 0), reused 0 (delta 0), pack-reused 1473
Receiving objects: 100% (1485/1485), 45.49 MiB | 10.69 MiB/s, done.
Resolving deltas: 100% (663/663), done.
```

![Thư mục git sau khi clone project thành công](<.gitbook/assets/image (48).png>)

### Chuyển branch

Khi clone source thì sẽ tự động clone source tại branch gốc (thường là `master` hoặc `main`). Nhưng đôi khi source chúng ta cần lại ở 1 nhánh khác, ví dụ ở đây là `develop`. Do đó chúng ta cần phải chuyển nhánh sang develop và pull code từ nhánh này.

