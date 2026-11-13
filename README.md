<p align="center">
  <img src="https://github.com/huutq88/appota-browser/releases/download/v0.2.0/appota-mark.png" width="96" alt="Appota">
</p>

<h1 align="center">Appota Browser</h1>

<p align="center">
  Trình duyệt có giao diện như Google Chrome, chặn sẵn quảng cáo và trình theo dõi, dùng ít RAM hơn Chrome.
</p>

<p align="center">
  <a href="https://github.com/huutq88/appota-browser/releases/latest"><b>Tải về cho macOS (Apple Silicon)</b></a>
</p>

---

## Tính năng

- **Hiển thị trang giống hệt Chrome.** Appota dùng Chromium, cùng công cụ hiển thị với Google Chrome, nên các trang web chạy như trên Chrome, kể cả Google.
- **Chặn quảng cáo và trình theo dõi có sẵn,** không cần cài tiện ích. Trình duyệt dùng các bộ lọc EasyList, EasyPrivacy và uBlock Origin, cùng bộ lọc ABPVN cho các trang Việt Nam. Bạn có thể tắt trong Cài đặt > Hiệu suất.
- **Tiết kiệm bộ nhớ:**
  - Thẻ không dùng trong 5 phút sẽ được tạm dừng để giải phóng RAM.
  - Khi quay lại, thẻ tự tải lại đúng trang bạn đang xem.
- **Giao diện quen thuộc kiểu Chrome:**
  - Thẻ trên thanh tiêu đề, thanh địa chỉ có gợi ý tìm kiếm.
  - Dấu trang, lịch sử, trang Thẻ mới với lối tắt.
  - Giao diện sáng và tối, toàn bộ bằng tiếng Việt.
- **Các thao tác như Chrome:**
  - Tìm trong trang, phóng to/thu nhỏ, in trang, lưu trang.
  - Tải tệp xuống và quản lý tệp đã tải.
  - Mở liên kết trong thẻ mới, menu chuột phải, xem nguồn trang.
  - Công cụ cho nhà phát triển.
- **Hỏi trước khi cấp quyền:** camera, micro, vị trí, thông báo, mở ứng dụng ngoài.
- **Chế độ siêu nhẹ (thử nghiệm):** hiển thị trang bằng công cụ Obscura (Rust), dùng rất ít RAM. Nhiều trang sẽ hiển thị chưa đúng như Chrome. Bật trong Cài đặt > Hiệu suất.

## Cài đặt

**Yêu cầu:** máy Mac chip Apple (M1 trở lên), macOS 11 trở lên.

1. Tải tệp `Appota-Browser-<phiên bản>-mac-arm64.dmg` từ [trang Releases](https://github.com/huutq88/appota-browser/releases/latest).
2. Mở tệp `.dmg`, kéo **Appota Browser** vào thư mục **Applications**.
3. Mở Appota Browser lần đầu: bản này chưa được Apple công chứng, nên macOS sẽ chặn ở lần mở đầu tiên. Hãy:
   1. Mở **Cài đặt hệ thống > Quyền riêng tư và bảo mật**.
   2. Kéo xuống phần **Bảo mật**, bấm **Vẫn mở**.
   3. Xác nhận **Mở**.

   Nếu macOS báo ứng dụng "bị hỏng", chạy lệnh sau trong Terminal rồi mở lại:

   ```bash
   xattr -dr com.apple.quarantine "/Applications/Appota Browser.app"
   ```

Từ lần thứ hai trở đi, ứng dụng mở bình thường.

## Hiệu năng so với Google Chrome

| Đo lường | Appota Browser 0.2.0 | Google Chrome | Chênh lệch |
|---|---|---|---|
| RAM khi mở 1 thẻ trống | **378 MB** | 1.126 MB | ít hơn 66% |
| RAM khi mở 6 trang web, sau 30 giây | **659 MB** | 1.719 MB | ít hơn 62% |
| RAM khi mở 6 trang web, đã tắt chặn quảng cáo | **1.275 MB** | 1.719 MB | ít hơn 26% |

Cách đo:
- **Máy và ngày đo:** MacBook Pro M4 Max, 64 GB RAM, macOS 26, ngày 13/11/2026.
- **Cấu hình:** mỗi trình duyệt dùng profile mới với thiết lập mặc định. Chrome không cài thêm tiện ích.
- **Sáu trang:**
  - example.com
  - Hacker News
  - Wikipedia (Vietnam, Hanoi)
  - VnExpress
  - GitHub
- **Chỉ số RAM:** "memory footprint" của macOS, tức con số Activity Monitor hiển thị, cộng cho mọi tiến trình của trình duyệt.

Kết quả thay đổi theo trang web và quảng cáo tại thời điểm đo. Mức tiết kiệm lớn nhất đến từ việc chặn quảng cáo và trình theo dõi: trên các trang báo nhiều quảng cáo, chúng chiếm phần lớn bộ nhớ và CPU.

## Hạn chế hiện tại

- **Hệ điều hành:** mới có bản cho macOS chip Apple. Chưa có bản cho Mac chip Intel, Windows và Linux.
- **Chữ ký số:** chưa có chữ ký của Apple Developer, nên lần mở đầu cần thao tác như hướng dẫn ở trên.
- **Tính năng Chrome còn thiếu:**
  - đồng bộ tài khoản;
  - tiện ích mở rộng;
  - mở lại các thẻ của phiên trước;
  - tự động cập nhật.

  Để cập nhật, tải bản mới ở trang Releases.
- **Thanh tìm trong trang:** khi mở, thanh này đẩy nội dung trang xuống một chút, thay vì nằm đè lên trang như Chrome.

## Quyền riêng tư

- Appota Browser không thu thập dữ liệu sử dụng và không gửi thống kê về Appota.
- Gợi ý tìm kiếm khi gõ vào thanh địa chỉ được lấy từ Google, giống Chrome.
- Danh sách bộ lọc quảng cáo được tải từ nguồn công khai, mỗi vài ngày một lần.
- Lịch sử, dấu trang và cài đặt chỉ lưu trên máy bạn.

## Phản hồi

Gửi lỗi và góp ý ở mục [Issues](https://github.com/huutq88/appota-browser/issues).

---

© 2026 Appota. Mã nguồn không được công bố trong kho này.
