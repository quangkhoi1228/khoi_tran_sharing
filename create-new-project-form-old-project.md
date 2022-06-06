# Create new project from old project

> &#x20;Sau là quy trình tạo một project mới từ project có sẵn trên **Intellij**, ví dụ được mô phỏng dưới đây dưa trên project tradingsystemweb, người đọc lưu ý đổi tên project cho phù hợp.

### Bước 1: Duplicate folder chứa project cũ&#x20;



![](<.gitbook/assets/Screenshot from 2022-04-03 16-33-40 (1).png>)

Có thể sử dụng copy paste thông thường để tạo projetc mới&#x20;

### Bước 2:  Đổi tên folder mới đã tạo

![](<.gitbook/assets/Screenshot from 2022-04-03 17-09-55.png>)

Đổi từ **tradingsystemweb** (copy) sang **doraemonbotweb**&#x20;

### Bước 3: Đổi tên forder bên trong folder git

![](<.gitbook/assets/Screenshot from 2022-04-03 17-11-00.png>)

Tương tự như bước 3, cần phải đổi cả tên thư mục nằm trong folder git từ tên cũ sang tên mới (**tradingsystemweb** sang **doraemonbotweb** )

### Bước 4: Xóa thư mục .git nằm trong folder chứa source project

Do copy thành project mới tuy nhiên project vẫn có sự connect lên gitlab, cần phải xóa connect này bằng cách xóa thư mục .git để tránh các ảnh hưởng lên git.

![](<.gitbook/assets/Screenshot from 2022-04-03 17-12-59.png>)

Do thư mục .git là thư mục ẩn, tick vào ô _**Show Hidden Files**_ như trên hình để hiện các thư mục ẩn, sau đó xóa thư mục .git như hình dưới.

![](<.gitbook/assets/Screenshot from 2022-04-03 17-12-36.png>)

### Bước 5: Import folder chứa source project vào intellij

![](<.gitbook/assets/Screenshot from 2022-04-03 17-30-45.png>)

Mở project mới trong IntelliJ như trên hình&#x20;

{% hint style="info" %}
Lưu ý: Mở thư mục bên trong folder git&#x20;
{% endhint %}

### Bước 6: Đổi tên trong file pom

![](<.gitbook/assets/Screenshot from 2022-04-03 17-34-48.png>)

Trong file pom.xml, đổi tên project từ cũ sang mới (chỗ quét khối như trên hình)&#x20;

### Bước 7: Đổi tên module trong open module setting

![](<.gitbook/assets/Screenshot from 2022-04-03 17-36-58.png>)

Chuột phải vào thư mục, chọn Open Module Setting (hoặc dùng phím tắt F4), sau đó đổi tên ở ô Name như trên hình (đổi từ aladin sang doraemonbot).&#x20;

### Bước 8: Đổi tên class file main

![](<.gitbook/assets/Screenshot from 2022-04-03 17-39-08.png>)

Vào thư mục main, đổi tên file main từ tên cũ sang tên mới như trên hình &#x20;

### Bước 9: Đổi tên đường dẫn package project

![](<.gitbook/assets/Screenshot from 2022-04-03 17-41-31.png>)

Đổi từ _**com.tradingsystemweb**_ sang _**com.doraemonweb**_

### Bước 10: Đổi tên đường dẫn trong file web.properties/localhost.properties

![](<.gitbook/assets/Screenshot from 2022-04-03 17-43-49.png>)

Trong file web.properties (lưu ý một số project cũ sẽ là file localhost.properties), đổi lại tên các đường dẫn (những chỗ quét khối như trên hình) từ  _**com.tradingsystemweb**_ sang _**com.doraemonweb.**_

### Bước 11: Đổi cấu hình trong run config&#x20;

![](<.gitbook/assets/Screenshot from 2022-04-03 17-47-55.png>)

Đổi file main mới, tên mới và cấu hình runconfig là chạy được&#x20;
