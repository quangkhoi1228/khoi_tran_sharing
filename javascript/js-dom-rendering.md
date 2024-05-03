---
description: >-
  Trong lập trình web, việc tạo và hiển thị các phần tử trên trang được thực
  hiện thông qua DOM (Document Object Model). JavaScript cung cấp các phương
  thức để tạo ra và thêm các phần tử vào DOM, cho ph
---

# JS Dom Rendering

### Tạo Element

Để tạo một phần tử HTML mới trong DOM, bạn có thể sử dụng phương thức `document.createElement()`.

```javascript
// Tạo một phần tử div mới
const newDiv = document.createElement('div');
```

### Thêm Element

Sau khi tạo phần tử, bạn có thể thêm nó vào DOM bằng cách sử dụng các phương thức như `appendChild()` hoặc `insertBefore()`.

```javascript
// Thêm phần tử div vào cuối body
document.body.appendChild(newDiv);
```

### Mô Tả Phương Thức

#### `document.createElement(tagName)`

Phương thức này tạo một phần tử HTML mới với tagName được chỉ định.

**Ví dụ:**

```javascript
const newDiv = document.createElement('div');
```

#### `parentNode.appendChild(node)`

Phương thức này thêm một phần tử con vào phần tử cha.

**Ví dụ:**

```javascript
document.body.appendChild(newDiv);
```

#### `parentNode.insertBefore(newNode, referenceNode)`

Phương thức này chèn một phần tử mới trước một phần tử tham chiếu trong phần tử cha.

**Ví dụ:**

```javascript
const referenceNode = document.getElementById('reference');
document.body.insertBefore(newDiv, referenceNode);
```

### Bài Tập Thực Hành

1. Tạo một trang web với một phần tử `<div>` có id là "container".
2. Sử dụng JavaScript để tạo một phần tử `<p>` mới với nội dung "Hello, world!".
3. Thêm phần tử `<p>` này vào phần tử có id là "container".
