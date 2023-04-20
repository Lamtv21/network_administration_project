# 2. Giới thiệu và Cài đặt phần mềm
## 2.1. GNS3
* GNS3 là một công cụ mô phỏng mạng miễn phí và mã nguồn mở, cho phép người dùng thiết kế, cấu hình và kiểm tra các mạng máy tính ảo. GNS3 cho phép người dùng tạo ra các mạng ảo trên máy tính của mình bằng cách kết hợp các thiết bị mạng ảo và thực tế để tạo ra một môi trường mạng ảo.
* GNS3 hỗ trợ nhiều loại thiết bị mạng phổ biến, bao gồm router, switch, firewall, máy chủ DHCP và DNS, và các thiết bị khác. Người dùng có thể kéo và thả các thiết bị này vào một mô hình mạng ảo, sau đó kết nối chúng với nhau để tạo ra một mạng máy tính hoàn chỉnh.
* Download trực tiếp từ trang https://www.gns3.com/software/download Mở file cài đặt. Sau khi tải về chúng ta chạy file có đuôi .exe. Nhấn next
* Tại cài đặt Npcap, nhấn cancel.
* Tiếp tục nhấn Next cho đến khi cài đặt kết thúc
* Khởi động GNS3, chọn “Run appliances on my local computer”, sau đó tiếp tục nhấn Next và chờ khi cài đặt kết thúc.

## 2.2.	Thêm router cho GNS3
* Khi download và cài đặt xong GNS3, để thực hiện tạo topo mạng trên GNS3 chúng ta phải tải IOS Cisco từ trên mạng và add nó vào GNS3 như sau:
* Vào Edit > Preferences…
* Chọn IOS routers > New > New Image > Browse…(trỏ đường dẫn đến file image của router đã cài đặt) > Next
* Chọn Idle-Pc finder > Finish > Apply > OK
  
## 2.3.	Winpcap
* Winpcap là một “packet driver” cho các ứng dụng chụp và truyền các gói tin mạng bỏ qua các chồng giao thức. Winpcap đã dừng hỗ trợ từ phiên bản 4.1.3 (năm 2021). Vậy nên khi cài đặt GNS3 từ bộ cài all-in-one thì bạn sẽ được cài công cụ Npcap.
* Nhưng do Npcap là công cụ mới nên vẫn chưa hoàn toàn tối ưu với GNS3 nên vẫn có tình trạng lỗi. Trên các diễn đàn cộng đồng của GNS3 cũng có nhiều trường hợp sử dụng Npcap gây ra lỗi không kết nối đến mạng bên ngoài. Vì vậy chúng ta nên kiểm tra và cài thêm Winpcap để thực hành với GNS3. Download phần mềm Winpcap tại trang web: https://www.winpcap.org/install/
## 2.4.	MIB Brower
* MIB Browser là một phần mềm giám sát và quản lý mạng máy tính, cho phép người dùng xem, tra cứu và thay đổi thông tin từ các thiết bị mạng được quản lý bằng giao thức SNMP (Simple Network Management Protocol).
* Phần mềm MIB Browser cho phép người dùng truy cập vào cơ sở dữ liệu MIB (Management Information Base), nơi chứa các thông tin liên quan đến tình trạng, hoạt động và các thông số của các thiết bị mạng như router, switch, firewall, server, etc. Nó cũng cung cấp các tính năng phân tích và đồ họa để hiển thị các dữ liệu được thu thập.
* Download phần mềm MIB Brower tại trang web: https://www.ireasoning.com/mibbrowser.shtml

## 2.5.	Wireshark
* Wireshark là một công cụ phân tích giao thức mạng được sử dụng để bắt và phân tích lưu lượng mạng trong thời gian thực. Nó cho phép người dùng xem những gì đang xảy ra trên mạng của họ ở mức độ vi mô bằng cách bắt và hiển thị các gói tin được truyền qua mạng.
* Wireshark có khả năng hiển thị các gói tin trên mạng dưới dạng đồ thị và bảng dữ liệu, cho phép người dùng xem các thông tin chi tiết về các giao thức và dữ liệu đang được truyền trên mạng. Ngoài ra, Wireshark cũng cung cấp các tính năng như lọc gói tin, tìm kiếm và phân tích gói tin, theo dõi hoạt động của ứng dụng và dịch vụ trên mạng, và đưa ra báo cáo chi tiết về các vấn đề liên quan đến mạng.
* Download phần mềm Wireshark tại trang web: https://www.wireshark.org/download.html
## 2.6.	PRTG
* PRTG là một phần mềm giám sát và quản lý mạng máy tính, cho phép người dùng giám sát các thiết bị mạng, ứng dụng và dịch vụ trên mạng của mình. PRTG sử dụng giao thức SNMP (Simple Network Management Protocol) để thu thập thông tin về các thiết bị mạng như router, switch, firewall, server, etc., và hiển thị chúng dưới dạng biểu đồ và báo cáo cho người dùng.
* PRTG cung cấp cho người dùng các tính năng như báo động, bảng điều khiển đồ thị, báo cáo, và tích hợp với các hệ thống quản lý sự cố để giúp người dùng nhanh chóng phát hiện và giải quyết các vấn đề liên quan đến mạng và hệ thống.
*  Để tải phần mềm PRTG chúng ta vào trang chủ của PRTG và tải về: https://www.softpedia.com/get/Network-Tools/Bandwidth Tools/?utm_source=spd&utm_campaign=postdl_redir
## 2.7.	Thêm card mạng cho PC
* Để thêm card mạng cho PC, nhấn chuột phải vào This PC, chọn Manage > Device Manager >Network Adapter.
* Chọn Action > Add legacy hardware.
* Chọn Install the hardware that I manually select from a list (Advance) rồi chọn Next. 
* Chọn Network Adapter rồi nhấn Next.
* Chọn Microsoft và chọn Microsoft KM-TEST Loopback Adapter và nhấn Next.

