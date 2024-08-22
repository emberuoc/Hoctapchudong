Networking:
  - Mạng cho phép các hệ thống Linux kết nối, tương tác và chia sẻ tài nguyên với các hệ thống khác, có thể là Linux, Windows, macOS hoặc bất kỳ hệ điều hành nào khác.
  - Linux cung cấp nhiều công cụ và lệnh để quản lý giao diện mạng, xem chi tiết cấu hình, khắc phục sự cố và tự động hóa các tác vụ, chứng minh tính mạnh mẽ và linh hoạt của nó.
  - Linux network stack được đánh giá cao về hiệu suất, khả năng chạy các cấu hình quy mô lớn và toàn diện, cũng như hỗ trợ nhiều giao thức mạng khác nhau.
  - Linux áp dụng phương pháp dựa trên tệp để cấu hình mạng, lưu trữ các thiết lập và cấu hình liên quan đến mạng trong các tệp chuẩn, chẳng hạn như /etc/network/interfaces hoặc /etc/sysconfig/network-scripts/, tùy thuộc vào bản phân phối Linux.
  - sử dụng lệnh: ifconfig -> xuất thông tin về tất cả các giao diện mạng hiện đang hoạt động trên hệ thống.
  - ifconfig đang trở nên lỗi thời và được thay thế bằng ip, cung cấp nhiều tính năng và khả năng hơn.

  - TCP/IP:
    + TCP/IP (Giao thức điều khiển truyền/Giao thức Internet) là một tập hợp các giao thức mạng cho phép hai hoặc nhiều máy tính giao tiếp với nhau.
    + Nó cung cấp một nền tảng để thiết lập kết nối và tạo điều kiện thuận lợi cho việc truyền dữ liệu giữa hai điểm cuối.
    + TCP/IP đóng vai trò quan trọng trong việc cho phép máy chủ, với cấu hình IP chính xác, kết nối và tương tác với các máy chủ khác trên cùng một mạng hoặc các mạng khác nhau.
    + Nó là mô hình bốn lớp, bao gồm các lớp Interface, Internet, Transport và Application.
    + Sử dụng lệnh: netstat -at -> hiển thị toàn bộ kết nối mjang TCP/IP.

  - Subneting:
    + Subneting việc chia một mạng thành hai hoặc nhiều mạng, được gọi là mạng con.
    + Subneting giúp cải thiện hiệu suất và bảo mật mạng.
    + Subbeting có thể được quản lý trong bối cảnh của lược đồ địa chỉ Giao thức Internet (IP), trong đó nó rất quan trọng trong việc tổ chức và quản lý các địa chỉ IP trong mạng, ngăn ngừa xung đột IP và sử dụng hiệu quả các dải địa chỉ IP.
    + Kỹ thuật này vô cùng có giá trị trong các môi trường mạng Linux phức tạp lớn, nơi việc quản lý địa chỉ IP có thể trở nên vô cùng phức tạp.
    + Sử dụng lệnh: route -n -> hiển thị bảng định tuyến (route table).
    + Sử dụng lệnh: route add -net -> thêm 1 subnet mới.
