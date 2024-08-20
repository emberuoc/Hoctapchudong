User Management:
  - Hệ điều hành Linux cung cấp một hệ thống quản lý người dùng có cấu trúc, cho phép nhiều người dùng tương tác với cùng một hệ thống theo cách riêng biệt.
  - Điều này bao gồm việc xác định vai trò người dùng, chỉ định quyền, nhóm, quyền sở hữu và các khía cạnh liên quan khác, đây là những nhiệm vụ quan trọng đối với quản trị viên Linux.
  - Để hoạt động trơn tru và được kiểm soát, quản lý người dùng trong Linux bao gồm các nhiệm vụ như tạo, xóa, sửa đổi người dùng và nhóm.
  - Nó cũng bao gồm việc chỉ định quyền và quyền sở hữu tệp và thư mục cho người dùng/nhóm.
  - Câu lệnh để tạo user trên linux: sudo useradd/ adduser + newuser -> tạo 1 user với account là newusser.
  - Ngược lại chúng ta sẽ có câu lệnh xóa user: sudo deluser/ userdel newuser.
  - Ngoài ra chúng ta sẽ có thêm câu lệnh passwd để tạo password cho user mới: sudo passwd newuser.
  - Để chuyển từ account này sang account khác chúng ta sử dụng lệnh su: su newuser.

  - Create/ Delete/ Update:
    + Quản lý người dùng trong Linux bao gồm việc tạo, cập nhật và xóa tài khoản người dùng để đảm bảo an ninh hệ thống và sử dụng tài nguyên hiệu quả.
    + Quản trị viên có thể tạo người dùng mới bằng các lệnh như useradd hoặc adduser, cập nhật thông tin chi tiết về người dùng như thư mục home hoặc shell đăng nhập bằng usermod và xóa người dùng bằng userdel.
    + Quản lý người dùng hiệu quả tận dụng khả năng đa người dùng của Linux, duy trì môi trường hệ thống an toàn và có tổ chức.
    + VD: tạo 2 user mới là user1 và user2 cùng password là 1.
      . sudo useradd user1, sudo useradd user2 -> tạo user1 và user2.
      . sudo passwd user1, sudo passwd user2 -> tạo pass cho user1 và user2.
      . sau đó thực hiện đổi password cho user1 (update): sudo passwd user1 -> đổi passwd thành 12345, sau khi đổi sẽ hiện lên thông báo password updated thành công.
      . thực hiện đổi tên user 1 -> hoanganh1: sudo usermod -l hoanganh1 user1.
      . thực hiện xóa user2: sudo deluser user2 -> sau khi chạy lệnh có thông báo remove thành công.
      . tương tự với Group thì thay usermod bằng groupmod với các lệnh tạo, sửa, xóa.

  - User and Group:
    + Quản lý người dùng trong Linux sử dụng nhóm người dùng để quản lý người dùng và quyền hệ thống một cách hiệu quả.
    + Nhóm người dùng là tập hợp những người dùng giúp đơn giản hóa việc quản trị hệ thống bằng cách xác định quyền truy cập vào các tài nguyên như tệp và thư mục.
    + Mỗi người dùng thuộc về một hoặc nhiều nhóm, cho phép quản trị viên cấp các đặc quyền cụ thể mà không cần quyền truy cập super user.

  - Managing permission:
    + Quyền được phân loại thành các loại đọc, ghi và thực thi và có thể được thiết lập cho chủ sở hữu tệp (người dùng), nhóm sở hữu và những người khác.
    + Các lệnh như chmod, chown và chgrp được sử dụng để xem và thao tác các quyền này.
    + Quản lý quyền đúng cách là rất quan trọng để duy trì bảo mật và tổ chức hệ thống.
      
