# Class 08: Vòng lặp While / Do-while

## Nội dung

{% content-ref url="../java/vong-lap-while-trong-java.md" %}
[vong-lap-while-trong-java.md](../java/vong-lap-while-trong-java.md)
{% endcontent-ref %}

{% content-ref url="../java/vong-lap-do-while-trong-java.md" %}
[vong-lap-do-while-trong-java.md](../java/vong-lap-do-while-trong-java.md)
{% endcontent-ref %}



## Bài tập

Cho người dùng nhập số N&#x20;

1. Sử dụng while tính tổng từ 1 -> N
2. Kiểm tra user có nhập đúng không? Nếu sai thì báo lỗi và cho nhập lại.

{% hint style="info" %}
Sử dụng&#x20;

```java
Scanner scanner = new Scanner(System.in);
System.out.print("Nhập số: ");
boolean isUserInputIntNumber = scanner.hasNextInt();
System.out.print("Bạn vừa nhập số: " + isUserInputIntNumber);
```

Để kiểm tra số nhập có phải là số không
{% endhint %}
