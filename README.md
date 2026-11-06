# Discord Bio Page

Trang bio một file, chạy được trên GitHub Pages.

## Cấu trúc
```
index.html      # toàn bộ giao diện + CONFIG (sửa ở đầu thẻ <script>)
assets/         # avatar, video nền, nhạc (xem assets/HUONG-DAN.txt)
.nojekyll       # báo GitHub Pages phục vụ file nguyên bản
```

## Sửa thông tin
Mở `index.html`, tìm `const CONFIG`. Đổi tên, username, bio, links, màu (`accent`, `accent2`)...

## Trạng thái Discord live
Điền `discordId`, rồi vào server https://discord.gg/lanyard (hoặc tự host Lanyard và đổi `lanyardWs`).

## Đưa lên GitHub Pages
1. Tạo repo mới (tên `username.github.io` để có link gốc).
2. Upload toàn bộ nội dung thư mục này (kể cả `assets` và `.nojekyll`).
3. Settings > Pages > Source: Deploy from a branch > `main` / `(root)` > Save.
4. Chờ ~1 phút, mở `https://username.github.io`.
