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





{% hint style="info" %}
Lưu ý:

* notification.js sử dụng các thư viện khác như: language.js, util.js, initbulma.js
* notification.js cần 1 d
* notification.js cần 1 thư viện 
{% endhint %}



