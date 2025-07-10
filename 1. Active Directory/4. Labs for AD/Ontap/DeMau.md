# Câu 1

![](Pasted%20image%2020250706100426.png)

```
dsadd ou "ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"

dsadd ou "ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"
dsadd ou "ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"

dsadd user "cn=TP_QT,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -upn TP_QT@Khoacntt.edu.vn -samid TP_QT -pwd 123456a@ -disabled no
dsadd user "cn=HTQT1,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -upn HTQT1@Khoacntt.edu.vn -samid HTQT1 -pwd 123456a@ -disabled no
dsadd user "cn=HTQT2,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -upn HTQT2@Khoacntt.edu.vn -samid HTQT2 -pwd 123456a@ -disabled no

dsadd computer "cn=PC_TPQT,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"
dsadd computer "cn=PC_QT1,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"
dsadd computer "cn=PC_QT2,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"

dsadd user "cn=TP_NC,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -upn TP_NC@Khoacntt.edu.vn -samid TP_NC -pwd 123456a@ -disabled no
dsadd user "cn=NCUD1,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -upn NCUD1@Khoacntt.edu.vn -samid NCUD1 -pwd 123456a@ -disabled no
dsadd user "cn=NCUD2,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -upn NCUD2@Khoacntt.edu.vn -samid NCUD2 -pwd 123456a@ -disabled no

dsadd computer "cn=PC_TPNC,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"
dsadd computer "cn=PC_NC1,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"
dsadd computer "cn=PC_NC2,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"

dsadd group "cn=NhomQT,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -secgrp yes -scope g
dsadd group "cn=NhomNC,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -secgrp yes -scope g

dsmod group "cn=NhomQT,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -addmbr "cn=TP_QT,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"
dsmod group "cn=NhomQT,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -addmbr "cn=HTQT1,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"
dsmod group "cn=NhomQT,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -addmbr "cn=HTQT2,ou=OU_HopTacQT,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"

dsmod group "cn=NhomNC,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -addmbr "cn=TP_NC,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"
dsmod group "cn=NhomNC,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -addmbr "cn=NCUD1,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"
dsmod group "cn=NhomNC,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn" -addmbr "cn=NCUD2,ou=OU_NCUD,ou=OU_VienNCUD,dc=Khoacntt,dc=edu,dc=vn"
```

# Câu 2
- Nhóm 2 không thể thay đổi mật khẩu.

![](Pasted%20image%2020250706105738.png)

- Chỉnh khung giờ :

![](Pasted%20image%2020250706110435.png)

# Câu 3
- Admin có toàn quyền đối với OU (mặc định).
- Trưởng phòng được tạo, xóa User và Group.
- Nhân viên được thêm bớt thành viên vào Group, thay đổi kiểu Group.

Truong Phong:

![](Pasted%20image%2020250706113025.png)

NhanVien:

![](Pasted%20image%2020250706113118.png)

![](Pasted%20image%2020250706113704.png)

![](Pasted%20image%2020250706114315.png)

![](Pasted%20image%2020250706114341.png)

# Câu 4
- Không được chạy các chương trình: Paint, Calculator:
	- Tạo GPO -> Edit -> User Configuration -> Administrative Templates -> System :
	- Truy cập "Don't run specified Windows applications".

![](Pasted%20image%2020250706120348.png)

- Enable -> Show -> notepad.exe + calculator.exe -> Apply -> OK.

![](Pasted%20image%2020250710154037.png)


- Tắt các chức năng Security và Connection trên IE:
```
User Configuration
 └── Policies
     └── Administrative Templates
         └── Windows Components
             └── Internet Explorer
                 └── Internet Control Panel

```

![](Pasted%20image%2020250710163553.png)

- Thiết lập homepage của IE thành google.com.vn:

	- Chuột phải vào **Internet Settings** > **New** > Chọn phiên bản phù hợp (ví dụ: **Internet Explorer 10**).
	- Trong tab **General**:
	    - **Home page**: nhập `https://www.google.com.vn`
	    - Tick vào ô “Start with home page”
	- Bấm vào biểu tượng xanh **"Common"** (góc dưới cùng), và chọn:
	    - **Apply once and do not reapply** _(hoặc không chọn nếu bạn muốn GPO luôn cưỡng chế homepage)

![](Pasted%20image%2020250710181129.png)

- Cập nhật lại GPO:
```
gpupdate /force
```

---
# Câu 5
Phân quyền sao cho chỉ các trưởng phòng có quyền chỉnh sửa GPO ở câu trên; những nhân viên phòng thứ nhất được quyền áp dụng chính sách, nhân viên phòng thứ hai chỉ có quyền xem chính sách đó.

- Add các user vào Scope:

![](Pasted%20image%2020250710185133.png)

- Vào Delegation -> Advanced:

| Tài khoản | Read | Apply Group Policy | Edit Settings |
| --------- | ---- | ------------------ | ------------- |
| TP_QT     | ✅    | ❌                  | ✅             |
| TP_NC     | ✅    | ❌                  | ✅             |
| HTQT1     | ✅    | ✅                  | ❌             |
| HTQT2     | ✅    | ✅                  | ❌             |
| NCUD1     | ✅    | ❌                  | ❌             |
| NCUD2     | ✅    | ❌                  | ❌             |
![](Pasted%20image%2020250710192746.png)

![](Pasted%20image%2020250710192818.png)

- **Result:**

![](Pasted%20image%2020250710192925.png)


```ad-note
- Edit Settings = Read + Write GPO.
- Edit Settings, delete, modify security = Full Control GPO.
```

---
# Câu 6

![](Pasted%20image%2020250710193810.png)

- Add roles and features -> DNS Server and Web Server (IIS).

![](Pasted%20image%2020250710194002.png)

- Vào role services -> Install.

![](Pasted%20image%2020250710194147.png)

- Tạo thư mục chia sẻ FTP:
	- Đặt name - `FTPRoot` 
- Mở **IIS Manager** (`inetmgr`).
- Chuột phải `Sites` → `Add FTP Site…`
    - Tên: `ftp.tên_miền_của_bạn` (VD: `ftp.khoacntt.edu.vn`)
    - Physical Path: `D:\FTP_Root`
- Cấu hình Binding:
    - IP: `192.168.1.1`
    - Port: `21`
    - Enable: `Start FTP site automatically`
    - **Tick:** “Allow SSL” → chọn `No SSL` (nếu không dùng SSL)
    
![](Pasted%20image%2020250710195944.png)

![](Pasted%20image%2020250710200254.png)

- Cài đặt authorization -> Finish:

![](Pasted%20image%2020250710200506.png)

- Đặt DNS cho FTP server:
	- Mở **DNS Manager** trên DC.
	- Chọn Forward Lookup Zones → Zone `khoacntt.edu.vn`.
	- Tạo bản ghi mới:
	    - `ftp` → A Record → trỏ về `192.168.1.2`
	    
![](Pasted%20image%2020250710202209.png)

- **Test máy:**
Yêu cầu đăng nhập:

![](Pasted%20image%2020250710202520.png)

Không tạo folder được:

![](Pasted%20image%2020250710202405.png)

---
