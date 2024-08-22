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
    
  - Adding disks:
    + Khi bạn thêm đĩa mới vào Linux, bạn cần chuẩn bị chúng trước khi có thể sử dụng.
    + Quá trình này bao gồm việc tạo phân vùng trên đĩa, tạo hệ thống tệp trên các phân vùng, sau đó gắn hệ thống tệp vào các thư mục trong cây thư mục của hệ thống.
    + Điều này rất quan trọng, đặc biệt khi làm việc với nhiều ổ đĩa hoặc các đơn vị lưu trữ dữ liệu lớn để tạo trải nghiệm người dùng liền mạch.
    + Cách tạo và add ổ đĩa mới:
      . Sử dụng lsblk để liệt kê tất cả các thiết bị khối (đĩa và phân vùng).
      . Sử dụng fdisk /dev/sdX để tạo một phân vùng mới trên đĩa.
      . Sử dụng mkfs.ext4 /dev/sdX1 để tạo một hệ thống tệp mới trên một phân vùng.
      . Sử dụng mount /dev/sdX1 /mount/point để gắn hệ thống tệp vào một thư mục.

  - swap:
    + Nếu hệ thống cần nhiều tài nguyên bộ nhớ hơn và bộ nhớ vật lý đã đầy, các trang không hoạt động trong bộ nhớ sẽ được chuyển đến không gian hoán đổi.
    + Không gian hoán đổi là một phần của ổ đĩa cứng được sử dụng cho bộ nhớ ảo.
    + Không gian hoán đổi đảm bảo rằng bất cứ khi nào hệ thống của bạn sắp hết bộ nhớ vật lý, nó có thể di chuyển một số dữ liệu đến không gian hoán đổi, giải phóng không gian RAM, nhưng điều này đi kèm với những tác động về hiệu suất vì lưu trữ dựa trên đĩa chậm hơn RAM.
    + Trong bối cảnh của đĩa và hệ thống tệp, không gian hoán đổi có thể tồn tại ở hai nơi:
      . Trong phân vùng chuyên dụng của riêng nó.
      . Trong một tệp thông thường trong hệ thống tệp hiện có.
    + VD để thêm 1 tệp hoán đổi sử dụng lệnh fallocate -> dùng lệnh mkswap để làm tệp phù hợp với mục đích sử dụng hoán đổi.
      . fallocate -l 1G /swapfile # tạo swap file.
      . chmod 600 /swapfile # bảo mật swap file bằng cách ngăn chặn người dùng thông thường đọc nó.
      . mkswap /swapfile # thiết lập vùng hoán đổi.
      . swapon /swapfile # cho phép file hoán đổi.

  - LVM:
    + Linux Logical Volume Manager (LVM) là một thiết bị ánh xạ cung cấp quản lý ổ đĩa logic cho Linux kernel.
    + Nó được tạo ra để dễ dàng quản lý đĩa, cho phép sử dụng các thiết bị lưu trữ trừu tượng, được gọi là ổ đĩa logic, thay vì sử dụng trực tiếp các thiết bị lưu trữ vật lý.
    + LVM cực kỳ linh hoạt và các tính năng bao gồm thay đổi kích thước ổ đĩa, sao chép ổ đĩa trên nhiều đĩa vật lý và di chuyển ổ đĩa giữa các đĩa mà không cần tắt nguồn.
    + LVM hoạt động trên 3 cấp độ: Ổ đĩa vật lý (PV), Nhóm ổ đĩa (VG) và Ổ đĩa logic (LV).
      . PV là các ổ đĩa hoặc phân vùng thực tế.
      . VG kết hợp các PV thành một nhóm lưu trữ duy nhất.
      . LV tách các phần từ VG để hệ thống sử dụng.
    + Để tạo LVM, sử dụng các câu lệnh sau:
      . pvcreate /dev/sdb1: tạo ổ đĩa vật lý trên /dev/sdb1.
      . vgcreate my-vg /dev/sdb1: tạo nhóm ổ đĩa tên my-vg.
      . lvcreate -L 10G my-vg -n my-lv: thêm 10BG ổ đĩa vật lý cho nhóm ổ đĩa và đặt tên là my-lv.
