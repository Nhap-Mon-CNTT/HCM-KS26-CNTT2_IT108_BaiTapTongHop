# Yêu cầu đầu ra
## Phần 1: Kiến trúc hệ điều hành

### 1/
- Hoạt động này là hoạt động **Quản lý tiến trình** của hệ điều hành. 4 phần mềm này chạy được mà không conflic với nhau là nhờ hệ điều hành đã phân công và sắp xếp các tiến trình bằng cách cho từng tiến trình chạy tháy phiên nhau và quá trình đổi qua lại rất nhanh có thể là vài mili giây, ngoài ra những dòng CPU mới còn có thể có nhiều nhân để có thể Multing Task. Ngoài ra HDH còn cấp cho mỗi tiến trình một phần RAM riêng để không bị đọc hay ghi dữ liệu cảu các tiến trình khác.
### 2/
- Khi bạn double-click vào file báo cáo để mở, thành động này sẽ được xử lý qua lớp Shell trước. Vai trò của lớp Shell này có thể được hiểu như là một người trung gian đứng giữa để giao tiếp giữa người dùng và máy tính. Shell sẽ nhận thao tác click của người dùng rồi gửi yêu cầu xuống kernell. Người dùng phổ thông sẽ thường không tương tác với lớp Kernel bởi đây là sẽ là phần điểu khiển phần cứng của máy tính nếu người dùng không biết cách giao tiếp thì sẽ có thể gây lỗi cho máy tính, kèm với đó là giao tiếp với nó rất khó phải sử dụng các ngôn ngữ cấp thấp.

## Phần 2: Cây thư mục và ổ đĩa

### 1/
- Root Directory là ổ D:\
- Parent Directory trực tiếp của file này là: Hinh anh\
- File `anh 1.jpg` đóng vai trò là "lá" trong mô hình cây thư mục. Vì đây là file và không con bất kỳ thư mục con nào bên trong
### 2/
- Lưu dữ liệu dự án ở Download và Desktop dưới góc nhìn kỹ thuật là cực kỳ nguy hiểm, hai lý do thể hiện điều này là:
  + Thứ nhất: Lưu dữ liệu ở 2 nơi này khi thì khi có vấn đề về hệ thống như hỏng ổ đĩa hay bị hack thì khi cài lại,reset lại windows thì dữ liệu sẽ bị xóa hoặc hỏng theo.
  + Thứ 2: Lưu dữ liệu ở Desktop và downloads sẽ chiếm chỗ của những file tạm, bộ nhớ ảo nên sẽ gây lag máy. Ngoài ra lưu trữ dữ liệu ở desktop nhiều thì khi mở máy máy tính phải liệt kê và vẽ các icon các app nhiều hơn nên cũng sẽ gây hơi lag máy lúc ban đầu.
- Em đề xuất lưu dữ liệu cảu mình tại ổ D:\ hoặc bất cứ ổ Root directory nào khác ngoại trừ ổ C:\ là nơi lưu hệ thống

## Phần 3: Đường dẫn

### 1/
 ```
 D:\Nam1\HocKy1\MonHoc\CongNgheThongTin\BaiTapLon\Session02\BaoCaoCuoiKy\Chuong1\Hinh anh\anh 1.jpg
```
### 2/ Đường dẫn để chèn file `logo.png` vào trong file `report.htlm`: `.\assets\logo.png`. Khi sử dụng Relative Path thì cách mà mô tả vị trí cho máy tính sẽ phụ thuộc hoàn toàn vào vị trí hiện tại chứ không cần chính xác tuyệt đối giúp khi chuyển qua máy khác thì dự án vẫn chạy bình thường.

## Phần 4: Quy tắc đặt tên

### 1/ bao-cao-bai-tap-lon-it101-ban-cuoi-v2.docx

## Phần 5: Tổ chức và dọn dẹp ổ đĩa

### 1/ 
- Đường dẫn 3b đang lồng 9 cấp và đang vi phạm quy tắc 3 cấp
- Sửa lại đường dẫn: D:\01_HocTap\CongNgheThongTin\Session02\anh 1.jpg

## Phần 6: Đuôi file và file ẩn

### 1/ file hiển thị là `de-thi-dap-an.pdf` nhưng máy đang ẩn đuôi mở rộng đây có thể là cạm bẫy mà hacker sử dụng để lừa người dùng mở nó khi thấy là file .pdf tưởng là file bình thường, tên thật nó có khả năng là `de-thi-dap-an.pdf.exe`. Để khắc phục tình trạng này thì cần bật hiển thị đuôi ẩn trên Windows như sau: thao tác trên Windows File Explorer là View->Show->File name extensions. Khi này sẽ hiện đầy đủ đường dẫn từ đó biết được nó là file gì và không bị dụ bấm vào