# Yêu cầu

## Phần 1: CLI vs GUI và cấu trúc câu lệnh

### 1/
- Command: `ls`
- Options/Flags: `-Force`
- Argument: `C:\Windows\logs`
### 2/
Bởi vì máy chủ cloud sẽ không có màn hình để mình có thể thao tác bằng giao diện GUI nên bắt buộc phải biết và sử dụng câu lệnh CLI để đưa dự án lên server.

## Phần 2: Điều hướng hệ thống file

### 3/ `Set-location .\quan-ly-sinh-vien`
### 4/ `C:\Users\student\Desktop\quan-ly-sinh-vien\src\main.py`
### 5/ `Get-ChildItem -Recurse -Force -Path ..\data`.Cờ `-Recurse` được sử dụng nếu sau này trong thư mục data còn có những thư mục con thì mình cũng có thể liệt kê ra hết luôn.

## Phần 3: 

### 6/ `New-Item -Itemtype directory ".\quan-ly-sinh-vien\src", ".\quan-ly-sinh-vien\data"`
### 7/ `New-Item -Itemtype file ".\quan-ly-sinh-vien\src\main.py", ".\quan-ly-sinh-vien\src\utils.py", ".\quan-ly-sinh-vien\README.md"`
### 8/ 
- Dùng để đổi tên: `Rename-Item quan-ly-sv quan-ly-sinh-vien`
- Dùng để tạo thư mục backup: `Copy-Item -Recurse -Force .\quan-ly-sinh-vien .\backup-quan-ly-sinh-vien`

## Phần 4: Xử lý lỗi Terminal

### 9/ Lỗi ở đây là lỗi `Cannot find` lỗi này trong trường hợp này xảy ra là do gõ sai chính tả đường dẫn vào thư mục `src` thành `scr`, cách để hạn chế lỗi này là ghi một vài chữ đầu tên file sau đó bấm nút `Tab` để đảm bảo sự chính xác tên file
### 10/ Lỗi này là lỗi khi chạy file script thì nếu chưa cấp quyền thì file script này sẽ bị Windows chặn, không cho phép chạy. Để khắc phục lỗi này thì:
- Bước 1: mở powershell bằng quyền admin `Run as administrator`
- Bước 2: Nhập câu lệnh Set-ExecutionPolicy RemoteSigned
### 11/ Powershell đưa ra cảnh báo để hỏi mình xác nhận lại là có muốn xóa thư mục `old-version` không vì trong đây vẫn còn những thư mục con khác. Để khi xóa file hay thư mục mà để PowerShell không hỏi lại thì sử dụng thêm cờ `Recurse`. Câu lệnh chuẩn, đầy đủ là: `Remove-Item -Recurse "old-version"`
### 12/
|Bước|Câu trả lời của bạn|
|:---|:---|
|a/ Dòng chứa thông điệp lỗi trực tiếp nhất | FileNotFoundError: [Errno 2] No such file or directory: 'data/input.csv'|
|b/ Từ khóa chứa lỗi | *FileNotFoundError*|
|c/ Điều cần kiểm tra tiếp để sửa lỗi|Lỗi này có thể được hiểu là trong thư mục làm việc là `src` không tìm thấy bất kỳ đường dẫn file nào là `.\data\input.csv`. Mà đây là điều đương nhiên vì thư mục data thì theo dự án là đang nằm cùng cấp với thư mục `src`. Cách để sửa lại là sửa lại đường dẫn trong code file `main.py` thành đường dẫn `..\data\input.csv`|