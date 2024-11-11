# 1. Phân tích ca sử dụng Create Employee

## Biểu đồ sequence mô tả hành vi của ca sử dụng create employee  trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/TD8nJiCm50RWtQTuwbG6Bf01DKfICLKHYTXTroMMOZkoNo9bPkG8BC28nCRK30mvIKx05N3IDWIKhlQdty-_tdVpjR983POo9vIXDX3JskWyztTIA67HK7T8IE6COAAW2c4nHnP0BSJ-NnZ98jSrvsjjv02YzJm8jC8-aXzpec2U9TnKWl6ZIUPDI95kgJsXa93OX-iRzx87gIbhODtXeu2zcmZIxl2gOPErRmhkHVkkIBJkRUnxS2kwvb41PbtpT4d_9c-o8HMpzbCz00e5Qd1Lxq1spRCuPKU11xRSIe7JSfPyClqLYOA19XummodoC_tFae65Bf5M5r4uPccr5qOcpYvjoHYtTinmKncEfL7zxHstPOuJ4vp_kHEso6azYyRgqcCBszRLXKDfqp9SHoyg0zORik9grw_U3m000F__0m00)

### Giải thích các bước trong biểu đồ sequence:

PayrollAdministrator truy cập form Tạo Nhân Viên trên giao diện.

EmployeeForm hiển thị form Tạo Nhân Viên cho PayrollAdministrator.

PayrollAdministrator nhập thông tin của nhân viên mới và nộp form.

EmployeeForm gửi dữ liệu nhân viên mới đến EmployeeController thông qua phương thức submitEmployeeForm(employeeData).

EmployeeController gọi phương thức createEmployee(employeeData) của EmployeeService để xử lý việc tạo nhân viên mới.

EmployeeService gửi yêu cầu saveEmployee(employeeData) đến EmployeeDatabase để lưu thông tin nhân viên vào cơ sở dữ liệu.

EmployeeDatabase xác nhận việc lưu trữ thành công và gửi phản hồi lại cho EmployeeService.

EmployeeService trả về kết quả lưu trữ cho EmployeeController.

EmployeeController gửi kết quả lưu trữ đến EmployeeForm để hiển thị thông báo.

EmployeeForm thông báo cho PayrollAdministrator rằng việc tạo nhân viên mới đã thành công.

## Biểu đồ lớp mô tả các lớp phân tích cho ca sử dụng create employee  trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/f9J1JiCm38RlVOeSos4lq0CQWY5nGziJU8qt8YLn5RkLAiIJSU2HU0MQaMvTsBHDzDJ-TktFoPzyVtxDMI18wsnHMs1Mhz07ilP1E-CDIm2XeDuBDJmp1L5zqPKoNfBamM6bLXACt-uafInjZI_lAjMHqKch0uBWmZMMUiGIqyiJ25HgCVaQV_ie4j0OVARW4eXIsd1ZeOzQreZRjJEo2rnkSbHiYTnQARcjQsIkr9h88lYpG8_a9IuLXZtMR_CfyTKG0QKDVWKTtignmj2P6lSGDo_rVm5YhJNmWO278jVrJwL7Sl8R4rnakAtxtg1ZimiUZObWRAOrR-Jpl8ROY26VoHgRuTGuz98562o4lb8RIo1fh0wiqSEMHD9oClGmoidJDflT7xc-E3e2q-Z1WiK9LqupaqcAt3JJd74VYpyRcsUT9zf5v-Xrl55-0000__y30000)

### Giải thích các lớp phân tích:

* PayrollAdministrator:

Thuộc tính:

adminId: ID của quản trị viên.

name: Tên của quản trị viên.

Phương thức:

login(): Đăng nhập vào hệ thống.

createEmployee(employeeData: EmployeeData): Tạo nhân viên mới.

Ý nghĩa: Đại diện cho người dùng (quản trị viên) có quyền tạo mới nhân viên trong hệ thống.

* EmployeeForm:

Phương thức:

displayForm(): Hiển thị form tạo nhân viên.

submitForm(employeeData: EmployeeData): Gửi form tạo nhân viên.

displayResult(success: boolean): Hiển thị kết quả tạo nhân viên.

Ý nghĩa: Quản lý giao diện người dùng cho chức năng tạo mới nhân viên.

* EmployeeController:

Phương thức:

submitEmployeeForm(employeeData: EmployeeData): Xử lý dữ liệu form từ EmployeeForm.

returnSaveResult(success: boolean): Trả về kết quả lưu trữ cho EmployeeForm.

Ý nghĩa: Điều khiển luồng dữ liệu giữa EmployeeForm và EmployeeService.

* EmployeeService:

Phương thức:

createEmployee(employeeData: EmployeeData): Tạo nhân viên mới.

returnSaveResult(success: boolean): Trả về kết quả lưu trữ cho EmployeeController.

Ý nghĩa: Xử lý logic nghiệp vụ và tương tác với EmployeeDatabase để lưu trữ dữ liệu.

* EmployeeDatabase:

Phương thức:

saveEmployee(employeeData: EmployeeData): Lưu dữ liệu nhân viên vào cơ sở dữ liệu.

confirmSave(success: boolean): Xác nhận việc lưu trữ.

Ý nghĩa: Quản lý việc lưu trữ dữ liệu nhân viên trong cơ sở dữ liệu.

* EmployeeData:

Thuộc tính:

employeeId: ID của nhân viên.

name: Tên của nhân viên.

email: Địa chỉ email của nhân viên.

phone: Số điện thoại của nhân viên.

position: Chức danh của nhân viên.

department: Phòng ban của nhân viên.

salary: Mức lương của nhân viên.

Phương thức:

validateData(): Xác thực thông tin dữ liệu.

Ý nghĩa: Đối tượng dữ liệu chứa thông tin chi tiết của nhân viên.

# 2. Phân tích ca sử dụng Maintain Purchse Order
## Biểu đồ sequence mô tả của ca sử dụng Maintain Purchse Order trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/b98nJiCm58RtdEA9gGnS80EgvAHYeeMK0xYEsrYAxSX-hjIPaGLc5YfMs92G6Y66LDmZ9-0AE6qfRLLLPR8iVv__zvxzNNwsBLA3JkO1PQWD42sbi5PenTDO5hcUS1u4XMS44mLL22Vxa1EW5aYy3VQSOHcrl6jIRZhQo0NLwtOEO4GhD3hFkLd1v02SS3CMZA_8v00PKQG3lrcXKH2G6CxEcs92w1it0LRFNWiO-YhXojMpPmLvzG7p-w-fWlb3FNj7oAedDGgyqfWa3k52rEMj0ipgykuOTIFpCblaOLQzgH6WQCXT7cHTFehVG3-A4AmRI85RhRMAtKPFlKAMIX82CvoYFxmfKhyUeIPBDV9fTFmVCVhBr6eeZ4oytxAECMxjnis-3yFH6TMSNtFhSjoao7f8gR15JYVxiVKhz9Sp75HJ3Qb_IJJLoxvfOhDam1ewQ7ELDh_-1m00__y30000).

### Giải thích các bước trong biểu đồ sequence:

CommissionedEmployee truy cập form Quản lý Đơn đặt hàng trên giao diện.

PurchaseOrderForm hiển thị form Quản lý Đơn đặt hàng cho CommissionedEmployee.

CommissionedEmployee nhập thông tin đơn đặt hàng mới và nộp form.

PurchaseOrderForm gửi dữ liệu đơn đặt hàng đến PurchaseOrderController thông qua phương thức submitPurchaseOrder(purchaseOrderData).

PurchaseOrderController gọi phương thức createOrUpdatePurchaseOrder(purchaseOrderData) của PurchaseOrderService để xử lý việc duy trì đơn đặt hàng.

PurchaseOrderService gửi yêu cầu saveOrUpdatePurchaseOrder(purchaseOrderData) đến PurchaseOrderDatabase để lưu thông tin đơn đặt hàng vào cơ sở dữ liệu.

PurchaseOrderDatabase xác nhận việc lưu trữ thành công và gửi phản hồi lại cho PurchaseOrderService.

PurchaseOrderService trả về kết quả lưu trữ cho PurchaseOrderController.

PurchaseOrderController gửi kết quả lưu trữ đến PurchaseOrderForm để hiển thị thông báo.

PurchaseOrderForm thông báo cho CommissionedEmployee rằng việc duy trì đơn đặt hàng mới đã thành công.

## Biểu đồ lớp mô tả các lớp phân tích cho ca sử dụng create employee  trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/h9HBJiCm48RtFiKimw8No09LAY2nQaN50Lnx2fRy26CxKeKu6GkEn1MmM_SH4X0qpIAI_qnclddvy_rZwWEd48rcGdFlOUQCKTuhPr7UcaQx3IAyCaZF1B08zx86PKDHBJTOmpAGiazR2K0Gye2BIEAPUvoJHAgQqzCD3xo6nNVfgeRMALcyn4QEylB6Ib8TYpj7fcG489LlDDzahUe6zt5bLDX--3zvSVk0FkfG-IW4Ub_3oZcDtFxEDtCsaDCQwK2vOnbRJi8GoIvvYsTnBP5Q9V00jUlnd1v7TkaYSDdXAXsE9KkUHh6LiFjadLqhCfdl3BB30hciTBUd8IUZ25tn9N8RLDXq3LFrQrXhnyEfknGWoVbTM5kkLKuxHwvECabyWzizcLptDuJrTwPdTvnKzjC4z_ufKyG6HwjdlMyh6sxseFrVoBTsKxGoNtnV0000__y30000)

### Giải thích các lớp phân tích:
* CommissionedEmployee:

Thuộc tính:

employeeId: ID của nhân viên hoa hồng.

name: Tên của nhân viên hoa hồng.

Phương thức:

createPurchaseOrder(purchaseOrderData: PurchaseOrderData): Tạo đơn đặt hàng mới.

updatePurchaseOrder(purchaseOrderData: PurchaseOrderData): Cập nhật đơn đặt hàng hiện tại.

Ý nghĩa: Đại diện cho nhân viên hoa hồng, người có thể tạo và cập nhật đơn đặt hàng.

* PurchaseOrderForm:

Phương thức:

displayForm(): Hiển thị form tạo và cập nhật đơn đặt hàng.

submitForm(purchaseOrderData: PurchaseOrderData): Gửi form tạo và cập nhật đơn đặt hàng.

displayResult(success: boolean): Hiển thị kết quả của việc tạo và cập nhật đơn đặt hàng.

Ý nghĩa: Quản lý giao diện người dùng cho chức năng tạo và cập nhật đơn đặt hàng.

* PurchaseOrderController:

Phương thức:

submitPurchaseOrder(purchaseOrderData: PurchaseOrderData): Xử lý dữ liệu form từ PurchaseOrderForm.

returnSaveResult(success: boolean): Trả về kết quả lưu trữ cho PurchaseOrderForm.

Ý nghĩa: Điều khiển luồng dữ liệu giữa PurchaseOrderForm và PurchaseOrderService.

* PurchaseOrderService:

Phương thức:

createOrUpdatePurchaseOrder(purchaseOrderData: PurchaseOrderData): Tạo hoặc cập nhật đơn đặt hàng.

returnSaveResult(success: boolean): Trả về kết quả lưu trữ cho PurchaseOrderController.

Ý nghĩa: Xử lý logic nghiệp vụ và tương tác với PurchaseOrderDatabase để lưu trữ dữ liệu.

* PurchaseOrderDatabase:

Phương thức:

saveOrUpdatePurchaseOrder(purchaseOrderData: PurchaseOrderData): Lưu hoặc cập nhật dữ liệu đơn đặt hàng vào cơ sở dữ liệu.

confirmSave(success: boolean): Xác nhận việc lưu trữ.

Ý nghĩa: Quản lý việc lưu trữ dữ liệu đơn đặt hàng trong cơ sở dữ liệu.

* PurchaseOrderData:

Thuộc tính:

orderId: ID của đơn đặt hàng.

productId: ID của sản phẩm.

quantity: Số lượng sản phẩm.

price: Giá của sản phẩm.

orderDate: Ngày đặt hàng.

Phương thức:

validateData(): Xác thực thông tin dữ liệu đơn đặt hàng.

Ý nghĩa: Đối tượng dữ liệu chứa thông tin chi tiết của đơn đặt hàng.

# 3. Phân tích ca sử dụng Login
## Biểu đồ sequence mô tả của ca sử dụng Login trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/T98_Ri8m5CPtd-A92QJs0XageaIeGzIX8GSmYI4MYPFQprJCZ5tQ6xJgr4hTEi7042wI4_GAjGFXZu3jvNi_VtxVS_vMwxv2Ab7d6Q4n5X8YnIGXfT5up4ig43fMwW1L49tgGJ7XOb38l6a6WmjThn0eYopR6GJUAUDgJ4CcPpncJTyDps_sAT8HLLiWyWc9uFREtER0KEevnFNofuIncG8shvk5c818hKI2WUKY1-vvlLe8mBHUlLm2ztuFpJTWzIrWytQ4mAnwXznK25CZVEcTUU0veFGevzY4xMephg0vku6IAlLSoAH70i-IRkW0DM6PCE4eCXli8kw6pTI-0nE6bl8aI-mfcgdzWHw9_DPLCjHI75FneMxzB3XZae_dLy3p4MoshRTzf4UcT8PTkY_RO7Pl2LTbHkVNkFOTXcdrQrOwgZuAcDRBDSAJhfUVfwicVIOI-pV-0m00__y30000)

### Giải thích các bước trong biểu đồ sequence:
User truy cập form Đăng nhập trên giao diện.

LoginForm hiển thị form Đăng nhập cho User.

User nhập tên đăng nhập và mật khẩu vào form.

LoginForm gửi dữ liệu đăng nhập đến LoginController thông qua phương thức submitLogin(username, password).

LoginController gọi phương thức authenticateUser(username, password) của AuthService để xác thực người dùng.

AuthService gửi yêu cầu getUserCredentials(username) đến UserDatabase để lấy thông tin đăng nhập của người dùng.

UserDatabase trả về thông tin đăng nhập cho AuthService.

AuthService xác thực thông tin đăng nhập với mật khẩu đã nhập.

AuthService trả về kết quả xác thực cho LoginController.

LoginController gửi kết quả xác thực đến LoginForm để hiển thị thông báo.

LoginForm thông báo kết quả đăng nhập cho User.

## Biểu đồ lớp mô tả các lớp phân tích cho ca sử dụng Login  trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/d5D1IiKm5Dpd55bMi1VeGhvy4GGNdryyGDeyQY1DIl9I4V5aBZoILp2fQPly8bIxoqnUPfWt_VhuF5Xa1bqlIIkPjVJ9Wg5lXFglfCuV7dX5XS84KQo7YjPeXEeYFFZH5sru1bCgTITKSLNHHci9J95t4cKU0tElJH-rAEN23fAz1YnCZ5hmo5ZNz08dubB-UgESZyP7ps2TnCAwjWLh5plptTpLKIiqMiebXzd1nFxPWW5qHjqwVDxh8jojmOoYXSK1ynWe52r322lQPsEE_RzEWj8TGzOmkrhf00D-DC238oRjnen_AA7d454RgBsUq3yfncPjL9FHh8dxUpSoARXFwXJfGgZ1uUdtWBpsLFool5chITQIBlXQ3d9Pbd0dMHr9rnYuD4oI9HlODAzSDsKEe7ZuLxy1003__mC0)

### Giải thích các lớp phân tích:
* User:

Thuộc tính:

userId: ID của người dùng.

username: Tên đăng nhập của người dùng.

password: Mật khẩu của người dùng.

Phương thức:

login(): Đăng nhập vào hệ thống, trả về kết quả thành công hay thất bại.

Ý nghĩa: Đại diện cho người dùng đăng nhập vào hệ thống.

* LoginForm:

Phương thức:

displayForm(): Hiển thị form đăng nhập.

submitForm(username: String, password: String): Gửi form đăng nhập.

displayResult(success: boolean): Hiển thị kết quả đăng nhập.

Ý nghĩa: Quản lý giao diện người dùng cho chức năng đăng nhập.

* LoginController:

Phương thức:

submitLogin(username: String, password: String): Xử lý dữ liệu form từ LoginForm.

returnAuthResult(success: boolean): Trả về kết quả xác thực cho LoginForm.

Ý nghĩa: Điều khiển luồng dữ liệu giữa LoginForm và AuthService.

* AuthService:

Phương thức:

authenticateUser(username: String, password: String): Xác thực người dùng.

returnAuthResult(success: boolean): Trả về kết quả xác thực cho LoginController.

Ý nghĩa: Xử lý logic nghiệp vụ xác thực và tương tác với UserDatabase để lấy thông tin đăng nhập.

* UserDatabase:

Phương thức:

getUserCredentials(username: String): Lấy thông tin đăng nhập của người dùng.

storeSession(userId: int): Lưu trữ phiên đăng nhập của người dùng.

Ý nghĩa: Quản lý việc lưu trữ và truy xuất thông tin đăng nhập của người dùng trong cơ sở dữ liệu.

* Credentials:

Thuộc tính:

username: Tên đăng nhập của người dùng.

password: Mật khẩu của người dùng.

Phương thức:

validatePassword(inputPassword: String): Xác thực mật khẩu nhập vào.

Ý nghĩa: Đối tượng dữ liệu chứa thông tin đăng nhập của người dùng.

# 4. Phân tích ca sử dụng Create Administrative Report
## Biểu đồ sequence mô tả của ca sử dụng Create Administrative Report trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/Z9AnJiCm48PtFyMfKnbuWGoe8L75X4II5t1SbrXAxEXyhjIPaPS0CRCnfGD3doHFm2lWE6sWKeOkbdtttN_td_np-5vPuaYkgHaNP13YJQEqieJSlnXhVL89rN9DiBZ8BO1RYDDB8fEjGLeRR48wMy-b4wC9JLtBKIDBvg1Suau9EHBv795ouYMt9oHbB4xXzixtZA10jmVHTvyjRFqiKFJTku7xep_4S3ovlllGGDWVNbcs7ihYD887rHzUVBZouIiA__ezLg4NLSSl_GoaD9JdafDybaHWNTae6eTVukJXXcL9GF8814fESWx90-A7j7mt2wIJXj5RXKtkkQLrGaXhfte_1KfogFEWObrD_vZax6UZR5lp_ImqRQiOtGQd5FOqcHusyQOhV_S4Mqcz6JxOBm000F__0m00)

Giải thích các bước trong biểu đồ sequence:

Administrator truy cập form Tạo Báo cáo Quản trị trên giao diện.

ReportForm hiển thị form Tạo Báo cáo Quản trị cho Administrator.

Administrator nhập thông tin của báo cáo vào form.

ReportForm gửi dữ liệu báo cáo đến ReportController thông qua phương thức submitReport(reportData).

ReportController gọi phương thức createReport(reportData) của ReportService để xử lý việc tạo báo cáo.

ReportService gửi yêu cầu saveReport(reportData) đến ReportDatabase để lưu thông tin báo cáo vào cơ sở dữ liệu.

ReportDatabase xác nhận việc lưu trữ thành công và gửi phản hồi lại cho ReportService.

ReportService trả về kết quả lưu trữ cho ReportController.

ReportController gửi kết quả lưu trữ đến ReportForm để hiển thị thông báo.

ReportForm thông báo cho Administrator rằng việc tạo báo cáo mới đã thành công.

## Biểu đồ lớp mô tả các lớp phân tích cho ca sử dụng  Create Administrative Report trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/f5DBReGm3Dtd55dI1HTWKKtLgbAtp5p0W3ko59AHOv2ggYVheaVg5Kh2dtvHMV3ni_qUzilxwzl12x0qjL6b0U_rJLMJ9IyCubW_AzrTgOOGVQWoJLQ6a8KQCtqK9dkE8QsDEvDDhZ9TE6SGx10k6K4mnujZIJW-xa0Wq_dqtjMqZYhreWOPFNJlk1uqQ5sHlnXu2h5apEyHtnGrnUHVsgyQvUWR8ubloXAzdqH_8-NMMM5d3F8agAVzqt_r1OpIi3r2Y_kuZyWjbJWHxnZe_uX3fmBypEnZYvzvDyjtzf6u3jnxM2VdzJHhw_Mn4ubPEt14mgxGoWQBKoDdk_PTMRWF4bimL7MVWNVftaxM-ZIawVN2c6hXqHcPVQ8-6MVE6ZQgrlkTyN7mQhE7TSRN2Y9oG5k5G_q1003__mC0)

### Giải thích các lớp phân tích:

* Administrator:

Thuộc tính:

adminId: ID của quản trị viên.

name: Tên của quản trị viên.

Phương thức:

login(): Đăng nhập vào hệ thống, trả về kết quả thành công hay thất bại.

createReport(reportData: ReportData): Tạo báo cáo quản trị.

Ý nghĩa: Đại diện cho quản trị viên, người có quyền tạo báo cáo quản trị trong hệ thống.

* ReportForm:

Phương thức:

displayForm(): Hiển thị form tạo báo cáo.

submitForm(reportData: ReportData): Gửi form tạo báo cáo.

displayResult(success: boolean): Hiển thị kết quả tạo báo cáo.

Ý nghĩa: Quản lý giao diện người dùng cho chức năng tạo báo cáo quản trị.

* ReportController:

Phương thức:

submitReport(reportData: ReportData): Xử lý dữ liệu form từ ReportForm.

returnSaveResult(success: boolean): Trả về kết quả lưu trữ cho ReportForm.

Ý nghĩa: Điều khiển luồng dữ liệu giữa ReportForm và ReportService.

* ReportService:

Phương thức:

createReport(reportData: ReportData): Tạo báo cáo quản trị.

returnSaveResult(success: boolean): Trả về kết quả lưu trữ cho ReportController.

Ý nghĩa: Xử lý logic nghiệp vụ và tương tác với ReportDatabase để lưu trữ dữ liệu.

* ReportDatabase:

Phương thức:

saveReport(reportData: ReportData): Lưu dữ liệu báo cáo vào cơ sở dữ liệu.

confirmSave(success: boolean): Xác nhận việc lưu trữ.

Ý nghĩa: Quản lý việc lưu trữ dữ liệu báo cáo trong cơ sở dữ liệu.

* ReportData:

Thuộc tính:

reportId: ID của báo cáo.

reportTitle: Tiêu đề của báo cáo.

reportContent: Nội dung của báo cáo.

creationDate: Ngày tạo báo cáo.

Phương thức:

validateData(): Xác thực thông tin dữ liệu báo cáo.

Ý nghĩa: Đối tượng dữ liệu chứa thông tin chi tiết của báo cáo quản trị.

# 5. Phân tích ca sử dụng Maintain Employee Info
## Biểu đồ sequence mô tả của ca sử dụng Maintain Employee Info trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/Z99BJiCm48RtFiM8LLbmWInGeoGLR8eWvG2kun9BoJYo9vMwPiabU2oG4EnOjK8iSfASW2lWfEbB2e-bFT_C_yzlVwq-XvQueJBF61Ua3VX9hb1PCjoT62jSKGbLS2GuEgWT0RVWXuT4b1UPNaWvqYPlWMZK3mGQoUWia-ivKT2FnTBCbP1h9kvdGavyocq7XOpv8PoSEcKF9gPSWAYNRmNCd2EuBElb4q9MVS0ahTxn1aWXZDFg4M6kgXTaqQZfzKCFpbIzkaMWj5xT_RTxfpnEMrNQSRZZ6alFs1d3XgHEE0eyiEKqLxJPxXndUY3tLZrcKT2YiGTbaN2Ilw5nYxfrB9_B2tFzPqEucIqqpfJ9OzStiAKGqjhjFEVII2eDDjKhQSkCzfXW4qAYR97nHI-qpRcBSbezQ4ZSSv6fNd_ApLtVOmgYARAXnAJvjzy0003__mC0)

### Giải thích các bước trong biểu đồ sequence:

Administrator truy cập form Quản lý Thông tin Nhân viên trên giao diện.

EmployeeForm hiển thị form Quản lý Thông tin Nhân viên cho Administrator.

Administrator nhập thông tin của nhân viên cần cập nhật và nộp form.

EmployeeForm gửi dữ liệu thông tin nhân viên đến EmployeeController thông qua phương thức submitEmployeeInfo(employeeData).

EmployeeController gọi phương thức updateEmployeeInfo(employeeData) của EmployeeService để xử lý việc cập nhật thông tin nhân viên.

EmployeeService gửi yêu cầu saveOrUpdateEmployeeInfo(employeeData) đến EmployeeDatabase để lưu hoặc cập nhật thông tin nhân viên vào cơ sở dữ liệu.

EmployeeDatabase xác nhận việc lưu trữ thành công và gửi phản hồi lại cho EmployeeService.

EmployeeService trả về kết quả lưu trữ cho EmployeeController.

EmployeeController gửi kết quả lưu trữ đến EmployeeForm để hiển thị thông báo.

EmployeeForm thông báo cho Administrator rằng việc duy trì thông tin nhân viên đã thành công.

## Biểu đồ lớp mô tả các lớp phân tích cho ca sử dụng Maintain Employee Info trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/f9J1JiCm38RlUOeSos4lq0CQWY7jXCJ40tYDDombSPMubIR4at7WaNW5cgtjsi8q5NhBRoV-dFpkryVdCWe4gPnLXOKOzPrnv2bA0E6WtvHkleM6fAvDhibBAtbmcEkD1FBxewIrvJtvx2RNMsQBu5kvAWq8hbnf-O2uzZlEi5qyW42kLuDLixjcCkfTjK1Ty963QtcqDXHB2uUaPTsEKoHMMqTo35mlCZhi6MDb9OjLKM2CVHCNWUxPIs1hCVHOf-8pEprj3IXLy1keSIx71aDD1VOGVxhk_qAaixOGpnInEUGflCna6HkdOB-Zu1BFF9BUjrsnAzPDYK1sefMlxATv9KSIOZ-H3PRD53dqCWb4i10EkTvP1cdRgi5IkfP4EfoMffNnz2qMjoFxgz4i3ADdBwfVx3dCRDsYfkuPvdIFgNwyxZJhCj4nkaHlqg_b6m00__y30000)

### Giải thích các lớp phân tích:

* Administrator:

Thuộc tính:

adminId: ID của quản trị viên.

name: Tên của quản trị viên.

Phương thức:

login(): Đăng nhập vào hệ thống, trả về kết quả thành công hay thất bại.

updateEmployeeInfo(employeeData: EmployeeData): Cập nhật thông tin nhân viên.

Ý nghĩa: Đại diện cho quản trị viên, người có quyền cập nhật thông tin nhân viên trong hệ thống.

* EmployeeForm:

Phương thức:

displayForm(): Hiển thị form cập nhật thông tin nhân viên.

submitForm(employeeData: EmployeeData): Gửi form cập nhật thông tin nhân viên.

displayResult(success: boolean): Hiển thị kết quả cập nhật thông tin nhân viên.

Ý nghĩa: Quản lý giao diện người dùng cho chức năng cập nhật thông tin nhân viên.

* EmployeeController:

Phương thức:

submitEmployeeInfo(employeeData: EmployeeData): Xử lý dữ liệu form từ EmployeeForm.

returnSaveResult(success: boolean): Trả về kết quả lưu trữ cho EmployeeForm.

Ý nghĩa: Điều khiển luồng dữ liệu giữa EmployeeForm và EmployeeService.

* EmployeeService:

Phương thức:

updateEmployeeInfo(employeeData: EmployeeData): Cập nhật thông tin nhân viên.

returnSaveResult(success: boolean): Trả về kết quả lưu trữ cho EmployeeController.

Ý nghĩa: Xử lý logic nghiệp vụ và tương tác với EmployeeDatabase để lưu trữ dữ liệu.

* EmployeeDatabase:

Phương thức:

saveOrUpdateEmployeeInfo(employeeData: EmployeeData): Lưu hoặc cập nhật dữ liệu nhân viên vào cơ sở dữ liệu.

confirmSave(success: boolean): Xác nhận việc lưu trữ.

Ý nghĩa: Quản lý việc lưu trữ dữ liệu nhân viên trong cơ sở dữ liệu.

* EmployeeData:

Thuộc tính:

employeeId: ID của nhân viên.

name: Tên của nhân viên.

email: Địa chỉ email của nhân viên.

phone: Số điện thoại của nhân viên.

position: Chức danh của nhân viên.

department: Phòng ban của nhân viên.

salary: Mức lương của nhân viên.

Phương thức:

validateData(): Xác thực thông tin dữ liệu nhân viên.

Ý nghĩa: Đối tượng dữ liệu chứa thông tin chi tiết của nhân viên.

# 6. Phân tích ca sử dụng Run Payroll
## Biểu đồ sequence mô tả của ca sử dụng Run Payroll trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/V9C_JiCm5CPtd-A9gHsuG0RKaBI21KMa5t1SjxLmdE0_bJ8pSeg8WGc9WIaTEbJgFN82he3J_26f0bFalD_xli_loT_xmqnfBBM9ES949n82dCc4StSLCy6KbjZ-H2Yr32CinKB3rHXo1LX1u8w2YqJ6TNqnMlSIeQilRLIyKIgaSiS8hP5mYCpZb2SPfJxMECAgXkR-gCw02No40XUkRsms1vRIP43AuYE5jSqCthOiyWnko-9DR82VFa-vsA1WSUPT1-vOkNyHeBVb_lNVZixXONjM9yUSsBRZbuKq4vNdUwN3okAWMmFF0MMYcEac-BrO9vFqzn9J57XdC7H06j5G5qHO4NFVWGtL_IbDfcZkTzrK6oa6PTexj38LIZ0dXcDDGyonP5IDazPGuHtjZVmYL-TD4h5cCWujFL664AfKf-ArqHgTHweCrptCQ-UwOYhbEFkBwpQsh6SU7VC4dgfXmxEnkm9IxoqQxcr6nQfw6Jy0003__mC0)

### Giải thích các bước trong biểu đồ sequence:

PayrollAdministrator truy cập form Chạy Bảng lương trên giao diện.

PayrollForm hiển thị form Chạy Bảng lương cho PayrollAdministrator.

PayrollAdministrator nhập các thông tin cần thiết vào form.

PayrollForm gửi dữ liệu bảng lương đến PayrollController thông qua phương thức submitPayrollInfo(payrollData).

PayrollController gọi phương thức runPayroll(payrollData) của PayrollService để xử lý việc chạy bảng lương.

PayrollService gửi yêu cầu getEmployeeData() đến EmployeeDatabase để lấy thông tin nhân viên.

EmployeeDatabase trả về dữ liệu nhân viên cho PayrollService.

PayrollService thực hiện tính toán lương dựa trên thông tin nhân viên.

PayrollService gửi yêu cầu savePayrollData(payrollData) đến PayrollDatabase để lưu thông tin bảng lương vào cơ sở dữ liệu.

PayrollDatabase xác nhận việc lưu trữ thành công và gửi phản hồi lại cho PayrollService.

PayrollService trả về kết quả chạy bảng lương cho PayrollController.

PayrollController gửi kết quả chạy bảng lương đến PayrollForm để hiển thị thông báo.

PayrollForm thông báo cho PayrollAdministrator rằng việc chạy bảng lương đã thành công.

## Biểu đồ lớp mô tả các lớp phân tích cho ca sử dụng Run Payroll trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/h5HBReCm4Dtx55xI1HT0LPIe7wbI5rKvmGGcaINZGVQ0XAgUh8iUgLSe14p094qYbOt5ZEVDyvlFpzVtsZ5OhWejCWtEoJTeB6czoGjbb6CBJ5P-2Db-iOJE-f8dKXaUJ0OAJ6JALfdzmIIbfhqoqLqYjqGQmGncMva1F2hxyn4O4f-n-sbZQbAv-1HpDizaYu64bBbofOQciqK-eFUuQbieFZWkPPX1lQEhD4UkoZ9qRkHzZiq36UvEj2EdFlFWVp4xkfA0HQwib-L66YdQMcKuShX1tpuW0vrL6XXJq60LkWYBKbE3s0U-jlM_VvgOLlz0Vegt1NUalqUU-hhIBWaiH5Z0EAXnuljBYdbxPcHsoXPf6tzr2JgWSJY6JFFnAD4gocS34aic1hqfg3ASo9qcyBUz_huWWGG7SxCQ2DUWLTvMpwlbdtDIwf6bJt5XYblcv1GhCe7P7JXusejSFSKBsNgCkG0jqidL4yUhwHOGquqmyHrdKYodT79l61eHp51t8-pCKtU2hXEBRWw1HDYd0SgvzuInC-1UPB56atUB-nS00F__0m00)

### Giải thích các lớp phân tích:

* PayrollAdministrator:

Thuộc tính:

adminId: ID của quản trị viên.

name: Tên của quản trị viên.

Phương thức:

login(): Đăng nhập vào hệ thống, trả về kết quả thành công hay thất bại.

runPayroll(payrollData: PayrollData): Chạy bảng lương.

Ý nghĩa: Đại diện cho quản trị viên, người có quyền chạy bảng lương trong hệ thống.

* PayrollForm:

Phương thức:

displayForm(): Hiển thị form chạy bảng lương.

submitForm(payrollData: PayrollData): Gửi form chạy bảng lương.

displayResult(success: boolean): Hiển thị kết quả chạy bảng lương.

Ý nghĩa: Quản lý giao diện người dùng cho chức năng chạy bảng lương.

* PayrollController:

Phương thức:

submitPayrollInfo(payrollData: PayrollData): Xử lý dữ liệu form từ PayrollForm.

returnPayrollResult(success: boolean): Trả về kết quả chạy bảng lương cho PayrollForm.

Ý nghĩa: Điều khiển luồng dữ liệu giữa PayrollForm và PayrollService.

* PayrollService:

Phương thức:

runPayroll(payrollData: PayrollData): Chạy bảng lương.

calculateSalaries(employeeData: List<EmployeeData>): Tính toán lương cho nhân viên.

returnPayrollResult(success: boolean): Trả về kết quả chạy bảng lương cho PayrollController.

Ý nghĩa: Xử lý logic nghiệp vụ và tương tác với EmployeeDatabase và PayrollDatabase để thực hiện chạy bảng lương.

* EmployeeDatabase:

Phương thức:

getEmployeeData(): Lấy thông tin nhân viên.

Ý nghĩa: Quản lý việc lưu trữ và truy xuất thông tin nhân viên từ cơ sở dữ liệu.

* PayrollDatabase:

Phương thức:

savePayrollData(payrollData: PayrollData): Lưu dữ liệu bảng lương vào cơ sở dữ liệu.

confirmSave(success: boolean): Xác nhận việc lưu trữ.

Ý nghĩa: Quản lý việc lưu trữ dữ liệu bảng lương trong cơ sở dữ liệu.

* PayrollData:

Thuộc tính:

payrollId: ID của bảng lương.

period: Kỳ lương.

totalAmount: Tổng số tiền lương.

employeeSalaries: Danh sách lương nhân viên.

Phương thức:

validateData(): Xác thực thông tin dữ liệu bảng lương.

Ý nghĩa: Đối tượng dữ liệu chứa thông tin chi tiết của bảng lương.

* EmployeeData:

Thuộc tính:

employeeId: ID của nhân viên.

name: Tên của nhân viên.

position: Chức danh của nhân viên.

salary: Mức lương của nhân viên.

Ý nghĩa: Đối tượng dữ liệu chứa thông tin chi tiết của nhân viên.

* EmployeeSalary:

Thuộc tính:

employeeId: ID của nhân viên.

salaryAmount: Số tiền lương của nhân viên.

Ý nghĩa: Đối tượng dữ liệu chứa thông tin lương của từng nhân viên.

