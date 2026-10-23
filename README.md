# Demo sửa trang Thanh toán: Thiết bị mầm non Việt Mỹ

Bản dựng lại phần nội dung trang https://website-demo-02.thcmedia.vn/checkout/ (chụp ngày 23/10/2026) bằng đúng markup, class và CSS của theme `thcmedia-atlas`, rồi áp 7 ý review của mục **Checkout** trong tab "Review tổng thể website" (dòng 224–230).

**Xem demo:** https://lanvi-commits.github.io/demo-thanh-toan-thiet-bi-mam-non-viet-my/

Thanh trên cùng có công tắc **Hiện tại (live) ↔ Đề xuất**, 4 kịch bản thử (form trống · bấm đặt hàng khi trống · SĐT 9 số, chưa chọn phường · điền đủ + hoá đơn) và khung **Desktop / Mobile 390**. Bản "Hiện tại" khớp live từng px. Form chạy thật trong trình duyệt nhưng **không gửi dữ liệu đi đâu**.

## 7 thay đổi

| # | Dòng sheet | Chỗ | Đề xuất |
|---|---|---|---|
| 1 | 224 | Ô bắt buộc | Chặn đủ 6 ô có dấu * (live chỉ chặn 3: Họ tên, Địa chỉ, Email). SĐT phải đủ 10 số, bắt đầu bằng 0 |
| 2 | 225 | Báo lỗi | Hộp lỗi thành 1 hàng phía trên 2 cột (live chen thành cột thứ 3, ép cột form 842 → 471px). Ô lỗi viền đỏ + chữ lỗi ngay dưới. Lỗi dùng đúng chữ trên form ("Họ và tên", không phải "Mục Tên") |
| 3 | 226 | Tóm tắt đơn | Badge "7 ngày đổi trả" theo chính sách (live: 30 ngày). Tên SP tối đa 2 dòng + dòng "Phân loại" + "Ghi chú" |
| 4 | 227 | Hoá đơn, ghi chú | Ô tick "Xuất hoá đơn công ty" mở 3 ô: Tên đơn vị · Mã số thuế · Địa chỉ xuất hoá đơn. Thêm "Ghi chú đơn hàng" |
| 5 | 228 | Phương thức thanh toán | Bọc `<fieldset>` + `<legend>`, đổi icon người → icon ví |
| 6 | 229 | Tỉnh / Thành phố | Dùng chung danh mục của form báo giá (34 mục). Live ghi sai "Thành phố Bắc Ninh / Quảng Ninh / Đồng Nai" |
| 7 | 230 | Hộp lưu ý | Bỏ dòng "Chuyển khoản Ngân hàng" bị dư |

Cuối trang demo có **ghi chú cho DEV**: đoạn PHP (hook WooCommerce), markup template, danh mục tỉnh, JS cho `checkout-custom.js` và khối CSS dán cuối `woocommerce-checkout.css`.

## Ghi chú

- Phường/xã chép từ provinces.open-api.vn/api/v2 (API site đang dùng), nhúng sẵn trong file.
- Ghi chú SP "Giao kèm hướng dẫn lắp ráp" và thông tin trong kịch bản điền sẵn là dữ liệu mẫu.
- File được sinh bằng `build.py` (thư mục làm việc trên máy), không sửa tay `index.html`.
