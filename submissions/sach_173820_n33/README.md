# PinkBook Manager – Hệ thống quản lý cửa hàng sách

## 1. Giới thiệu sản phẩm
PinkBook Manager là ứng dụng web hỗ trợ số hóa hoạt động của cửa hàng sách. Hệ thống tập trung các nghiệp vụ quản lý danh mục sách, giá bán, tồn kho, bán hàng tại quầy, khách hàng thành viên, nhân viên và báo cáo. Mục tiêu là giảm thao tác thủ công, hạn chế sai lệch dữ liệu và giúp người quản lý theo dõi tình hình kinh doanh trên một nền tảng thống nhất.

### Đối tượng sử dụng
- Chủ cửa hàng/quản lý: quản lý sách, kho, nhân sự, cấu hình và xem báo cáo.
- Nhân viên: tra cứu sách, thực hiện bán hàng và các thao tác được phân quyền.
- Khách hàng: được lưu hồ sơ thành viên để phục vụ giao dịch và tích điểm; không trực tiếp truy cập trang quản trị.

### Công nghệ
- Frontend: React, Vite, JavaScript, CSS.
- Backend: Node.js, Express, REST API.
- Cơ sở dữ liệu: PGlite khi chạy cục bộ hoặc PostgreSQL qua biến môi trường `DATABASE_URL`.
- Kiểm thử: Node.js test runner và Vite build.

## 2. Phạm vi MVP
### Chức năng nằm trong MVP
1. Đăng nhập, đăng xuất và phân quyền quản lý/nhân viên.
2. Quản lý danh mục sách, thể loại, giá bán và tìm kiếm.
3. Theo dõi tồn kho và ghi nhận nghiệp vụ nhập sách.
4. Bán hàng tại quầy, tạo hóa đơn và cập nhật dữ liệu giao dịch.
5. Quản lý thông tin khách hàng và hỗ trợ thành viên/tích điểm.
6. Quản lý tài khoản nhân viên và các thông tin ca làm/chấm công.
7. Thống kê doanh thu, tồn kho, khách hàng và nhân viên.

### Ngoài phạm vi MVP
- Đồng bộ với hệ thống kế toán hoặc ERP bên ngoài.
- Tích hợp cổng thanh toán trực tuyến và vận chuyển bên thứ ba.
- Ứng dụng di động native.
- Dự báo nhu cầu nhập sách bằng mô hình học máy.

## 3. Kiến trúc và tổ chức mã nguồn
Ứng dụng được tổ chức theo mô hình frontend–backend:
- Giao diện React gửi yêu cầu HTTP đến các REST API.
- Backend Express xác thực phiên, kiểm tra quyền và thực thi nghiệp vụ.
- Lớp truy cập dữ liệu kết nối PGlite/PostgreSQL.
- Schema SQL định nghĩa các bảng dữ liệu nghiệp vụ.

Mã nguồn được đặt trong `src/`; tài liệu yêu cầu, kiến trúc và kiểm thử trong `report/`; dàn ý trình bày trong `slides/`.

## 4. Hướng dẫn cài đặt và chạy
Xem hướng dẫn đầy đủ tại `src/README.md`. Mã nguồn gốc và nhánh tham chiếu:
https://github.com/daohailinh10-code/tao-web-quan-li/tree/fix/pinkbook-local-database

Tại thư mục `src/`, cài đặt và chạy:
```bash
npm ci
npm test
npm run dev
```

Không commit file `.env`, mật khẩu, token, cơ sở dữ liệu cá nhân hoặc dữ liệu người dùng thật. Chỉ sử dụng dữ liệu demo/synthetic khi kiểm thử.

## 5. Kiểm thử và tiêu chí nghiệm thu
Báo cáo kiểm thử chi tiết nằm ở `report/TEST_REPORT.md`; ma trận truy vết ở `report/TRACEABILITY.md`. Nhóm cần chạy lại `npm test` trên commit bàn giao cuối, lưu log thực tế và kiểm tra các luồng đăng nhập, quản lý sách, bán hàng, cập nhật kho, khách hàng và báo cáo.

## 6. Hướng phát triển Tuần 11–15
- **Tuần 11:** rà soát yêu cầu, hoàn thiện luồng nghiệp vụ còn thiếu và chuẩn hóa dữ liệu demo.
- **Tuần 12:** bổ sung kiểm thử API/UI, kiểm tra phân quyền và các trường hợp dữ liệu biên.
- **Tuần 13:** hoàn thiện báo cáo kiến trúc, sơ đồ C4, ma trận truy vết và hướng dẫn cài đặt.
- **Tuần 14:** kiểm thử tích hợp, sửa lỗi, tối ưu giao diện và rà soát bảo mật.
- **Tuần 15:** đóng gói phiên bản bàn giao, chạy kiểm thử hồi quy, hoàn thiện slide và chuẩn bị demo.

## 7. Nhóm & tuân thủ
- **Lớp:** 173820.
- **Nhóm:** N33 (`173820_n33`).
- **Thành viên (MSSV):**
  - `202414217`
  - `202413991`

Nhóm cam kết không đưa mật khẩu, token, khóa API, file môi trường hoặc dữ liệu cá nhân thật vào repository. Các dữ liệu dùng trong demo/kiểm thử phải là dữ liệu giả lập. Nội dung và kết quả trong báo cáo cần được đối chiếu với phiên bản mã nguồn thực tế trước khi nghiệm thu.

## 8. Lưu ý về mã case study
Đề tài PinkBook Manager là hệ thống quản lý cửa hàng sách. Slug `sach` hiện **không nằm trong danh sách slug được validator của repository nhận bài cho phép**. Không tự ý thay slug bằng một case study khác (ví dụ `hoang_mai_toan` hoặc `may_day`) vì như vậy sẽ khai báo sai đề tài. Nhóm cần hỏi giảng viên/TA cách nộp đề tài tự chọn hoặc xin mã case study hợp lệ trước khi mở PR.
