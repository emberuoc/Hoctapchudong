Package Management:
  - Quản lý gói là một khái niệm quan trọng trong Linux giúp xử lý các gói (tập hợp các tệp) cho phép người dùng cài đặt phần mềm mới bằng các lệnh đơn lẻ mà còn giúp quản lý các phần mềm hiện có bao gồm cài đặt, cập nhật, định cấu hình và xóa các gói phần mềm.
  - Quản lý gói kết hợp một hệ thống chuẩn hóa theo dõi các điều kiện tiên quyết của mọi phần mềm và xử lý việc cài đặt, cập nhật và xóa.
  - Một số trình quản lý gói thường được sử dụng là apt (Advanced Packaging Tool) cho các bản phân phối dựa trên Debian, yum (Yellowdog Updater, Modified) và dnf (Dandified YUM) cho các bản phân phối dựa trên Red-Hat và pacman cho Arch Linux.

  - Package repository:
    + Quản lý gói trong Linux liên quan đến việc xử lý các gói hoặc mô-đun phần mềm, hợp lý hóa quy trình cài đặt, nâng cấp và cấu hình các bản phân phối Linux.
    + Trọng tâm của quản lý gói là các kho lưu trữ, các thành phần quan trọng lưu trữ và quản lý các bộ sưu tập các gói phần mềm.
    + Kho lưu trữ trong Linux là vị trí lưu trữ mà hệ thống lấy và cài đặt các bản cập nhật và ứng dụng hệ điều hành cần thiết.
    + Các kho lưu trữ này chứa hàng nghìn Gói phần mềm hoặc Gói RPM được biên dịch cho các bản phân phối Linux cụ thể.
    + Kho lưu trữ cụ thể được sử dụng phụ thuộc vào bản phân phối Linux (như Ubuntu, Fedora, v.v.) và định dạng gói mà bản phân phối sử dụng (như .deb trong Debian và Ubuntu hoặc .rpm trong Fedora và CentOS).
    + Kho lưu trữ cung cấp phương pháp cập nhật các công cụ và ứng dụng trên hệ thống Linux của bạn và chúng cũng đảm bảo tất cả các bản cập nhật và phụ thuộc hoạt động cùng nhau và được kiểm tra để tích hợp trước khi chúng được phát hành.
    + Không có cách chuẩn nào để sử dụng các kho lưu trữ trên nhiều bản phân phối khác nhau, mỗi kho lưu trữ đều có bộ kho lưu trữ được cấu hình sẵn.
    + VD:
      . sudo apt update: câu lệnh update repository trên Ubuntu.
      . sudo yum update: câu lệnh update repository trên CentOS hoặc Fedora.
      . raco pkg update: câu lệnh update tất cả các package đã cài đặt trên Racket.

  - snap:
    + Snap là một phương pháp tiếp cận hiện đại để quản lý gói trong các hệ thống Linux được Canonical (công ty đứng sau Ubuntu) thúc đẩy.
    + Không giống như các hệ thống quản lý gói truyền thống như dpkg hoặc RPM, Snap tập trung vào việc cung cấp phần mềm dưới dạng các gói độc lập (được gọi là 'Snap') bao gồm tất cả các phụ thuộc của chúng.
    + Điều này đảm bảo rằng ứng dụng Snap chạy nhất quán trên nhiều bản phân phối Linux khác nhau.
    + Snap được cài đặt từ cửa hàng Snapcraft và được tự động cập nhật trong nền.
    + Quá trình cập nhật Snap là transactional, nghĩa là nếu có sự cố xảy ra trong quá trình cập nhật, Snap có thể tự động trở lại phiên bản hoạt động trước đó.
    + syntax: sudo snap install [package_name].
   
  - Finding and installing packages:
    + Khả năng tìm và cài đặt các gói phần mềm hiệu quả là một kỹ năng cơ bản khi làm việc với các hệ thống dựa trên Linux.
    + Các công cụ quản lý gói Linux như apt, yum hoặc dnf được sử dụng để tự động hóa quy trình cài đặt, nâng cấp, cấu hình và xóa các gói phần mềm theo cách nhất quán.
    + Điều quan trọng là phải hiểu cách quản lý gói hoạt động trong Linux, vì nó đơn giản hóa đáng kể quy trình quản lý phần mềm, loại bỏ nhu cầu tải xuống, biên dịch và cài đặt phần mềm thủ công từ mã nguồn.
    + VD:
      . Với các bản phối debian-base như Ubuntu thì có thể sử dụng lệnh apt hoặc apt-get để cài đặt packages.
      . Với các bản phối như Fedora hoặc CentOS thì dùng yum hoặc dnf.

  - Listing installed packages:
    + Các trình quản lý gói trong linux giúp chúng ta cài đặt, cập nhật hoặc xóa phần mềm theo cách có hệ thống.
    + Mỗi bản phân phối Linux có thể đi kèm với hệ thống quản lý gói riêng. Ví dụ bao gồm apt trong các hệ thống dựa trên Debian, dnf trong Fedora, zypper trong OpenSUSE và pacman trong Arch Linux.
    + Một tác vụ phổ biến mà bạn thường cần là liệt kê các gói đã cài đặt trong hệ thống của mình.
    + Tác vụ này có thể giúp ích trong nhiều tình huống khác nhau như kiểm tra phần mềm đã cài đặt, viết tập lệnh hoặc tự động triển khai phần mềm trên máy mới.
    + Để list các dịch vụ đã được cài đặt, sử dụng lệnh sudo apt list --installed.

  - Install/ Update/ Remove Packages:
    + Các gói trong Linux là các mô-đun phần mềm được biên dịch trước bao gồm các tệp thực thi và tệp cần thiết để chạy và sử dụng phần mềm.
    + Các bản phân phối Linux sử dụng các trình quản lý gói khác nhau như apt cho các bản phân phối dựa trên Debian/Ubuntu, yum và dnf cho Fedora/RHEL/CentOS và zypper cho SUSE.
    + Quản lý các gói bao gồm các tác vụ như cài đặt các gói phần mềm mới, xóa các gói không sử dụng và nâng cấp các gói hiện có lên phiên bản mới hơn.
    + Tất cả các tác vụ này có thể được thực hiện bằng cách sử dụng các hướng dẫn dòng lệnh dành riêng cho từng trình quản lý gói.
