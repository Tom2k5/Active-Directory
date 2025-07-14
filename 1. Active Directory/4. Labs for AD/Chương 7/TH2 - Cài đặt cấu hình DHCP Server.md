# Yêu cầu Lab

- Cài đặt và cấu hình DHCP Server trên Window Server 2016.

![](../../Image/Pasted%20image%2020250711163730.png)

---
- Authorize DHCP:

![](../../Image/Pasted%20image%2020250711165730.png)

- New scope:

![](../../Image/Pasted%20image%2020250711163829.png)

- Đặt scope name:

![](../../Image/Pasted%20image%2020250711163903.png)

- Đặt range:

![](../../Image/Pasted%20image%2020250711164109.png)

- Đặt exclusions:

![](../../Image/Pasted%20image%2020250711164152.png)

- Đặt lease (8 ngày):

![](../../Image/Pasted%20image%2020250711164301.png)

- Đặt default gateway (192.168.1.1):

![](../../Image/Pasted%20image%2020250711164334.png)

- Skip domain name and DNS server và WINS server (nếu không cần).
- Renew - Release để làm mới lại IP:

```
ipconfig /release
ipconfig /renew
```

- Kiểm tra:

![](../../Image/Pasted%20image%2020250711170027.png)

![](../../Image/Pasted%20image%2020250711170140.png)

- Đặt IP cố định cho client:
Revervation -> New Reservation

![](../../Image/Pasted%20image%2020250711170446.png)

![](../../Image/Pasted%20image%2020250711170529.png)

- Kiểm tra:

![](../../Image/Pasted%20image%2020250711170706.png)

![](../../Image/Pasted%20image%2020250711170721.png)

---
