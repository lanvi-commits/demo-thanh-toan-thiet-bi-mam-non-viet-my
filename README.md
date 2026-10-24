# Demo trang Thanh toán — Thiết bị mầm non Việt Mỹ

Trang Thanh toán của site đang dựng (website-demo-02.thcmedia.vn/checkout/) sau khi áp 7 ý review mục **Checkout**, tab "Review tổng thể website" (dòng 224–230):

1. Bắt buộc đủ 6 ô có dấu *: thêm Số điện thoại, Tỉnh / Thành phố, Phường / Xã; SĐT phải đủ 10 số, bắt đầu bằng 0 (dòng 224)
2. Hộp lỗi thành 1 hàng phía trên form (không còn chen thành cột thứ 3); ô lỗi viền đỏ + chữ lỗi ngay dưới; lỗi dùng đúng chữ trên form: "Họ và tên", "Địa chỉ chi tiết", "Email liên hệ" (dòng 225)
3. Tóm tắt đơn: badge "7 ngày đổi trả" theo chính sách; tên SP tối đa 2 dòng + dòng "Phân loại" và "Ghi chú" (dòng 226)
4. Ô tick "Xuất hoá đơn công ty" mở 3 ô: Tên đơn vị · Mã số thuế · Địa chỉ xuất hoá đơn; thêm "Ghi chú đơn hàng" (dòng 227)
5. Phương thức thanh toán bọc `<fieldset>` + `<legend>`, đổi icon người → icon ví (dòng 228)
6. Danh mục Tỉnh / Thành phố dùng chung với form báo giá (34 mục, đúng tên) (dòng 229)
7. Bỏ dòng "Chuyển khoản Ngân hàng" bị dư trong hộp lưu ý (dòng 230)

Header, breadcrumb, footer, thanh liên hệ nổi giữ nguyên như site. Phần mới chỉ gồm `<div class="custom-checkout-page">`, `<style id="vmx-change">` (dán cuối `woocommerce-checkout.css`) và `<script id="vmx-page-js">`. Bấm "Xác nhận đặt hàng" khi để trống để xem cách báo lỗi.

- Xem trực tiếp: https://lanvi-commits.github.io/demo-thanh-toan-thiet-bi-mam-non-viet-my/
- Trang mẫu, không phải site thật (có `noindex`). **Form không gửi đi đâu:** đã gỡ `checkout.js` của WooCommerce, WooCommerce Blocks và Contact Form 7; `<script id="vmx-demo-guard">` chỉ dành cho demo, không đưa lên site.
- Trong file demo, `page.js` tự kiểm ô bắt buộc / SĐT / mã số thuế để mô phỏng phản hồi máy chủ. Trên site, phần kiểm này phải làm ở PHP (hook `woocommerce_after_checkout_validation`), JS chỉ đọc lỗi máy chủ trả về để đánh dấu từng ô.
- Ghi chú SP "Giao kèm hướng dẫn lắp ráp" là câu mẫu.

`index.html` là bản build từ `Design UX-UI/brands/viet-my/nguyen-lieu/2026-10-23_thanh-toan-trang-build/` (sửa `section.html` / `change.css` / `page.js` → chạy `build.py` → commit + push). Đừng sửa tay `index.html`.
