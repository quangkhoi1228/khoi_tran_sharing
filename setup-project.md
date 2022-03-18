# Setup Project

{% hint style="warning" %}
Lưu ý: đây là quy trình setup cho project `cmedweb` nên các bạn lúc thực hiện phải thay đổi tên project cho phù hợp.
{% endhint %}

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

```shell
# vào source code và kiểm tra branch hiện tại
cd cmedweb
git branch
#* master

# chuyển nhánh và pull source
git checkout develop
#Branch 'develop' set up to track remote branch 'develop' from 'origin'.
#Switched to a new branch 'develop'

git pull
#Already up to date.
```

![folder git sau khi pull](<.gitbook/assets/image (58) (1).png>)

## Setup run server với inteliJ IDEA

### Open folder project

Tại giao diện `intelliJ` click vào nút `Open` sau đó chọn thư mục `cmedweb` nằm trong thư mục `git` để open folder project

![InteliJ IDEA](<.gitbook/assets/image (62).png>)

![folder cmedweb](<.gitbook/assets/image (60).png>)

`Trust Project` để hoàn tất

![](<.gitbook/assets/image (64).png>)

### Link source đến các project và thư viện liên quan

Các bạn phải xác định project của mình cần link với các project và thư viện nào?

Trong trường hợp `cmedweb` cần link với:

1. **Project**
   1. shinobicore
   2. shinobiutil
2. **Thư viện**
   1. shinobiserver.jar

#### Các bước thực hiện

Chuột phải vào module và chọn `Open Module Settings`

![](<.gitbook/assets/image (54).png>)

![](<.gitbook/assets/image (50) (1).png>)

#### Link source với project

Tại Project Settings -> Modules chọn tab Sources

![](<.gitbook/assets/image (66).png>)

Nhấn vào nút `Add Content Root` sau đó chọn thư mục `src` của các project liên quan để link source

![](<.gitbook/assets/image (59) (1) (1).png>)

Sau khi thêm thành công sẽ có thêm Source Folder được liệt kê nằm dưới, làm lại tương tự với các project khác.

#### Thêm các thư viện

Tại Project Settings -> Modules chọn tab Dependencies

![](<.gitbook/assets/image (67) (1).png>)

Nhấn vào nút `cộng` sau đó chọn `JARs or Directories...` sau đó chọn file để thêm

![](<.gitbook/assets/image (57).png>)

![](<.gitbook/assets/image (56).png>)

Sau khi thêm thành công sẽ có thêm file được liệt kê nằm dưới, làm lại tương tự với các thư viện khác.

![](<.gitbook/assets/image (49).png>)

Nhấn apply sau khi thêm đầy đủ các project và thư viện liên quan

![](<.gitbook/assets/image (63).png>)

###

### Tạo run config của project

#### Mở panel run config

Tại intelliJ click vào nút `Add Configuration...` để mở panel

![](<.gitbook/assets/image (34) (1).png>)

Chọn `Add new...` và chọn `Application`

![](<.gitbook/assets/image (51) (1).png>)

Bên dưới là các thông  số của run config&#x20;

![](<.gitbook/assets/image (59) (1).png>)

#### Chọn main class

Chọn hàm main của project ở đây là `CmedMain`

![](<.gitbook/assets/image (50).png>)

#### Thêm VM options

VM options là các run time argument của project do đó cần phải xác định chính xác trước khi muốn tạo run config, tham khảo thêm tại [Mô tả chi tiết VM options](setup-project/mo-ta-chi-tiet-vm-options.md)

_Ví dụ VM options của Cmed_&#x20;

```systemd
-Dconfig=/Volumes/home/Project/cmedweb/git/cmedweb/web.properties   
-Ds3=/Volumes/home/Project/cmedweb/git/cmedweb/s3.properties   
-Dwebdir=/Volumes/home/Project/cmedweb/git/cmedweb/web/webdir/   
-Dlogdbconfig=/Volumes/home/Project/cmedweb/git/cmedweb/logdbconfig.properties   
-Ddbconfig=/Volumes/home/Project/cmedweb/git/cmedweb/dbconfig.properties   
-Dcustomconfig=/Volumes/home/Project/cmedweb/git/cmedweb/config.properties   
-Dorg.owasp.esapi.resources=/Volumes/home/Project/cmedweb/git/cmedweb/web   
-Dloggerlevel=TRACE   
-DSTARTWEBSOCKETSERVER=true   
-DSOCKETSERVERHOST=localhost   
-DSOCKETSERVERPORT=8090   
-DISDEVMODE=true   
-Ddomain=LOCALHOST
```

Thêm VM options: Tại panel run config click `modify options` chọn `Add VM options`

![](<.gitbook/assets/image (61) (1).png>)

Dán nội dung vào input VM options vừa hiện ra

![](<.gitbook/assets/image (58).png>)

#### Đặt tên run config&#x20;

![](<.gitbook/assets/image (52).png>)

#### Lưu run config

Nhấn nút `Apply` và `Ok` để hoàn tất quá trình&#x20;

Sau khi thành công sẽ có thêm 1 run config xuất hiện trong danh sách run config

![](<.gitbook/assets/image (34).png>)

### Chạy project

click nút mũi tên kế bên `run config` đang chọn để chạy nó

![](<.gitbook/assets/image (61).png>)

Trong trường hợp có nhiều hàm main click vào dấu xổ xuống tại `run config` hiện tại sau đó chọn `run config` tương ứng để chạy

![](<.gitbook/assets/image (59).png>)&#x20;

{% hint style="danger" %}
Có thể xảy ra lỗi khi chạy `run config`, có thể tham khảo Một số lỗi thường gặp khi chạy Project để khăc phục
{% endhint %}
