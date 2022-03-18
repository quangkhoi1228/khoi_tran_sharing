# deploy doc

deploy doc

### Tạo folder deploy, file build.xml, folder chứa các file jar <a href="#_iv5zv5c529l" id="_iv5zv5c529l"></a>

### B1: trong folder project tạo folder "deloy" <a href="#_qkhthdtapehe" id="_qkhthdtapehe"></a>

![](../.gitbook/assets/0)

### B2: chuột phải project -> Export <a href="#_q3tdffhen9vc" id="_q3tdffhen9vc"></a>

![](../.gitbook/assets/1)

### B3: Chọn Runnable JAR file <a href="#_39yi68293bod" id="_39yi68293bod"></a>

![](../.gitbook/assets/2)

### B4: điền các thông số <a href="#_eutrgi99cswn" id="_eutrgi99cswn"></a>

![](../.gitbook/assets/3)

1. Launch configuration: trỏ đến run as configuration của project
2. Export destination: trỏ đến thư mục deploy vừa tạo và đặt tên file là ‘project.jar’
3. Library handling: chọn cái 3
4. Tích vào save as ANT script (Nhớ cái ant script vào máy trước)
5. ANT script location: trỏ đến thư mục deploy và đặt tên ‘build\_projectname.xml’

### B5: Kết quả <a href="#_o5am78wqxeqy" id="_o5am78wqxeqy"></a>

![](../.gitbook/assets/4)

### get ssh keygen <a href="#_j1s4m9ptduwb" id="_j1s4m9ptduwb"></a>

![](../.gitbook/assets/5)

cd %user%/.ssh

cat id\_rsa.pub

thêm host vào /etc/hosts

![](../.gitbook/assets/6)

ssh ![](../.gitbook/assets/7)

### Setup project trên server <a href="#_hpvvkqqzfox1" id="_hpvvkqqzfox1"></a>

### B1: tạo thư mục ‘project name’ trên server <a href="#_8tatf0kv4b12" id="_8tatf0kv4b12"></a>

ssh username@server

mkdir projectname

### B2: copy các file liên quan lên ‘project name’ .jar, thư mục chứa các file jar, .properties file <a href="#_83r3ix636dnx" id="_83r3ix636dnx"></a>

exit

cd /project/deploy

scp build\_projectname.xml username@server:path/folderproject

scp projectname.jar username@server:path/folderproject

scp -r projectname\_lib username@server:path/folderproject

scp ../\*\*.properties username@server:path/folderproject

...

scp ../\*\*.properties username@server:path/folderproject

_lưu ý:_

* _path/folderproject là đường dẫn tuyệt đối đến folder vừa tạo ở bước 1_
* _scp -r để copy folder_
* /\*\*.properties là đường dẫn đến các file cần thiết .properties

### B3: Tạo file deploy\_projectname.sh trong local computer <a href="#_7gx2tffn43m2" id="_7gx2tffn43m2"></a>

ant -f build\_cbv.xml

scp cbv.jar shinobiweb@cbvuat:/home/shinobiweb/cbv/

cd ../git/cbv/web/optimize

chmod +x ./buildresource.sh

./buildresource.sh

cd ../

tar cjvf webdir.tar.bz2 webdir

echo 'extract done'

scp webdir.tar.bz2 shinobiweb@cbvuat:/home/shinobiweb/cbv/

\#scp ../dbamailconfig.properties shinobiweb@cbvuat:/home/shinobiweb/cbv/

\#scp ../dbconfig.properties shinobiweb@cbvuat:/home/shinobiweb/cbv/

\#scp ../logdbconfig.properties shinobiweb@cbvuat:/home/shinobiweb/cbv/

scp ../s3.properties shinobiweb@cbvuat:/home/shinobiweb/cbv/

scp ../web.properties shinobiweb@cbvuat:/home/shinobiweb/cbv/

rm webdir.tar.bz2

ssh shinobiweb@cbvuat 'sh deploy\_stockmobile.sh' &

![](../.gitbook/assets/8)

### B4: Tạo file deploy\_projectname.sh trên server <a href="#_1n136iup8z6s" id="_1n136iup8z6s"></a>

cd stockmobile

rm -r shinobicore

tar xjvf shinobicore.tar.bz2

ps -ef | grep "stockmobile.jar" | awk '{print $2}' | xargs kill

cd ../jdk-11.0.5+10/bin

./java -Xshareclasses -XX:SharedCacheHardLimit=1024m -Xscmx300m -XX:+IdleTuningGcOnIdle -Xtune:virtualized -Xquickstart -Xgc:concurrentScavenge -server -Xmx6g -Xms6g -XX:SurvivorRatio=8 -XX:NewSize=256m -XX:MaxNewSize=256m -jar -Djdk.nio.maxCachedBufferSize=262144 -DHAZELCAST\_CLUSTER\_IPS=localhost -DIS\_STARTUP\_SERVICE\_ENABLED=false -Dconfig=/home/gbsofts/stockmobile/web.properties -Ddbconfig=/home/gbsofts/stockmobile/db.properties -Ds3=/home/gbsofts/stockmobile/s3.properties -Dlogdbconfig=/home/gbsofts/stockmobile/logdb.properties -Dwebdir=/home/gbsofts/stockmobile/shinobicore/ -Dlogname=shinobitrade1.log /home/gbsofts/stockmobile/stockmobile.jar &
