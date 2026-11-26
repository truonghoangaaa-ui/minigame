# Đại đoàn kết toàn dân tộc — Minigame V6.1

Bản cập nhật cho repo đã triển khai V5. Giải nén ZIP vào `D:\` (thư mục gốc trong ZIP là `doan-ket-quiz`), ghi đè các file trùng. ZIP chủ ý không chứa `wrangler.jsonc` và `.git` để giữ tên Worker, cấu hình deploy và lịch sử Git đang dùng. Mở `docs/index.html` bằng Chrome/Edge để thử.

V6.1: đồng bộ câu 16 với Google Doc mới nhất (bỏ nhãn liên kết chương ở đầu câu); bỏ tự focus tiêu đề câu hỏi.

## Luật chơi

- 6 đội; 22 câu theo thứ tự cố định, 12 câu đầu giữ nguyên từ V5, câu 13–22 theo Google Doc vận dụng cao.
- Câu 1–12: 15 giây; câu 13–22: 30 giây.
- Đáp án sai bị gạch bỏ và không thể chọn lại. Không hiện đáp án đúng khi mới sai 1–2 lần. Đồng hồ tiếp tục chạy; MC có thể đổi đội và chọn đáp án còn lại.
- Đáp án đúng: +100 điểm cho đội được chọn, hiện lời giải, MC chuyển câu tiếp theo. Sai đủ 3 phương án: không cộng điểm, tự chuyển câu sau 0,75 giây. Hết giờ: hiện đáp án, không điểm, MC chuyển câu. Nút hiện đáp án (R) không cộng điểm.
- Phím 1–6 chọn đội, A–D trả lời, P tạm dừng/tiếp tục, R hiện đáp án, Enter hoặc mũi tên phải sang câu đã chốt, F toàn màn hình.
- Một máy điều khiển, không đồng bộ điện thoại; tải lại trang sẽ mất điểm.

## Nguồn câu hỏi

- Câu 1–12: Google Doc minigame gốc, dữ liệu giữ từ V5: https://docs.google.com/document/d/1Nt30_mBLqYlRq1RlWOZIukjo6o_H1Xi6vAU2rIFfpVc/edit
- Câu 13–22: https://docs.google.com/document/d/1ouwQZCoIYW0l64tSJXnBQ-it3PTt16hLxeKiawD-ls8/edit
- Hai tài liệu không có bảng đáp án riêng trong phần văn bản đọc được. Đáp án và giải thích do người tạo web suy ra, nên nhóm kiểm tra trước buổi trình chiếu. Khóa 13–22: B, A, C, B, D, A, B, D, B, A.
- Ảnh bìa: Wikimedia Commons, Ho Chi Minh with Vietnamese expats in France, 1946. Ảnh tải trực tuyến như V5; nếu không có mạng, bìa dự phòng vẫn hoạt động. https://commons.wikimedia.org/wiki/File:Ho_Chi_Minh_with_Vietnamese_expats_in_France,_1946.jpg

## Cập nhật GitHub

```cmd
cd /d D:\doan-ket-quiz && git add docs/index.html README.md && git commit -m "V6.1 - Sync question 16" && git push
```

Cloudflare tự deploy nếu đã kết nối repo và bật tự động triển khai; URL công khai không thay đổi nếu giữ Worker hiện tại. Không cần tạo repo mới.
