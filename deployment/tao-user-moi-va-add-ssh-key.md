# Tạo user mới và add SSH key

Để tạo một người dùng mới trên Ubuntu, bạn có thể thực hiện các bước sau:

#### Bước 1: SSH vào máy chủ Ubuntu

1. **Mở terminal trên máy tính của bạn.**
2.  **Kết nối đến máy chủ bằng lệnh SSH:**

    ```sh
    ssh your_username@your_server_ip
    ```

    * `your_username`: Tên người dùng hiện tại của bạn trên máy chủ.
    * `your_server_ip`: Địa chỉ IP của máy chủ.

#### Bước 2: Tạo người dùng mới

1.  **Chạy lệnh sau để tạo người dùng mới:**

    ```sh
    sudo adduser new_username
    ```

    * `new_username`: Tên người dùng mới mà bạn muốn tạo.
2. **Làm theo hướng dẫn trên màn hình để đặt mật khẩu và các thông tin khác cho người dùng mới.**

#### Bước 3: Thêm người dùng mới vào nhóm sudo (tuỳ chọn)

Nếu bạn muốn người dùng mới có quyền sudo, bạn cần thêm họ vào nhóm `sudo`.

1.  **Chạy lệnh sau để thêm người dùng mới vào nhóm sudo:**

    ```sh
    sudo usermod -aG sudo new_username
    ```

#### Bước 4: Tạo khóa SSH cho người dùng mới (nếu cần)

Nếu bạn muốn người dùng mới sử dụng SSH key để đăng nhập, bạn có thể làm như sau:

**Trên máy tính của người dùng mới**

1.  **Tạo cặp khóa SSH:**

    ```sh
    ssh-keygen -t ed25519 -C "new_user_email@example.com"
    ```

    Hoặc sử dụng RSA:

    ```sh
    ssh-keygen -t rsa -b 4096 -C "new_user_email@example.com"
    ```
2.  **Hiển thị nội dung của khóa công khai:**

    ```sh
    cat ~/.ssh/id_ed25519.pub
    ```

    Hoặc nếu sử dụng RSA:

    ```sh
    cat ~/.ssh/id_rsa.pub
    ```

**Trên máy chủ Ubuntu**

1.  **Chuyển sang người dùng mới:**

    ```sh
    sudo su - new_username
    ```
2.  **Tạo thư mục `.ssh` và tệp `authorized_keys`:**

    ```sh
    mkdir -p ~/.ssh
    nano ~/.ssh/authorized_keys
    ```
3. **Dán nội dung của khóa công khai vào tệp `authorized_keys`.**
4.  **Thiết lập quyền chính xác cho thư mục `.ssh` và tệp `authorized_keys`:**

    ```sh
    chmod 700 ~/.ssh
    chmod 600 ~/.ssh/authorized_keys
    ```

#### Bước 5: Kiểm tra kết nối SSH

1.  **Thử kết nối đến máy chủ bằng tài khoản người dùng mới:**

    ```sh
    ssh new_username@your_server_ip
    ```

#### Tổng kết các bước

1.  **SSH vào máy chủ:**

    ```sh
    ssh your_username@your_server_ip
    ```
2.  **Tạo người dùng mới:**

    ```sh
    sudo adduser new_username
    ```
3.  **Thêm người dùng mới vào nhóm sudo (tuỳ chọn):**

    ```sh
    sudo usermod -aG sudo new_username
    ```
4. **Tạo khóa SSH cho người dùng mới (nếu cần):**
   *   Trên máy tính của người dùng mới:

       ```sh
       ssh-keygen -t ed25519 -C "new_user_email@example.com"
       ```
   *   Hiển thị khóa công khai:

       ```sh
       cat ~/.ssh/id_ed25519.pub
       ```
   *   Trên máy chủ Ubuntu:

       ```sh
       sudo su - new_username
       mkdir -p ~/.ssh
       nano ~/.ssh/authorized_keys
       chmod 700 ~/.ssh
       chmod 600 ~/.ssh/authorized_keys
       ```
5.  **Kiểm tra kết nối SSH:**

    ```sh
    ssh new_username@your_server_ip
    ```

Nếu bạn gặp bất kỳ vấn đề gì, hãy kiểm tra lại các bước trên hoặc liên hệ với quản trị viên hệ thống của bạn để được hỗ trợ.
