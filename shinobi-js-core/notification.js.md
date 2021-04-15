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
![](../.gitbook/assets/image%20%2820%29.png)
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
![](../.gitbook/assets/image%20%2825%29.png)
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
![](../.gitbook/assets/image%20%2823%29.png)
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Lưu ý: để hủy thông báo loading gọi hàm

```javascript
shinobi.notification.notification.loaded();
```
{% endhint %}

### 





































