# Scenario

![](../Image/Pasted%20image%2020250527143905.png)

Với hệ thống mạng như trong lab1, Anh/Chị muốn cấp quyền cho người dùng theo yêu cầu sau: 
- Tài khoản TUNG có quyền thêm, xóa, sửa tài khoản người dùng. 
- Tài khoản DIEP có quyền backup server. 
- Tài khoản TUAN có quyền quản lý máy in.
# Practical Exercises

- Tạo OUs

![](../Image/Pasted%20image%2020250527150045.png)

 - Delegation of Control Wizard
 
![](../Image/Pasted%20image%2020250527150156.png)

- Chọn User Tung

![](../Image/Pasted%20image%2020250527150024.png)

- Tài khoản TUNG có quyền thêm, xóa, sửa tài khoản người dùng. 

![](../Image/Pasted%20image%2020250527150344.png)

- Tài khoản DIEP có quyền backup server. 
	- Dùng **Add to a group**
	
![](../Image/Pasted%20image%2020250527150944.png)

![](../Image/Pasted%20image%2020250527151119.png)

- Tài khoản TUAN có quyền quản lý máy in.
	- Tải **Print And Document Services** trong **Add Features**.
	- **Print Management** từ **Tools**
	- Truy cập **Print Server Properties**

![](../Image/Pasted%20image%2020250527152418.png)

- Add User Tuan

![](../Image/Pasted%20image%2020250527152610.png)

- Cấp quyền như **Manage printer** và **Manage documents**.

![](../Image/Pasted%20image%2020250527152741.png)