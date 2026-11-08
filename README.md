# Offshore English Garden

Website học tiếng Anh cá nhân (Bản quyền © 2026 Đoàn Linh). Một trang tĩnh, không cần build, không cần Node.js.

## Cấu trúc
- `index.html`: toàn bộ website (giao diện, bài học, flashcard, từ vựng, lưu tiến độ bằng LocalStorage)
- `vercel.json`: cấu hình triển khai
- `*.csv`: từ vựng bổ sung, nhập ở mục Kho từ, nút "Nhập CSV" (không bắt buộc)

## 1. Chạy trên máy tính
Cách đơn giản nhất: bấm đúp `index.html` để mở bằng Chrome.
Hoặc chạy máy chủ cục bộ (cần Python): `python -m http.server 8000` rồi mở http://localhost:8000

## 2. Đưa lên GitHub
1. Tạo tài khoản và một repository mới (ví dụ `offshore-english-garden`) trên github.com, để trống (không thêm README).
2. Mở Terminal trong thư mục dự án và chạy:
```
git init
git add .
git commit -m "First version"
git branch -M main
git remote add origin https://github.com/TEN-CUA-BAN/offshore-english-garden.git
git push -u origin main
```

## 3. Triển khai trên Vercel
1. Vào vercel.com, đăng nhập bằng tài khoản GitHub.
2. Chọn "Add New..." rồi "Project", chọn repository vừa tạo, bấm Import.
3. Framework Preset: chọn **Other**. Để trống Build Command và Output Directory.
4. Bấm Deploy. Sau vài chục giây bạn có link dạng `https://ten-du-an.vercel.app`.
5. Mỗi lần sửa code và `git push`, Vercel tự triển khai lại.

Cách khác không cần GitHub: cài `npm i -g vercel`, chạy `vercel` trong thư mục dự án và làm theo hướng dẫn.

## Lưu ý về dữ liệu
- Tiến độ học vẫn được lưu trong trình duyệt (LocalStorage) và được đồng bộ lên Supabase, nên điện thoại và máy tính dùng chung dữ liệu, không cần đăng nhập.
- Cách hoạt động: mỗi lần học, web tự gửi tiến độ lên Supabase; mở lại web hoặc quay lại tab thì tải bản mới nhất về. Bản có thời điểm lưu mới hơn sẽ được giữ.
- Cài đặt một lần: chạy file `supabase.sql` trong Supabase > SQL Editor (file này không đưa lên GitHub).
- Mã đồng bộ `SB_CODE` nằm trong `index.html`; ai có mã này mới đọc/ghi được tiến độ. Export HTML đã được loại bỏ mã này.
- Nút "Đồng bộ ngay" ở mục Cài đặt để đồng bộ thủ công. Sao lưu/Khôi phục JSON vẫn dùng được.

## Giao diện mới (v3)
- Menu bên phải (thu gọn được; trên điện thoại là nút ☰): Trang chủ, Kho từ vựng, Luyện tập, Kiểm tra, Tiến trình học, Cài đặt. Các tab cũ nằm trong thanh chip phía trên mỗi mục.
- 3 trái tim: sai 1 câu mất 1 tim; hết tim thì hiện modal cứu hộ (trả lời 1 câu để hồi 1 tim, quay lại đúng câu đang làm).
- Kho từ vựng: thêm/sửa/xóa, tìm kiếm, lọc, sắp xếp, phân trang, Import Excel (có xem trước, kiểm tra trùng), tải file Excel mẫu, Export Excel. Cần mạng để tải thư viện ExcelJS từ cdnjs.
- Sao lưu/Khôi phục JSON nằm trong Cài đặt.
