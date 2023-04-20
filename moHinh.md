# 3. Mô hình quản trị
## 3.1.	Mục đích
* Sử dụng các phần mềm GNS3, MIB Brower, PRTG để giám sát và quản lý một mạng gồm 3 router.
## 3.2.	Yêu cầu
*	Tạo lập một mô hình kết nối mạng gồm 3 router kết nối với nhau.
*	Kết nối, cài đặt cơ bản cho máy tính và các router ping thông tới nhau.
*	Cấu hình SNMPv2c trên các router.
*	Sử dụng bản tin Get để lấy về các thông tin của router.
*	Sử dụng bản tin GetBulk để lấy về toàn bộ thông tin của router.
*	Sử dụng bản tin Set để thay đổi tên router.
*	Kiểm tra tính năng thông báo traps từ router về máy tính.
*	Cài đặt và xem lưu lượng mạng trên PRTG.
## 3.3.	Mô hình mạng
![Mô hình mạng](https://drive.google.com/file/d/1DVeIPOyWxDMS1jdmfCrFoRSr0lQsMPA_/view?usp=share_link)
## 3.4. Các bước thực hiện
### 3.4.1.	Xây dựng mô hình mạng trên GNS3
![Mô hình mạng](https://drive.google.com/file/d/1SO7catMrwTvf9IMoCKGMCV0JGgdq96AP/view?usp=share_link)
### 3.4.2. Cấu hình cơ bản router
### 3.4.3. Cấu hình địa chỉ IP trên máy tính
### 3.4.4. Kiểm tra kết nối
* Lưu ý: Add các dải mạng trong topo bằng câu lệnh route add 10.10.0.0 mask 255.255.0.0 10.10.10.1, với 10.10.10.1 là địa chỉ cổng default getway trên R1
### 3.4.5.	Cấu hình SNMP trên máy tính
### 3.4.6.	Sử dụng MIB Brower
* Mở MIB browser, ở mục address điền địa chỉ cổng mà mình muốn xem. Chọn advanced, điền mật khẩu read only và read write, snmp chọn version 2
### 3.4.7.	Sử dụng PRTG
* Vào ứng dụng PRTG sau đó chọn freeware edition
* Chọn địa chỉ router muốn xem, nhập pass read only
* Chọn những cổng mà mình muốn xem



