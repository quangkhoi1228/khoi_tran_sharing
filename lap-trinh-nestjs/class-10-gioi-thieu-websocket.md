# Class 10: Giới thiệu WebSocket

WebSocket là giao thức mạng cho phép thiết lập kết nối hai chiều (full-duplex) giữa client và server. Khác với HTTP truyền thống, WebSocket giữ kết nối mở để cả hai bên có thể gửi dữ liệu đến nhau bất cứ lúc nào mà không cần yêu cầu lại.

Trong NestJS, WebSocket được hỗ trợ rất tốt thông qua module `@nestjs/websockets` giúp dễ dàng xây dựng các ứng dụng realtime như chat, thông báo trực tiếp,...

***

## Cài đặt `@nestjs/websockets`

Bạn cần cài các package sau:

```bash
npm install @nestjs/websockets @nestjs/platform-socket.io socket.io
```

* `@nestjs/websockets`: Thư viện WebSocket của NestJS
* `@nestjs/platform-socket.io`: Adapter cho Socket.IO (giao thức WebSocket phổ biến)
* `socket.io`: thư viện client-server cho realtime communication

***

## Tạo gateway chat đơn giản

Gateway trong NestJS giống như controller, nhưng xử lý các kết nối WebSocket realtime.

### Tạo file `chat.gateway.ts`

```ts
import { WebSocketGateway, SubscribeMessage, MessageBody, WebSocketServer } from '@nestjs/websockets';
import { Server, Socket } from 'socket.io';

@WebSocketGateway({
  cors: { origin: '*' }, // cho phép truy cập từ mọi nguồn
})
export class ChatGateway {
  @WebSocketServer()
  server: Server;

  // Khi client gửi message với event 'msgToServer', server nhận và phát lại cho tất cả client
  @SubscribeMessage('msgToServer')
  handleMessage(@MessageBody() message: string): void {
    console.log('Tin nhắn nhận từ client:', message);
    this.server.emit('msgToClient', message);
  }
}
```

### Đăng ký gateway trong module

```ts
import { Module } from '@nestjs/common';
import { ChatGateway } from './chat.gateway';

@Module({
  providers: [ChatGateway],
})
export class ChatModule {}
```

Thêm `ChatModule` vào `AppModule`.

***

## Giải thích chi tiết

* **@WebSocketGateway()**: Decorator đánh dấu class là một WebSocket gateway. Có thể truyền options như `cors` để cấu hình.
* **@WebSocketServer()**: Inject server socket.io instance để dùng broadcast, emit,...
* **@SubscribeMessage(eventName)**: Đánh dấu method xử lý khi nhận sự kiện `eventName` từ client.
* **handleMessage(@MessageBody() message)**: Phương thức nhận dữ liệu gửi từ client qua WebSocket.
* `server.emit('msgToClient', message)`: Phát sự kiện `msgToClient` với dữ liệu đến tất cả client đang kết nối.

***

## Thực hành: Gửi & nhận tin nhắn realtime giữa client-server

Bạn có thể test gateway trên với đoạn code frontend đơn giản dưới đây (ví dụ dùng plain HTML + JS):

```html
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <title>Chat WebSocket</title>
  <script src="https://cdn.socket.io/4.5.0/socket.io.min.js"></script>
</head>
<body>
  <input id="msgInput" placeholder="Nhập tin nhắn..." />
  <button onclick="sendMsg()">Gửi</button>
  <ul id="messages"></ul>

  <script>
    const socket = io('http://localhost:3000');

    socket.on('connect', () => {
      console.log('Kết nối WebSocket thành công');
    });

    socket.on('msgToClient', (msg) => {
      const li = document.createElement('li');
      li.textContent = msg;
      document.getElementById('messages').appendChild(li);
    });

    function sendMsg() {
      const input = document.getElementById('msgInput');
      if (input.value.trim()) {
        socket.emit('msgToServer', input.value);
        input.value = '';
      }
    }
  </script>
</body>
</html>
```

***

## Hướng dẫn chi tiết

* Client kết nối tới server NestJS qua Socket.IO (`io('http://localhost:3000')`).
* Khi người dùng nhập tin nhắn và nhấn nút, client gửi sự kiện `msgToServer` lên server.
* Server nhận tin nhắn, broadcast lại cho tất cả client sự kiện `msgToClient`.
* Các client lắng nghe `msgToClient` và hiển thị tin nhắn realtime trên trang.

***

## Bài tập thực hành cho học viên

* Tạo project NestJS mới hoặc thêm module `ChatModule` với gateway chat như trên.
* Cài đặt và cấu hình WebSocket với `@nestjs/websockets`.
* Viết gateway xử lý sự kiện gửi và nhận tin nhắn.
* Viết frontend đơn giản kết nối WebSocket, gửi nhận tin nhắn realtime.
* Mở nhiều tab trình duyệt, thử gửi tin nhắn và xem nó xuất hiện realtime ở các client khác.
* Nâng cấp: Thêm tên người gửi cho mỗi tin nhắn (client gửi kèm tên).
* Nâng cấp: Gửi riêng cho 1 client, không broadcast toàn bộ.
* Tìm hiểu thêm các sự kiện như `connection`, `disconnect` để xử lý trạng thái client.
