# Hệ thống con BankSystem 
## Biểu đồ ngữ cảnh của hệ thống con BankSystem.
![Diagram](https://www.planttext.com/api/plantuml/png/h94zQWCn48NxESNWoeROE6qmYt4gTm6VGDQEYR1-5irio69yiXGvKguGQN-CO5jNceVUlFSX_VtyxbbKbDPPq5OnuuVgOh3sFNZ99qNSxL0F2giARu0OMp_QbYku0nWl52zA4nuFobzF7GkvtbbJ4zZ8Cjdr9-ahDkFmWjbvz9SGdH8JF9v7tISEB4LOWk3sp8DeOlZkCennZIL7NlZ9pO-jr9lYZUIwWgfO1vW_sMAxsRmkSBskfh74UyFQHD8oCJBsNOnVHW6KpXmmeSmkPXnxydNwo7y0003__mC0)
### Mô tả hệ thống con, interface của hệ thống con
Các hệ thống con và giao diện

1. Hệ thống con PayrollController:

Chức năng: Điều khiển quá trình tính lương và gửi lương.

Giao diện:

Phương thức runPayroll(): Thực hiện việc tính toán lương và gọi đến hệ thống ngân hàng để gửi lương.

Mối quan hệ: Có mối quan hệ với hệ thống con IBankSystem thông qua giao diện. Mối quan hệ này cho thấy PayrollController sẽ sử dụng các dịch vụ của hệ thống ngân hàng để thực hiện việc gửi lương.

2. Hệ thống con IBankSystem:

Chức năng :Định nghĩa một giao diện chung cho các hệ thống ngân hàng. Đây không phải là một hệ thống con thực tế mà là một giao diện (interface) mà các hệ thống ngân hàng cụ thể phải tuân thủ.

Giao diện:

Phương thức deposit(Paycheck paycheck, BankInformation bankInfo): Phương thức này cho phép gửi một phiếu lương vào một tài khoản ngân hàng cụ thể.

Mối quan hệ: Là một giao diện, IBankSystem được các hệ thống ngân hàng cụ thể thực hiện.

3. Hệ thống con BankSystem:

Chức năng: Thực hiện các chức năng của một hệ thống ngân hàng, bao gồm việc gửi tiền vào tài khoản. Đây là một hệ thống con thực tế, có thể là một proxy cho một hệ thống ngân hàng bên ngoài hoặc một hệ thống ngân hàng được phát triển nội bộ.

Giao diện:

Phương thức deposit(Paycheck paycheck, BankInformation bankInfo): Thực hiện việc gửi phiếu lương vào tài khoản ngân hàng.

Mối quan hệ:

Thực hiện giao diện IBankSystem: Điều này có nghĩa là BankSystem phải cung cấp một thực hiện cho phương thức deposit().

Liên kết với Paycheck và BankInformation: Cho thấy phương thức deposit() cần thông tin về phiếu lương và thông tin ngân hàng để thực hiện giao dịch.

Các lớp khác

Paycheck: Đại diện cho một phiếu lương, chứa thông tin về số tiền, người nhận, v.v.

BankInformation: Chứa thông tin về tài khoản ngân hàng, như số tài khoản, tên ngân hàng, v.v.

Tóm tắt

Hệ thống con PayrollController: Điều khiển quá trình tính lương và gửi lương.

Hệ thống con BankSystem: Thực hiện việc gửi tiền vào tài khoản ngân hàng.

Giao diện IBankSystem: Định nghĩa giao tiếp giữa hệ thống xử lý lương và hệ thống ngân hàng.

Các lớp Paycheck và BankInformation: Cung cấp dữ liệu cần thiết cho quá trình gửi lương.

## Analysis class to design element map
Ánh xạ các lớp phân tích đến các phần tử thiết kế.
![image](https://github.com/user-attachments/assets/0c419952-9f25-48e1-8027-16cbb84f7a42)
## Design element to owning package map
 Ánh xạ các phần tử thiết kế vào các gói.
![image](https://github.com/user-attachments/assets/aa6b5314-8039-4a35-b079-0b521b45427a)
## Architectural layers and their dependencies
Biểu đồ mô tả các layers trong hệ thống và quan hệ giữa chúng :
![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWf9JObvsS6LnIMgkaa8rbm8GHDlOv2HMfXRPsIau5XJaP2OdbcJcvyMYopcL5cVcfHONAmId5fLb9gSMOwXmIIn9L71C1afXbqjAB4w5IE2pLq5FpuuqUp5Le9j1o6KmEMpw8AwkvN98pKi1XIG0003__mC0)

### Giải thích các layers:
Application:

Đây là lớp giao diện người dùng, nơi khách hàng và nhân viên ngân hàng tương tác với hệ thống.

Business Services:

Lớp này chứa các dịch vụ kinh doanh và logic nghiệp vụ của hệ thống, xử lý các yêu cầu từ lớp Application.

Data Access:

Lớp này chịu trách nhiệm truy cập và thao tác dữ liệu từ lớp Database.

Database:

Lớp này chứa cơ sở dữ liệu, nơi lưu trữ tất cả các thông tin cần thiết của hệ thống.

# Hệ thống con PrintService
## Biểu đồ ngữ cảnh của hệ thống con PrintService
![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bToJc9niK90KMPUYND-NabHVavEQf52DPS24EZhAnIdvgKePEKdAPJaAnI056beSjLoSG4PgKLfYScf2fvWhS6fHMMPG1v47rYXItvoQMugK4CAb66b01C26u5aCTcwOK9SNEWUq4t9By_JjKDpdXNOFyKGAq3UAbOeoqpaGbLaKwEdX-8kD7bTeB5mYt7BE01j0WKm0000__y30000))
### Mô tả hệ thống con, interface của hệ thống con
PrintController:

Lớp này chịu trách nhiệm gửi các công việc in đến dịch vụ in.

IPrintService:

Giao diện này định nghĩa phương thức printDocument(document: Document) mà dịch vụ in phải thực hiện.

PrintService:

Lớp này triển khai giao diện IPrintService và thực hiện phương thức printDocument(document: Document).

Document:

Đối tượng đại diện cho tài liệu sẽ được in.

Quan hệ giữa các lớp:
PrintController sử dụng IPrintService để gửi các công việc in.

PrintService triển khai giao diện IPrintService.

Cả IPrintService và PrintService đều có quan hệ với đối tượng Document.
Send Print Job (Gửi công việc in): Hệ thống bên ngoài có thể tương tác với PrintService để gửi công việc in.

## Analysis class to design element map
Ánh xạ các lớp phân tích đến các phần tử thiết kế.

![image](https://github.com/user-attachments/assets/c56f4d9c-c802-450d-aa70-d87aa499bbcc)
## Design element to owning package map
 Ánh xạ các phần tử thiết kế vào các gói.
 
![image](https://github.com/user-attachments/assets/9e5fa9b4-6b20-47e8-bb1e-1719e0c37c3f)

## Architectural layers and their dependencies
Biểu đồ mô tả các layers trong hệ thống và quan hệ giữa chúng :

![Diagram]( https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWb90KMPUIN1gKLbcSggIGZMN0X14szZa95Qc5jdPAGGKfHQdvfKabcJcvyMYIpeM5EHa9eFb57poqpEJCLH03SOGTqaiILHmJ4vEBIx6a0j8BIhEB2v9pOFfm-ic1LrTEzBSXAa2tGnSheQ9ewl7vnjaENHzA3wjvN98pKi1nGq0003__mC0)

Giải thích các layers:

Presentation:

Đây là lớp giao diện người dùng, nơi người dùng và quản trị viên tương tác với hệ thống PrintService.

Application Logic:

Lớp này chứa logic ứng dụng và xử lý các yêu cầu từ lớp Presentation.

Service:

Lớp này chứa các dịch vụ kinh doanh và logic nghiệp vụ của hệ thống, xử lý các yêu cầu từ lớp Application Logic.

Data Access:

Lớp này chịu trách nhiệm truy cập và thao tác dữ liệu từ lớp Persistence.

Persistence:

Lớp này chứa cơ sở dữ liệu, nơi lưu trữ tất cả các thông tin cần thiết của hệ thống.

# Hệ thống con ProjectManagementDatabase subsystems
## Biểu đồ ngữ cảnh của hệ thống con ProjectManagementDatabase subsystems
![Diagram](https://www.planttext.com/api/plantuml/png/x9J1IiD048RlUOgX9mNRteD8GIyz24AVODniuzhDRBlP14HxzZ6aIF4a8dWoY8U0xv4dy1NCjXjjiKdhtJriDfFvlvaTVlAPlVTYWzeaaVJYaQ0nQenWZ6o48H-OAyb1SsQGGiazpyMXTQRLPHa-HIfV8qxc10sUOynRSEr1kPZ4E8PVQSUAZ5PISktoxEfsOP8Kh_S4Cdy3biyO6BkbHJO7LcGF246HFKC-euLcwYqUWWpNGsGS-gvErSI0wrIKyPyI60GkPm_TmQ-wEx0aLMbzg4vz6YeTeH6Azhz1caSgvGsieLRHZgna7A1fOWdQWUIciJRm_q4uwRhBp4N-GY4OGHiDjLHkuDTIsCSCuYAxixWdaAB8RfDLOfF_s-sZMkFwblfegVEoqYH120Kg26o1PSjroiERJgV61Oqwsutxj3LlmuHMRxiD_KVorEjn2kp_wGi00F__0m00)
### Mô tả hệ thống con, interface của hệ thống con ProjectManagementDatabase

* Hệ thống con ProjectManagementDatabase chịu trách nhiệm quản lý và lưu trữ thông tin liên quan đến các dự án trong một tổ chức. Hệ thống này bao gồm các chức năng chính sau:

Quản lý Dự án:

Tạo mới, cập nhật và xóa các dự án.

Lưu trữ thông tin chi tiết của dự án như tên, mô tả, ngày bắt đầu, ngày kết thúc, và trạng thái dự án.

Quản lý Nhiệm vụ:

Cập nhật các nhiệm vụ liên quan đến dự án.

Phân công nhiệm vụ cho các thành viên nhóm dự án.

Đồng bộ dữ liệu:

Hỗ trợ đồng bộ dữ liệu với các hệ thống bên ngoài để đảm bảo tính nhất quán của thông tin dự án.

* Interface của hệ thống con ProjectManagementDatabase

ProjectManagementController

Vai trò: Lớp này chịu trách nhiệm quản lý các tác vụ của dự án.

Phương thức:

class ProjectManagementController {
    // quản lý các tác vụ của dự án
}

IProjectDatabaseService

Vai trò: Giao diện này định nghĩa các phương thức mà dịch vụ cơ sở dữ liệu phải thực hiện.

Phương thức:

interface IProjectDatabaseService {
    addProject(aProject: Project, intoDatabase: DatabaseInformation)
    removeProject(aProject: Project, fromDatabase: DatabaseInformation)
    updateProject(aProject: Project, inDatabase: DatabaseInformation)
}

ProjectDatabaseService

Vai trò: Lớp này triển khai giao diện IProjectDatabaseService và thực hiện các phương thức quản lý dự án trong cơ sở dữ liệu.

Phương thức:

class ProjectDatabaseService {
    addProject(aProject: Project, intoDatabase: DatabaseInformation)
    removeProject(aProject: Project, fromDatabase: DatabaseInformation)
    updateProject(aProject: Project, inDatabase: DatabaseInformation)
}

Project

Vai trò: Đối tượng đại diện cho dự án.

Thuộc tính:

class Project {
    // thông tin dự án
}

DatabaseInformation

Vai trò: Đối tượng đại diện cho thông tin cơ sở dữ liệu.

Thuộc tính:

class DatabaseInformation {
    // thông tin cơ sở dữ liệu
}

* Quan hệ giữa các lớp:

ProjectManagementController sử dụng IProjectDatabaseService để thực hiện các tác vụ quản lý dự án.

ProjectDatabaseService triển khai giao diện IProjectDatabaseService.

IProjectDatabaseService và ProjectDatabaseService đều có quan hệ với các đối tượng Project và DatabaseInformation.

## Analysis class to design element map
Ánh xạ các lớp phân tích đến các phần tử thiết kế.

![image](https://github.com/user-attachments/assets/55c56d6d-fd69-4132-b6a7-11c28a2d6032)

## Design element to owning package map
 Ánh xạ các phần tử thiết kế vào các gói.
 
 ![image](https://github.com/user-attachments/assets/e60b0849-8057-411a-8df0-a339d64b5d06)

 ## Architectural layers and their dependencies
Biểu đồ mô tả các layers trong hệ thống và quan hệ giữa chúng :

![Diagram](https://www.planttext.com/api/plantuml/png/b5512i903Bpt5Q7t_g2K5ZmgB7WK3p66ijfkooOA8hxCWq_o2xP2GNUnO6x9p2Gpv7b_bABezTGsIOzqn9eXDRuxCEaAtT2sx7I1YZiKJk6Qm52RF6_mmhuem7YMWO5gExSDmQhl6qjl39PTRIbYhDcVBN4q7oz2HSGY4MROYnLbD-bcFK6M5VzvYXdXZb-kftd8dqlpYOMwhwItf6It7n_r0W00__y30000)

Giải thích các layers:

Presentation:

Đây là lớp giao diện người dùng, nơi người quản lý dự án và thành viên nhóm tương tác với hệ thống ProjectManagementDatabase.

Application Logic:

Lớp này chứa logic ứng dụng và xử lý các yêu cầu từ lớp Presentation.

Service:

Lớp này chứa các dịch vụ kinh doanh và logic nghiệp vụ của hệ thống, xử lý các yêu cầu từ lớp Application Logic.

Data Access:

Lớp này chịu trách nhiệm truy cập và thao tác dữ liệu từ lớp Persistence.

Persistence:

Lớp này chứa cơ sở dữ liệu, nơi lưu trữ tất cả các thông tin cần thiết của hệ thống.

