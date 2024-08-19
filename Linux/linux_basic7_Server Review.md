Server Review:
  - Server Review là quá trình đánh giá hiệu suất, bào mật và các cấu hình của máy chủ để xác định các vị trí càn phải cải thiện hoặc để phát hiện bất kỳ nguy cơ nào đến hoạt động của máy chủ.
  - Phạm vi đánh giá có thể bao gồm kiểm tra các cải tiến về bảo mật, kiểm tra tệp nhật ký, xem xét tài khoản người dùng, phân tích cấu hình mạng của máy chủ và kiểm tra các phiên bản phần mềm của máy chủ.
  - Một số lệnh cơ bản để review server như :
    + free -m: hiển thị thông tin bộ nhớ.
    + df -h: thể hiện dung lượng đã sử dụng.
    + uptime: CPU load.

  - Uptime and load:
    + Lệnh uptime trong Linux cung cấp thông tin về thời gian hệ thống chạy mà không tắt hoặc khởi động lại và tải trung bình của hệ thống.
    + Tải trung bình của hệ thống là một chỉ báo quan trọng minh họa lượng công việc tính toán mà hệ thống máy tính thực hiện.
    + Chỉ báo này phản ánh số lượng quy trình đang xếp hàng để có thời gian CPU.
    + Tải trung bình của hệ thống thường được hiển thị trong khoảng thời gian 1, 5 và 15 phút.
    + Nếu máy chủ có tải trung bình cao, điều này có thể cho thấy tài nguyên hệ thống không đủ hoặc được định cấu hình sai, dẫn đến hiệu suất có thể chậm hoặc hệ thống không phản hồi.
    + Câu lệnh để kiểm tra tải trung bình của server: uptime, output hiển thị sẽ là thời gian hệ thống hoạt động và mức tải trung bình trong 1, 5 và 15 phút gần nhất.
  
  - Auth logs:
    + Khi xử lý máy chủ Linux và bảo trì máy chủ, một trong những thành phần quan trọng nhất cần xem xét thường xuyên là auth logs.
    + Các nhật ký này, thường nằm trong /var/log/auth.log (đối với các bản phân phối dựa trên Debian) hoặc /var/log/secure (đối với Red Hat và CentOS), ghi lại tất cả các sự kiện và hoạt động liên quan đến xác thực đã xảy ra trên máy chủ.
    + Auth logs có thể chỉ ra các cuộc tấn công đăng nhập bằng cách dùng vũ lực, các nỗ lực truy cập trái phép và bất kỳ hành vi đáng ngờ nào.
    + Phân tích thường xuyên auth logs là một nhiệm vụ cơ bản để đảm bảo tính bảo mật của máy chủ và tính toàn vẹn của dữ liệu.
    + Câu lệnh kiểm tra log: tail /var/log/auth.log.
  
  - Service running:
    + Các dịch vụ chạy trên máy chủ Linux có thể bao gồm từ dịch vụ web đến dịch vụ cơ sở dữ liệu, máy chủ DNS, mail server và nhiều dịch vụ khác.
    + Định kỳ kiểm tra các dịch vụ đang chạy để quản lúy tài nguyên, trạng thái của dịch vụ và khắc phục các sự cố, đảm bảo hiệu tình trạng và hiệu suất của máy chủ.
    + Câu lệnh kiểm tra service: systemctl --type=service, kết quả hiển thị sẽ bao gồm các đơn vị dịch vụ, tình trạng hiện tại và mô tả của dịch vụ.
   
  - Available memory/disk:
    + Là một phần của quá trình đánh giá máy chủ.
    + Liên quan đến việc sử dụng nhiều công cụ dòng lệnh do Linux cung cấp, chẳng hạn như free, vmstat và top.
    + Những công cụ này có thể hỗ trợ theo dõi mức sử dụng bộ nhớ và số liệu hiệu suất, đảm bảo hệ thống không bị quá tải và có đủ tài nguyên cho các ứng dụng quan trọng.
    + câu lệnh kiểm tra dung lượng bộ nhớ: free.
    
