<p align="center">
  <img src="https://github.com/huutq88/appota-browser/releases/download/v0.2.0/appota-mark.png" width="96" alt="Appota">
</p>

<h1 align="center">Appota Browser</h1>

<p align="center">
  Trình duyệt viết bằng Rust, có giao diện và cách hiển thị trang như Google Chrome. Chặn sẵn quảng cáo và trình theo dõi, dùng ít RAM và CPU hơn Chrome.
</p>

<p align="center">
  <a href="https://github.com/huutq88/appota-browser/releases/latest"><b>Tải về cho macOS (Apple Silicon)</b></a>
</p>

---

## Tính năng

- **Giao diện và trang web như Chrome.** Appota dùng Chromium 156, cùng công cụ với Google Chrome, kể cả giao diện:
  - dải thẻ, thanh địa chỉ, menu;
  - trang Thẻ mới, dấu trang, lịch sử, tải xuống, cài đặt.

  Toàn bộ giao diện bằng tiếng Việt, và các trang như Google, YouTube chạy bình thường.
- **Viết bằng Rust.** Toàn bộ mã của Appota viết bằng Rust:
  - khởi chạy và quản lý profile;
  - cấu hình Chromium;
  - chặn quảng cáo;
  - thương hiệu.

  Chromium được nhúng qua CEF (Chromium Embedded Framework).
- **Chặn quảng cáo và trình theo dõi có sẵn,** dùng bộ máy [adblock-rust](https://github.com/brave/adblock-rust) của Brave:
  - **Bộ lọc:** EasyList, EasyPrivacy, uBlock Origin và ABPVN cho các trang Việt Nam.
  - **Cập nhật:** bộ lọc tự cập nhật mỗi 4 ngày.
  - **Bật/tắt:** nhấp chuột phải vào trang để tắt cho riêng trang đó, hoặc tắt cho toàn trình duyệt.
- **Gọn nhẹ:** các dịch vụ chạy ngầm không cần thiết của Chrome được tắt sẵn.
- **Trang Thẻ mới mang logo Appota,** kèm sẵn lối tắt tới Appota (appota.com) và GoG (gog.zone), có biểu tượng của từng trang.
- **Hồ sơ cục bộ:** Menu ⋮ > Hồ sơ > Thêm sẽ tạo ngay một hồ sơ mới trên máy, không cần tài khoản Google. Mỗi hồ sơ có dấu trang, lịch sử và cookie riêng.
- **Tự kiểm tra bản mới** mỗi ngày một lần, và hỏi bạn trước khi tải bản cập nhật.
- **Chuyển dữ liệu từ bản 0.2:** dấu trang được nhập tự động ở lần mở đầu tiên.
- **Có chữ ký số:** ứng dụng được ký bằng Developer ID và đã được Apple công chứng (notarized).

## Cài đặt

**Yêu cầu:** máy Mac chip Apple (M1 trở lên), macOS 12 trở lên.

1. Tải tệp `Appota-Browser-<phiên bản>-mac-arm64.dmg` từ [trang Releases](https://github.com/huutq88/appota-browser/releases/latest).
2. Mở tệp `.dmg`, kéo **Appota Browser** vào thư mục **Applications**.
3. Mở Appota Browser từ Launchpad hoặc thư mục Applications.

Khi có bản mới, Appota sẽ hỏi bạn có muốn tải về không. Cài bản mới bằng cách kéo vào Applications và chọn **Thay thế**; dấu trang, lịch sử và cài đặt được giữ nguyên.

## Hiệu năng so với Google Chrome

**Bộ nhớ và CPU khi mở 6 trang web, sau 30 giây:**

| | Appota Browser 0.3 | Google Chrome | Chênh lệch |
|---|---|---|---|
| RAM | **908 MB** | 1.719 MB | ít hơn 47% |
| CPU | **6,9%** | 32,6% | ít hơn 79% |
| Số tiến trình | **11** | 37 | |

**Thời gian tải trang** (đến sự kiện `load`, profile mới, mỗi trang đo một lần):

| Trang | Appota Browser | Google Chrome |
|---|---|---|
| VnExpress | **2,0 giây** | 5,4 giây |
| Dân trí | **1,9 giây** | 2,4 giây |
| YouTube | **2,0 giây** | 5,2 giây |
| Wikipedia (Vietnam) | **1,1 giây** | 3,1 giây |
| GitHub | 2,0 giây | **1,2 giây** |

Cách đo:
- **Máy và ngày đo:** MacBook Pro M4 Max, 64 GB RAM, macOS 26, ngày 13/11/2026.
- **Cấu hình:** mỗi trình duyệt dùng profile mới với thiết lập mặc định. Chrome không cài thêm tiện ích.
- **Sáu trang đo RAM và CPU:**
  - example.com
  - Hacker News
  - Wikipedia (Vietnam, Hanoi)
  - VnExpress
  - GitHub
- **Chỉ số RAM:** "memory footprint" của macOS, tức con số Activity Monitor hiển thị, cộng cho mọi tiến trình của trình duyệt.

Thời gian tải trang phụ thuộc mạng và quảng cáo tại thời điểm đo, nên chỉ nên xem là số tham khảo. Phần lớn chênh lệch đến từ việc chặn quảng cáo: ví dụ VnExpress trên Chrome có 16 khung quảng cáo nhúng (iframe), trên Appota còn 1.

## Hạn chế hiện tại

- **Hệ điều hành:** mới có bản cho macOS chip Apple. Chưa có bản cho Mac chip Intel, Windows và Linux.
- **Đăng nhập tài khoản Google và đồng bộ:** không có, vì Google chỉ cấp quyền này cho Chrome chính hãng. Hồ sơ chỉ lưu trên máy. Đây cũng là lý do thanh công cụ không có nút avatar như Chrome.
- **Cập nhật:** Appota báo khi có bản mới, nhưng bạn vẫn tự cài bản mới bằng file `.dmg`.
- **Lần mở đầu tiên:** bộ lọc quảng cáo mất khoảng 5 giây để tải về. Các trang mở trong lúc đó có thể còn quảng cáo hoặc để lại khoảng trống ở chỗ khung quảng cáo.

## Quyền riêng tư

- Appota Browser không thu thập dữ liệu sử dụng và không gửi thống kê về Appota.
- Lịch sử, dấu trang, mật khẩu và cài đặt chỉ lưu trên máy bạn, trong thư mục `~/Library/Application Support/Appota Browser`.
- Danh sách bộ lọc quảng cáo được tải từ nguồn công khai, mỗi 4 ngày một lần.
- Kiểm tra bản mới chỉ gọi API công khai của GitHub Releases, không gửi thông tin nào về bạn.

## Phiên bản trước

Bản 0.2.0 dùng vỏ Electron, vẫn có ở [trang Releases](https://github.com/huutq88/appota-browser/releases/tag/v0.2.0). Từ bản 0.3.0, Appota được viết lại bằng Rust.

## Phản hồi

Gửi lỗi và góp ý ở mục [Issues](https://github.com/huutq88/appota-browser/issues).

---

© 2026 Appota. Mã nguồn không được công bố trong kho này. Appota Browser dùng Chromium (giấy phép BSD) và adblock-rust (giấy phép MPL-2.0).
