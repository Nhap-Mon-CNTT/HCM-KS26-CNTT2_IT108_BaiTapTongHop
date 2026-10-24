# Yêu cầu
## Phần 1: Hoàn thiện SRS bằng Heading Styles và Auto TOC
- Thực hiện các yêu cầu trong file word : [SRS_ThuVien.docx](SRS_ThuVien.docx)
- File chụp lại kết quả đã đổi trang: [ket_qua.png](ket_qua.png)
---
## Phần 2: Chuẩn hóa dữ liệu và AutoFilter
- 1/

|Lỗi|Vị trí (hàng)|Quy tắc bị vi phạm|
|:---|:---|:---|
|1|Hàng 1|Không merge ô|
|2|Hàng 5|Không được có hàng trống trong bảng|
|3|Hàng 6|Không được tính tổng trong vùng data|

- 2/ Thực hiện trong file: [PhieuMuon_ThuVien.xlsx](PhieuMuon_ThuVien.xlsx)
- 3/ 

Ví dụ cho 1 record: Như hàng 3 nó sẽ là một record bởi vì nó chứa thông tin đầy đủ cho một cá thể bao gồm MSSV, họ tên, mã sách, ngày mượn, tình trạng

Ví dụ cho 1 field: Như cột A chỉ chứa duy nhất một loại thông tin dữ liệu đó chính là mã số sinh viên của sinh viên thôi chứ không chứa loại dữ liệu khác

- 4/ Mô tả cách bật AutoFilter

**Cách 1:**

*Bước 1*: Chọn mục Data trên thanh công cụ 

*Bước 2*: Chọn Filter (hình chiếc phễu) trong vùng sort & filter

**Cách 2**: 

Chọn vào một ô bất kỳ trong bảng và bấm tổ hợp phím là Ctrl+Shift+L

**Kết quả lọc ra sinh viên đang có tình trạng quá hạn**: [ket_qua_loc.png](ket_qua_loc.png)

---

## Phần 3: Nối dữ liệu bằng VLOOKUP

- 1 + 3: Thực hiện trong file: [PhieuMuon_ThuVien.xlsx](PhieuMuon_ThuVien.xlsx)

- 2/ Nó hiện lỗi là `#N/A`. Lỗi này xuất hiện là do khi hệ thống tìm tên sách cho mã sách S099 thì không tìm thấy bất kỳ tên sách nào trong bảng DanhMucSach.

---

## Phần 4: Slide báo cáo tiến độ

- 1/  Kết quả thiết kế file báo cáo phần 2+3: [SlideBaoCao.pptx](SlideBaoCao.pptx)

Lý do em chọn biểu đồ bar là vì mình đang so sánh 3 trạng thái rời rạc khác nhau của loại dữ liệu tình trạng là "Đang mượn", "Quá hạn", "Đã trả", nên khi thể hiện biểu đồ bả mình sẽ thấy được độ dài ngắn nên hoàn toàn có thể dễ dàng so sánh.

- 2/ Áp dụng quy tắc 10/20/30 thì đây chỉ chiếm 1 silde trong 10 slide nên em sẽ dự kiến trình bày nội dung slide này trong 2 phút



