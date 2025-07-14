# Yêu cầu bài Lab

- Cài đặt dịch vụ DNS trên máy DC12-01. 
+ Cấu hình dịch vụ DNS: 
	- Cấu hình Primary Zone trong Forward Lookup Zone với tên: bkaptech.vn. 
	- Cấu hình Reverse Zone trong Reverse Lookup Zone với dải :192.168.1.0. 
	- Cấu hình các bản ghi : A, PTR, CNAME, MX…. 
+ Khai báo DNS client và kiểm tra: 
	- Khai báo tên máy :DC12-01. 
	- Dùng nslookup để kiểm tra phân giải.

---

- Cài đặt dịch vụ DNS trên DC12-01.
	- Add roles and features -> DNS -> Install.

- Cấu hình Primary Zone trong Forward Lookup Zone với tên: bkaptech.vn. 

![](../../Image/Pasted%20image%2020250711144430.png)

![](../../Image/Pasted%20image%2020250711144410.png)

![](../../Image/Pasted%20image%2020250711144620.png)

![](../../Image/Pasted%20image%2020250711145804.png)

![](../../Image/Pasted%20image%2020250711145822.png)

- Cấu hình Reverse Zone trong Reverse Lookup Zone với dải :192.168.1.0. 
	- Reverse Lookup Zones -> New Zone -> Allow both nonsecure and secure dynamic updates (tương tự Forward).
	- IPv4 Reverse Lookup Zone.

![](../../Image/Pasted%20image%2020250711150110.png)

![](../../Image/Pasted%20image%2020250711150314.png)

---
Cấu hình các bản ghi : A, PTR, CNAME, MX…. 
- Cấu hình A host và PTR:

![](../../Image/Pasted%20image%2020250711151127.png)

Tick -> Create associated pointer record (PTR) : Make PTR.

- Cấu hình CNAME:

![](../../Image/Pasted%20image%2020250711160123.png)

Khi truy cập `www.bkaptech.vn` -> truy vấn `DC12-01.bkaptech.vn`.

- Cấu hình MX:

![](../../Image/Pasted%20image%2020250711153008.png)
##### **FQDN (Fully Qualified Domain Name)**
- Đây là **tên miền mà bạn muốn nhận email cho nó**.
- Trong hình của bạn: `bkaptech.vn.`
- Ý nghĩa: bạn đang cấu hình để nhận email gửi tới các địa chỉ như:
    - `admin@bkaptech.vn`
    - `support@bkaptech.vn`
    - v.v.
🔹 **Nó là tên miền chính mà bạn sở hữu.**

##### **FQDN of Mail Server**
- Đây là **tên miền của máy chủ thư (mail server)** sẽ **xử lý email đến domain bên trên**.
- Ví dụ: `mail.bkaptech.vn.`, `mx1.bkaptech.vn.`, `smtp.google.com.`, v.v.
- Đây là nơi **DNS sẽ hướng thư đến**, khi có email gửi về `@bkaptech.vn`.
🔹 **Nó là tên máy chủ vận hành phần mềm mail server (như Exchange, Postfix,...).**

##### Quá trình hoạt động
1. Ai đó gửi email tới `admin@bkaptech.vn`.
2. DNS kiểm tra bản ghi MX cho `bkaptech.vn`.
3. Thấy bản ghi:
    `bkaptech.vn.    MX 10 mail.bkaptech.vn.`
4. DNS lấy IP của `mail.bkaptech.vn.` (thông qua A record hoặc CNAME).
5. Email được gửi đến IP của `mail.bkaptech.vn`.

---
- Kiểm tra bằng máy client

![](../../Image/Pasted%20image%2020250711160652.png)

---
