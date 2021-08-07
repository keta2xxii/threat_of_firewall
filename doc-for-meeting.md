## Tìm hiểu các mối nguy hiểm tấn công vào Firewall trường.

### 1.  D-link.devices.hnap.soapaction-header.command.execution

  **Cách thức hoạt động:** 
  - Sử dụng các lỗ hổng bảo mật của các router hãng D-link để tạo ra các cuộc tấn công mạng. Hầu hết đều dựa lỗ hổng Command Execution. 
  - Các thiết bị router sẽ bị nhiễm độc khi các thiết bị này xử lý các các yêu cầu HTTP đã bị nhiễm độc. Các hacker sẽ dựa vào điều này để tấn công vào các router D-Link.
  - Một số model của router đã được ghi nhận là đang bị tấn công : DAP-1522 revB, DAP-1650 revB, DIR-880L, DIR-865L, DIR-860L revA, DIR-860L revB DIR-815 revB, DIR-300 revB, DIR-600 revB, DIR-645, TEW-751DR, TEW-733GR
  - HNAP là một giao thức dựa trên SOAP được dùng để tạo ra giao diện quản lý các thiết bị mạng dành cho administrator. HNAP được sử dụng trong "Quick Router Setup Wizard" - được sử dụng trong việc thay đổi TCP/IP, một số công cụ khác. Hầu hết các thiết bị đều yêu cầu xác thực để thực thi các yêu cầu này, tuy nhiên một số model của D-Link thì cho phép bỏ qua việc xác thực này và đây là lỗ hỏng được hacker sử dụng để tấn công.
  - [Demo attack](http://www.devttys0.com/2015/04/hacking-the-d-link-dir-890l/)

**Remote Code Execution**
- Là kĩ thuật tấn công mạng của hacker dựa vào các lỗ hổng bảo mật xuất hiện trên các thiết bị mạng của hệ thống. Từ đó hacker sẽ truy cập đó thực thi các mã độc từ xa, điều khiển các cuộc tấn công mạng từ xa.
- Dựa vào kĩ thuật này, hacker có thể tạo ra các cuộc tấn công mạng vào các mục tiêu mà không cần sự thoả hiệp của các thiết bị nạn nhân.
- Là một trong những phương thức tấn công nguy hiểm nhất vì kẻ tấn công có thể tùy ý cài đặt mã độc lên máy của nạn nhân cũng như có thể đánh cắp các dữ liệu nhạy cảm của nạn nhân.


**Phương thức phòng tránh**
  - Một trong những cách thức ngăn chặn việc tấn công dựa vào các lỗ hổng bảo mật là người dùng nên cập nhật bản cập nhật hệ thống mới nhất được nhà phát hành sản xuất.

### 2. DASAN.GPON.Remote.Code.Execution

**GPON là gì** 
- Là một thiết bị mang quang được sử dụng dể cung cấp các kết nối gốc, các điểm truy cập tại nhà và hệ thống ăng ten phát tín hiệu (Distributed Antenna Systems).
- Được sử dụng nhiều trên toàn thế giới đặc biệt ở 3 nước như là Mexico, Kazakhstan và Việt Nam. 



**Cách thức hoạt động**

Các thiết bị này đã xuất hiện khá nhiều lỗ hổng như :
1. CVE-2018-10561 & CVE-2018-10562,CERT Kazakhstan, KZ-CERT.
   - Đối với lỗ hổng CVE-2018-10561 thì hacker có thể thêm ‘?Images/’ vào cuối URL trên trang HTML hoặc GponForm/page, kẻ tấn công có thể truy cập vào thiết bị.
   - Đối với CVE-2018-10562, cho phép kẻ tấn công có khả năng thực thi mã từ xa trên thiết bị bị xâm nhập. Bởi vì các lệnh ping và traceroute trên diagnostics pages là “root level”, nên nó cho phép các lệnh khách thực hiện từ xa trên thiết bị thông qua một phương thức “injection” (tiêm vào).

**Mục tiêu của cuộc tấn công**

Dasan Networks là một mục tiêu nổi tiếng nhất kể từ khi các nhà nghiên cứu và tin tặc tập trung vào một số lỗ hồng được tìm thấy trong thiết bị của họ. Nghiên cứu của Radware đã phát hiện ra một biến thể mới của Satori Botnet – nhắm vào cổng 8080 – có khả năng quét và khai thác CVE-2017-18046, một sự khai thác các thiết bị Dasan.

   
