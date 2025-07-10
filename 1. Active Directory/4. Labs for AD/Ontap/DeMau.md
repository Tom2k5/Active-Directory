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

