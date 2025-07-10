![](../../Image/Pasted%20image%2020250705193730.png)

- Tạo group, user, OU:

```
dsadd ou "ou=HocVien,dc=Khoacntt,dc=edu,dc=vn"
dsadd user "cn=Hung,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -upn Hung@Khoacntt.edu.vn -pwd 123456a@ -disabled no
dsadd user "cn=Trong,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -upn Trong@Khoacntt.edu.vn -pwd 123456a@ -disabled no
dsadd user "cn=Diep,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -upn Diep@Khoacntt.edu.vn -pwd 123456a@ -disabled no
dsadd user "cn=Tuan,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -upn Tuan@Khoacntt.edu.vn -pwd 123456a@ -disabled no
dsadd user "cn=Tung,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -upn Tung@Khoacntt.edu.vn -pwd 123456a@ -disabled no
dsadd group "cn=BanGiamDoc,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -secgrp yes -scope g
dsadd group "cn=NhanVien,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -secgrp yes -scope g
dsmod group "cn=BanGiamDoc,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -addmbr "cn=Hung,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn"
dsmod group "cn=BanGiamDoc,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -addmbr "cn=Trong,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn"
dsmod group "cn=NhanVien,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -addmbr "cn=Diep,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn"
dsmod group "cn=NhanVien,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -addmbr "cn=Tuan,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn"
dsmod group "cn=NhanVien,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn" -addmbr "cn=Tung,ou=HocVien,dc=Khoacntt,dc=edu,dc=vn"
```

- **Tạo home folder cho từng user :**

![](../../../Image/Pasted%20image%2020250705171218.png)

![](../../../Image/Pasted%20image%2020250705171605.png)

- Bật quyền Read cho Everyone ở tab Sharing đối với Data folder:

![](../../../Image/Pasted%20image%2020250705175603.png)

- Bật quyền Read các group ở tab Sharing đối với các group BanGiamDoc, NhanVien tương ứng:

![](../../../Image/Pasted%20image%2020250705175740.png)

- Disable Inheritance và đặt Full Control cho tất cả folder riêng tương ứng cho từng user:

![](../../../Image/Pasted%20image%2020250705181232.png)

- Vì Hung, Diep là trưởng nhóm nên đặt quyền Read cho các group tương ứng :

![](../../Image/Pasted%20image%2020250705194846.png)

- Tạo thư mục dùng trong **Public** :
	- Remove inheritance
	- Thêm:
	    - `Everyone` → **Create files/folders** và **List folder / read data**, không được **Delete**
	    - `CREATOR OWNER` → **Delete**

![](../../../Image/Pasted%20image%2020250705182536.png)

![](../../../Image/Pasted%20image%2020250705183633.png)

📁 `D:\Data`
- Chuột phải → Properties → Tab **Sharing**
- Click **Advanced Sharing** → tick “Share this folder”
- Nhấn **Permissions**
    - Thêm `Everyone` → **Full Control**

![](../../../Image/Pasted%20image%2020250705183848.png)

```ad-note
**Best practice**: **Luôn đặt Share Permission = Full Control** cho nhóm người dùng cần truy cập (Everyone là chính) cho shared folder gốc, và **sử dụng NTFS (Security) Permission để kiểm soát chi tiết quyền truy cập với từng shared folder con**.
```
