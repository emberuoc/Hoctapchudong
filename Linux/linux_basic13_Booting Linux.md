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
    + 
