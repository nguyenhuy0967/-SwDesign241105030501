# Lab 5
Thiết kế các hệ thống con trong hệ thống Payroll System
## 1. Security Subsystem:
- Hệ thống này đảm bảo an toàn cho hệ thống Payroll:
   + Xác thực người dùng (login).
   + Phân quyền truy cập theo vai trò.
   + Quản lý các phiên làm việc và kiểm soát truy cập cho từng chức năng.
- Thành phần chính:
  + `LoginForm:` Giao diện để người dùng nhập thông tin đăng nhập.
  + `AuthenticationService:` Xác thực thông tin đăng nhập từ cơ sở dữ liệu người dùng.
  + `AccessControl:` Quản lý quyền truy cập dựa trên vai trò.
  + `SessionManager:` Quản lý các phiên làm việc của người dùng.
  + `UserDatabase:` Lưu trữ thông tin người dùng.
    
![](https://www.planttext.com/api/plantuml/png/X9C_JiCm5CRtdCBgL2HwWGXLXI8GWag8mW5Snqgi9i_1Te8gn80Oc3a0WWuiI9KOM6W6XbJSmoVW2jX9q_z0bYJFdt_Vb_VYx-op9HKMAeb2H_OP8C4bTKY8fKGdt6Tmm4M4hXrahqHI0JYYBkegmS0lgx7HNd7XBLTbqekOgc-vAENCSswSANGtKG45nGXMZ4ENYfGHMXcaE6GULhGjg6T5E9JrLTFjDKFZiSTvI36K5BFCV3WpbMBpqQ9m6d4UXn0gPPk34ZoiOf20aluf5H4p90vrixHWZubDli5y1ktIOby70_QfgAX5dwTBwy6ABXKw2bwbakLzNJYpkZ2SVQnm3ykgYmtBbYxgu7YdocnbpHBlKsNVrlfgqBPkqVF1DnhDNoRcejgXpaOCgI1_1nyfy-zC7YPtvX42FHx5DMVpHejSIcr8vo8Pe5IFNs0H1_xNcyuU6VBo3_3_uYrFqKRBXu0kau7ERWtIqib_cLQ6PY37WSwUp0VgyP2ZE63vAw0mVuvGodHsJsfEoupA7fmV0000__y30000)

## 2. Payroll Subsystem:
- Hệ thống này chịu trách nhiệm quản lý và xử lý toàn bộ nghiệp vụ tính lương:
  + Lấy dữ liệu chấm công và hợp đồng nhân viên để tính toán lương.
  + Xử lý thanh toán qua ngân hàng hoặc in phiếu lương.
  + Lưu trữ lịch sử thanh toán.
- Thành phần chính:
  + `PayrollController:` Điều phối các hoạt động tính lương.
  + `PayrollDBManager:` Lưu trữ thông tin thanh toán trong cơ sở dữ liệu.
  + `SalaryCalculator:` Tính toán lương dựa trên các điều kiện hợp đồng và chấm công.
  + `Paycheck:` Lưu thông tin phiếu lương cho từng nhân viên.

![](https://www.planttext.com/api/plantuml/png/T5BBQi905DtdAowk8YZTXo9ItGWLYWfTJvDB4fpC3VEGXj9rlyD5bwMkTU52y3_o1Vs59eunZQcpo8HpppdtpfdvsUs7IZEfJS8TjOm5I5Be-9mf1KyiayJvY8GkTvJmva2vKaa-AdMkkrqFLXG7jXQYGCaq5aK_Gd_fOf9ooX0dWGTpBMCH5logwhmxpMRZXoaJBBpqwgSMdw5FCb0UJ5bwRsrwbSRM1hQ_OYjiuAuyRLwJVJMpRafkpLnJwi7dZ3EPZHZt3MUQBY7vPmGjmOt8IFLCSec5QK3cXMCFIf1diu9LOTtgvyfbH4aIAnMJS1NZg6eF-Q_wRx2dgAkvscUpE4l82DtiNeG_FhcNtzAo_IJw_K7xxZpeF1utvcuXJGQl9jz-QWZotJVmEDzzcCuDdrQKXS_Yy2KYq7HO2-37pN4jmblooqbBMRvT4wHHd6_tfXOEKGJbK_y5003__mC0)

## 3. Timecard Subsystem:
- Quản lý dữ liệu thẻ chấm công cho nhân viên:
   + Nhập thông tin giờ làm việc, mã phí và ngày làm.
   + Lưu trữ dữ liệu thẻ chấm công trong cơ sở dữ liệu.
   + Xác thực thông tin chấm công trước khi lưu.
- Thành phần chính:
   + `TimecardForm`: Giao diện cho nhân viên nhập dữ liệu thẻ chấm công.
   + `TimecardController`: Xử lý logic nghiệp vụ liên quan đến thẻ chấm công.
   + `TimecardDBManager`: Lưu trữ và truy xuất dữ liệu thẻ chấm công.
   + `Timecard`: Đại diện cho dữ liệu thẻ chấm công.

![](https://www.planttext.com/api/plantuml/png/j5F1IWCn4BtdAuQUsaD_O95Isg8Kwic2vtGpRaEJZ2JPYeWVqRCd4Oz23vww1mzA_sE_m5ymIvjgw-91COUGpBnvxp6Jl1SlNUUvzRbMpCsa0KiEMQguSp2M6bDknJ5P3JSCgeNwKj4rub0aSEQjDDacVaLsDk0U4wZsJMnAkNNd8O41B2YVg6tY0h5F0lSPN3xHqZTR2Sn92dRB3bpqoNXBIg6DNkPSIH7K8g8PBZpP5GIc7f52RhO2VFu3j5vqq3lbXcSxpRRV9bm28-dyKGHsDXeP-XXnpU-zQjLN_SPPR48qT3YGVnbKSB7tADhjJjry4cYSbCMJ13zzVJPPy6Z2iLmLa8RzKKDQXHkiflGhusVp0-5elSp_o5VHZClLFO4kYpi9RukoM0IJwsLPF0JQY6kmBXfH_OWF0000__y30000)

## 4. Integration Subsystem:
- Hệ thống này quản lý việc tích hợp với các hệ thống bên ngoài:
   + Kết nối với ngân hàng để thực hiện chuyển khoản.
   + Tích hợp với dịch vụ in để in phiếu lương.
   + Hỗ trợ kết nối API của bên thứ ba.
- Thành phần chính:
   + `IntegrationManager`: Điều phối kết nối với các hệ thống bên ngoài.
   + `BankSystem`: Thực hiện chuyển khoản ngân hàng.
   + `PrintService`: Xử lý in phiếu lương.
   + `ExternalAPI`: Giao diện cho các hệ thống thứ ba.

![](https://www.planttext.com/api/plantuml/png/Z9A_JiCm4CRtFCMfKv3e2sH0fH987IXLMudvOX-9gMC7swce43C34pCB0Z4my0GP6FeaVG9U0Rj_89LQX0VxVFBz_7rdVzMV7UlGkAgGaPq81KPRYfX4Qw6d76K6dT3g31LcPE0sWZ0iAJxMNLIJcAF310OuCrhA8J5j-442NQqbeMgU7XZXUUO_1M9zCLq8bnyFUZ6Meey59J1odf8TmWfodbuHSxvwgWMFxgArxg1hDBEEYerUPr3PIpAdbU8sHiPqfLo_Ab8olqmiGZO1hgjKKaFJ3tXfOKHcAXXjq6N8UJSi9pQ9gIYbdX7r-1_SRRKdDxuh2gNtsMplaAuhiYxsOQb5gD_ZVPKEl1tlrMuVDTkHG6iy_s0vv8lwjOJfeduIeBBvYu9y_goorZx6blET5Bwe7tpARzxy--q5DTtkvFZu7foV7rMsNDyXnLRKyNq8V_GR003__mC0)

## 5. Project Management Subsystem:
- Hệ thống này quản lý thông tin về dự án và mã phí:
   + Duy trì danh sách dự án và các mã phí liên quan.
   + Hỗ trợ cung cấp thông tin mã phí cho thẻ chấm công.
- Thành phần chính:
   + `ProjectController`: Xử lý logic liên quan đến dự án và mã phí.
   + `ProjectDBManager`: Quản lý thông tin dự án trong cơ sở dữ liệu.
   + `FeeCodeManager`: Quản lý danh sách mã phí.

![](https://www.planttext.com/api/plantuml/png/T5B1IiD04BtlLmmvHJ1u3n9A6uH2Ae9Vi6J7k9hiXfrjeOWV8-9HqAizU0Zu7_q2Vy74R6AJs1oMvBqtcVTczdltEIFBZLqNEQDxgS1eGfRcd0YkZBx3r2wqiaRdEHfuOD0y6Lh7aNyIGYB9dZiWwXKNY0ijaFooPPOYX6jhfCgwalOhOezis32UhxZYMTylS7-WOwqSCDyknR_T7D_gYM_G0PsuLzJQZPRYpv4BCV9puwA5iEAbYt4ANPpH06AqNERakw83M-tB97utvKcI0Np92nmIjQ7KoD9AhOR4xu9ZRcjzSxOWAd40rHwcsmw2QBgI4Bna__6oFKk-tjOWzhjtg9wKTwHyDB-k68hg6ShRwjLZizf8S_b-0000__y30000)
