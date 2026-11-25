# PinkBook Manager – Hệ thống quản lý cửa hàng sách

## 1. Thông tin nhóm
- **Đề tài:** Xây dựng hệ thống quản lý cửa hàng sách PinkBook Manager.
- **Lớp / nhóm:** 173820 – N33.
- **Mã nhóm:** `173820_n33`.
- **Thành viên (MSSV):**
  - `202414217`
  - `202413991`

## 2. Tóm tắt bài làm
PinkBook Manager là ứng dụng web hỗ trợ quản lý hoạt động của một cửa hàng sách. Hệ thống tập trung vào các nghiệp vụ: quản lý danh mục và thông tin sách; theo dõi tồn kho; bán hàng tại quầy; quản lý khách hàng và điểm thành viên; quản lý nhân viên, ca làm và chấm công; tổng hợp số liệu bán hàng và kho.

Ứng dụng được xây dựng theo mô hình frontend–backend. Giao diện sử dụng React và Vite; backend sử dụng Node.js và Express; dữ liệu được lưu bằng PostgreSQL tương thích qua PGlite khi chạy cục bộ hoặc PostgreSQL thông qua biến môi trường `DATABASE_URL`.

## 3. Chức năng chính
1. **Quản lý sách:** thêm, cập nhật, tìm kiếm sách theo mã/tên/tác giả; phân loại theo thể loại; cập nhật giá và theo dõi số lượng tồn.
2. **Bán hàng:** tìm sách, thêm vào giỏ, điều chỉnh số lượng, lập hóa đơn và thanh toán.
3. **Khách hàng:** lưu hồ sơ, tra cứu theo tên/số điện thoại/email; hỗ trợ khách thành viên và tích điểm theo giao dịch.
4. **Nhân viên:** quản lý tài khoản, duyệt đăng ký, phân quyền, xếp ca và ghi nhận thời gian làm việc.
5. **Thống kê:** tổng hợp doanh thu, tình hình tồn kho, khách hàng và nhân sự.
6. **Bảo mật và dữ liệu:** xác thực bằng số điện thoại/mật khẩu, phiên đăng nhập, kiểm tra quyền theo vai trò, ghi nhận nhật ký và sao lưu/khôi phục dữ liệu.

## 4. Kiến trúc và công nghệ
- Frontend: React, Vite, JavaScript, CSS.
- Backend: Node.js, Express.
- Cơ sở dữ liệu: PGlite (mặc định cục bộ) hoặc PostgreSQL.
- Kiểm thử: Node.js test runner và kiểm tra build Vite.
- Giao tiếp: REST API qua các endpoint `/api/*`.

## 5. Cấu trúc thư mục nộp
- `report/`: đặc tả yêu cầu, mô tả kiến trúc, kế hoạch và kết quả kiểm thử.
- `src/`: hướng dẫn truy xuất mã nguồn và cách cài đặt/chạy ứng dụng.
- `slides/`: dàn ý nội dung thuyết trình.

## 6. Mã nguồn và cách chạy
Mã nguồn ứng dụng gốc được quản lý tại:
https://github.com/daohailinh10-code/tao-web-quan-li

Nhánh mã nguồn tham chiếu: `fix/pinkbook-local-database`.

Các bước chạy được mô tả trong `src/README.md`. Không đưa tệp `.env`, mật khẩu, dữ liệu người dùng thật hoặc dữ liệu cơ sở dữ liệu cá nhân vào bản nộp.

## 7. Kiểm thử
Báo cáo kiểm thử được tổng hợp tại `report/TEST_REPORT.md`. Kết quả được ghi theo tài liệu kiểm thử hiện có của dự án; nhóm cần chạy lại trên môi trường nộp cuối cùng trước khi nghiệm thu.

## 8. Lưu ý về mã case study
Đề tài PinkBook Manager là đề tài quản lý cửa hàng sách của nhóm. Mã slug `sach` và mã case study `N/A` hiện là thông tin nhóm tự khai báo, chưa phải mã case study chính thức trong danh sách slug của repository nhận bài. Cần xác nhận với giảng viên/TA trước khi mở PR để tránh CI từ chối cấu trúc.
