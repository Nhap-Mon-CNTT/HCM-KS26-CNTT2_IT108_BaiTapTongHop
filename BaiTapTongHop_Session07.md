# Yêu cầu
 
## Phần 1: Đọc và định vị tệp tin
### 1.  Vì hiện tại đã đang ở thư mục devops-lap rồi nền để lấy nội dung trong file sever.log thì ta gõ cú pháp là:
`Get-Content .\logs\server.log`

### 2. Giả sử file server.log năng đến tận 500MB mà mở bằng notepad thì nó có thể gây treo máy bởi vì cách này khi mở file thì dữ liệu 500MB này sẽ được đẩy từ ổ cứng lên RAM kèm theo đó là Notepad sẽ phải chuẩn bị giao diện GUI để mở cho người dùng nên dung lượng chiếm dụng trên RAM có thể lớn hơn 500MB nếu như dung lượng RAM thấp không chứa nổi lượng dữ liệu notepad yêu cầu thì sẽ gây ra hiện tượng Swap file dẫn đến bị treo máy. Còn khi mở file 500Mb này bằng terminal như trong powershell là `Get-Content` thì dữ liệu khi xuất ra màn hình là từng dòng nên sẽ chiếm cực kỳ ít RAM ngay cả khi file nặng đến đâu

### 3. Câu lệnh để tìm đó là:
`Get-ChildItem -Recurse -Filter *.log`

## Phần 2: Lọc dữ liệu và pipe
### 4.
- Do hiện tại phiên làm việc đang là:
`C:\Users\student\Desktop\devops-lab` nên cú pháp để lọc các chữ ERROR là: `Get-ChildItem -Recurse -Filter server.log | Select-String -Pattern "ERROR"`


### 5. 
|Câu hỏi|Lệnh PowerShell|
|:---|:---|
|"File sever.log đang nằm trong thư mục nào"-> Bản chất câu hỏi này là trong hàng loạt folder và hàng loạt file của một dự án hãy xác định vị trí file sever.log đang nằm ở đâu| `Get-ChildItem -Recurse -Filter "server.log"`|
|"Bên trong file này có dòng lệnh nào chứa lỗi 404 không?" Bản chất câu hỏi này là tìm chuỗi ký tự có trong file cần tìm ví dụ là tìm chuỗi 404 có trong file sever.log| `Select-String -Pattern "404" -Path ".\logs\server.log"`|

- Lệnh kết hợp **Pipe** `|` để đọc `server.log` rồi lọc ra các dòng chứa `404`: `Get-ChildItem -Recurse -Filter server.log | Get-Content | Select-String -Pattern "404"`
### 6. Tìm đệ quy tất cả file `.log` trong `devops-lab`, rồi trong các file đó lọc ra những dòng **không chứa** chữ `INFO`:
- Câu lệnh: `Get-ChildItem -Recurse -Filter *.log | Select-String -Pattern "INFO" -NotMatch`


## Phần 3
### 7. 

- Câu lệnh: `Get-Content -Path ".\logs\server.log" | Select-String -Pattern "404" > reports\daily_report.txt`


### 8. 
- Câu lệnh mới: 
  `$old = Get-Content .\reports\daily_report.txt; Get-Content .\logs\server.log | Select-String -Pattern "404" | ForEach-Object { $_.Line } |
Where-Object { $_ -notin $old } >> .\reports\daily_report.txt`
- Nếu dùng lệnh cũ là lệnh ở trên câu 7 chứa toán tử `>` thì dòng lọc lỗi 404 trước đó sẽ bị ghi đè bởi nhưng dòng lỗi 404 mới này nên sẽ làm mất dữ liệu lọc được trong file báo cáo cũ
## Phần 4: Shell script và lệnh `echo`
### 9. 
- In thông báo tiến trình: `Write-Output "Dang loc log..."`
- Toán tử phù hợp ghi dòng tiêu đề `=== LOG REPORT ===` làm **dòng đầu tiên** của `reports\daily_report.txt`: Câu lệnh: `Write-Output "=== LOG REPORT ==="> reports\daily_report.txt`
### 10. 
 script:
```Script
# Lọc các lỗi 404 có trong file server.log
Write-Output "Dang loc log..."
Write-Output "=== LOG REPORT ===" > reports\daily_report.txt
Get-Content -Path ".\logs\server.log" | Select-String -Pattern "404" >> reports\daily_report.txt
```
## Phần 5: Viết chạy và thẩm định Script AI
 ### 11.
 - Bước 1. Viết: tạo file script và đọc lại nội dung trước khi chạy
 - Bước 2. Chạy: thực thi script bằng lệnh: .\scripts\auto_report.ps1
 - Bước 3: Kiểm tra đã có fiel báo cao chưa: bằng câu lệnh `Test-Path .\reports\daily_report.txt` và kiểm tra nội dung bên trong bằng câu lệnh `Get-Content .\reports\daily_report.txt`

 ### 12:
 - a/ Dòng lệnh nguy hiểm đó là 
`Remove-Item -Recurse -Force C:\*`. Hậu quả nếu chạy dòng lệnh này là lệnh sẽ cố xóa tất cả những gì tài khoản đang chạy có quyền xóa. Kết quả thực tế phụ thuộc vào quyền như là admin hay user và file nào đang được sử dụng. Nhưng trường hợp xấu nhất là mất dữ liệu người dùng, hỏng hệ điều hành và máy không khởi động lại được. Vì vậy đây là lệnh tuyệt đối không được chạy.
- b/ Sửa lại đường dẫn và cả câu lệnh là:
`Remove-Item -Force -Recurse ".\temp\*"`


