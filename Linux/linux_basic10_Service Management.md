Service management:
  - Là việc hệ thống kiểm soát các dịch vụ (hoặc daemon) mà hệ thống khởi động và dừng trong quá trình khởi động va tắt máy tính.
  - Các dịch vụ này thực hiện nhiều chức năng khác nhau và cung cấp quy trình không được gắn vào giao diện người dùng.
  - Nhiều lệnh liên quan đến quản lý dịch vụ trong Linux bao gồm systemctl start, systemctl stop, systemctl restart, systemctl reload, systemctl status và systemctl enable/disable, cùng nhiều lệnh khác.
  - Trong các bản phân phối Linux hiện đại, quản lý dịch vụ chủ yếu được xử lý bởi systemd nhưng trong các bản phân phối cũ hơn hoặc tối giản hơn, nó được xử lý bởi các hệ thống cũ hơn như SystemV hoặc Upstart.
  - VD: sử dụng lệnh để khởi chạy dịch vụ sshd: sudo systemctl start sshd.
        sử dụng lệnh kiểm tra trạng thái của dịch sshd: sudo systemctl status sshd.

  - Service Status:
    + Được sử dụng để kiểm tra trạng thái của các dịch vụ đang chạy trên hệ thống.
    + Các dịch vụ có thể bao gồm các quy trình mạng, máy chủ phụ trợ hoặc các ứng dụng chạy ở chế độ nền
    + Lệnh systemctl là lệnh được sử dụng chủ yếu để kiểm soát hệ thống systemd và trình quản lý dịch vụ.
    + Lệnh trạng thái kết hợp với systemctl đặc biệt hữu ích để kiểm tra trạng thái của dịch vụ.
    + Lệnh này cho phép quản trị viên truy vấn và kiểm soát trạng thái của hệ thống systemd và trình quản lý dịch vụ.
    + sử dụng lệnh: systemctl status tên_dịch_vụ.service để kiểm tra trạng thái của dịch vụ đang được khởi chạy hay dừng.

  - Start stop service:
    + Một trong những phần cơ bản của quản lý dịch vụ trong Linux là khởi động và dừng dịch vụ.
    + Quản trị viên hệ thống thường cần khởi động, dừng hoặc khởi động lại các dịch vụ sau khi cập nhật hoặc thay đổi cấu hình.
    + sử dụng lệnh systemctl để tác động đến hoạt động của các dịch vụ:
      . sudo systemctl start service: khởi chạy 1 dịch vụ.
      . sudo systemctl stop service: dừng dịch vụ.
      . sudo systemctl restart service: khởi động lại 1 dịch vụ.

  - Checking service log:
    + Log là các yếu tố cơ bản để đi sâu hơn về những gì đang diễn ra bên trong hệ thống.
    + Các bản ghi trong Log cung cấp theo trình tự thời gian về các sự kiện liên quan đến hệ thống trong việc gỡ lỗi và khắc phụ sự cố.
    + Một số log thiết yếu do các quy trình hệ thống, người dùng và hành động của quản trị viên tạo ra có thể được tìm thấy trong thư mục /var/log.
    + Hầu hết các nhật ký hệ thống được quản lý bởi systemd và có thể được kiểm tra bằng lệnh journalctl.
    + sử dụng lệnh journalctl để hiển thị toàn bộ log  từ khi khởi động cho đến thời điểm hiện tại.
    + để kiểm tra log của riêng 1 dịch vụ, sử dụng lệnh: journalctl -u service_name.

  - Create New Services:
    + Việc tạo dịch vụ trong Linux sẽ đề cập đến quá trình thiết lập các ứng dụng nền này để chạy và thực hiện các tác vụ mong muốn.
    + Quá trình này thường bao gồm việc viết các tệp dịch vụ (tập lệnh) chỉ định cách bắt đầu, dừng và khởi động lại dịch vụ bằng hệ thống quản lý dịch vụ.
    + Hệ thống quản lý dịch vụ phổ biến nhất trong các bản phân phối Linux hiện đại là systemd.
    + Với systemd, các dịch vụ được xác định bằng cách đặt các tệp đơn vị dịch vụ vào các thư mục cụ thể.
    + Các dịch vụ mới tạo khi khởi chạy sẽ được đặt trong /etc/systemd/system/ để systemd nhận ra nó.
    + Sau đó, bạn sẽ kiểm soát dịch vụ bằng systemctl, công cụ lệnh của systemd.
