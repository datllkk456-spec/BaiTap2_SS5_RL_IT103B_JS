# Tài Liệu Báo Cáo: Khắc Phục Lỗi Bất Biến Chuỗi (String Immutability) Trong Mã Phiếu Kiosk

## 1. Phân Tích Lỗi Logic Kỹ Thuật

### Lỗi Không Lưu Kết Quả Thao Tác Chuỗi (String Immutability Violation)
* **Vị trí lỗi:** 
  ```javascript
  rawTicketCode.trim();
  rawTicketCode.toUpperCase();

startsWith("MED-") trả về false do chuỗi gốc bắt đầu bằng khoảng trắng và là chữ thường.

slice(4, 7) cắt ra "med" thay vì mã khoa "CARD" do khoảng trắng thừa làm lệch hoàn toàn vị trí index.

includes("-UT") trả về false do đuôi chưa chuyển thành chữ hoa ("-ut").

Chuỗi in phiếu displayCode bị dính khoảng trắng thừa ở hai đầu.