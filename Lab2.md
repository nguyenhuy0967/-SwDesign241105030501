# 1. Phân tích ca sử dụng Create Employee
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
