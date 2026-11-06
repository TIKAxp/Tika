# Slayer Tika – Discord Bio Page

Trang bio một file (HTML + CSS + JS thuần), chạy thẳng trên GitHub Pages, không cần build.

## Tính năng
- Luxury Dark + Glassmorphism, aurora nền, hạt sáng, ánh sáng theo chuột
- Card nghiêng 3D theo chuột, viền sáng bám con trỏ
- Avatar viền gradient xoay, trạng thái Discord live (Lanyard), hiện Spotify / game đang chơi
- Badge hỗ trợ emoji thường và emoji Discord tùy chỉnh (kể cả động)
- Social links có icon và màu thương hiệu, thêm/xóa tùy ý
- Lượt xem, vị trí, giờ địa phương, trình phát nhạc
- Responsive desktop / tablet / mobile

## Cấu trúc
```
index.html        giao diện + CONFIG (sửa ở đầu thẻ <script>)
assets/           avatar, favicon, video/ảnh nền, nhạc
.nojekyll         file ẩn, giúp GitHub Pages phục vụ file nguyên bản
```

## File trong assets/

| File | Định dạng | Khuyến nghị | Dung lượng |
|---|---|---|---|
| avatar | PNG, JPG, WebP, GIF, SVG | Vuông 256–512px | ≤ 500KB |
| favicon | PNG, ICO, SVG, JPG, WebP, GIF hoặc emoji | PNG vuông 64–128px | ≤ 50KB |
| video nền | MP4 (H.264), WebM | 720p, 10–20 giây, bỏ tiếng, loop mượt | ≤ 15MB |
| ảnh nền | JPG, WebP, PNG, GIF | 1920×1080 | ≤ 1MB |
| nhạc | MP3, OGG, M4A, WAV | MP3 128kbps | ≤ 8MB |

Quy tắc tên file: viết thường, không dấu, không khoảng trắng; tên trong CONFIG phải khớp 100%.
Không dùng video MOV / MKV / AVI / HEVC vì nhiều trình duyệt không phát.

```js
avatar: "assets/avatar.png",
favicon: "assets/favicon.png",      // hoặc emoji: "🔥"
background: { type: "video", src: "assets/bg.mp4" },   // ảnh: type "image", src "assets/bg.jpg"
music: { src: "assets/song.mp3", title: "Tên bài hát" },
```

## Cấu hình (CONFIG)

| Key | Ý nghĩa |
|---|---|
| `name`, `username`, `bio` | Tên, @username (bấm để copy), bio nhiều dòng (`\n`) |
| `verified`, `badges` | Tích xanh; badge emoji hoặc `<a:ten:ID>` của Discord |
| `avatar`, `favicon` | Ảnh trên card; icon tab (tách riêng) |
| `background`, `music` | Nền (video/ảnh), nhạc |
| `accent`, `accent2` | Màu chủ đạo, màu phụ |
| `links` | Danh sách liên kết |
| `discordId`, `lanyardWs` | Trạng thái Discord live |
| `tilt`, `tiltMax` | Bật/tắt và độ mạnh nghiêng 3D (0–25 độ) |
| `respectReducedMotion` | `true` = tắt hiệu ứng khi hệ điều hành bật "giảm chuyển động" |
| `counterKey` | Tên riêng cho bộ đếm lượt xem |

Thêm link: thêm một dòng vào `links`, ví dụ
`{ label: "Telegram", url: "https://t.me/yourname", icon: "telegram" }`.
Icon hỗ trợ: `discord github tiktok youtube instagram facebook telegram link`.
Muốn nút bấm là copy thay vì mở link: thêm `copy: "nội dung cần copy"`.

## Trạng thái Discord live
1. Điền `discordId` (ID dạng số).
2. Vào server https://discord.gg/lanyard để bot Lanyard thấy bạn.
3. Hoặc tự host Lanyard bằng bot riêng, rồi đổi `lanyardWs`.
Nếu `avatar` vẫn là link dicebear mặc định, ảnh card sẽ tự đổi thành avatar Discord thật.

## Đưa lên GitHub Pages
1. Tạo repo mới (đặt tên `username.github.io` để có link gốc).
2. Upload NỘI DUNG thư mục này: `index.html`, `assets/`, `.nojekyll`.
   Upload qua web tối đa 25MB mỗi file; file lớn hơn dùng git.
3. Settings → Pages → Deploy from a branch → `main` / `(root)` → Save.
4. Chờ khoảng 1 phút rồi mở link. Thấy bản cũ thì nhấn Ctrl+F5.

## Xử lý lỗi
- Ảnh / video / nhạc không hiện: F12 → Network, file nào 404 là sai tên hoặc sai đường dẫn.
- Nhạc không tự phát: bình thường, người xem phải bấm màn hình mở đầu trước.
- Video không chạy: đổi sang MP4 H.264.
- Favicon chưa đổi: Ctrl+F5 hoặc mở tab ẩn danh.
- Card không nghiêng: kiểm tra `tilt: true`, `tiltMax` lớn hơn 0; trên điện thoại hiệu ứng này tắt.
