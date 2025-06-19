*. Khái niệm cốt lõi
Mã Băm (Hash): Chuỗi cố định (SHA-256) đại diện cho nội dung tài liệu. Thay đổi nhỏ nhất cũng tạo ra mã băm khác biệt.
Khóa Bí Mật (Private Key): Dùng để tạo chữ ký số, chỉ người sở hữu biết và không được chia sẻ.
Khóa Công Khai (Public Key): Dùng để xác thực chữ ký số, có thể chia sẻ công khai.
Chữ Ký Số (Digital Signature): Mã băm tài liệu được mã hóa bằng Khóa Bí mật, chứng minh tính toàn vẹn và nguồn gốc của tài liệu.
*.Tính năng nổi bật
Giao diện web trực quan.
Tự động tạo cặp khóa RSA (2048-bit).
Băm tài liệu bằng SHA-256.
Ký tài liệu an toàn với đệm PSS.
Xác thực chữ ký qua tài liệu gốc, chữ ký và Khóa Công khai.
Tự động tạo URL công khai bằng Ngrok.
*.Hướng dẫn cài đặt & sử dụng
1. Điều kiện tiên quyết
Python 3.6 trở lên.
pip.
Tài khoản Ngrok (để lấy Authtoken).
2. Lấy Ngrok Authtoken
Đăng ký tài khoản miễn phí tại dashboard.ngrok.com.
Truy cập Your Authtoken sau khi đăng nhập.
Sao chép token của bạn.
3. Chạy Code
Tạo ô code trong Colab để chứa riêng biệt mã nguồn cho "Trình Tạo Chữ Ký Số" và "Trình Xác Thực Chữ Ký Số".
Lưu mã nguồn vào từng ô tương ứng.
Cấu hình Ngrok Authtoken: Mở cả hai ô code, tìm dòng NGROK_AUTH_TOKEN = "YOUR_NGROK_AUTH_TOKEN" và thay thế "YOUR_NGROK_AUTH_TOKEN" bằng token thực của bạn.
4. Quy trình làm việc
Bước 1: Tạo chữ ký số
Trong ô code của Trình Tạo Chữ Ký Số, nhấp vào nút "play" ở góc trái màn hình để chạy ứng dụng.
Sau khi ứng dụng khởi chạy, bạn sẽ thấy một URL công khai từ Ngrok (ví dụ: https://<random-string>.ngrok-free.app). Mở URL này trong trình duyệt.
Tải lên tài liệu bạn muốn ký. Ứng dụng sẽ hiển thị:
Khóa Công khai
Khóa Bí mật
Mã Băm (SHA-256 Hash)
Chữ ký số
Sao chép và lưu giữ cẩn thận Khóa Công khai và Chữ ký số để sử dụng trong bước xác thực.
Lưu ý: Giữ Khóa Bí mật an toàn. Mỗi lần tải tệp lên sẽ tạo một cặp khóa mới.

Bước 2: Xác thực chữ ký số
Trong ô code của Trình Xác Thực Chữ Ký Số, nhấp vào nút "play" ở góc trái màn hình.
Mở URL Ngrok mới được tạo cho trình xác thực trong trình duyệt của bạn.
Trên trang xác thực, bạn cần cung cấp 3 thông tin:
Tải lên tệp gốc: Chính xác tệp đã dùng ở Bước 1.
Dán chữ ký số: Chuỗi chữ ký số (dạng hex) đã sao chép.
Dán nội dung khóa công khai: Toàn bộ khóa công khai (bao gồm -----BEGIN PUBLIC KEY----- và -----END PUBLIC KEY-----).
Nhấp vào nút "Xác thực".
Kết quả sẽ hiển thị:
✅ Xác thực thành công! Đây là chữ ký hợp lệ. (nếu thông tin khớp).
❌ Xác thực không thành công! Chữ ký không khớp với tệp. (nếu tài liệu hoặc thông tin xác thực không đúng).
