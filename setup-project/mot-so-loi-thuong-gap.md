# Một số lỗi thường gặp

## Không tìm thấy file .properties

```properties
Exception in thread "main" java.io.FileNotFoundException: /Volumes/home/Project/cmedweb/git/cmedweb/dbconfig.properties (No such file or directory)
	at java.base/java.io.FileInputStream.open0(Native Method)
	at java.base/java.io.FileInputStream.open(FileInputStream.java:219)
	at java.base/java.io.FileInputStream.<init>(FileInputStream.java:157)
	at java.base/java.io.FileInputStream.<init>(FileInputStream.java:112)
	at com.shinobiutil.dbhelper.DbConfigFactory.create(DbConfigFactory.java:26)
	at com.shinobi.persistence.impl.DataSourceManager.registerDataSource(DataSourceManager.java:27)
	at com.cmed.main.CmedMain.registerDB(CmedMain.java:59)
	at com.cmed.main.CmedMain.main(CmedMain.java:34)
```

Không tìm thấy file .properties là một lỗi thường hay xảy ra và thường sẽ có các trường hợp sau:&#x20;

### Đường dẫn được cấu hình không chính xác

Trong run config của project sẽ cấu hình các đường dẫn đến file .properties

```systemd
# ví dụ sai
-Dconfig=/đường_dẫn_máy_người_ta/cmedweb/web.properties   
-Ds3=/đường_dẫn_máy_người_ta/cmedweb/s3.properties    
...
```

Trong một vài trường hợp phải chỉnh lại đường dẫn trỏ đến file .properties trên máy của mình cho chính xác

```systemd
# đúng
-Dconfig=/Volumes/home/Project/cmedweb/git/cmedweb/web.properties   
-Ds3=/Volumes/home/Project/cmedweb/git/cmedweb/s3.properties   
```

### Không có file .properties trong source code

Các file properties có chứa các thông số nhạy cảm như: địa chỉ IP, username, password,... của hệ thống và thường sẽ không được public và commit do đó khi pull source code xuống thông thường sẽ không có các file này.

Để fix lỗi này chúng ta phải tạo các file này, một vài ví dụ file .properties

* dbconfig.properties

```systemd
DRIVER_CLASS=org.postgresql.Driver
JDBC_URL=jdbc:postgresql://192.168.1.1:5432/dbcmed
USER_NAME=username
PASSWORD=username
MAX_POOL_SIZE=10
TIME_OUT=0
```

* logdbconfig.properties

```systemd
DRIVER_CLASS=org.postgresql.Driver
JDBC_URL=jdbc:postgresql://192.168.1.1:5432/dbsystemlog
USER_NAME=username
PASSWORD=username
MAX_POOL_SIZE=10
TIME_OUT=0
```

* config.properties

```systemd
#Caching config
com.shinobiutil.caching.CachingConfig.HAZELCAST_PORT=5777
```

* s3.properties

```systemd
BUCKET_URL = https://s3.wasabisys.com
BUCKET_AK =0J7P5IKNDD8JUBHHDJDWIWDJWDN2
BUCKET_SK =12313123jjda12312dawdawd
BUCKET_REGION = us-east-1
BUCKET_AVATAR = test.finance
BUCKET_IMAGE = test.finance.public.image
BUCKET_FILE = test.finance.public.file
BUCKET_IMAGE_URL = https://image.test.finance
BUCKET_FILE_URL = https://file.test.finance
```
