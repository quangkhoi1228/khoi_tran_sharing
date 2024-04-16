# Chức năng tìm kiếm với JS và DOM

## Chức năng ẩn phần tử với JS và DOM

#### 1. Tạo Khung Tìm Kiếm Cơ Bản:

Đầu tiên, chúng ta sẽ tạo một khung tìm kiếm đơn giản gồm một ô input và một nút tìm kiếm.

```html
<input type="text" id="searchInput" placeholder="Nhập từ khóa...">
<button id="searchButton">Tìm Kiếm</button>
```

#### 2. Thêm Sự Kiện Click:

Sau khi tạo khung tìm kiếm, chúng ta cần thêm một sự kiện click vào nút tìm kiếm để xử lý khi người dùng nhấn vào nút này.

```javascript
const searchButton = document.getElementById('searchButton');

searchButton.addEventListener('click', function() {
    const searchInputValue = document.getElementById('searchInput').value;
    console.log("Giá trị tìm kiếm:", searchInputValue);
});
```

#### 3. Giới Thiệu DOM và Chọn Danh Sách Phần Tử:

DOM (Document Object Model) là một biểu diễn của tài liệu HTML dưới dạng cây, cho phép chúng ta tương tác với các phần tử trên trang web.

Chúng ta có thể chọn các phần tử trong DOM bằng cách sử dụng các phương thức như `getElementById`, `getElementsByClassName`, `getElementsByTagName`, `querySelector`, `querySelectorAll`.

```javascript
// Chọn phần tử bằng ID
const elementById = document.getElementById('myElementId');

// Chọn phần tử bằng class
const elementsByClass = document.getElementsByClassName('myClass');

// Chọn phần tử bằng thẻ
const elementsByTag = document.getElementsByTagName('div');

// Sử dụng CSS selector
const elementByQuery = document.querySelector('.myClass');
const elementsByQueryAll = document.querySelectorAll('.myClass');
```

#### 4. Ẩn Phần Tử DOM:

Chúng ta có thể ẩn một phần tử DOM thông qua thuộc tính ID của DOM với giá trị là giá trị hiện tại của input.

```javascript
const hideElement = document.getElementById('elementToHide');
const searchInput = document.getElementById('searchInput');

searchButton.addEventListener('click', function() {
    const searchInputValue = searchInput.value;
    hideElement.style.display = 'none';
    console.log("Giá trị tìm kiếm:", searchInputValue);
});
```

## Chức năng tìm kiếm với JS và DOM

**Bài Giảng: Tìm Kiếm Phần Tử trong DOM**

#### 1. Chọn Danh Sách Phần Tử DOM:

Trước tiên, chúng ta cần chọn danh sách các phần tử DOM mà chúng ta muốn tìm kiếm thông qua.

```javascript
const elementsToSearch = document.querySelectorAll('.searchable');
```

#### 2. Thêm Sự Kiện Click:

Sau đó, chúng ta thêm một sự kiện click vào nút tìm kiếm để thực hiện chức năng tìm kiếm.

```javascript
searchButton.addEventListener('click', function() { // Thêm sự kiện click cho nút tìm kiếm
    const searchInputValue = searchInput.value.toLowerCase(); // Lấy giá trị từ ô input tìm kiếm và chuyển thành chữ thường

    for (let i = 0; i < elementsToSearch.length; i++) { // Duyệt qua mảng các phần tử cần tìm kiếm
        const element = elementsToSearch[i]; // Lấy phần tử thứ i trong mảng
        const elementId = element.id.toLowerCase(); // Lấy ID của phần tử và chuyển thành chữ thường
        
        if (!elementId.includes(searchInputValue)) { // Kiểm tra nếu ID của phần tử không chứa từ khóa tìm kiếm
            element.style.display = 'none'; // Ẩn phần tử đi
        } else {
            element.style.display = 'block'; // Hiển thị lại phần tử nếu nó đang ẩn
        }
    }

    console.log("Giá trị tìm kiếm:", searchInputValue); // Log giá trị tìm kiếm ra console
});

```

#### Kết Luận:

Trong bài giảng này, chúng ta đã thêm chức năng tìm kiếm phần tử qua các bước. Chúng ta đã chọn danh sách các phần tử DOM cần tìm kiếm, và khi người dùng nhấn vào nút tìm kiếm, chúng ta lặp qua từng phần tử trong danh sách và ẩn các phần tử không chứa từ khóa tìm kiếm. Tiếp theo, bạn có thể mở rộng chức năng này bằng cách thêm các tính năng bổ sung như tìm kiếm không phân biệt hoa thường, hiển thị kết quả tìm kiếm, vv.
