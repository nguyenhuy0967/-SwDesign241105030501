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

# 2. Cơ chế phân tích
## Dưới đây là danh sách các cơ chế chính cần giải quyết trong hệ thống Payroll và lý do lựa chọn từng cơ chế:
1 .Quản lý thông tin nhân viên:

Lý do: Đảm bảo rằng tất cả thông tin cá nhân và công việc của nhân viên được lưu trữ và quản lý một cách chính xác và an toàn.

Ý nghĩa: Giúp dễ dàng truy xuất và cập nhật thông tin nhân viên khi cần thiết.

2.Ghi nhận thời gian làm việc:

Lý do: Theo dõi giờ làm việc của nhân viên để tính toán lương chính xác.

Ý nghĩa: Đảm bảo rằng nhân viên được trả lương đúng với thời gian làm việc thực tế.

3.Tính toán lương:

Lý do: Tự động hóa quá trình tính toán lương dựa trên giờ làm việc, mức lương, và các khoản phụ cấp hoặc khấu trừ.

Ý nghĩa: Giảm thiểu sai sót và tiết kiệm thời gian trong quá trình tính lương.

4.Quản lý phương thức thanh toán:

Lý do: Cho phép nhân viên chọn phương thức thanh toán phù hợp (chuyển khoản ngân hàng, tiền mặt, v.v.).

Ý nghĩa: Tăng tính linh hoạt và tiện lợi cho nhân viên.

5.Tạo báo cáo quản trị:

Lý do: Cung cấp các báo cáo chi tiết về lương, giờ làm việc, và các thông tin liên quan khác cho quản trị viên.

Ý nghĩa: Hỗ trợ quản trị viên trong việc ra quyết định và quản lý hiệu quả.

6.Quản lý đơn đặt hàng (dành cho nhân viên hoa hồng):

Lý do: Theo dõi và quản lý các đơn đặt hàng để tính toán hoa hồng cho nhân viên.

Ý nghĩa: Đảm bảo rằng nhân viên hoa hồng nhận được khoản thanh toán chính xác dựa trên doanh số bán hàng.

7.Xử lý giao dịch tài chính:

Lý do: Tích hợp với hệ thống ngân hàng để xử lý các giao dịch thanh toán lương.

Ý nghĩa: Đảm bảo rằng các khoản thanh toán được thực hiện một cách an toàn và chính xác.

8.In tài liệu liên quan đến lương:

Lý do: Cung cấp các bản sao vật lý của tài liệu lương cho nhân viên hoặc lưu trữ.

Ý nghĩa: Đáp ứng yêu cầu pháp lý và cung cấp tài liệu tham khảo cho nhân viên.

9.Bảo mật và quyền truy cập:

Lý do: Đảm bảo rằng chỉ những người có quyền mới có thể truy cập và chỉnh sửa thông tin nhạy cảm.

Ý nghĩa: Bảo vệ dữ liệu cá nhân và tài chính của nhân viên khỏi các mối đe dọa bảo mật.

10.Tự động hóa quy trình:

Lý do: Tự động hóa các quy trình như tính lương, tạo báo cáo, và xử lý giao dịch để giảm thiểu sai sót và tăng hiệu suất.

Ý nghĩa: Giúp hệ thống hoạt động mượt mà và hiệu quả hơn.

# 3. Phân tích ca sử dụng Payment
![Diagram](https://www.planttext.com/api/plantuml/png/P91B2i8m48RtESNWIXTUe0ifXReB17A2a4unc1V9TD6pkV18Ni7qfLHdb_c-Vtx8w_6iCwb4WxDCQGe9MXTj617NPwFyNOwPq34MYsYqYSeJ73Rl02f3ksT2ZIbOEoFnXnnwuaYtq2q2tnlVnXatah4MpXSG5MIqg6btudXYOgQyWfY2nfnNFX4-eKPMG4dvt6Ew3hxBXJHo2-dWUvFSRwYqnMKbbglugMehy85CFwuPEUX9ABX6tqq_MUOD003__mC0).
