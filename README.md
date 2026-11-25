# Đại đoàn kết toàn dân tộc — Minigame V4

Web trình chiếu HTML/CSS/JS thuần. Mở `docs/index.html` bằng Edge/Chrome. Trang bìa bấm bất kỳ đâu để bắt đầu; không có settings. 30 câu theo thứ tự tài liệu, 4 đội, 30 giây/câu, +100 điểm cho câu đúng. MC nhấn 1–4 để đổi đội ngay, sau đó nhấn A–D hoặc bấm đáp án. Phím Enter hoặc mũi tên phải để bắt đầu/qua câu đã chốt; 1–4 để chọn đội; A–D để trả lời; P để tạm dừng; R để hiện đáp án; F để toàn màn hình. Chơi chung một màn hình, không đồng bộ các thiết bị. Tải lại trang sẽ mất điểm.

## Ảnh bìa
Ảnh tư liệu: Ho Chi Minh with Vietnamese expats in France, 1946 (Wikimedia Commons, tác giả không rõ; Commons đánh dấu public domain).
https://commons.wikimedia.org/wiki/File:Ho_Chi_Minh_with_Vietnamese_expats_in_France,_1946.jpg

Ảnh được tải từ Wikimedia khi có mạng; không nhúng bản sao vì môi trường tạo file không tải được ảnh gốc. Khi không tải được ảnh, web tự dùng bìa đỏ-vàng dạng vector với tiêu đề, toàn bộ game vẫn hoạt động offline. Có thể tải ảnh về `docs/cover.jpg` rồi đổi hằng số `PHOTO` trong `index.html` thành `./cover.jpg` nếu muốn dùng ảnh thật offline.

## Triển khai
- Cloudflare Workers: kết nối GitHub repo; branch `main`, root repo, build command trống, deploy command `npx wrangler deploy`. Đã có `wrangler.jsonc` với assets `./docs`. Chỉnh tên Worker nếu cần. Chưa triển khai lên hosting thật.
- GitHub Pages: Settings > Pages > Deploy from a branch > main > /docs > Save.
- Host tĩnh khác: publish thư mục `docs`, không cần build.

Nếu cập nhật repo đã có, giải nén ZIP vào thư mục cha của repo doan-ket-quiz (ví dụ D:\), đồng ý ghi đè file trùng, `git add .`, `git commit -m "Fix slide minigame V4"`, `git push`. Không ghi đè lịch sử Git.

## QR truy cập
Sau khi deploy, tạo QR từ URL HTTPS công khai của Worker bằng chức năng tạo mã QR của trình duyệt hoặc công cụ QR. Điện thoại quét được link nhưng mỗi thiết bị là một phiên chơi riêng; không đồng bộ điểm hoặc phòng với máy chiếu.

## Cấu hình
Google Doc không quy định số đội. V4 dùng 4 đội mặc định; nếu cần 6, thêm Đội 5 và Đội 6 vào mảng TEAMS trong index.html (phím 5–6 được hỗ trợ).

## Kiểm thử
Đáp án và lời giải kế thừa bản V3 (suy ra từ Google Doc không có bảng đáp án riêng); nhóm nên rà soát trước khi trình chiếu.
