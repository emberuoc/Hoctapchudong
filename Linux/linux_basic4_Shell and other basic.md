1. Command Path:
  - Trong Linux, command path là một khái niệm quan trọng trong các khái niệm cơ bản về shell.
  - Nói một cách đơn giản, command path là một biến được shell sử dụng để xác định nơi tìm kiếm các tệp thực thi để chạy.
  - Thông thường, khi bạn nhập lệnh trong thiết bị đầu cuối, shell cần biết đường dẫn tuyệt đối của tệp thực thi lệnh để chạy lệnh đó. 
  - Thay vì nhập đường dẫn đầy đủ mỗi lần, command paths cho phép shell tự động tìm kiếm các thư mục được chỉ định theo đúng thứ tự. 
  - Các đường dẫn này được lưu trữ trong biến môi trường $PATH với syntax : echo $PATH.
  - Chạy lệnh này trong thiết bị đầu cuối Linux sẽ trả về tất cả các thư mục mà shell sẽ tìm kiếm theo thứ tự để tìm ra lệnh cần chạy.

2. Environment Variables:
  - Biến môi trường giúp đóng góp vào tính linh hoạt tuyệt vời và có thể tùy trong các hệ thống Unix. 
  - Chúng cung cấp một cách đơn giản để chia sẻ cài đặt cấu hình giữa nhiều ứng dụng và tiến trình trong Linux.
  - Có thể sử dụng lệnh 'env' để liệt kê tất cả các biến môi trường trong phiên shell.

3. Command help:
  - Trợ giúp lệnh trong Linux là một tính năng thiết yếu cho phép người dùng dễ dàng điều hướng qua các lệnh shell Linux. 
  - Tính năng này hiển thị thông tin tóm tắt về cách sử dụng các lệnh.
  - Nhập 'man' trước bất kỳ lệnh nào sẽ hiển thị mục nhập thủ công cho lệnh đó, giải thích lệnh đó làm gì, cú pháp của lệnh và các tùy chọn khả dụng. VD như man ls, man mv, man cp, etc.
  - Một lệnh phổ biến khác là 'help', phù hợp hơn với các hàm tích hợp sẵn của shell, cung cấp mô tả tóm tắt về từng hàm. VD như ls --help, mv --help, etc.

4. Redirects:
  - Shell trong Linux cung cấp một cách mạnh mẽ để quản lý các luồng đầu vào và đầu ra của lệnh hoặc chương trình, cơ chế này được gọi là Chuyển hướng.
  - Mọi quy trình thường có 3 luồng được mở:
    + Đầu vào chuẩn (stdin) - Đây là nơi quy trình đọc đầu vào của mình. Mặc định là bàn phím.
    + Đầu ra chuẩn (stdout) - Quy trình ghi đầu ra của mình vào stdout. Theo mặc định, điều này có nghĩa là thiết bị đầu cuối.
    + Lỗi chuẩn (stderr) - Quy trình ghi thông báo lỗi vào stderr. Theo mặc định, thông báo này cũng sẽ được chuyển đến thiết bị đầu cuối.
  - VD sử dụng lệnh ls -al > file_list.txt, lưu trữ đầu ra của lệnh ls -al sẽ được ghi vào file file_list.txt với toán tử >, nếu file đã tồn tại thì sẽ được ghi đè, nếu không tồn tại thì sẽ được tạo mới.

5. Super User:
  - Super user hay còn được gọi là Root user đại diện cho một tài khoản người dùng trong Linux với các quyền hạn, đặc quyền và khả năng mở rộng. 
  - Root user có toàn quyền kiểm soát hệ thống và có thể truy cập bất kỳ dữ liệu nào được lưu trữ trên đó.
  - Việc sử dụng supper user rất quan trọng để vận hành hệ thống Linux đúng cách và an toàn vì nó có khả năng gây ra thiệt hại nghiêm trọng.
  - Super user có thể được truy cập thông qua các lệnh sudo hoặc su.
  - lệnh 'su -' sẽ chuyển đổi từ người dùng bình thường sang super user (Hạn chế sử dụng do khả năng gây thiệt hại lớn).
  - lệnh 'sudo +command' sẽ thực thi câu lệnh đó với quyền hạn super user (Được khuyến khích sử dụng).
