Kiểm tra khóa SSH đã cấu hình trên máy của bạn:

1 Trên máy tính của bạn, kiểm tra xem bạn đã tạo khóa SSH chưa bằng lệnh:
bash :
ls -al ~/.ssh
====================

2 Tạo khóa SSH nếu chưa có:

Nếu bạn chưa có khóa SSH, bạn có thể tạo bằng lệnh:

ssh-keygen -t ed25519 -C "your_email@example.com"

Hoặc nếu bạn muốn dùng RSA:

ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

Nhấn Enter để chấp nhận các giá trị mặc định và không cần thiết lập mật khẩu (passphrase) nếu bạn không muốn.
===================
3 Thêm khóa SSH vào tài khoản GitHub của bạn:

Sao chép nội dung của file id_ed25519.pub hoặc id_rsa.pub (tùy thuộc vào loại khóa bạn đã tạo):
cat ~/.ssh/id_ed25519.pub

hoặc

cat ~/.ssh/id_rsa.pub
====================
4 Kiểm tra lại quyền truy cập:

Đảm bảo rằng bạn có quyền truy cập vào repository mà bạn đang cố gắng kết nối. Bạn có thể kiểm tra quyền truy cập bằng cách thử:
ssh -T git@github.com
Nếu thành công, bạn sẽ thấy một thông báo chào mừng từ GitHub.