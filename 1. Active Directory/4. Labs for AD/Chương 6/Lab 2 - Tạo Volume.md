![](../../Image/Pasted%20image%2020250705212634.png)

![](../../Image/Pasted%20image%2020250705221936.png)


---
- Vào **Computer Management** ở **Server Manager**.
- Bật **online** lên hết các **disk** -> **GPT ở initialize disk**.

![](../../Image/Pasted%20image%2020250705222539.png)

![](../../Image/Pasted%20image%2020250705224004.png)

### Tạo volume
**Volume OS**: 7GB trên Disk 0 – để cài hệ điều hành.
**Volume Software**: Mirror (RAID-1) từ 400MB của Disk1 + Disk2.
**Volume Data**: RAID-5 từ 400MB của Disk1 + Disk2 + Disk3.

- Chuyển dang Dynamic Link :

![](../../Image/Pasted%20image%2020250705224338.png)

- Chuột phải disk 1 rồi chọn New Mirrored Volume -> lấy 400 MB từ Disk 1 và Disk 2:

![](../../Image/Pasted%20image%2020250705224936.png)

- **Volume Data : RAID-5 từ 400MB của Disk1 + Disk2 + Disk3.**

![](../../Image/Pasted%20image%2020250705225234.png)