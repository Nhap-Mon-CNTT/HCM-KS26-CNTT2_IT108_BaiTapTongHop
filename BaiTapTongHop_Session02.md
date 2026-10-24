# Yêu cầu
## Phần 1 - Lĩnh vực CNTT và đơn vị lưu trữ
### 1/ Em chọn ứng viên B. Em chọn như vậy dựa theo nhu cầu thực tế của Cyber Arena cần người phụ trách kỹ thuật, thiết kế hệ thống quay/xem lại trận đấu và nâng cấp máy. Cyber này lại đang kiếm tiền bằng cách cho thuê khách chơi game và là nơi luyện tập cho đội tuyển esport nhỏ luyện tập nếu như máy tính có hỏng hóc, mạng rớt thì sẽ là vấn đề lớn ảnh hưởng đến doanh số hoặc khi có nâng cấp máy thì cũng cần người hiểu am hiểu về phần cứng máy tính
### 2/ Sắp xếp theo thứ tự tăng dần: byte < KB < MB < GB < TB
## Phần 2: Mô hình IPO và lĩnh vực CNTT

### 1/
|Thành phần|Trong hệ thống quay/xem lại trận đấu|
|:---|:---|
|Input|Các thông số, hình ảnh, âm thanh trận đấu|
|Process|Nén các dữ liệu lại thành một file video|
|Output|Cho ra đươc video trận đấu|
|Storage|Lưu trữ trận đấu đó lại trông đám mây hoặc ổ cứng|

### 2/ 
- Hoạt động: livestream: lĩnh vực Mạng-Bảo mật: Vì khi livestrem thì cần phải đảm bảo đường truyền tốt.
- Hoạt động: xem lại phân tích: lĩnh vực Big Data: vì sẽ phải hiểu được quá trình trận đấu diễn ra phân tích được số liệu để đưa ra phương án cải thiện và phát huy điểm mạnh điểm yếu của đội tuyển.
## Phần 3: Tính toán dung lượng và tốc độ mạng

### 1/ Tính dung lượng
- 20 (trận) X 500 (MB)= 10000 (MB)
- 10000 MB = 9.765625 GB
- Sử dụng ổ SSD 512 GB thì sau một tháng vẫn đủ dùng để chứa video. Sau 1 tháng đầu tiên vận hành thì ổ cứng còn trống là: 512 - 9.765625 = 502.234375 (GB)
### 2/ Tính tốc độ mạng
- Mạng 100 Mbps tương đương tối đa 100/8 = 12.5 MB/s
- Up một đoạn video 200 MB cần: 200/12.5 = 16 (s)
- Trên thực tế tốc độ tải thường chậm hơn thường là do đường truyền mạng có thể không ổn định được 12.5 MB/s, nhiều người dùng mạng, do quá trình nén dữ liệu để truyền đi.
## Phần 4
### 1/
- Khi máy tính bị giật do vừa chơi game và quay video livestream thì theo em sẽ nên ưu tiên nâng cấp RAM. Ta xét cùng lúc vài trò của CPU và RAM, RAM sẽ là nơi lưu trữ tạm thời dữ liệu hình ảnh, âm thanh của trận đấu, file nén của CPU sau khi xử lý còn CPU sẽ là nơi xử lý dữ liệu của game là tính toán các thao tác, thông số, phần mềm quay sẽ là nén lại dữ liệu. Chính vì vậy để có thể cho CPU xử lý được nhiều thứ cùng lúc thì nơi lưu trữ dữ liệu phải nhiều lên để có thể lưu trữ nhiều thông tin hơn cho CPU
### 2/
- DIKW:
  ||Nội dung trong tình huống|Vì sao thuộc tầng này (1 câu)
  |:---|:---|:---|
  |Data|các lần chết, thời điểm xày ra| Thuộc tầng này là do đây là dữ liệu thô chưa có bối cảnh|
  |Information| Huấn luyện viên xem video thấy tuyển thủ hay chết ở phút 15-20| Đây là câu đã liên kết các dữ liệu thô chưa có bối cảnh lại với nhau|
  |Knowledge| phát hiện do thiếu tầm nhìn bản đồ| Dựa vào kiến thức, kinh nghiệm thì huấn luyện viên đã biết được nguyên nhân tại sao việc này|
  |Wisdom|yêu cầu mua thêm mắt (Ward) cho trận sau. | Thuộc tầng này là do huấn luyện viên đã hiểu được tại sao và đưa ra nguyên nhân khắc phục, cải thiện để không xảy ra tình trạng này nữa|