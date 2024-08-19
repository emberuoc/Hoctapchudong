Process management:
  - Quản lý tiến trình là một phần không thể thiếu trên bất kỳ hệ điều hành nào và Linux cũng không ngoại lệ.
  - Bất kỳ chương trình nào chạy trên Linux, dù là ứng dụng hay hệ thống đều được coi là 1 tiến trình.
  - Các tiến trình thực hiện các tác vụ khác nhau nhưng lại hoạt động cùng nhau để việc vận hành máy chủ được liền mạch.
  - để hiển thị thông tin về các tiến trình đang chạy gõ lệnh: ps aux -> liệt kê thông tin về các tiến trình đang chạy trên máy chủ.
  - Để cập nhật trực tiếp trạng tháu hiện tại của hệ thống (bao gồm các tiến trình trên máy chủ), sử dụng lệnh: top.
  - Ngoài ra, chúng ta có thể kill các tiến trình bằng câu lệnh: kill -SIGTERM/-SIGKLL pid (thay pid bằng tiến trình muốn dừng).
      + -SIGTERM là dừng tiến trình một cách tự nhiên, nhẹ nhàng.
      + -SIGKILL là cưỡng bức dừng tiến trình.

  
  - Backgournd/ Foreground process:
      + Một tiến trình trong linux có thể chạy ở foreground (fg) hoặc background (bg).
      + Nó lấy dữ liệu đầu vào trực tiếp từ user, hiển thị đầu ra và lỗi trên thiết bị đầu cuối.
      + Thông thường 1 tiến trình được bắt đầu từ fg nhưng cũng có thể đưa nó về bg.
      + sử dụng & khi kết thúc câu lệnh để tiến trình bắt đầu từ bg thay vì fg (mặc định tiến trình chạy ở fg).
      + fg job_number: đưa 1 job từ bg -> fg.
      + CTRL z: đưa 1 job từ fg -> bg.
   
  - Listing/ Finding Process:
      + Để quản lý hiệu quả hệ thống thì điều quan trọng là phải biết liệt kê và tìm kiếm các process đang hoạt động.
      + proc filesystem là 1 công cụ vô cùng hữu ích trong việc liệt kê và tìm kiếm các process đang chạy, nó cung câp thông tin chi tiết về các process bao gồm PID, status và mức tiêu thụ tài nguyên của process đó.
      + Để list các process đang chạy sử dụng lệnh ps -ef.
      + Để hiển thị danh sách các tiến trình đang chạy dùng lệnh top.
      + sử dụng lệnh htop để có giao diện thân thiện hơn với người dùng.
      + có thể đi sâu hơn bằng cách khám phá proc -> các tham số hạt nhân và chi tiết hệ thống cụ thể của từng process.

  - Process Signals:
      + Trong Linux, quản lý quy trình là một phần cơ bản của hệ thống bao gồm việc tạo, lập lịch, chấm dứt và phối hợp thực hiện các quy trình.
      + Một khía cạnh quan trọng của điều này là tín hiệu proc hoặc tín hiệu quy trình.
      + Tín hiệu quy trình là một dạng cơ chế giao tiếp trong các hệ thống Unix và Linux.
      + Chúng cung cấp phương tiện để thông báo cho quy trình về các sự kiện đồng bộ hoặc không đồng bộ.
      + Có nhiều loại tín hiệu như SIGINT, SIGSTOP, SIGKILL, v.v. có thể được gửi đến quy trình đang chạy để ngắt, tạm dừng hoặc chấm dứt quy trình đó.
      + VD nếu muốn gửi tín hiệu dừng tới tiến trình có PID là 12345, sử dụng lệnh kill: kill -SIGSTOP 12345.
   
  - Killing process:
      + Đôi khi, các tiến trình này có thể không hoạt động như mong đợi do một số lý do như lỗi hệ thống, hành vi hệ thống không mong muốn hoặc khởi tạo vô tình và có thể yêu cầu chấm dứt.
      + vì vậy, khía niện kill process được xuất hiện trong management process.
      + Có thể sử dụng lệnh kill để gửi tín hiệu cụ thể tới một tiến trình.
      + Syntax: kill [signal or option] PID(s).

  - Process priority:
      + Trong linux, các mức độ ưu tiên đóng vai trò quan trọng trong việc sử dụng tài nguyên hệ thống hiệu quả, cho phép Linux tinh chỉnh quá trình thực thi và phân bổ tài nguyên hệ thống một cách thông minh.
      + Nhân Linux sắp xếp các quy trình trong cấu trúc proc, thường được tìm thấy trong thư mục hệ thống tệp /proc.
      + Cấu trúc này chứa thông tin về tất cả các quy trình đang hoạt động, bao gồm cả mức độ ưu tiên của chúng.
      + Giá trị ưu tiên "nice" nằm trong khoảng từ -20 (mức độ ưu tiên cao nhất) đến +19 (mức độ ưu tiên thấp nhất).
      + Bằng cách hiểu và quản lý các mức độ ưu tiên proc, bạn có thể tối ưu hóa hiệu suất hệ thống và kiểm soát quy trình nào nhận được nhiều hay ít sự chú ý của CPU.
      + Một câu lệnh đơn giản để hiển thị process ID, độ ưu tiên và user cho mọi tiến trình: ps -eo pid,pri,user.
      + để thay đổi thứ tự ưu tiên của tiến trình, sử dụng lệnh renice: renice +5 [PID] -> tăng độ ưu tiên lên 5 đơn vị.

  - Process Forking:
      + Phân nhánh quy trình là một khái niệm cơ bản trong quản lý quy trình trong các hệ thống Linux.
      + Thuật ngữ này đề cập đến cơ chế mà một quy trình đang chạy (quy trình cha) có thể tạo ra một bản sao của chính nó (quy trình con), cho phép thực thi đồng thời cả hai quy trình.
      + Điều này được hỗ trợ bởi lệnh gọi hệ thống 'fork', là một khía cạnh nổi bật trong việc hiểu cách tạo và kiểm soát các quy trình trong môi trường Linux.
      + Quy trình con được tạo ra bởi fork là bản sao gần như hoàn hảo của quy trình cha ngoại trừ một vài giá trị bao gồm ID quy trình và ID quy trình cha.
      + Bất kỳ thay đổi nào được thực hiện trong quy trình con đều không ảnh hưởng đến quy trình cha và ngược lại.
