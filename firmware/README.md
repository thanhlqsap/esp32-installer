# Thư mục chứa file Firmware (.bin) cho Web Installer

Đặt file firmware của bạn vào thư mục này với tên trùng khớp trong file `manifest.json`.

---

## 💡 Cách tạo file .bin gộp duy nhất (Merged Binary) bằng `esptool.py`
Để nạp online mượt mà nhất ở offset `0x0`, bạn nên gộp Bootloader, Partitions, BootApp0 và App thành 1 file duy nhất:

```bash
# Ví dụ lệnh gộp file cho chip ESP32 tiêu chuẩn:
esptool.py --chip esp32 merge_bin -o esp32_firmware.bin --flash_mode dio --flash_freq 40m --flash_size 4MB 0x1000 bootloader.bin 0x8000 partitions.bin 0xe000 boot_app0.bin 0x10000 firmware.bin
```

Sau khi có file `esp32_firmware.bin`, chỉ cần copy vào thư mục `firmware/` này là xong!
