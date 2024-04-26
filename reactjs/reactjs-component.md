# ReactJS Component

## Component là gì?

Trong react chúng ta sẽ cố gắng chia giao diện thành các khối code UI nhỏ để có thể tái sử dụng lại trong ứng dụng được gọi là Component.&#x20;

{% hint style="info" %}
Component có thể chỉ là 1 button, 1 heading hoặc cũng có thể là cả 1 khối code rất lớn.
{% endhint %}

```jsx
<button>button</button>
```

```jsx
<article>
  <h1>My First Component</h1>
  <ol>
    <li>Components: UI Building Blocks</li>
    <li>Defining a Component</li>
    <li>Using a Component</li>
  </ol>
</article>
```

Thông thường khi code giao diện trang web truyền thống các dev sẽ vẽ markup bằng HTML và CSS sau đó thêm các tương tác vào những đoạn code HTML đó bằng JS.

React cũng giữ nguyên cách chúng ta code giao diện như vậy tuy nhiên sẽ phân tách các khối UI khác nhau bằng cách tạo ra các component và trong component sẽ chứa tất cả các markup(HTML, CSS) và bao gồm luôn cả tương tác JS trong đó. &#x20;

{% hint style="info" %}
React component là một hàm JS sẽ trả về markup của UI và bao gồm luôn cả các tương tác trong component đó
{% endhint %}

Ví dụ 1 component đơn giản:

```jsx
export default function HelloMessage() {
  return (
    <article>
      <h1>Hello World!</h1>
      <p>This is my first ReactJS component</p>
      <hr />
    </article>
  )
}
```

![](<../.gitbook/assets/image (4).png>)

## Cách tạo 1 component trong React

### 1. Định nghĩa function

Đầu tiên chúng ta cần phải định nghĩa một function bởi vì trong React các component là một function.

```jsx
function HelloMessage() { }
```

Trong ví dụ trên chúng ta khởi tạo 1 hàm có tên là HelloMessage để định nghĩa component HelloMessage

{% hint style="warning" %}
Component trong react là một function bình thường trong JS tuy nhiên để xác định đây là một component thì chúng ta bắt buộc phải viết hoa chữ cái đầu của hàm để chúng có thể hoạt động được
{% endhint %}

### 2. Thêm nội dung component

Nội dung của một component bao gồm 2 phần chính là giao diện và tương tác của component. Đối với giao diện bởi thì chúng ta sẽ sử dụng cú pháp có tên là JSX. JSX có cách viết khá giống cách viết của HTML.

{% hint style="info" %}
JSX là một cú pháp đặc biệt cho phép chúng ta viết code markup trong React, tuy nhiên khi ra thực tế thì JSX sẽ được biên dịch ra code HTML, CSS, JS thuần để trình duyệt web có thể đọc và xử lý được. Các bạn có thể tham khảo thêm JSX [tại đây](https://app.gitbook.com/s/-MC5-BglfKHq4hM84twh/\~/changes/384/reactjs/reactjs-jsx)
{% endhint %}

Và từ khoá return sẽ giúp chúng ta trả về giá trị cần trả. Chúng ta có thể ghi tất cả nội dung trong 1 dòng duy nhất như hình dưới.

```jsx
return <h1>Hello World!</h1>
```

Tuy nhiên nếu code của chúng ta nhiều dòng chúng ta nên wrap chúng trong cặp dấu ngoặc tròn `()`

```jsx
return (
    <article>
      <h1>Hello World!</h1>
      <p>This is my first ReactJS component</p>
      <hr />
    </article>
  )
```

{% hint style="info" %}
Về cách thêm tương tác cho component ReactJS chúng ta sẽ được học ở bài [Tương tác trong React](https://app.gitbook.com/s/-MC5-BglfKHq4hM84twh/\~/changes/383/reactjs/tuong-tac-trong-react)
{% endhint %}

### 3.  Export component ra ngoài

Sau khi chúng ta đã code xong nội dung của component chúng ta cần export component ra ngoài để sử dụng bằng từ khoá export default

```jsx
export default function HelloMessage() {
  return (
    <article>
      <h1>Hello World!</h1>
      <p>This is my first ReactJS component</p>
      <hr />
    </article>
  )
}
```

{% hint style="info" %}
Từ khoá export default này có sẵn trong JS chứ không phải là cú pháp của React. Các bạn có thể đọc thêm [ở đây](broken-reference)
{% endhint %}

## Sử dụng Component

Sau khi bạn đã định nghĩa component . Bạn có thể lồng nó vào trong các component khác.&#x20;

Ví dụ trong trường hợp chúng ta đã định nghĩa component HelloMessage. Và chúng ta mong muốn có một component tổng hợp lại thì chúng ta có thể lồng component này trong component tổng.

{% hint style="info" %}
Để dễ dàng quản lý thì chúng ta nên tách component thành 1 file riêng sau đó import vào trong file mà chúng ta mong muốn sử dụng component đó. Tham khảo thêm [tại đây](https://app.gitbook.com/s/-MC5-BglfKHq4hM84twh/\~/changes/386/reactjs/import-export-conponent)
{% endhint %}

file HelloMessage.js

```jsx
export default function HelloMessage() {
  return (
    <article>
      <h1>Hello World!</h1>
      <p>This is my first ReactJS component</p>
      <hr />
    </article>
  )
}
```

file Class01.js

```jsx
import HelloMessage from "./components/HelloMessage";

export default function Class01() {
  return (
    <>
      <HelloMessage />
      <HelloMessage />
      <HelloMessage />
    </>
  );
}
```

![](<../.gitbook/assets/image (3) (4).png>)

## Tóm tắt

* React cho phép bạn tạo các component, các phần tử giao diện người dùng có thể tái sử dụng cho ứng dụng của bạn.
* Trong ứng dụng React, mọi phần của giao diện người dùng đều là component
* Các React component là các hàm JavaScript thông thường, ngoại trừ:
  1. Tên của nó luôn bắt đầu bằng một chữ in hoa
  2. Chúng trả lại JSX.



