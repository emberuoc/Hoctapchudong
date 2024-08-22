Booting Linux:
  - Booting Linux là quá trình mà hệ điều hành Linux trải qua khi hệ thống máy tính được bật nguồn.
  - Khi bật thiết bị, bộ nạp khởi động hệ thống được tải vào bộ nhớ chính từ một vị trí cố định để khởi động hệ điều hành chính.
  - Toàn bộ quá trình có một số giai đoạn bao gồm POST (Power-On Self Test), MBR (Master Boot Record), GRUB (GRand Unified Bootloader), Kernel, quy trình Init và cuối cùng là GUI hoặc giao diện dòng lệnh nơi người dùng tương tác.
  - Trong quá trình này, các kiểm tra hệ thống quan trọng được thực hiện, phần cứng được phát hiện, trình điều khiển thích hợp được tải, hệ thống tệp được gắn kết, các quy trình hệ thống cần thiết được khởi động và cuối cùng, người dùng được hiển thị lời nhắc đăng nhập.
  - Ví dụ cho file cấu hình GRUB /etc/default/grub để cấu hình GRUB bootloadder options:
    + GRUB_DEFAULT=0
    + GRUB_TIMEOUT=5
    + GRUB_DISTRIBUTOR=`lsb_release -i -s 2> /dev/null || echo Debian`
    + GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
    + GRUB_CMDLINE_LINUX=""

  - Logs:
    + “Log khởi động” trong Linux đề cập đến các thông báo và thông tin được tạo ra trong quá trình khởi động.
    + Các log này ghi lại tất cả các hoạt động và sự kiện diễn ra trong khi hệ thống đang khởi động, có thể hỗ trợ chẩn đoán sự cố hệ thống hoặc hiểu hành vi của hệ thống.
    + Trong quá trình khởi động, các thông báo từ nhiều thành phần khác nhau của hệ thống như kernel, init, dịch vụ, v.v. được lưu trữ.
    + Nhiều bản phân phối Linux sử dụng hệ thống ghi nhật ký systemd, journalctl, lưu trữ nhật ký của quá trình khởi động.
    + Có thể xem thông báo khởi động theo thời gian thực bằng lệnh dmesg -> đọc và in kernel ring buffer.
    + Hoặc có thể truy cập thông báo này thông qua thiết lập ghi log của hệ thống, thường bao gồm các tệp văn bản trong /var/log.
    + Sử dụng lệnh: dmesf | less -> trình bày log khởi động theo định dạng ít trực tiếp hơn với khả năng cuộn.
   
  - Boot loader:
    + Khi hệ thống được bật, Boot Loader sẽ chịu trách nhiệm và tải kernel của hệ điều hành vào bộ nhớ của hệ thống.
    + Sau đó, kernel sẽ khởi tạo các thành phần phần cứng và tải các trình điều khiển cần thiết, sau đó khởi động trình lập lịch và thực thi quy trình init.
    + Thông thường, hai bộ nạp khởi động được sử dụng phổ biến nhất trong Linux là LILO (Linux Loader) và GRUB (GRand Unified Bootloader).
    + GRUB đặt ra tiêu chuẩn cho quá trình khởi động Linux hiện đại, cung cấp các tính năng phong phú như giao diện đồ họa, khả năng viết kịch bản và gỡ lỗi.
    + Mặt khác, LILO cũ hơn và không có nhiều tính năng bằng, nhưng chạy trên nhiều nền tảng phần cứng hơn.
    + Sử dụng lệnh sudo update-grub để update GRUB bootloader.
