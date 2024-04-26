# Thêm custom routes

## Vào file functions.php trong theme

```php
function zoom_endpoint_callback()
{
	$data = array(
		'message' => 'Hello, this is the zoom endpoint!',
	);

	return rest_ensure_response($data);
}

add_action('rest_api_init', function () {
	register_rest_route(
		'zoom/v1',
		'/endpoint',
		array(
			'methods' => 'GET',
			'callback' => 'zoom_endpoint_callback',
		)
	);
});
```

Trong đó

* `/wp-json/zoom/v1/endpoint`: là đường link API

