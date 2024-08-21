Disks and Filesystems:
  - Linux sử dụng nhiều hệ thống tệp khác nhau để cho phép chúng ta lưu trữ và truy xuất dữ liệu từ phần cứng của hệ thống máy tính như disk.
  - Hệ thống tệp xác định cách dữ liệu được sắp xếp, lưu trữ và truy xuất trên các thiết bị lưu trữ này.
  - Ví dụ về các hệ thống tệp Linux phổ biến bao gồm EXT4, FAT32, NTFS và Btrfs.
  - Mỗi hệ thống tệp có những ưu điểm, nhược điểm và trường hợp sử dụng riêng.
  - VD:
    + EXT4 thường được sử dụng cho các ổ đĩa hệ thống Linux do tính mạnh mẽ và khả năng tương thích với Linux.
    + FAT32 có thể được sử dụng cho phương tiện di động như ổ USB vì khả năng tương thích với hầu hết mọi hệ điều hành.

  - Inodes:
    + Inode là cấu trúc dữ liệu lưu trữ thông tin quan trọng về tệp ngoại trừ tên và dữ liệu thực tế của tệp bao gồm kích thước tệp, chủ sở hữu, quyền truy cập, thời gian truy cập, etc.
    + Mỗi tệp hoặc thư mục trong hệ thống tệp Linux đều có một inode duy nhất và mỗi inode được xác định bằng số inode trong hệ thống tệp riêng của nó.
    + Số inode này cung cấp một cách theo dõi từng tệp, hoạt động như một mã định danh duy nhất cho hệ điều hành Linux.
    + Bất cứ khi nào một tệp được tạo trong Linux, tệp đó sẽ tự động được gán một inode lưu trữ siêu dữ liệu của tệp đó.
    + Cấu trúc và lưu trữ inode được xử lý bởi hệ thống tệp, nghĩa là loại và lượng siêu dữ liệu trong inode có thể khác nhau giữa các hệ thống tệp.
    + Việc hiểu inode có thể rất hữu ích khi xử lý các thao tác tệp nâng cao, chẳng hạn như tạo liên kết hoặc khôi phục tệp đã xóa.
    + Để kiểm tra thông tin inode của file dữ liệu trên linux sử dụng lệnh: ls -i tên_file.

  - Filesystems:
    + Hệ thống tệp là cách các tệp được lưu trữ và sắp xếp trên đĩa lưu trữ.
    + Đây là thành phần quan trọng của hệ thống vì nó đảm bảo tính toàn vẹn, độ tin cậy và khả năng truy cập dữ liệu hiệu quả.
    + Đĩa được cài đặt trong hệ thống Linux có thể được chia thành nhiều phân vùng, mỗi phân vùng có hệ thống tệp riêng.
    + Linux hỗ trợ nhiều loại hệ thống tệp khác nhau, chẳng hạn như EXT4, XFS, BTRFS, etc -> mỗi loại đều có những ưu điểm riêng về hiệu suất, tính toàn vẹn của dữ liệu và các tùy chọn khôi phục.
    + Tất cả các tệp và thư mục bắt đầu từ thư mục gốc, được biểu thị bằng '/'.
    + Hiểu được khái niệm và cách quản lý hệ thống tệp là chìa khóa để quản lý thành công các hệ thống Linux, vì nó liên quan đến các tác vụ thường xuyên như gắn/gỡ ổ đĩa, kiểm tra dung lượng đĩa, quản lý quyền tệp và sửa chữa các hệ thống tệp bị hỏng.
    + Để hiển thị hệ thống tập tin trên linux: df -T.

  - Mounts:
    + Lệnh mount trong Linux được sử dụng để gắn hệ thống tệp.
    + Khi một hệ thống tệp cụ thể được 'gắn' vào một thư mục cụ thể, hệ thống có thể bắt đầu đọc dữ liệu từ thiết bị và diễn giải dữ liệu đó theo các quy tắc của hệ thống tệp.
    + Linux có một thư mục đặc biệt, /mnt, thường được sử dụng làm điểm gắn tạm thời cho các hoạt động gắn và tháo gắn thủ công.
    + VD : sử dụng lệnh mount /dev/sdb1 /mnt để gắn hệ thống tệp vào phân vùng thứ 2 của ổ cứng thứ 2 tại thư mục /mnt.
    
