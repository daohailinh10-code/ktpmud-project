# PinkBook Manager – Hệ thống quản lý cửa hàng sách

## 1. Thông tin nhóm
- **Đề tài:** Xây dựng hệ thống quản lý cửa hàng sách PinkBook Manager.
- **Lớp / nhóm:** 173820 – N33.
- **Mã nhóm:** `173820_n33`.
- **Thành viên (MSSV):** `202414217`, `202413991`.

## 2. Tóm tắt bài làm
PinkBook Manager là ứng dụng web hỗ trợ quản lý danh mục sách, tồn kho, bán hàng tại quầy, khách hàng và điểm thành viên, nhân viên, ca làm, chấm công và thống kê kinh doanh.

## 3. Công nghệ và kiến trúc
- Frontend: React, Vite, JavaScript, CSS.
- Backend: Node.js, Express, REST API.
- Cơ sở dữ liệu: PGlite cục bộ hoặc PostgreSQL qua `DATABASE_URL`.
- Kiểm thử: Node.js test runner và Vite build.
- Kiến trúc: frontend–backend, lớp API, lớp nghiệp vụ, lớp truy cập dữ liệu và cơ sở dữ liệu.

## 4. Các chức năng
1. Quản lý danh mục sách, thể loại, giá và tồn kho.
2. Bán hàng tại quầy, tạo hóa đơn và thanh toán.
3. Quản lý khách hàng, tra cứu hồ sơ và tích điểm thành viên.
4. Quản lý tài khoản nhân viên, phân quyền, xếp ca và chấm công.
5. Thống kê doanh thu, kho, khách hàng và nhân viên.
6. Xác thực, nhật ký thao tác và sao lưu/khôi phục dữ liệu.

## 5. Cấu trúc thư mục
- `report/`: SRS, mô tả kiến trúc, báo cáo kiểm thử.
- `src/`: mã nguồn ứng dụng đã sao chép từ repository PinkBook Manager, kèm hướng dẫn chạy.
- `slides/`: dàn ý 10 slide thuyết trình.

## 6. Cài đặt
Xem `src/README.md`. Mã nguồn gốc: https://github.com/daohailinh10-code/tao-web-quan-li (nhánh `fix/pinkbook-local-database`). Không đưa file môi trường, mật khẩu, dữ liệu người dùng thật hoặc cơ sở dữ liệu cá nhân vào bản nộp.

## 7. Kiểm thử
Xem `report/TEST_REPORT.md`. Kết quả lịch sử chỉ là tham chiếu; nhóm cần chạy lại `npm test` trên đúng commit bàn giao cuối cùng.

## 8. Lưu ý về quy định case study
Slug `sach` và mã case study `N/A` hiện là thông tin nhóm tự khai báo, chưa nằm trong danh sách slug hợp lệ của repository nhận bài. Cần xin giảng viên/TA xác nhận mã case study và slug trước khi mở PR; CI hiện tại sẽ từ chối slug `sach`.
