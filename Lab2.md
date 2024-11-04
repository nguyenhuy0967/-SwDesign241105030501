# 1. Phân tích ca sử dụng Create Employee

## Biểu đồ lớp mô tả các sequence phân tích cho ca sử dụng create employee  trong hệ thống payroll

![Diagram](https://www.planttext.com/api/plantuml/png/TD8nJiCm50RWtQTuwbG6Bf01DKfICLKHYTXTroMMOZkoNo9bPkG8BC28nCRK30mvIKx05N3IDWIKhlQdty-_tdVpjR983POo9vIXDX3JskWyztTIA67HK7T8IE6COAAW2c4nHnP0BSJ-NnZ98jSrvsjjv02YzJm8jC8-aXzpec2U9TnKWl6ZIUPDI95kgJsXa93OX-iRzx87gIbhODtXeu2zcmZIxl2gOPErRmhkHVkkIBJkRUnxS2kwvb41PbtpT4d_9c-o8HMpzbCz00e5Qd1Lxq1spRCuPKU11xRSIe7JSfPyClqLYOA19XummodoC_tFae65Bf5M5r4uPccr5qOcpYvjoHYtTinmKncEfL7zxHstPOuJ4vp_kHEso6azYyRgqcCBszRLXKDfqp9SHoyg0zORik9grw_U3m000F__0m00)

*Giải thích các bước trong biểu đồ sequence:*

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
Giải thích các lớp phân tích:
*PayrollAdministrator:

Thuộc tính:

adminId: ID của quản trị viên.

name: Tên của quản trị viên.

Phương thức:

login(): Đăng nhập vào hệ thống.

createEmployee(employeeData: EmployeeData): Tạo nhân viên mới.

Ý nghĩa: Đại diện cho người dùng (quản trị viên) có quyền tạo mới nhân viên trong hệ thống.

*EmployeeForm:

Phương thức:

displayForm(): Hiển thị form tạo nhân viên.

submitForm(employeeData: EmployeeData): Gửi form tạo nhân viên.

displayResult(success: boolean): Hiển thị kết quả tạo nhân viên.

Ý nghĩa: Quản lý giao diện người dùng cho chức năng tạo mới nhân viên.

*EmployeeController:

Phương thức:

submitEmployeeForm(employeeData: EmployeeData): Xử lý dữ liệu form từ EmployeeForm.

returnSaveResult(success: boolean): Trả về kết quả lưu trữ cho EmployeeForm.

Ý nghĩa: Điều khiển luồng dữ liệu giữa EmployeeForm và EmployeeService.

*EmployeeService:

Phương thức:

createEmployee(employeeData: EmployeeData): Tạo nhân viên mới.

returnSaveResult(success: boolean): Trả về kết quả lưu trữ cho EmployeeController.

Ý nghĩa: Xử lý logic nghiệp vụ và tương tác với EmployeeDatabase để lưu trữ dữ liệu.

*EmployeeDatabase:

Phương thức:

saveEmployee(employeeData: EmployeeData): Lưu dữ liệu nhân viên vào cơ sở dữ liệu.

confirmSave(success: boolean): Xác nhận việc lưu trữ.

Ý nghĩa: Quản lý việc lưu trữ dữ liệu nhân viên trong cơ sở dữ liệu.

*EmployeeData:

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
