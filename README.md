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
- Tiến độ học lưu trong trình duyệt của từng thiết bị (LocalStorage), theo từng tên miền. Đổi tên miền hoặc đổi thiết bị thì tiến độ bắt đầu lại.
- Muốn chuyển tiến độ: ở Kho từ bấm "Sao lưu JSON" trên thiết bị cũ, rồi "Khôi phục JSON" trên thiết bị mới.
- Không dùng cơ sở dữ liệu, không cần API key, không có biến môi trường.
