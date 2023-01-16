---
description: Trong bài này chúng ta sẽ tìm hiểu về Bash/Shell Script là gì?
---

# Giới thiệu Bash/Shell Script

## Các khái niệm

### Kernel

Mọi hệ điều hành đều có một nhân **Kernel**. **Kernel** là **một lớp** thuộc OS và là **cầu nối giữa hệ điều hành và ứng dụng** chạy trên máy tính.&#x20;

**Kernel** được khởi chạy khi start máy tính và sau đó có nhiệm vụ cung cấp giao diện cho tất cả ứng dụng, kiểm soát phần cứng và xử lý cung cấp các thông tin khi được yêu cầu.

{% hint style="info" %}
**Kernel** chỉ hiểu được ngôn ngữ binary(chỉ có 0 và 1) do đó **Shell** được sinh ra để giải quyết vấn đề này
{% endhint %}

### Shell

**Shell** là một lớp nằm giữa người dùng và **kernel**, nó cung cấp một bộ các dòng lệnh(Command Line) để người dùng tương tác với **kernel** vì **kernel** chỉ hiểu được mã code binary.&#x20;

**Shell** cho phép người dùng nhập các dòng lệnh theo cú pháp được định nghĩa sẵn và dịch các lệnh này sang các code binary mà **Kernel** hiểu được.

{% hint style="info" %}
Loại Shell nguyên thuỷ của linux là **sh**
{% endhint %}

### Bash

**Bash** (viết tắt của **B**ourne **A**gain **SH**ell) là một **Shell** được đặt làm mặc định trên 1 vài phiên bản trên linux.

**Bash** phổ biến vì không chỉ có trên các hệ điều hành Linux mà còn xuất hiện trên MacOS và trên window qua ứng dụng Window Subsystem for Linux

Một vài loại Shell khác:

* cshell
* kshell&#x20;

### Terminal

Là một ứng dụng gom tất cả lại với nhau, nó cung cấp giao diện để người dùng nhập dòng lệnh **Shell**, tương tác và sau đó trả lại kết quả cho người dùng.

{% hint style="info" %}
Trong series này chúng ta sẽ sử dụng Terminal tích hợp trong VS Code để thực hành
{% endhint %}

## Cách mở Terminal trên VS Code

### Mở bằng GUI

Tại giao diện chúng ta vào Menu bar --> Terminal --> New Terminal để mở một cửa sở terminal mới

<figure><img src="../.gitbook/assets/image (2) (2).png" alt=""><figcaption></figcaption></figure>

### Mở bằng phím tắt&#x20;

Dùng tổ hợp phím `` control + ` ``  trên MacOS để mở terminal mới&#x20;

### Kết quả

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>
