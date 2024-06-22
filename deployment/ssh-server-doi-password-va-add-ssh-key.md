# SSH server, đổi password và add SSH key

Để SSH vào một máy chủ Ubuntu, thay đổi mật khẩu và thêm khóa SSH, bạn có thể làm theo các bước sau:

#### Bước 1: SSH vào máy chủ Ubuntu

1. **Mở terminal trên máy tính của bạn.**
2.  **Kết nối đến máy chủ bằng lệnh SSH:**

    ```sh
    ssh your_username@your_server_ip
    ```

    * `your_username`: Tên người dùng của bạn trên máy chủ.
    * `your_server_ip`: Địa chỉ IP của máy chủ.

    Ví dụ:

    ```sh
    ssh user@192.168.1.10
    ```
3. **Nhập mật khẩu hiện tại khi được yêu cầu.**

#### Bước 2: Đổi mật khẩu trên máy chủ Ubuntu

1.  Sau khi kết nối thành công vào máy chủ, chạy lệnh sau để đổi mật khẩu:

    ```sh
    passwd
    ```
2. Hệ thống sẽ yêu cầu bạn nhập mật khẩu hiện tại, sau đó là mật khẩu mới và xác nhận lại mật khẩu mới.

#### Bước 3: Thêm khóa SSH vào máy chủ Ubuntu

**Tạo cặp khóa SSH (nếu chưa có)**

Nếu bạn chưa có cặp khóa SSH trên máy tính của mình, bạn cần tạo một cặp khóa mới:

1.  **Tạo cặp khóa SSH:**

    ```sh
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```

    Nếu bạn muốn sử dụng loại RSA thay vì ED25519, hãy sử dụng:

    ```sh
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    ```
2. **Làm theo hướng dẫn trên màn hình để lưu cặp khóa SSH.**

**Sao chép khóa công khai đến máy chủ**

Có hai phương pháp phổ biến để sao chép khóa công khai đến máy chủ.

**Cách 1: Sử dụng `ssh-copy-id`**

1.  **Sử dụng lệnh `ssh-copy-id`:**

    ```sh
    ssh-copy-id your_username@your_server_ip
    ```

**Cách 2: Sao chép thủ công**

1.  **Hiển thị nội dung của khóa công khai:**

    ```sh
    cat ~/.ssh/id_ed25519.pub
    ```

    hoặc nếu bạn sử dụng RSA:

    ```sh
    cat ~/.ssh/id_rsa.pub
    ```
2. **Sao chép nội dung của khóa công khai.**
3.  **Trên máy chủ, mở hoặc tạo tệp `~/.ssh/authorized_keys`:**

    ```sh
    nano ~/.ssh/authorized_keys
    ```
4. **Dán nội dung của khóa công khai vào tệp `authorized_keys`.**
5. **Lưu và thoát khỏi trình soạn thảo văn bản.**

**Thiết lập quyền chính xác**

1.  **Chạy các lệnh sau trên máy chủ để đảm bảo rằng thư mục `.ssh` và tệp `authorized_keys` có quyền chính xác:**

    ```sh
    chmod 700 ~/.ssh
    chmod 600 ~/.ssh/authorized_keys
    ```

#### Bước 4: Kiểm tra kết nối

1.  **Thử kết nối lại với máy chủ bằng SSH:**

    ```sh
    ssh your_username@your_server_ip
    ```

Nếu mọi thứ được thiết lập đúng cách, bạn sẽ được kết nối với máy chủ mà không cần nhập mật khẩu.

#### Tổng kết các bước

1.  **SSH vào máy chủ:**

    ```sh
    ssh your_username@your_server_ip
    ```
2.  **Đổi mật khẩu:**

    ```sh
    passwd
    ```
3.  **Tạo cặp khóa SSH (nếu chưa có):**

    ```sh
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```
4.  **Sao chép khóa công khai đến máy chủ:**

    ```sh
    ssh-copy-id your_username@your_server_ip
    ```

    Hoặc thủ công:

    ```sh
    cat ~/.ssh/id_ed25519.pub
    ```

    Trên máy chủ:

    ```sh
    nano ~/.ssh/authorized_keys
    ```
5.  **Thiết lập quyền chính xác:**

    ```sh
    chmod 700 ~/.ssh
    chmod 600 ~/.ssh/authorized_keys
    ```
6.  **Kiểm tra kết nối:**

    ```sh
    ssh your_username@your_server_ip
    ```

Nếu bạn gặp bất kỳ vấn đề gì, hãy kiểm tra lại các bước trên hoặc liên hệ với quản trị viên hệ thống của bạn để được hỗ trợ.
