# API là gì? (giải thích kiểu Feynman)

## Hình dung đơn giản

Hãy tưởng tượng bạn vào **nhà hàng**:

- **Bạn** = ứng dụng (app điện thoại, website)
- **Bếp** = hệ thống lưu trữ dữ liệu và xử lý (server)
- **Người phục vụ** = **API**

Bạn không được vào bếp tự nấu. Bạn cũng không cần biết bếp làm món thế nào. Bạn chỉ cần xem **thực đơn**, gọi món với người phục vụ, và họ mang món ra cho bạn.

> **API là người trung gian nhận yêu cầu từ bên này, chuyển sang bên kia, rồi mang kết quả trả về.**

Tên đầy đủ là *Application Programming Interface* (giao diện lập trình ứng dụng), nhưng bạn chỉ cần nhớ nó là "người phục vụ" giữa hai phần mềm.

## Ví dụ thực tế: app xem thời tiết

Khi bạn mở app thời tiết trên điện thoại:

1. App **không tự biết** thời tiết. Nó gửi yêu cầu qua API: *"Cho tôi thời tiết Phan Thiết hôm nay"*.
2. API chuyển yêu cầu đến hệ thống của trạm khí tượng.
3. Hệ thống trả kết quả: *"32°C, nắng nhẹ"*.
4. API mang kết quả về, app hiển thị cho bạn.

Một số ví dụ quen thuộc khác:

- Nút **"Đăng nhập bằng Google"** trên một website: website dùng API của Google để xác nhận bạn là ai.
- **Thanh toán qua MoMo/VNPay** trên Shopee: Shopee gọi API của ví điện tử để xử lý tiền.
- **Bản đồ** trong app gọi xe: app dùng API của Google Maps.

## Tại sao API quan trọng?

- **An toàn**: bạn chỉ nhận được thứ "thực đơn" cho phép, không chạm được vào "bếp".
- **Tiết kiệm công sức**: lập trình viên không cần tự làm bản đồ hay hệ thống thanh toán, chỉ cần "gọi món" từ nơi đã có sẵn.
- **Kết nối**: các phần mềm khác nhau có thể làm việc cùng nhau.

## Kiểm tra xem bạn đã hiểu chưa

Hãy thử giải thích lại cho một người bạn bằng một câu:

> *"API giống như người phục vụ: mình gửi yêu cầu, họ lấy dữ liệu từ nơi khác và mang về cho mình."*

Nếu bạn nói được câu này, bạn đã nắm được ý chính.

## Bước tiếp theo

Khi học sâu hơn, bạn sẽ gặp các khái niệm như **request/response** (yêu cầu/phản hồi), **JSON** (định dạng dữ liệu) và **REST API**. Bạn chỉ cần hiểu hình ảnh nhà hàng ở trên là đủ làm nền để học tiếp.
