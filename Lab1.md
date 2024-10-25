# **1. Phân tích kiến trúc**
## Kiến trúc phù hợp với hệ thống Payroll là kiến trúc phân tầng (Layered Architecture)
## Lí do lựa chọn kiến trúc phân tầng:
-Tính mô-đun: Dễ dàng bảo trì và mở rộng hệ thống.

-Tách biệt trách nhiệm: Mỗi tầng có một nhiệm vụ riêng, giúp giảm sự phụ thuộc giữa các phần của hệ thống.

-Tái sử dụng: Các tầng có thể được tái sử dụng trong các dự án khác nhau.

-Hiệu suất: Tối ưu hóa hiệu suất bằng cách tách biệt các nhiệm vụ khác nhau.
## Kiến trúc phân tầng của hệ thống Payroll
1.Tầng Presentation (Giao diện người dùng)

-Login: Cho phép Payroll Administrator đăng nhập vào hệ thống.

-Select Payment: Cho phép nhân viên chọn phương thức thanh toán.

2.Tầng Business Logic (Logic nghiệp vụ)

-Maintain Timecard: Giúp nhân viên ghi lại giờ làm việc.

-Create Employee: Hỗ trợ thêm nhân viên mới vào hệ thống.

-Maintain Purchase Order: Cho phép nhân viên hoa hồng quản lý đơn đặt hàng.

-Create Administrative Report: Tạo báo cáo cho mục đích quản trị.

-Maintain Employee Info: Quản lý thông tin nhân viên.

-Run Payroll: Tự động hóa quá trình tính lương dựa trên đồng hồ hệ thống.

3. Tầng Data Access (Truy cập dữ liệu)

-Project Database: Lưu trữ và truy xuất dữ liệu liên quan đến nhân viên và thẻ thời gian.

-Printer: In các tài liệu liên quan đến lương.

-Bank System: Xử lý các giao dịch tài chính liên quan đến lương.

4. Tầng Database (Cơ sở dữ liệu)

-Project Database: Lưu trữ thông tin về nhân viên, thời gian làm việc, lương, và các dữ liệu liên quan khác.

## Biểu đồ package mô tả kiến trúc hệ thống payroll 
![Diagram](https://www.planttext.com/api/plantuml/png/Z5DBJWCn3Dtd557tlG9g2ooGYXYrNC1aJ0dDP-HaAeqgJiQ28t45CW7K_938AlRpUuxzbC_tZvNpG7xKYWqWZd10lkW87HeFNbh3jp0XBVYPyN240kVurXwaIU8zAXI-Wqa75djZ5wNDwAJ17ufeQTs339saUPGQ1L2VGDU4uF5M3yfEY0rEDv9u0OSFr2DLn7MlfP7EKvZZX3iSBFc6oA_-dNcs2RmRJHY8h5BPG3VWWQ-5Y3FLqtHaNyCgvggdyB0C2UsoLsx07FUJywYh3ZFtF_A15xtWo-LLuK8MHRpQT9c8LSNIyp3JoRVVp2QAJJV-Xh9EcKMjPAnE7BjS8rAkhOA_hIdIYJyhDFtyGnZx0W00__y30000).

