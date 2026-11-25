# Mã nguồn PinkBook Manager

## Repository nguồn
Mã nguồn ứng dụng đầy đủ được lưu tại:
https://github.com/daohailinh10-code/tao-web-quan-li

Nhánh tham chiếu: `fix/pinkbook-local-database`.

> Thư mục `src/` trong bản nộp này ghi nhận nguồn mã và hướng dẫn tái lập. Mã nguồn gốc hiện vẫn nằm trong repository riêng nêu trên; chưa được sao chép vật lý toàn bộ vào thư mục nộp.

## Cấu trúc mã nguồn chính
- `frontend/src/app.jsx`: điều hướng ứng dụng, đăng nhập và phân quyền giao diện.
- `frontend/src/book_workspace.jsx`: quản lý danh mục sách.
- `frontend/src/sales_workspace.jsx`: bán hàng tại quầy.
- `frontend/src/quan_li_khach_hang.jsx`: quản lý khách hàng.
- `frontend/src/staff_workspace.jsx`: lịch làm và chấm công.
- `frontend/src/thong_ke.jsx`: thống kê.
- `server/app.js`: Express API, xác thực và middleware.
- `server/service.js`: nghiệp vụ và truy cập dữ liệu.
- `server/db.js`: kết nối PGlite/PostgreSQL.
- `server/schema.sql`: cấu trúc cơ sở dữ liệu.
- `server/security.js`: kiểm tra dữ liệu, mật khẩu và quyền.
- `tests/runtime.test.js`: kiểm thử tự động.

## Yêu cầu
- Node.js phiên bản `>=22.12.0`.
- npm.
- Không bắt buộc cài PostgreSQL nếu dùng PGlite mặc định.
- Nếu dùng PostgreSQL ngoài, cấu hình `DATABASE_URL` trong môi trường chạy.

## Cài đặt và chạy
Tại thư mục gốc repository mã nguồn:
```bash
npm install
npm test
npm run dev
```

Để chạy theo chế độ start:
```bash
npm start
```

Lưu ý: cấu hình môi trường phải được thiết lập theo `.env.example`; không commit file `.env` hoặc thông tin đăng nhập. Dữ liệu ứng dụng mặc định được lưu trong thư mục `data/` và không nên đưa dữ liệu thực lên repository công khai.

## Kiểm tra
Lệnh `npm test` chạy kiểm thử runtime và build frontend. Khi bàn giao, cần đính kèm log thực tế của lần chạy trên commit cuối.
