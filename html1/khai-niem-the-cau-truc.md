# Format văn bản trong HTML

## Tổng quan <a href="#cac-the-html-can-ban" id="cac-the-html-can-ban"></a>

HTML là ngôn ngữ đánh dấu văn bản do đó đa phần nội dung của trang web là văn bản. Nên việc chúng ta học cách thể hiện văn bản trong HTML là một phần khá cần thiết

## Một số thẻ dùng để format văn bản

### \<p>

\<p> Thẻ này tạo ra một đoạn văn bản (paragraph) mới trên trang web.

```html
<p>This is a paragraph of text.</p>
```

### **\<h1> --> \<h6>**

Các thẻ này được sử dụng để tạo tiêu đề với các mức độ khác nhau. `<h1>` là tiêu đề cấp cao nhất và `<h6>` là tiêu đề cấp thấp nhất.

```markup
<h1>This is a heading level 1</h1>
<h2>This is a heading level 2</h2>
<!-- ... -->
<h6>This is a heading level 6</h6>
```

### **\<strong>** và **\<em>**

Các thẻ này được sử dụng để làm nổi bật văn bản. `<strong>` là để làm nổi bật mạnh mẽ và `<em>` để làm nổi bật nghiêng (được hiển thị là italic).

```markup
<p>This is <strong>strong</strong> and <em>emphasized</em> text.</p>
```

### **\<a>**

Thẻ này tạo liên kết (hyperlink) đến một trang web khác.

```markup
<a href="https://www.example.com">Visit Example Website</a>
```

### \<br>

Thẻ này tạo một dòng mới trong văn bản, thường được sử dụng để ngắt dòng.

```markup
<p>This is the first line.<br>This is the second line.</p>
```

### **\<blockquote>**

Thẻ này tạo ra một khối trích dẫn.

```markup
<blockquote>
  This is a quoted text.
</blockquote>
```

### **\<ul>**, **\<ol>**, và **\<li>**

Các thẻ này được sử dụng để tạo danh sách không có thứ tự (`<ul>`) hoặc có thứ tự (`<ol>`), và mỗi mục trong danh sách được đại diện bởi thẻ `<li>`.

```markup
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>

<ol>
  <li>First</li>
  <li>Second</li>
</ol>
```

### \<hr>

Thẻ này tạo ra một đường ngang ngăn cách trong văn bản.

```markup
<p>This is some text above the line.</p>
<hr>
<p>This is some text below the line.</p>
```

### \<i>, \<b>, và \<u>

Thẻ `<i>` được sử dụng để làm nghiêng (italic) văn bản. Thường được sử dụng để biểu thị văn bản có ý nghĩa khác biệt hoặc làm nổi bật một phần của văn bản mà không thay đổi ý nghĩa chính.

```markup
<p>This is <i>italic</i> text.</p>
```

Thẻ `<u>` được sử dụng để gạch chân văn bản. Tuy nhiên, việc sử dụng gạch chân nhiều lần không khuyến khích, vì ngày nay người ta thường dùng gạch chân để biểu thị liên kết. Thay vào đó, để tạo kiểu gạch chân cho văn bản, tốt hơn hết là sử dụng CSS (Cascading Style Sheets).

```markup
<p>This is <u>underlined</u> text.</p>
```

Thẻ `<b>` được sử dụng để làm đậm (bold) văn bản. Nó thường được sử dụng để làm nổi bật một phần quan trọng của văn bản, nhưng không nhất thiết phải liên quan đến ý nghĩa thay đổi của văn bản.

```markup
<p>This is <b>bold</b> text.</p>
```

{% hint style="info" %}
việc sử dụng các thẻ `<i>`, `<u>`, và `<b>` để định dạng văn bản cơ bản đã trở nên lỗi thời. Thay vào đó, người ta thường sử dụng CSS để kiểm soát định dạng văn bản và giao diện của trang web. CSS cho phép bạn tùy chỉnh kiểu dáng, màu sắc và các thuộc tính khác của văn bản một cách linh hoạt hơn mà không cần sử dụng các thẻ định dạng trực tiếp trong HTML.
{% endhint %}
