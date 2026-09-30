# Studocu Helper

Tiện ích mở rộng (Chrome/Edge/Cốc Cốc, Manifest V3) giúp làm sạch giao diện xem tài liệu trên Studocu và xuất tài liệu ra PDF để đọc offline.

> **Phiên bản:** v1.0 · **Cài đặt:** thủ công (chưa có trên Store)

## Tính năng

### 1. Làm sạch trang (mờ / watermark)
- Ẩn lớp phủ mờ, banner và popup che nội dung.
- Bật lại việc chọn và sao chép văn bản.
- Nút **"Gỡ mờ và watermark"** xoá cookie của Studocu rồi tải lại trang.
  > ⚠️ Xoá cookie sẽ **đăng xuất tài khoản Studocu** của bạn trên trình duyệt.

### 2. Tạo file PDF
- Dựng lại từng trang tài liệu thành khung chuẩn gồm lớp ảnh nền và lớp chữ.
- Khổ giấy in khớp đúng kích thước trang, nên hạn chế trang trống và lệch hình/chữ.
- Khi xong sẽ mở hộp thoại in của trình duyệt, chọn **Save as PDF** để lưu.

## Cài đặt

1. Tải mã nguồn (clone hoặc tải `.zip` rồi giải nén).
2. Mở `chrome://extensions/` (hoặc `edge://extensions/`).
3. Bật **Developer mode**.
4. Chọn **Load unpacked** và trỏ tới thư mục dự án.

## Cách sử dụng

1. Mở tài liệu trên Studocu.
2. Nếu trang bị mờ hoặc có watermark, mở extension và bấm **1. Gỡ mờ và watermark**.
3. **Tự cuộn chuột xuống cuối tài liệu** để trang tải đủ tất cả các trang (extension không tự cuộn).
4. Mở extension, bấm **2. Tạo file PDF**, xác nhận số trang tìm thấy.
5. Ở hộp thoại in, đặt:
   - **Destination:** Save as PDF
   - **Margins:** None
   - **Scale:** 100% (không chọn Fit to page)
   - **Background graphics:** bật

## Xử lý sự cố

| Hiện tượng | Cách xử lý |
|---|---|
| "Không tìm thấy trang nào" | Cuộn xuống cuối tài liệu để tải hết nội dung rồi thử lại |
| Còn trang trống / lệch | Kiểm tra Margins = None, Scale = 100%, rồi tải lại trang và thử lại |
| Thiếu ảnh | Đợi ảnh tải xong (cuộn qua hết tài liệu) rồi bấm lại |
| Bị đăng xuất | Do nút Gỡ mờ và watermark xoá cookie Studocu, hãy đăng nhập lại |
| Hỏng sau khi Studocu đổi giao diện | Công cụ phụ thuộc vào cấu trúc HTML của Studocu, cần cập nhật selector |

## Cấu trúc dự án

| File | Vai trò |
|---|---|
| `manifest.json` | Khai báo extension, quyền, content script |
| `popup.html` / `popup.css` / `popup.js` | Giao diện popup và logic (xoá cookie, dựng trang PDF) |
| `custom_style.css` | CSS tự chèn vào trang Studocu để ẩn overlay |
| `viewer_styles.css` | CSS cho khung xem sạch và bố cục in |

## Hạn chế

- Phụ thuộc vào markup của Studocu (`data-page-index`, `.pc`, ...), nên có thể hỏng khi trang đổi.
- Khổ giấy PDF lấy theo trang đầu tiên, tài liệu có nhiều khổ trang khác nhau có thể chưa chuẩn.
- Tài liệu rất dài có thể xử lý chậm.

## Lưu ý (Disclaimer)

Dự án chỉ phục vụ học tập và nghiên cứu cá nhân. Việc vượt qua giới hạn xem tài liệu có thể vi phạm điều khoản sử dụng của Studocu, và tài liệu trên đó có thể thuộc bản quyền của tác giả. Bạn tự chịu trách nhiệm khi sử dụng, hãy tôn trọng bản quyền và không phát tán lại nội dung.

## Video demo

https://github.com/user-attachments/assets/0f98de3a-cdbb-464d-8209-b9953b0721ee

## Stars ⭐

<img width="2748" height="1986" alt="star-history-20251211 (1)" src="https://github.com/user-attachments/assets/f0fd47b7-d196-477d-a0d6-4311fdcac177" />

---

Built with ❤ by Anthalia
