# Scenario

![](../Image/Pasted%20image%2020250527131102.png)

Anh/Chị hãy tạo tài khoản người dùng và nhóm cho Công ty theo yêu cầu sau: 
- Nhóm **BanGiamDoc** gồm: Hung
- Nhóm **NhanVien** gồm: Diep, Tuan, Tung.
Anh/Chị hãy cấp quyền các tài khoản theo yêu cầu sau: 
- Tài khoản TUNG chỉ có thể đăng nhập từ máy TUNG, và phải thay đổi mật khẩu ở lần đăng nhập đầu tiên. 
- Tài khoản DIEP chỉ sử dụng đến ngày 30.09.2008 thì sẽ bị khóa. Tài khoản này chỉ có thể đăng nhập trong giờ hành chánh. Tài khoản này không được phép đổi mật khẩu.
# Practical Exercises

![](../Image/Pasted%20image%2020250527133623.png)

Thực hiện trên DC12-01, tạo nhóm và tài khoản người dùng:
- Snapshot “DC” để quản lý miền **Khoacntt.edu.vn**
- Vào dịch vụ **Active Directory User and Computer** để tạo OU, Group, User. 
	- Vào **Server Manager / Tools / Active Directory User and Computer**.

![](../Image/Pasted%20image%2020250527134519.png)

- Tiến hành tạo các đối tượng group:
	- Tại Users , chuột phải chọn New / Group. 
	- Hoặc Click vào biểu tượng tạo Group trên thanh công cụ.
	- Tại cửa sổ New object – Group, nhập vào tên Group. 
		- Group scope : Global
		- Group Type : Security

![](../Image/Pasted%20image%2020250527134843.png)

- Tiến hành tạo tài khoản người dùng ( User ) :
	- Tại Users, click chuột phải chọn New / User 
	- Hoặc click vào biểu tượng tạo User trên thanh công cụ.

![](../Image/Pasted%20image%2020250527135100.png)

- Tại cửa sổ tiếp theo, nhập vào mật khẩu của tài khoản **diep:123456a@**
	- Lưu ý: 
		- User must change password at next logon: tài khoản phải thay đổi mật khẩu trong lần đăng nhập tiếp theo (khuyển khích bỏ tùy chọn này). 
		- User cannot change password : Tài khoản không được thay đổi password ( khuyến khích dùng tùy chọn này ). 
		- Password never expires: Mật khẩu không bao giờ hết hạn ( khuyến khích dùng tùy chọn này ). 
		- Account is disabled : Tài khoản bị khóa ( khuyến khích không dùng tùy chọn này )

![](../Image/Pasted%20image%2020250527135438.png)

- Tiến hành Add User vào Group:
	- Click chuột phải tại Group NhanVien, chọn Properties 
	- Tại cửa sổ NhanVien Properties, chuyển sang tab Members.
	- Click vào Add
	- Tại cửa sổ Select Users, Contacts, Computers , Service Accounts…. / Enter the object names to select , nhập vào User cần add vào Group ( VD: nhập vào User diep@Khoacntt.edu.vn ) ( click vào **Check Names** khi nhập tên User )
	- Apply
	
![](../Image/Pasted%20image%2020250527135809.png)

![](../Image/Pasted%20image%2020250527140021.png)

- Tương tự đối với Group - User:
	- Nhóm **BanGiamDoc** gồm: Hung
	- Nhóm **NhanVien** gồm: Diep, Tuan, Tung.

![](../Image/Pasted%20image%2020250527140715.png)

![](../Image/Pasted%20image%2020250527140731.png)

- Add User nhanh vào Group:
	- Bôi đen các User cần được add.
	- **Add to a group**

![](../Image/Pasted%20image%2020250527140521.png)

![](../Image/Pasted%20image%2020250527140544.png)

![](../Image/Pasted%20image%2020250527140601.png)

Tài khoản TUNG chỉ có thể đăng nhập từ máy TUNG, và phải thay đổi mật khẩu ở lần đăng nhập đầu tiên. 
- Chọn vào tài khoản Tung
- Click chuột phải, chọn Properties. 
- Tại cửa sổ Tung Properties, chuyển sang Tab Account. 
- Chọn vào tùy chọn đầu tiên ( User must change password at next logon )

![](../Image/Pasted%20image%2020250527141426.png)

- Tài khoản này chỉ có thể đăng nhập trong giờ hành chánh.

![](../Image/Pasted%20image%2020250527142051.png)

- Tài khoản DIEP chỉ sử dụng đến ngày 30.09.2008 thì sẽ bị khóa.

![](../Image/Pasted%20image%2020250527142301.png)

Kiểm tra:
- Tài khoản Tung chỉ có thể đăng nhập từ máy TUNG, và phải thay đổi mật khẩu ở lần đăng nhập đầu tiên. 

![](../Image/Pasted%20image%2020250527142955.png)

![](../Image/Pasted%20image%2020250527143006.png)

![](../Image/Pasted%20image%2020250527143114.png)

- Tài khoản Diep chỉ sử dụng đến ngày 30.09.2008 thì sẽ bị khóa. Tài khoản này chỉ có thể đăng nhập trong giờ hành chánh. Tài khoản này không được phép đổi mật khẩu.

![](../Image/Pasted%20image%2020250527143312.png)

![](../Image/Pasted%20image%2020250527143730.png)




