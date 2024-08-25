Networking:
  - Mạng cho phép các hệ thống Linux kết nối, tương tác và chia sẻ tài nguyên với các hệ thống khác, có thể là Linux, Windows, macOS hoặc bất kỳ hệ điều hành nào khác.
  - Linux cung cấp nhiều công cụ và lệnh để quản lý giao diện mạng, xem chi tiết cấu hình, khắc phục sự cố và tự động hóa các tác vụ, chứng minh tính mạnh mẽ và linh hoạt của nó.
  - Linux network stack được đánh giá cao về hiệu suất, khả năng chạy các cấu hình quy mô lớn và toàn diện, cũng như hỗ trợ nhiều giao thức mạng khác nhau.
  - Linux áp dụng phương pháp dựa trên tệp để cấu hình mạng, lưu trữ các thiết lập và cấu hình liên quan đến mạng trong các tệp chuẩn, chẳng hạn như /etc/network/interfaces hoặc /etc/sysconfig/network-scripts/, tùy thuộc vào bản phân phối Linux.
  - sử dụng lệnh: ifconfig -> xuất thông tin về tất cả các giao diện mạng hiện đang hoạt động trên hệ thống.
  - ifconfig đang trở nên lỗi thời và được thay thế bằng ip, cung cấp nhiều tính năng và khả năng hơn.

  - TCP/IP Stack:
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

  - Ethernet, ARRP/RARP:
    + Ba thành phần quan trọng bao gồm Ethernet, ARP (Giao thức phân giải địa chỉ) và RARP (Giao thức phân giải địa chỉ ngược).
    + Ethernet: Đây là công nghệ LAN (Mạng cục bộ) được cài đặt rộng rãi nhất, cho phép các thiết bị giao tiếp trong mạng cục bộ.
    + ARP: Đúng như tên gọi, nó cung cấp khả năng phân giải địa chỉ, chuyển đổi địa chỉ IP thành địa chỉ MAC (Kiểm soát truy cập phương tiện), tạo điều kiện cho giao tiếp mạng trực tiếp hơn.
    + RARP: Đây là Giao thức phân giải địa chỉ ngược, hoạt động theo cách ngược lại với ARP, nó chuyển đổi địa chỉ MAC thành địa chỉ IP, hữu ích trong các tình huống khi máy tính biết địa chỉ MAC của mình nhưng cần tìm ra địa chỉ IP của mình.
    + Kiến thức về các thành phần này là điều không thể thiếu trong việc chẩn đoán và quản lý các sự cố mạng trong Linux

  - DHCP:
    + Dynamic Host Configuration Protocol (DHCP) được sử dụng để phân bổ địa chỉ IP động trong mạng.
    + Máy chủ DHCP quản lý hiệu quả các địa chỉ IP và thông tin liên quan đến chúng, đảm bảo rằng mỗi máy khách nhận được một IP duy nhất và tất cả thông tin mạng chính xác.
    + Trong Linux, DHCP có thể được cấu hình và quản lý bằng các lệnh đầu cuối bao gồm việc cài đặt phần mềm máy chủ DHCP, chỉnh sửa các tệp cấu hình và quản lý các dịch vụ của máy chủ.
    + Máy chủ DHCP truyền thống phải có địa chỉ IP tĩnh để quản lý phân phối IP hiệu quả, DHCP trong Linux cũng xử lý DNS và các dữ liệu liên quan khác mà mạng của bạn có thể yêu cầu.
    + Sử dụng lệnh: sudo apt-get install isc-dhcp-server -> cài đặt DHCP
    + Mọi cấu hình của máy chủ DHCP đều được thực hiện trong file cấu hình nằm tại /etc/dhcp/dhcpd.conf, có thể chỉnh sửa bằng bất kỳ trình soạn thảo văn bản nào.

  - IP Routing:
    + Định tuyến IP trong Linux đề cập đến quá trình thiết lập bảng định tuyến và cấu hình các tuyến mạng cho các giao diện mạng trong hệ điều hành Linux.
    + Hạt nhân chịu trách nhiệm xử lý bao gồm việc lựa chọn các đường dẫn để gửi các gói tin mạng đến đích dự định của chúng trên mạng.
    + Công cụ dòng lệnh chính để cấu hình mạng trong Linux trước đây là ifconfig, nhưng hiện nay hầu hết đã được thay thế bằng lệnh ip.
    + Sử dụng lệnh: ip route show -> trả về list tất cả các routes mà kernel biết đến.
   
  - DNS Resolution:
    + Domain Name System (DNS) là một hệ thống phi tập trung được sử dụng để chuyển đổi tên máy chủ thành địa chỉ IP, giúp người dùng dễ dàng truy cập các trang web mà không cần phải nhớ các địa chỉ IP số cụ thể.
    + Trên các hệ thống Linux, khi một ứng dụng cần kết nối đến một URL nhất định, nó sẽ tham khảo trình phân giải DNS.
    + Trình phân giải này, sử dụng tệp /etc/resolv.conf, giao tiếp với máy chủ DNS, sau đó chuyển đổi URL thành địa chỉ IP để thiết lập kết nối mạng.
    + Sử dụng lệnh: nslookup www.google.com/ dig www.google.com -> truy vấn DNS và lấy địa chỉ IP của www.google.com.
   
  - Netfilter:
    + Netfilter là một công cụ mạnh mẽ có trong Linux, cung cấp chức năng điều khiển và thay đổi các gói tin mạng.
    + Nó hoạt động như một giao diện giữa hạt nhân và gói tin, cho phép thao tác và chuyển đổi các gói tin trong quá trình truyền tải.
    + Ứng dụng chính của Netfilter là phát triển các hệ thống tường lửa và quản lý dịch địa chỉ mạng (NAT).
    + Trong Linux, netfilter cực kỳ quan trọng do phạm vi ứng dụng rộng, từ kiểm soát lưu lượng, sửa đổi gói tin, ghi nhật ký và phát hiện xâm nhập mạng.
    + Cấu trúc của netfilter cho phép chèn các chức năng tùy chỉnh, thường được gọi là hook, vào ngăn xếp mạng của hạt nhân.
    + Các hook này có thể thao tác hoặc kiểm tra các gói tin ở nhiều giai đoạn khác nhau như định tuyến trước, cục bộ vào, chuyển tiếp, cục bộ ra và hậu định tuyến.
    + Một công cụ phổ biến được sử dụng kết hợp với netfilter là iptables, cung cấp cơ chế để định cấu hình các bảng trong hạt nhân do Netfilter Framework cung cấp.
    + sử dụng lệnh: iptables -A INPUT -i eth0 -s 192.168.0.0/24 -m netfilter --netfilter-name example --action drop -> tạo firewall rule bằng iptable và netfilter module. Trong đó:
      + ‘-A INPUT’ đang thêm một quy tắc mới vào chuỗi ‘INPUT’.
      + ‘-i eth0’ đang chỉ định giao diện mạng và ‘-s 192.168.0.0/24’ đang chỉ định phạm vi địa chỉ IP cho quy tắc.
      + ‘-m netfilter’ đang gọi mô-đun netfilter, ‘—netfilter-name example’ đang đặt tên cho quy tắc.
      + ‘—action drop’ đang chỉ định cách xử lý các gói tin khớp (Trong trường hợp này, loại bỏ chúng).

  - SSH:
    + Secure Shell (SSH) là giao thức mạng mã hóa chủ yếu được sử dụng để truyền dữ liệu an toàn, đăng nhập dòng lệnh từ xa, thực thi lệnh từ xa và các dịch vụ mạng an toàn khác giữa hai máy tính được kết nối mạng.
    + Nhấn mạnh vào tính bảo mật, toàn vẹn và an toàn của dữ liệu trong quá trình truyền, SSH cung cấp phương pháp truy cập từ xa an toàn hơn nhiều so với các phương pháp không an toàn khác, chẳng hạn như Telnet.
    + Do tầm quan trọng và mức độ sử dụng rộng rãi của nó, việc hiểu rõ chức năng của nó là điều cần thiết đối với bất kỳ ai muốn điều hướng hệ điều hành Linux và quản lý mạng hiệu quả.
    + Ví dụ sử dụng lệnh: ssh hoanganh@192.168.1.1 -> kết nối SSH từ local machine tới remote server.
    + Trong lệnh trên, ‘hoanganh’ biểu thị tên tài khoản người dùng từ xa và ‘192.168.1.1’ là địa chỉ IP của máy chủ từ xa mà bạn đang cố gắng truy cập.
   
  - File Tranfer:
    + Trong Linux, truyền tệp là hành động sao chép hoặc di chuyển tệp từ máy tính này sang máy tính khác qua kết nối mạng.
    + Khái niệm này rất quan trọng đối với quản trị viên hệ thống và người dùng cuối cần có khả năng chia sẻ tệp giữa các hệ thống hoặc mạng.
    + Linux cung cấp một số công cụ dòng lệnh và ứng dụng để truyền tệp qua mạng. Các công cụ này hỗ trợ nhiều giao thức chuẩn như FTP, HTTP, SCP, SFTP và NFS.
    + Một số lệnh truyền tệp nổi tiếng nhất bao gồm scp, rsync và wget.
    + VD: scp /path/to/local/file username@remote:/path/to/destination -> sao chép tệp vào hệ thống từ xa được chỉ định.

