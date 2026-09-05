# Dự Án 2: ESP32 External Web Installer (Sẵn Sàng Publish Online)

Trang web này cho phép bạn xuất bản (publish) lên mạng internet để người dùng ở bất cứ đâu có thể cắm ESP32 vào máy tính và bấm nút nạp trực tiếp file `.bin` từ server của bạn.

---

## 📁 Cấu trúc thư mục
```
external/
├── index.html        # Trang giao diện Web Installer chính
├── style.css         # Giao diện responsive, đẹp mắt
├── manifest.json     # Cấu hình nạp của ESP Web Tools
├── firmware/         # Thư mục chứa file .bin trên server
│   ├── README.md
│   └── esp32_firmware.bin # (File firmware của bạn đặt tại đây)
└── README.md
```

---

## 🚀 Cách đưa trang web lên Online (Miễn phí & Có sẵn HTTPS)

Do **Web Serial API** yêu cầu kết nối **HTTPS**, bạn nên sử dụng một trong các nền tảng miễn phí sau:

### Cách 1: Sử dụng GitHub Pages (Đơn giản nhất & Khuyên dùng)
1. Đẩy toàn bộ thư mục `external/` này lên một kho lưu trữ (Repository) trên **GitHub**.
2. Trên GitHub, vào **Settings** -> **Pages**.
3. Tại mục **Build and deployment**, chọn Branch `main` (hoặc `master`), thư mục `/ (root)`.
4. Bấm **Save**. 
5. Sau 1-2 phút, bạn sẽ nhận được đường link web có dạng: `https://<ten-user>.github.io/<ten-repo>/`.

---

### Cách 2: Sử dụng Vercel hoặc Netlify
1. Truy cập [vercel.com](https://vercel.com) hoặc [netlify.com](https://netlify.com).
2. Kéo thả toàn bộ thư mục `external/` vào bảng điều khiển (Deploy Dropzone).
3. Hệ thống sẽ tự động cấp phát domain có sẵn chứng chỉ HTTPS cho bạn ngay lập tức.

---

## ⚙️ Cập nhật Firmware mới trong tương lai
Khi bạn viết code mới và muốn cập nhật:
1. Xuất file `.bin` mới.
2. Ghi đè file `.bin` mới vào thư mục `firmware/esp32_firmware.bin`.
3. Tăng phiên bản trong file `manifest.json` (ví dụ từ `"1.0.0"` lên `"1.0.1"`).
4. Đẩy lên GitHub/Vercel. Người dùng chỉ cần F5 lại trang web là có thể nạp ngay bản mới nhất!
