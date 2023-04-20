# 1. Cơ sở lý thuyết
## 1.1. Tổng quan SNMP
#### SNMP (Simple Network Management Protocol) là một giao thức ở tầng ứng dụng được sử dụng để quản lý các thiết bị mạng như máy chủ, router, switch và các thiết bị mạng khác. SNMP cho phép các quản trị viên mạng giám sát các hoạt động của các thiết bị này và đưa ra quyết định để tối ưu hóa hoạt động của mạng.
> SNMP được thiết kế để đơn giản hóa quá trình quản lý các thành phần trong mạng bằng cách sử dụng luôn cơ sở hạ tầng hiện tại cho việc quản lý. Nhờ đó các phần mềm SNMP có thể được phát triển nhanh, sử dụng được trên đa dạng thiết bị và tốn ít chi phí nhưng việc này lại làm tăng đáng kể lưu lượng mạng. Các thành phần của SNMP bao gồm:   
- SNMP Agent: Là phần mềm chạy trên các thiết bị mạng, cung cấp thông tin về trạng thái và hoạt động của thiết bị cho các hệ thống quản lý mạng.
- MIB (Management Information Base): Là cơ sở dữ liệu nằm trên các thiết bị mạng được sử dụng để lưu trữ thông tin về các thành phần mạng, như các thành phần phần cứng, thông số cấu hình và thông tin về lưu lượng mạng.
- SNMP Manager: Là phần mềm quản lý mạng được sử dụng để giám sát và điều khiển các thiết bị mạng.
- SNMP Application: Là giao diện tương tác giữa người quản trị và SNMP Manager.
  
![Các thành phần của SNMP](https://drive.google.com/file/d/1tULDZ7qBqyKZ9sTDCCr0-l-D_QopjHGO/view?usp=share_link)

## 1.2. Các phiên bản của SNMP
> SNMP có ba phiên bản hiện được sử dụng rộng rãi là SNMPv1, SNMPv2c và SNMPv3. Dưới đây là một số đặc điểm của từng phiên bản:
### 1.2.1. SNMPv1
> Là phiên bản đầu tiên của SNMP, được phát triển vào năm 1988. SNMPv1 chỉ hỗ trợ các tính năng cơ bản như đọc và ghi thông tin vào các biến MIB (Management Information Base). SNMPv1 không cung cấp tính năng bảo mật và dễ dàng bị tấn công bởi các hacker.
### 1.2.2. SNMPv2c
> Là phiên bản được phát triển vào năm 1993 và bổ sung thêm các tính năng mới như: GETBULK để lấy các giá trị của nhiều biến MIB cùng lúc, SET để cập nhật các giá trị trong biến MIB, và TRAP để thông báo về sự kiện xảy ra trên các thiết bị mạng. SNMPv2c cung cấp khái niệm “community” vừa sử dụng thay mật khẩu, vừa phân quyền cho các người dùng trong “commnunity” bằng 2 mode là read-only (chỉ cho phép đọc) hoặc read-write (cho phép đọc và sửa). Việc sử dụng “community” thay cho mật khẩu này có mức độ bảo mật khá thấp.

### 1.2.3. SNMPv3
>Là phiên bản mới nhất của SNMP, được phát triển vào năm 2002. SNMPv3 cung cấp tính năng bảo mật cao hơn bằng cách sử dụng các cơ chế mã hóa và xác thực để bảo vệ thông tin trong quá trình truyền tải. SNMPv3 cung cấp bảo mật với ba chính sách khác nhau bao gồm: 
  * NoAuthNoPriv: (No Authentication, No Privacy) Không cần xác thực và tin nhắn không được mã hóa. Vì những lý do rõ ràng, điều này chỉ nên được sử dụng trong các mạng khép kín và an toàn.
  * AuthNoPriv: (Authentication, No Privacy) Tin nhắn phải được xác thực để được thực hiện; tuy nhiên, chúng không được mã hóa trong quá trình truyền.
  * AuthPriv: (Authentication, Privacy) Đây là triển khai SNMPv3 an toàn nhất. Tin nhắn SNMP phải được xác thực và tất cả dữ liệu được mã hóa trong quá trình truyền.
>Trong thực tế, SNMPv3 là phiên bản được các chuyên gia khuyến nghị sử dụng khi có thể để cung cấp tính bảo mật cao nhất cho các hệ thống quản lý mạng. Tuy nhiên, một số thiết bị mạng có thể chỉ hỗ trợ phiên bản SNMP thấp hơn, nên cần kiểm tra khả năng hỗ trợ phiên bản SNMP của từng thiết bị trước khi triển khai hệ thống quản lý mạng.

## 1.3 Cách thức hoạt động 
> SNMP là một giao thức quản lý mạng cho phép các quản trị viên mạng giám sát các hoạt động của các thiết bị mạng và đưa ra quyết định để tối ưu hóa hoạt động của mạng. Trong hầu hết các trường hợp, SNMP hoạt động trong một mô hình đồng bộ, với giao tiếp được khởi tạo bởi người quản lý SNMP và tác nhân gửi phản hồi. Các lệnh và thông báo này, thường được vận chuyển qua giao thức UDP (trên cổng 161 và 162). Có ba phương thức vận hành chính của SNMP bao gồm:
  * Các thiết bị được quản lý sẽ gửi các thông báo sự kiện đến NMS để thông báo các thay đổi của mình.
  * NMS có thể hỏi các thiết bị đang được quản lý về thông tin trạng thái cấu hình của chúng.
  * NMS có thể yêu cầu các thiết bị đang được quản lý thay đổi trạng thái cấu hình của chúng.
> Các thông tin được lưu trong MIB dưới dạng biến có tên là OID (Object Identifyer) có cấu trúc khá phức tạp và được dùng để định danh các thông tin như sysname, interface, …
![Ví dụ về OID liên quan đến tên của thiết bị](https://drive.google.com/file/d/1qJfDOgn8oFz11gwW-YeFJgS81XPK3YuL/view?usp=share_link)

> Các loại bản tin của SNMP bao gồm:
 - GET-Request: Được tạo bởi trình quản lý SNMP và được gửi đến một agent để lấy giá trị của một biến số nào đó, được xác định bởi OID của nó, trong một MIB.
 - RESPONSE: Được gửi bởi agent cho người quản lý SNMP, được phát đi để trả lời các yêu cầu GET và SET. Chứa các giá trị của các biến được yêu cầu hoặc chỉ trả về là thành công đối với SET-Request.
 - GETNEXT-Request: Được gửi bởi người quản lý SNMP đến agent để lấy các giá trị của OID tiếp theo trong hệ thống phân cấp của MIB.
 - GETBULK-Request: Được gửi bởi người quản lý SNMP cho agent để có được các bảng dữ liệu lớn bằng cách thực hiện nhiều lệnh GETNEXT-Request.
 - SET-Request: Được gửi bởi người quản lý SNMP cho agent để đưa ra các cấu hình hoặc lệnh.
 - TRAP: Một thông báo không đồng bộ được gửi bởi agent đến trình quản lý SNMP để chỉ ra một sự kiện quan trọng, chẳng hạn như lỗi hoặc sự cố, đã xảy ra

## 1.4 Cấu hình SNMPv2c trên router của Cisco
> Vào mode cấu hình với lệnh: 
```php
Router#configure terminal
```
>Sử dụng lệnh sau để cấu hình community string ở chế độ Read-only 
```php
Router(config)# snmp-server community public RO 
//“public” là chuỗi đại diện cho community ở chế độ read-only
```
>Sử dụng lệnh sau để cấu hình community string ở chế độ Write-Read:
```php
Router(config)#snmp-server community private RW
//với "private" là chuỗi đại diện cho community ở chế độ read-write
```
>Sử dụng lệnh sau để cấu hình loại bản tin Trap gửi đến NMS: 
```php
Router(config)#snmp-server enable traps snmp.
Router(config)#snmp-server enable traps config 
Router(config)#snmp-server enable traps snmp linkdown linkup.
```
>Sử dụng lệnh sau để cấu hình địa chỉ NMS, phiên bản SNMP và community: 
```php
Router(config)#snmp-server host 10.10.10.10 traps version 2 public
```
>Thoát khỏi và lưu cấu hình:  
```php
Router(config)#exit 
Router#write
```