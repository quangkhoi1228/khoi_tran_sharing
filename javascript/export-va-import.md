# Export và Import

Trong JavaScript, import và export là cú pháp được sử dụng để chia sẻ và sử dụng mã giữa các module (đơn vị mã độc lập). Đây là một tính năng của ES6 (ECMAScript 2015) và được hỗ trợ trong các trình duyệt hiện đại và các môi trường chạy JavaScript như Node.js. Dưới đây là một giới thiệu về import và export trong JavaScript:

1. Export:
   *   Export Default: Đây là cách thông thường để xuất một giá trị từ module. Bạn có thể export một giá trị duy nhất là giá trị mặc định của module.

       ```javascript
       // file moduleA.js
       const greeting = 'Hello, world!';
       export default greeting;
       ```
   *   Named Export: Bạn có thể export nhiều giá trị từ một module bằng cách đặt tên cho từng giá trị.

       ```javascript
       // file moduleB.js
       export const sum = (a, b) => a + b;
       export const multiply = (a, b) => a * b;
       ```
2. Import:
   *   Import Default: Bạn có thể import giá trị mặc định từ một module và gán nó cho một biến bất kỳ.

       ```javascript
       // file main.js
       import greeting from './moduleA.js';
       console.log(greeting); // 'Hello, world!'
       ```
   *   Named Import: Bạn có thể import các giá trị được đặt tên từ một module và sử dụng chúng trong mã của bạn.

       ```javascript
       // file main.js
       import { sum, multiply } from './moduleB.js';
       console.log(sum(2, 3)); // 5
       console.log(multiply(2, 3)); // 6
       ```
   *   Import tất cả (Wildcard): Bạn có thể import tất cả các giá trị được export từ một module và sử dụng chúng trong mã của bạn.

       ```javascript
       // file main.js
       import * as utils from './moduleB.js';
       console.log(utils.sum(2, 3)); // 5
       console.log(utils.multiply(2, 3)); // 6
       ```

Lưu ý rằng đường dẫn `./moduleA.js` và `./moduleB.js` trong các ví dụ trên là đường dẫn tương đối đến các file module. Bạn cần chỉ định đúng đường dẫn tới file module mà bạn muốn import.

Import và export cho phép bạn tái sử dụng mã và tạo sự tương tác giữa các module khác nhau, giúp quản lý mã dễ dàng và làm cho mã của bạn có cấu trúc rõ ràng hơn.
