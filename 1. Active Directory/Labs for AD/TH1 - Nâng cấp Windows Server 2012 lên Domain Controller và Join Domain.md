# Scenario

![](../Image/Pasted%20image%2020250527092946.png)

- Nâng cấp máy chủ windows server 2012 lên thành máy chủ quản trị miền **Khoacntt.edu.vn** 
- Tiến hành đưa các máy client vào làm thành viên của miền.
# Practical Exercises

![](../Image/Pasted%20image%2020250527095525.png)

## Details
- Server:
	- IP: 192.168.1.2
	- Subnet mask: 255.255.255.0
	- Default Gateway: 192.168.1.1
	- DNS server: 192.168.1.2
- Workstation 1:
	- IP: 192.168.1.10
	- Subnet mask: 255.255.255.0
	- Default Gateway: 192.168.1.1
	- DNS server: 192.168.1.2
## Guide
### BKAP-DC12-01 - Nâng cấp lên Domain Controller
- Cấu hình đặt địa chỉ IP cho các máy tương ứng

![](../Image/Pasted%20image%2020250527100651.png)

Thực hiện cài đặt dịch vụ **Active Directory Domain Services** trên máy BKAP-DC12-01:
- Click **Server Manager / Add Roles and Features** . 
	
![](../Image/Pasted%20image%2020250527101207.png)

- Tại **Select server roles**, click chọn vào dịch vụ **Active Directory Domain Services.**
- Add Features.

![](../Image/Pasted%20image%2020250527101346.png)

- Tại cửa sổ **Confirm installation selections**, click **Install** để cài đặt dịch vụ **ADDS**.
- Tại cửa sổ **Deployment Configuration**:
	- **Select the deployment operation**, click **Add a new forest** để tạo 1 domain mới.
	- Tại **Root domain name**, nhập vào tên miền “Khoacntt.edu.vn”.
	
![](../Image/Pasted%20image%2020250527102136.png)

- Tại **Domain Controller Options**, lựa chọn “Forest functional level” và “Domain functional level” phù hợp với hệ thống đang có. 
- Nhập mật khẩu của **Directory Services Restore Mode (DSRM) password**(123456a@).

![](../Image/Pasted%20image%2020250527102411.png)

- Tại **Additional Options**, đặt tên **NetBIOS domain name** là KHOACNTT.
- Tại **Paths**, chính là đường dẫn lưu CSDL của Active Directory trong máy Domain Controller.

![](../Image/Pasted%20image%2020250527102707.png)

- Tại cửa sổ **Review Options**, tại đây là những thông tin đã cấu hình ở trên.
- Tại cửa sổ **Prerequisites Check**, click vào **Install** để máy bắt đầu cài đặt.
- Restart máy -> Logon lại **Administrator:123456a@**.
- Kiểm tra lại 

![](../Image/Pasted%20image%2020250527103922.png)

Thực hiện Join máy Client WRK10-01 vào Domain.
- Mở máy WRK10-01, snapshot “Begin”.
- Đặt cùng VMnet với máy DC12-01. 
- Sửa lại địa chỉ IP của máy WRK10-01 như sau:
	- IP address: 192.168.1.10
	- Subnet mask: 255.255.255.0
	- Default Gateway: 192.168.1.1
	- Preferred DNS server: 192.168.1.2
- Thực hiện ping từ máy BKAP-WRK10-01 đên máy BKAP-DC12- 01.
- Để Join máy Client **WRK10-01** vào Domain, vào `Control Pane/System and Security/System`
- Tại cửa sổ **System Properties**, Tab **Computer name**, click vào **Change**.

![](../Image/Pasted%20image%2020250527110751.png)

- Tại cửa sổ Computer Name/Domain Changes, click chọn vào Domain, tại đây nhập vào tên miền của Domain 

![](../Image/Pasted%20image%2020250527111007.png)

- Nhập administrator:password

![](../Image/Pasted%20image%2020250527130302.png)

![](../Image/Pasted%20image%2020250527130253.png)

=> WRK10-01 đã join **Khoacntt.edu.vn** domain.