<div align="center">

# 📚 Studocu Helper

**Tiện ích mở rộng giúp làm sạch giao diện Studocu và xuất tài liệu ra PDF để đọc offline.**

![Version](https://img.shields.io/badge/version-1.0-blue)
![Manifest](https://img.shields.io/badge/Manifest-V3-green)
![Browser](https://img.shields.io/badge/Chrome%20%7C%20Edge%20%7C%20C%E1%BB%91c%20C%E1%BB%91c-supported-orange)
![Install](https://img.shields.io/badge/c%C3%A0i%20%C4%91%E1%BA%B7t-th%E1%BB%A7%20c%C3%B4ng-lightgrey)

</div>

---

## 📖 Giới thiệu

Studocu Helper là tiện ích mở rộng (Chrome, Edge, Cốc Cốc, Manifest V3) giúp làm sạch giao diện xem tài liệu trên Studocu và xuất tài liệu ra PDF để đọc offline.

> **Phiên bản:** v1.0 · **Cài đặt:** thủ công (chưa có trên Store)

## ✨ Tính năng

### 1. Làm sạch trang (mờ / watermark)

- Ẩn lớp phủ mờ, banner và popup che nội dung.
- Bật lại việc chọn và sao chép văn bản.
- Nút **"Gỡ mờ và watermark"** xoá cookie của Studocu rồi tải lại trang.

> ⚠️ **Lưu ý:** Xoá cookie sẽ **đăng xuất tài khoản Studocu** của bạn trên trình duyệt.

### 2. Tạo file PDF

- Dựng lại từng trang tài liệu thành khung chuẩn gồm lớp ảnh nền và lớp chữ.
- Khổ giấy in khớp đúng kích thước trang, nên hạn chế trang trống và lệch hình/chữ.
- Khi xong sẽ mở hộp thoại in của trình duyệt, chọn **Save as PDF** để lưu.

## 🚀 Cài đặt

1. Tải mã nguồn (clone hoặc tải `.zip` rồi giải nén).
2. Mở `chrome://extensions/` (hoặc `edge://extensions/`).
3. Bật **Developer mode**.
4. Chọn **Load unpacked** và trỏ tới thư mục dự án.

## 🛠️ Cách sử dụng

1. Mở tài liệu trên Studocu.
2. Nếu trang bị mờ hoặc có watermark, mở extension và bấm **1. Gỡ mờ và watermark**.
3. **Tự cuộn chuột xuống cuối tài liệu** để trang tải đủ tất cả các trang (extension không tự cuộn).
4. Mở extension, bấm **2. Tạo file PDF**, xác nhận số trang tìm thấy.
5. Ở hộp thoại in, đặt như bảng dưới:

| Tuỳ chọn | Giá trị |
|---|---|
| **Destination** | Save as PDF |
| **Margins** | None |
| **Scale** | 100% (không chọn Fit to page) |
| **Background graphics** | Bật |

## 🩺 Xử lý sự cố

| Hiện tượng | Cách xử lý |
|---|---|
| "Không tìm thấy trang nào" | Cuộn xuống cuối tài liệu để tải hết nội dung rồi thử lại |
| Còn trang trống / lệch | Kiểm tra Margins = None, Scale = 100%, rồi tải lại trang và thử lại |
| Thiếu ảnh | Đợi ảnh tải xong (cuộn qua hết tài liệu) rồi bấm lại |
| Bị đăng xuất | Do nút Gỡ mờ và watermark xoá cookie Studocu, hãy đăng nhập lại |
| Hỏng sau khi Studocu đổi giao diện | Công cụ phụ thuộc vào cấu trúc HTML của Studocu, cần cập nhật selector |

## 📁 Cấu trúc dự án

| File | Vai trò |
|---|---|
| `manifest.json` | Khai báo extension, quyền, content script |
| `popup.html` / `popup.css` / `popup.js` | Giao diện popup và logic (xoá cookie, dựng trang PDF) |
| `custom_style.css` | CSS tự chèn vào trang Studocu để ẩn overlay |
| `viewer_styles.css` | CSS cho khung xem sạch và bố cục in |

## ⚠️ Hạn chế

- Phụ thuộc vào markup của Studocu (`data-page-index`, `.pc`, ...), nên có thể hỏng khi trang đổi.
- Khổ giấy PDF lấy theo trang đầu tiên, tài liệu có nhiều khổ trang khác nhau có thể chưa chuẩn.
- Tài liệu rất dài có thể xử lý chậm.

---

<div align="center">

Built with ❤ by **Anthalia**

</div>