# Notification.js

## Notification.js là gì?

notification.js là một thư viện viết dựa trên Bulma dùng để hiển thị ra các thông báo trên màn hình, một vài loại thao tác hỗ trợ như:

* Thông báo thông tin 
* Thông báo lỗi
* Thông báo đang xử lý
* Thông báo xác nhận đơn giản
* Hiển thị hình ảnh

## Yêu cầu

### HTML 

notification.js cần 1 đoạn HTML nằm trong nội dung trang

```markup
<div id="confirmPanel" class="modal is-small">
	<div class="modal-background"></div>
	<div class="modal-card">
		<header class="modal-card-head">
			<p class="modal-card-title" snb-lang="PAGECODE_WARNING">Cảnh báo</p>
			<button class="delete" aria-label="close"></button>
		</header>
		<section class="modal-card-body" snb-lang="PAGECODE_ARE_YOU_SURE">Bạn
			chắc chắn?</section>
		<footer class="modal-card-foot">
			<button class="button is-success yes" snb-lang="PAGECODE_CONFIRM">Xác
				nhận</button>
			<button class="button cancel" snb-lang="PAGECODE_CANCEL">Hủy</button>
		</footer>
	</div>
</div>

<div id="shinobinotification" class="notification  shinobinotification">
	<button class="delete"></button>
	<div class="notificationcontent" snb-lang="PAGECODE_UPDATE_SUCCESS">Update
		success</div>
</div>
```

### CSS

* bulma.css
* shinobicomponent.css

```markup
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma@0.9.2/css/bulma.min.css">
<link rel="stylesheet" href="https://naruto.finance/static/css/component/shinobicomponent.css">
```

### JS

notification.js sử dụng các thư viện khác như: 

* language.js
* util.js
* initbulma.js

```markup
<script src="https://naruto.finance/static/js/component/language.js"></script>
<script src="https://naruto.finance/static/js/component/util.js"></script>
<script src="https://naruto.finance/static/js/component/initbulma.js"></script>
```

## Cách dùng

### Thông báo thông tin

{% tabs %}
{% tab title="Cú pháp" %}
```javascript
shinobi.notification.notification.info(infoMessageContent);
```
{% endtab %}

{% tab title="Code" %}
```javascript
shinobi.notification.notification.info('info');
```
{% endtab %}

{% tab title="Ví dụ" %}
```markup
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/bulma@0.9.2/css/bulma.min.css">
    <link rel="stylesheet"
        href="https://naruto.finance/static/css/component/shinobicomponent.css">


    <script>
        shinobi = {};
    </script>
    <script
        src="https://naruto.finance/static/js/component/language.js"></script>
    <script src="https://naruto.finance/static/js/component/util.js"></script>
    <script
        src="https://naruto.finance/static/js/component/initbulma.js"></script>

    <script
        src="https://naruto.finance/static/js/component/notification.js"></script>
</head>

<body>

    <div class="hero">
        <div class="hero-body">
            <div class="buttons">
                <a id="info" class="button is-info">info</a>
                <a id="error" class="button is-danger">error</a>
                <a id="loading" class="button ">loading</a>
                <a id="loaded" class="button ">loaded</a>
                <a id="confirm" class="button ">confirm</a>
            </div>
        </div>
    </div>
    <div id="confirmPanel" class="modal is-small">
        <div class="modal-background"></div>
        <div class="modal-card">
            <header class="modal-card-head">
                <p class="modal-card-title" snb-lang="PAGECODE_WARNING">Cảnh báo
                </p>
                <button class="delete" aria-label="close"></button>
            </header>
            <section class="modal-card-body" snb-lang="PAGECODE_ARE_YOU_SURE">
                Bạn
                chắc chắn?</section>
            <footer class="modal-card-foot">
                <button class="button is-success yes"
                    snb-lang="PAGECODE_CONFIRM">Xác
                    nhận</button>
                <button class="button cancel"
                    snb-lang="PAGECODE_CANCEL">Hủy</button>
            </footer>
        </div>
    </div>

    <div id="shinobinotification" class="notification  shinobinotification">
        <button class="delete"></button>
        <div class="notificationcontent" snb-lang="PAGECODE_UPDATE_SUCCESS">
            Update
            success</div>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            document.getElementById('info').onclick = function () {
                shinobi.notification.notification.info('info');
            }
        });

    </script>
</body>

</html>
```
{% endtab %}

{% tab title="Kết quả" %}
![](../.gitbook/assets/image%20%2823%29.png)
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Lưu ý: Thông báo thông tin tự biến mất sau 5 giây
{% endhint %}

### Thông báo lỗi

{% tabs %}
{% tab title="Cú pháp" %}
```javascript
shinobi.notification.notification.error(errorMessageContent);
```
{% endtab %}

{% tab title="Code" %}
```javascript
shinobi.notification.notification.error('error');
```
{% endtab %}

{% tab title="Ví dụ" %}
```markup
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/bulma@0.9.2/css/bulma.min.css">
    <link rel="stylesheet"
        href="https://naruto.finance/static/css/component/shinobicomponent.css">


    <script>
        shinobi = {};
    </script>
    <script
        src="https://naruto.finance/static/js/component/language.js"></script>
    <script src="https://naruto.finance/static/js/component/util.js"></script>
    <script
        src="https://naruto.finance/static/js/component/initbulma.js"></script>

    <script
        src="https://naruto.finance/static/js/component/notification.js"></script>
</head>

<body>

    <div class="hero">
        <div class="hero-body">
            <div class="buttons">
                <a id="info" class="button is-info">info</a>
                <a id="error" class="button is-danger">error</a>
                <a id="loading" class="button ">loading</a>
                <a id="loaded" class="button ">loaded</a>
                <a id="confirm" class="button ">confirm</a>
            </div>
        </div>
    </div>
    <div id="confirmPanel" class="modal is-small">
        <div class="modal-background"></div>
        <div class="modal-card">
            <header class="modal-card-head">
                <p class="modal-card-title" snb-lang="PAGECODE_WARNING">Cảnh báo
                </p>
                <button class="delete" aria-label="close"></button>
            </header>
            <section class="modal-card-body" snb-lang="PAGECODE_ARE_YOU_SURE">
                Bạn
                chắc chắn?</section>
            <footer class="modal-card-foot">
                <button class="button is-success yes"
                    snb-lang="PAGECODE_CONFIRM">Xác
                    nhận</button>
                <button class="button cancel"
                    snb-lang="PAGECODE_CANCEL">Hủy</button>
            </footer>
        </div>
    </div>

    <div id="shinobinotification" class="notification  shinobinotification">
        <button class="delete"></button>
        <div class="notificationcontent" snb-lang="PAGECODE_UPDATE_SUCCESS">
            Update
            success</div>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            document.getElementById('info').onclick = function () {
                shinobi.notification.notification.info('info');
            }
            document.getElementById('error').onclick = function () {
                shinobi.notification.notification.error('error');
            }
        });

    </script>
</body>

</html>
```
{% endtab %}

{% tab title="Kết quả" %}
![](../.gitbook/assets/image%20%2839%29.png)
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Lưu ý: Thông báo lỗi không tự biến mất
{% endhint %}

### Thông báo đang xử lý

{% tabs %}
{% tab title="Cú pháp" %}
```javascript
shinobi.notification.notification.loading();
```
{% endtab %}

{% tab title="Code" %}
```javascript
shinobi.notification.notification.loading();
```
{% endtab %}

{% tab title="Ví dụ" %}
```markup
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/bulma@0.9.2/css/bulma.min.css">
    <link rel="stylesheet"
        href="https://naruto.finance/static/css/component/shinobicomponent.css">


    <script>
        shinobi = {};
    </script>
    <script
        src="https://naruto.finance/static/js/component/language.js"></script>
    <script src="https://naruto.finance/static/js/component/util.js"></script>
    <script
        src="https://naruto.finance/static/js/component/initbulma.js"></script>

    <script
        src="https://naruto.finance/static/js/component/notification.js"></script>
</head>

<body>

    <div class="hero">
        <div class="hero-body">
            <div class="buttons">
                <a id="info" class="button is-info">info</a>
                <a id="error" class="button is-danger">error</a>
                <a id="loading" class="button ">loading</a>
                <a id="loaded" class="button ">loaded</a>
                <a id="confirm" class="button ">confirm</a>
            </div>
        </div>
    </div>
    <div id="confirmPanel" class="modal is-small">
        <div class="modal-background"></div>
        <div class="modal-card">
            <header class="modal-card-head">
                <p class="modal-card-title" snb-lang="PAGECODE_WARNING">Cảnh báo
                </p>
                <button class="delete" aria-label="close"></button>
            </header>
            <section class="modal-card-body" snb-lang="PAGECODE_ARE_YOU_SURE">
                Bạn
                chắc chắn?</section>
            <footer class="modal-card-foot">
                <button class="button is-success yes"
                    snb-lang="PAGECODE_CONFIRM">Xác
                    nhận</button>
                <button class="button cancel"
                    snb-lang="PAGECODE_CANCEL">Hủy</button>
            </footer>
        </div>
    </div>

    <div id="shinobinotification" class="notification  shinobinotification">
        <button class="delete"></button>
        <div class="notificationcontent" snb-lang="PAGECODE_UPDATE_SUCCESS">
            Update
            success</div>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            document.getElementById('info').onclick = function () {
                shinobi.notification.notification.info('info');
            }
            document.getElementById('error').onclick = function () {
                shinobi.notification.notification.error('error');
            }

            document.getElementById('loading').onclick = function () {
                shinobi.notification.notification.loading();
            }

            document.getElementById('loaded').onclick = function () {
                shinobi.notification.notification.loaded();
            }
        });

    </script>
</body>

</html>
```
{% endtab %}

{% tab title="Kết quả" %}
![](../.gitbook/assets/image%20%2826%29.png)
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Lưu ý: để hủy thông báo loading gọi hàm

```javascript
shinobi.notification.notification.loaded();
```
{% endhint %}

### Thông báo xác nhận đơn giản

{% tabs %}
{% tab title="Cú pháp" %}
```javascript
shinobi.notification.confirm(callback,options);
```
{% endtab %}

{% tab title="Code" %}
```javascript
//không có options
var callback = function () {
    shinobi.notification.notification.info('Xác nhận thành công');
}
shinobi.notification.confirm(callback);

//có options
var callback = function () {
    shinobi.notification.notification.info('Xác nhận thành công');
}
var options = {
    title: 'Tiêu đề',// title modal
    content: 'Nội dung',// content modal
    yescontent: 'confirm button',
    nocontent: 'cancel button',
    // modalsize: 'is-large', //base on size of Bulma modal component 
    initfunction: function (modalElement) {
        shinobi.notification.notification.info('Hàm chạy khi khởi tạo modal');
    },
    ishiddenfooter: false,// true || false
    notclosewhenacceft: false,// không đóng modal khi nhấn nút chấp nhận
}
shinobi.notification.confirm(callback, options);
```
{% endtab %}

{% tab title="Ví dụ" %}
```markup
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/bulma@0.9.2/css/bulma.min.css">
    <link rel="stylesheet"
        href="https://naruto.finance/static/css/component/shinobicomponent.css">


    <script>
        shinobi = {};
    </script>
    <script
        src="https://naruto.finance/static/js/component/language.js"></script>
    <script src="https://naruto.finance/static/js/component/util.js"></script>
    <script
        src="https://naruto.finance/static/js/component/initbulma.js"></script>

    <script
        src="https://naruto.finance/static/js/component/notification.js"></script>
</head>

<body>

    <div class="hero">
        <div class="hero-body">
            <div class="buttons">
                <a id="info" class="button is-info">info</a>
                <a id="error" class="button is-danger">error</a>
                <a id="loading" class="button ">loading</a>
                <a id="loaded" class="button ">loaded</a>
                <a id="confirm" class="button ">confirm</a>
                <a id="confirmAdvanced" class="button ">confirm has options</a>
            </div>
        </div>
    </div>
    <div id="confirmPanel" class="modal is-small">
        <div class="modal-background"></div>
        <div class="modal-card">
            <header class="modal-card-head">
                <p class="modal-card-title" snb-lang="PAGECODE_WARNING">Cảnh báo
                </p>
                <button class="delete" aria-label="close"></button>
            </header>
            <section class="modal-card-body" snb-lang="PAGECODE_ARE_YOU_SURE">
                Bạn
                chắc chắn?</section>
            <footer class="modal-card-foot">
                <button class="button is-success yes"
                    snb-lang="PAGECODE_CONFIRM">Xác
                    nhận</button>
                <button class="button cancel"
                    snb-lang="PAGECODE_CANCEL">Hủy</button>
            </footer>
        </div>
    </div>

    <div id="shinobinotification" class="notification  shinobinotification">
        <button class="delete"></button>
        <div class="notificationcontent" snb-lang="PAGECODE_UPDATE_SUCCESS">
            Update
            success</div>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            document.getElementById('info').onclick = function () {
                shinobi.notification.notification.info('info');
            }
            document.getElementById('error').onclick = function () {
                shinobi.notification.notification.error('error');
            }

            document.getElementById('loading').onclick = function () {
                shinobi.notification.notification.loading();
            }

            document.getElementById('loaded').onclick = function () {
                shinobi.notification.notification.loaded();
            }
            document.getElementById('confirm').onclick = function () {
                var callback = function () {
                    shinobi.notification.notification.info('Xác nhận thành công');
                }
                shinobi.notification.confirm(callback);
            }

            document.getElementById('confirmAdvanced').onclick = function () {
                var callback = function () {
                    shinobi.notification.notification.info('Xác nhận thành công');
                }
                var options = {
                    title: 'Tiêu đề',// title modal
                    content: 'Nội dung',// content modal
                    yescontent: 'confirm button',
                    nocontent: 'cancel button',
                    // modalsize: 'is-large', //base on size of Bulma modal component 
                    initfunction: function (modalElement) {
                        shinobi.notification.notification.info('Hàm chạy khi khởi tạo modal');
                    },
                    ishiddenfooter: false,// true || false
                    notclosewhenacceft: false,// không đóng modal khi nhấn nút chấp nhận
                }
                shinobi.notification.confirm(callback, options);
            }
        });

    </script>
</body>

</html>
```
{% endtab %}

{% tab title="Kết quả" %}
![](../.gitbook/assets/image%20%2822%29.png)

![](../.gitbook/assets/image%20%2827%29.png)

**Có options**

![](../.gitbook/assets/image%20%2836%29.png)

![](../.gitbook/assets/image%20%2830%29.png)
{% endtab %}
{% endtabs %}

Danh sách các thuộc tính `options` 

| Thuộc tính | Giá trị mặc định | Diễn giải |
| :--- | :--- | :--- |
| title | Cảnh báo | Tiêu đề  |
| content | Bạn chắc chắn | Nội dung |
| yescontent | Xác nhận  | Nội dung nút xác nhận |
| nocontent | Hủy | Nội dung nút hủy |
| initfunction | null | Hàm được gọi khi khởi tạo modal, syntax: function\(modalElement\) |
| ishiddenfooter | false | Có ẩn footer modal hay không |
| notclosewhenacceft | false | Có ẩn modal khi nhấn nút xác nhận hay không |

{% hint style="info" %}
Lưu ý: 

**khi nhấn vào:**

* Nút "Hủy"
* Dấu X của modal
* Bên ngoài modal

==&gt; modal tự đóng 

* Nút "Xác nhận" 

==&gt; chạy hàm `callback`
{% endhint %}

### Hiển thị hình ảnh

{% tabs %}
{% tab title="Cú pháp" %}
```javascript
shinobi.notification.image(url);
```
{% endtab %}

{% tab title="Code" %}
```javascript
shinobi.notification.image('https://i.ytimg.com/vi/NmFlxfisnCI/hqdefault.jpg?sqp=-oaymwEcCNACELwBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDFUR_JC9Ld_7GtGpbiRPtZqXwzWw');
```
{% endtab %}

{% tab title="Ví dụ" %}
```markup
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/bulma@0.9.2/css/bulma.min.css">
    <link rel="stylesheet"
        href="https://naruto.finance/static/css/component/shinobicomponent.css">


    <script>
        shinobi = {};
    </script>
    <script
        src="https://naruto.finance/static/js/component/language.js"></script>
    <script src="https://naruto.finance/static/js/component/util.js"></script>
    <script
        src="https://naruto.finance/static/js/component/initbulma.js"></script>

    <script
        src="https://naruto.finance/static/js/component/notification.js"></script>
</head>

<body>

    <div class="hero">
        <div class="hero-body">
            <div class="buttons">
                <a id="info" class="button is-info">info</a>
                <a id="error" class="button is-danger">error</a>
                <a id="loading" class="button ">loading</a>
                <a id="loaded" class="button ">loaded</a>
                <a id="confirm" class="button ">confirm</a>
                <a id="confirmAdvanced" class="button ">confirm has options</a>
                <a id="image" class="button is-link">image</a>
            </div>
        </div>
    </div>
    <div id="confirmPanel" class="modal is-small">
        <div class="modal-background"></div>
        <div class="modal-card">
            <header class="modal-card-head">
                <p class="modal-card-title" snb-lang="PAGECODE_WARNING">Cảnh báo
                </p>
                <button class="delete" aria-label="close"></button>
            </header>
            <section class="modal-card-body" snb-lang="PAGECODE_ARE_YOU_SURE">
                Bạn
                chắc chắn?</section>
            <footer class="modal-card-foot">
                <button class="button is-success yes"
                    snb-lang="PAGECODE_CONFIRM">Xác
                    nhận</button>
                <button class="button cancel"
                    snb-lang="PAGECODE_CANCEL">Hủy</button>
            </footer>
        </div>
    </div>

    <div id="shinobinotification" class="notification  shinobinotification">
        <button class="delete"></button>
        <div class="notificationcontent" snb-lang="PAGECODE_UPDATE_SUCCESS">
            Update
            success</div>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            document.getElementById('info').onclick = function () {
                shinobi.notification.notification.info('info');
            }
            document.getElementById('error').onclick = function () {
                shinobi.notification.notification.error('error');
            }

            document.getElementById('loading').onclick = function () {
                shinobi.notification.notification.loading();
            }

            document.getElementById('loaded').onclick = function () {
                shinobi.notification.notification.loaded();
            }
            document.getElementById('confirm').onclick = function () {
                var callback = function () {
                    shinobi.notification.notification.info('Xác nhận thành công');
                }
                shinobi.notification.confirm(callback);
            }

            document.getElementById('confirmAdvanced').onclick = function () {
                var callback = function () {
                    shinobi.notification.notification.info('Xác nhận thành công');
                }
                var options = {
                    title: 'Tiêu đề',// title modal
                    content: 'Nội dung',// content modal
                    yescontent: 'confirm button',
                    nocontent: 'cancel button',
                    // modalsize: 'is-large', //base on size of Bulma modal component 
                    initfunction: function (modalElement) {
                        shinobi.notification.notification.info('Hàm chạy khi khởi tạo modal');
                    },
                    ishiddenfooter: false,// true || false
                    notclosewhenacceft: false,// không đóng modal khi nhấn nút chấp nhận
                }
                shinobi.notification.confirm(callback, options);
            }

            document.getElementById('image').onclick = function () {
                shinobi.notification.image('https://i.ytimg.com/vi/NmFlxfisnCI/hqdefault.jpg?sqp=-oaymwEcCNACELwBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDFUR_JC9Ld_7GtGpbiRPtZqXwzWw');

            }
        });

    </script>
</body>

</html>
```
{% endtab %}

{% tab title="Kết quả" %}
![](../.gitbook/assets/image%20%2821%29.png)
{% endtab %}
{% endtabs %}

