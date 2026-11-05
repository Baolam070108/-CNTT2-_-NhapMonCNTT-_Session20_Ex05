# BÀI TỔNG HỢP – THIẾT KẾ HỆ THỐNG ĐĂNG NHẬP CRYPTO WALLET

## 1. Vấn đề

Ứng dụng ví tiền điện tử cần bảo mật cao, tránh hacker đánh cắp tài khoản và tài sản ngay cả khi đã biết mật khẩu.

## 2. Yêu cầu

- Sử dụng xác thực nhiều yếu tố MFA.
- Áp dụng thuật toán TOTP để tạo mã OTP.
- Thiết kế 3 lớp bảo vệ tài khoản.
- Đảm bảo lấy được mã OTP khi không có Internet.

## 3. Cách làm

### a. Thiết kế 3 lớp bảo vệ

- Lớp 1: Nhập mật khẩu tài khoản.
- Lớp 2: Nhập mã OTP 6 số từ ứng dụng Authenticator.
- Lớp 3: Xác nhận bằng vân tay hoặc Face ID trên thiết bị.

### b. Sơ đồ hoạt động

### b. Sơ đồ hoạt động

[Người dùng] → [Nhập mật khẩu] → [Nhập mã OTP] → [Xác nhận Face ID / Vân tay] → [Đăng nhập thành công] → [Truy cập ví và giao dịch]

Nếu hacker chỉ biết mật khẩu thì vẫn không thể đăng nhập nếu thiếu mã OTP và xác thực sinh trắc học.


### c. Xử lý khi không có Internet

- TOTP tạo mã dựa trên khóa bí mật và thời gian trên thiết bị.
- Người dùng vẫn mở ứng dụng Authenticator để lấy mã OTP dù không có Internet hoặc sóng điện thoại.
- Khi có mạng trở lại, người dùng có thể gửi yêu cầu xác thực và thực hiện giao dịch.
