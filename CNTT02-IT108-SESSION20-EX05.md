 # Bài 5 : Xây dựng cơ chế xác thực an toàn cho Crypto Wallet
 ## Lớp bảo vệ két sắt (Chống hacker dù có mật khẩu)
 - [x] Lớp 1 (Khóa vân tay/Khuôn mặt): Giống như bảo vệ yêu cầu bạn phải quét vân tay hoặc khuôn mặt mới được chạm vào két. Hacker dù có lấy được mật khẩu chữ viết tay (mật khẩu ví) cũng đành chịu vì không có khuôn mặt/vân tay của bạn.
 - [x] Lớp 2 (Chip bảo mật phần cứng trong điện thoại): Bên trong điện thoại có một "két sắt mini" riêng biệt chứa chìa khóa bí mật (private key). Mọi giao dịch chuyển tiền bắt buộc phải có lệnh đồng ý từ két sắt mini này.
 - [x] Lớp 3 (Tự động khóa két): Ngay khi bạn rời đi hoặc tắt ứng dụng, két sắt sẽ tự động sập cửa khóa lại ngay lập tức để người khác không thể lợi dụng điện thoại của bạn.
## 2. Cách lấy mã OTP khi ở trên máy bay (Không có mạng)
- [x] Thuật toán tạo mã OTP (gọi là TOTP) giống như một chiếc đồng hồ đếm giờ bí mật được cài sẵn giống hệt nhau trong điện thoại của bạn và máy chủ:
- [x] Không cần Internet: Cả điện thoại và hệ thống đều tự động đếm thời gian thực (ví dụ: cứ mỗi 30 giây đổi mã một lần) bằng một chiếc chìa khóa mã hóa có sẵn từ trước.
- [x] Lấy mã ngoại tuyến: Khi ở trên máy bay, dù không có sóng hay mạng, điện thoại của bạn vẫn tự tính toán ra mã OTP chính xác dựa vào giờ hiện tại trên máy.
- [x] Xác thực sau: Khi máy bay hạ cánh và có mạng trở lại, hệ thống sẽ đối chiếu lại thời gian và mã OTP đó để duyệt giao dịch một cách an toàn mà không cần nhận tin nhắn SMS.