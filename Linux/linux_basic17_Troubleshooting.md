Troubleshooting:
  - Troubleshooting là việc xác định và giải quyết các sự cố hoặc vấn đề trong hệ thống Linux.
  - Các sự cố này có thể bao gồm từ lỗi hệ thống phổ biến, sự cố phần cứng hoặc phần mềm, sự cố kết nối mạng đến quản lý tài nguyên hệ thống.
  - Quá trình xử lý sự cố trong Linux thường liên quan đến việc sử dụng các công cụ dòng lệnh, kiểm tra tệp nhật ký hệ thống và ứng dụng, hiểu các quy trình hệ thống và đôi khi, tìm hiểu sâu về hạt nhân Linux.
  - Chìa khóa để xử lý sự cố hiệu quả là hiểu cách Linux hoạt động và quen thuộc với các công cụ dòng lệnh phổ biến.
  - Ngoài ra, khả năng diễn giải các thông báo lỗi, sử dụng các công cụ gỡ lỗi tích hợp của Linux và hiểu các triệu chứng sự cố phổ biến có thể đẩy nhanh thời gian giải quyết.
  - VD : lệnh top là một công cụ khắc phục sự cố thường được sử dụng, cung cấp chế độ xem động, thời gian thực về các quy trình đang chạy trên hệ thống.

  - Ping:
    + Lệnh ping cho phép bạn kiểm tra trạng thái kết nối giữa máy chủ của bạn và máy mục tiêu, có thể là máy tính khác, máy chủ hoặc bất kỳ thiết bị nào trên mạng.
    + Công cụ chẩn đoán này gửi các gói ICMP (Giao thức tin nhắn điều khiển Internet) ECHO_REQUEST đến máy chủ mục tiêu và lắng nghe các phản hồi ECHO_RESPONSE, cung cấp thông tin chi tiết về tình trạng và tốc độ của kết nối.
    + VD: ping <192.168.1.1> -> gửi các gói tin phản hồi từ địa chỉ IP trên về máy local.
   
  - ICMP:
    + Internet Control Message Protocol (ICMP) là một giao thức hỗ trợ được sử dụng chủ yếu bởi các thiết bị mạng để truyền đạt thông tin cập nhật hoặc lỗi đến các thiết bị khác.
    + ICMP có thể được sử dụng để gửi thông báo lỗi cho biết, ví dụ, dịch vụ được yêu cầu không khả dụng hoặc không thể truy cập máy chủ hoặc bộ định tuyến.
    + ICMP cũng có thể được sử dụng để chuyển tiếp tin nhắn truy vấn.
    + Trong các hệ thống Linux, các công cụ dòng lệnh phổ biến liên quan đến ICMP bao gồm ping và traceroute, cả hai đều được sử dụng để chẩn đoán trạng thái của mạng và thường là một phần của nỗ lực khắc phục sự cố.
    + VD:
      + # sử dụng ICMP thông qua lệnh ping để gửi thông tin phản hồi từ specific host
        ping www.google.com

  - Traceroute:
    + Traceroute là một công cụ chẩn đoán mạng được sử dụng rộng rãi trong các hệ thống Linux để khắc phục sự cố.
    + Công cụ này được thiết kế để hiển thị đường dẫn mà các gói tin đi từ hệ thống nơi traceroute được chạy đến một hệ thống đích hoặc trang web đã chỉ định.
    + Nó được sử dụng để xác định các sự cố định tuyến, cung cấp phép đo độ trễ và tìm ra cấu trúc mạng khi các gói tin di chuyển qua internet.
    + Mỗi lần nhảy dọc theo tuyến đường được kiểm tra nhiều lần (mặc định là 3 lần nhưng có thể thay đổi) và thời gian khứ hồi cho mỗi gói tin được hiển thị.
    + Nếu một số gói tin không đến được đích, traceroute có thể giúp chẩn đoán lỗi xảy ra ở đâu.
    + Có thể theo dõi tuyến đường trong Linux bằng cách thực hiện lệnh traceroute cho phép bạn khám phá các tuyến đường mà các gói tin giao thức internet đi theo khi di chuyển đến đích.
    + VD: traceroute www.dantri.com

  - Netstat:
    + Netstat, viết tắt của network statistics, là một công cụ dòng lệnh tích hợp được sử dụng trong các hệ thống Linux để khắc phục sự cố mạng và đo lường hiệu suất.
    + Công cụ này cung cấp số liệu thống kê cho các giao thức, danh sách các cổng mở, thông tin bảng định tuyến và các chi tiết quan trọng khác về mạng.
    + Chức năng của công cụ này được mở rộng nhờ nhiều tùy chọn dòng lệnh mà công cụ này hỗ trợ, có thể được sử dụng riêng lẻ hoặc kết hợp để tinh chỉnh đầu ra.
    + Các tùy chọn này có thể bao gồm hiển thị địa chỉ số thay vì tên (-n), giám sát liên tục (-c) hoặc phát hiện các kết nối trên một giao thức cụ thể (-t, -u).
    + VD: netstat -n -> liệt kê tất các các kết nối với numerical values.
   
  - Packet Analysis:
    + Packet Analysis sử dụng các công cụ và kỹ thuật để nắm bắt và phân tích lưu lượng mạng.
    + Bằng cách kiểm tra dữ liệu được gửi và nhận qua mạng, quản trị viên hệ thống và mạng có thể xác định và xử lý sự cố như hiệu suất kém, sự cố kết nối và lỗ hổng bảo mật.
    + Các công cụ như tcpdump và Wireshark là những tiện ích phổ biến cho mục đích này.
    + Chúng hiển thị thông tin chi tiết ở cấp độ gói tin để cung cấp bức tranh toàn cảnh về các hoạt động mạng.
    + Những công cụ này đặc biệt hữu ích cho việc chẩn đoán mạng và gỡ lỗi các sự cố liên quan đến giao thức mạng.
    + VD: sudo tcpdump -i eth0 -> chụp và hiển thị các gói tin đang được truyền hoặc nhận qua giao diện mạng eth0.
    + 
