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
## Biểu đồ sequence mô tả hành vi của ca sử dụng "Payment" trong hệ thống payroll
![Diagram](https://www.planttext.com/api/plantuml/png/P91B2i8m48RtESNWIXTUe0ifXReB17A2a4unc1V9TD6pkV18Ni7qfLHdb_c-Vtx8w_6iCwb4WxDCQGe9MXTj617NPwFyNOwPq34MYsYqYSeJ73Rl02f3ksT2ZIbOEoFnXnnwuaYtq2q2tnlVnXatah4MpXSG5MIqg6btudXYOgQyWfY2nfnNFX4-eKPMG4dvt6Ew3hxBXJHo2-dWUvFSRwYqnMKbbglugMehy85CFwuPEUX9ABX6tqq_MUOD003__mC0).

**Giải thích các bước trong biểu đồ sequence:**
-Employee chọn phương thức thanh toán thông qua hệ thống Payroll.

-Payroll gửi yêu cầu xử lý thanh toán đến PaymentMethod.

-PaymentMethod tương tác với BankSystem để chuyển tiền.

-BankSystem xác nhận giao dịch và gửi phản hồi lại cho PaymentMethod.

-PaymentMethod thông báo cho Payroll rằng thanh toán đã được xử lý.

-Payroll thông báo cho Employee rằng thanh toán đã thành công.

## Biểu đồ lớp mô tả các lớp phân tích cho ca sử dụng "Payment" trong hệ thống payroll
![Diagram](https://www.planttext.com/api/plantuml/png/V9DDJiCm48NtESKiMubS80jK8O740bHHBk0wqsBXdyYU82B4oLXm9Av0KZjkxAJDpc_6Cz-yZFz-VZUEcALMoO9BvXpSgqQQ3X6-2kY_4Z08ZtK5GbDGDLDOmOwiqCSWDQnJgEa9wStqkTlfyPG2u50YfoIoKalvwme-ZAYBxo9W9T78vk-cP5vxpla06ciuEXSghPWohQOAQjFk9Iurj4RAsAhnvxJNw4qLRGk1j7W0u4poLZB27PFCTgjr5iTFv2tX23X3kcFwVTSvGXMfzhsK8WtAml1acNO7j0-jhbqs-mqmphtWxrnoV-iTDFRiogYa455U815Qa63dCNEMg_iGZ3Jw8AowQDGBDiPIXBIdOqhejTUkoV6EgD7sUBx6j7Py6MLvcsttk2n396x2L9obJvPvY9z_RJ7p-dgxF3q9-Y6A3UfwUE7zzmy00F__0m00).

**Giải thích các lớp phân tích:**

  * Employee:
  
  -Thuộc tính:
  
   +employeeId: ID của nhân viên.
  
   +name: Tên của nhân viên.
  
   +paymentMethod: Phương thức thanh toán của nhân viên.
  
  -Phương thức:
  
   +selectPaymentMethod(method: PaymentMethod): Chọn phương thức thanh toán.
  
  Ý nghĩa: Đại diện cho nhân viên trong hệ thống, là đối tượng chính cần quản lý thông tin và phương thức thanh toán.
  
  * PaymentMethod:
  
  -Thuộc tính:
  
  +methodId: ID của phương thức thanh toán.
  
  +methodName: Tên của phương thức thanh toán.
  
  -Phương thức:
  
  +processPayment(amount: double): Xử lý thanh toán.
  
  Ý nghĩa: Quản lý các phương thức thanh toán khác nhau, giúp tăng tính linh hoạt cho hệ thống.
  
  * Payroll:
  
  -Thuộc tính:
  
  +payrollId: ID của bảng lương.
  
  +employee: Thông tin nhân viên.
  
  +amount: Số tiền lương.
  
  -Phương thức:
  
  +calculateSalary(): Tính toán lương.
  
  +executePayment(): Thực hiện thanh toán.
  
  Ý nghĩa: Quản lý quá trình tính toán và xử lý lương, đảm bảo tính chính xác và hiệu quả.
  
  * BankSystem:
  
  -Thuộc tính:
  
  +bankId: ID của ngân hàng.
  
  +bankName: Tên của ngân hàng.
  
  -Phương thức:
  
  +transferFunds(amount: double, account: String): Chuyển tiền.
  
  Ý nghĩa: Tương tác với hệ thống ngân hàng để xử lý các giao dịch tài chính, đảm bảo an toàn và bảo mật.
  
  * PaymentProcessor:
  
  -Thuộc tính:
  
  +processorId: ID của bộ xử lý thanh toán.
  
  +processorName: Tên của bộ xử lý thanh toán.
  
  -Phương thức:
  
  +initiatePayment(amount: double, method: PaymentMethod): Khởi tạo thanh toán.
  
  +confirmPayment(): Xác nhận thanh toán.
  
  Ý nghĩa: Xử lý các yêu cầu thanh toán, đảm bảo quá trình thanh toán diễn ra suôn sẻ.
  
 * Report:
  
  -Thuộc tính:
  
  +reportId: ID của báo cáo.
  
  +reportType: Loại báo cáo.

  -Phương thức:
  
  +generateReport(): Tạo báo cáo.
  
  Ý nghĩa: Tạo các báo cáo liên quan đến thanh toán và lương, hỗ trợ quản trị viên trong việc ra quyết định.

# 4. Phân tích ca sử dụng Maintain Timecard
##  Biểu đồ sequence mô tả hành vi của ca sử dụng "Maintain Timecard" trong hệ thống payroll
![Diagram](https://www.planttext.com/api/plantuml/png/V8mn3i8m34LtdyBgr0vS80DYIFS8vG8c2LAafAaI5wbdO-18N04eoL09iLdlVR_d_N4gJ9cN680CfunZd4DQdGEOtzmRFzF4s3NS8HKSzqxHcbC8cr9xfNrqXhBTdFxj935Tg7pJMWACU3YY4aZMjatFzH3Oq03gizC2RnIy9NRz0Bg-LkJJT7Pb2TotjHHOwER-ThMi5PEcgyznwxm0003__mC0).

*Giải thích các bước trong biểu đồ sequence:*

-Employee gửi yêu cầu thêm thẻ thời gian mới thông qua hệ thống Payroll.

-Payroll gửi yêu cầu xác thực thông tin thẻ thời gian đến Timecard.

-Timecard trả về kết quả xác thực cho Payroll.

-Payroll gửi yêu cầu lưu thẻ thời gian vào TimecardDatabase.

-TimecardDatabase xác nhận việc lưu trữ và gửi phản hồi lại cho Payroll.

-Payroll thông báo cho Employee rằng thẻ thời gian đã được lưu thành công.

##  Biểu đồ lớp mô tả các lớp phân tích cho ca sử dụng "Maintain Timecard" trong hệ thống payroll
![Diagram](https://www.planttext.com/api/plantuml/png/Z5FBQiCm4BpxA_QOGFq3eeGSsaEXXq82FQ-j9HLTIqOFWodziXxwIVs5ogqansbAeeD1CoFjxAprzV6vTHwj3nrNBQDpSD_rR4OYUAiWhXee0GzIWD8-eHex4h3pLkb3Whpgg4KhdO17vVpjFkqtFpm0IfcXLTOAoD1Qm62KJDhGI_HqXVozIhupKNpdCqlVvxkPYWcuYzy4l9XWtREnhnHrqeI6AJaRaDKaNqK7ZJ5Cg6SJJpXQmrmyzB_xynP4oJeHs9cW_Kcz5haD70lkaD6EKza5Vo1DDjAnj6FLh_uD9dQ73Rfvi381ItUNfkXmk6OksPmlsfFaRuv2Ny_d9z_b5wphpKpaR2Um17SC5kMVZY-pvS8jQJazXkeR003__mC0).

*Giải thích các lớp phân tích:*
* Employee:

- Thuộc tính:

 + employeeId: ID của nhân viên.

  +name: Tên của nhân viên.

  +timecards: Danh sách các thẻ thời gian của nhân viên.

- Phương thức:

  +addTimecard(timecard: Timecard): Thêm thẻ thời gian mới.

  +updateTimecard(timecard: Timecard): Cập nhật thẻ thời gian.

Ý nghĩa: Đại diện cho nhân viên trong hệ thống, là đối tượng chính cần quản lý thông tin và thẻ thời gian.

* Timecard:

 -Thuộc tính:

  +timecardId: ID của thẻ thời gian.

  +employeeId: ID của nhân viên.

  +date: Ngày làm việc.

  +hoursWorked: Số giờ làm việc.

 -Phương thức:

  +validate(): Xác thực thông tin thẻ thời gian.

Ý nghĩa: Quản lý thông tin chi tiết về thời gian làm việc của nhân viên, giúp tính toán lương chính xác.

* Payroll:

 -Thuộc tính:

  +payrollId: ID của bảng lương.

  +employee: Thông tin nhân viên.

  +amount: Số tiền lương.

 -Phương thức:

  +calculateSalary(): Tính toán lương dựa trên thẻ thời gian.

  +generatePayslip(): Tạo phiếu lương.

Ý nghĩa: Quản lý quá trình tính toán và xử lý lương, đảm bảo tính chính xác và hiệu quả.

* TimecardDatabase:

 -Thuộc tính:

  +databaseId: ID của cơ sở dữ liệu.

  +timecards: Danh sách các thẻ thời gian.

 -Phương thức:

  +saveTimecard(timecard: Timecard): Lưu thẻ thời gian vào cơ sở dữ liệu.

  +getTimecard(employeeId: int, date: Date): Truy xuất thẻ thời gian của nhân viên theo ngày.

Ý nghĩa: Quản lý việc lưu trữ và truy xuất dữ liệu thẻ thời gian, đảm bảo tính toàn vẹn và bảo mật của dữ liệu.

# 5. Hợp nhất kết quả phân tích
##  Biểu đồ lớp hợp nhất các lớp phân tích cho ca sử dụng "Payment" và "Maintain Timecard" trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/Z5LBQkGm4Dtx55ewaBw02I64cO61cH3IWQohfKeYee-Hv2Pcc9DbaIFb2h5R7tVP3kbUDEZLvprLbSeVR-zNFe0BdLOLL-0z-wbRPNj4zgzYms_3C06_HSEa2GareB5Xs-2aUKfG2xr64_vYUBQ3x-tnCRa4gP634xvXVwGF5_VfV7cmC-PH8GyaijPh-SuQjhTIf30G8cUgCqN3CaHzkrP0m1FS_rUf8eIub2NAeaM9sCsyD8orpdBqFcMgGTlEX8O9s-qKBWYpaiALHLAszSQCjslOZ-4_0S-sS_x1kXSKcJ6fseEIetizADXPgn0CkRMpIXKDRJolIsZAs2G3lM7Yuw1ufmR2BIXm_KXBxFYAl0kOgqJxzeG67HoiNicsNbJj6ipBjlS1TT6y6o0gU4HM-XCS6F-8xbTdX9-rvvm1vn68CLyDo6riidLJpJ92HHHuHOaqCaYOYZ3NSi9huDOyIgVdPInoxx2rBXIHxd2a2YDstxTpURaBCSSoTnxTOVvW1txQ8Y81bEVRVG3xKvvgrXQAx-njd1yzYxCfVjHTzjrcSpdRMSHKOlB36C4ozSSWJN9iMSqndnvYZ7Mkw0eQ3TEqLulnMufOj8MeMRMMgrsX4UFduHC00F__0m00)

*Tài liệu mô tả biểu đồ lớp phân tích cho 2 ca sử dụng Payment và Maintain Timecard của hệ thống Payroll trên :*

* 1.Lớp Employee
-Mô tả: Lớp này đại diện cho nhân viên trong hệ thống payroll. Nó chứa thông tin cá nhân của nhân viên và các phương thức để quản lý thẻ thời gian và phương thức thanh toán.

 -Thuộc tính:

 +employeeId: ID duy nhất của nhân viên.

 +name: Tên của nhân viên.

 +paymentMethod: Phương thức thanh toán mà nhân viên đã chọn.

 +timecards: Danh sách các thẻ thời gian của nhân viên.

 -Phương thức:

 +selectPaymentMethod(method: PaymentMethod): Cho phép nhân viên chọn phương thức thanh toán.

 +addTimecard(timecard: Timecard): Thêm thẻ thời gian mới cho nhân viên.

 +updateTimecard(timecard: Timecard): Cập nhật thông tin thẻ thời gian của nhân viên.

* 2. Lớp PaymentMethod
     
-Mô tả: Lớp này quản lý các phương thức thanh toán khác nhau mà nhân viên có thể chọn.

-Thuộc tính:

 +methodId: ID duy nhất của phương thức thanh toán.

 +methodName: Tên của phương thức thanh toán.

-Phương thức:

 +processPayment(amount: double): Xử lý thanh toán cho một số tiền cụ thể.

* 3. Lớp Timecard
-Mô tả: Lớp này đại diện cho thẻ thời gian của nhân viên, chứa thông tin về thời gian làm việc của họ.

-Thuộc tính:

 +timecardId: ID duy nhất của thẻ thời gian.

 +employeeId: ID của nhân viên liên quan đến thẻ thời gian.

 +date: Ngày làm việc.

 +hoursWorked: Số giờ làm việc.

-Phương thức:

 +validate(): Xác thực thông tin thẻ thời gian.

* 4. Lớp Payroll
-Mô tả: Lớp này quản lý quá trình tính toán và xử lý lương cho nhân viên.

-Thuộc tính:

 +payrollId: ID duy nhất của bảng lương.

 +employee: Thông tin nhân viên liên quan đến bảng lương.

 +amount: Số tiền lương.

-Phương thức:

 +calculateSalary(): Tính toán lương dựa trên thẻ thời gian.

 +executePayment(): Thực hiện thanh toán lương.

 +generatePayslip(): Tạo phiếu lương cho nhân viên.

* 5. Lớp BankSystem
-Mô tả: Lớp này tương tác với hệ thống ngân hàng để xử lý các giao dịch tài chính.

-Thuộc tính:

 +bankId: ID duy nhất của ngân hàng.

 +bankName: Tên của ngân hàng.

-Phương thức:

 +transferFunds(amount: double, account: String): Chuyển tiền cho một tài khoản cụ thể.

* 6. Lớp PaymentProcessor
-Mô tả: Lớp này xử lý các yêu cầu thanh toán từ hệ thống payroll.

-Thuộc tính:

 +processorId: ID duy nhất của bộ xử lý thanh toán.

 +processorName: Tên của bộ xử lý thanh toán.

-Phương thức:

 +initiatePayment(amount: double, method: PaymentMethod): Khởi tạo thanh toán.

 +confirmPayment(): Xác nhận thanh toán.

* 7. Lớp Report
-Mô tả: Lớp này tạo các báo cáo liên quan đến thanh toán và lương.

-Thuộc tính:

 +reportId: ID duy nhất của báo cáo.

 +reportType: Loại báo cáo.

-Phương thức:

 +generateReport(): Tạo báo cáo.

* 8. Lớp TimecardDatabase
-Mô tả: Lớp này quản lý việc lưu trữ và truy xuất dữ liệu thẻ thời gian.

 -Thuộc tính:

 +databaseId: ID duy nhất của cơ sở dữ liệu.

 +timecards: Danh sách các thẻ thời gian.

-Phương thức:

 +saveTimecard(timecard: Timecard): Lưu thẻ thời gian vào cơ sở dữ liệu.

 +getTimecard(employeeId: int, date: Date): Truy xuất thẻ thời gian của nhân viên theo ngày.

