 1. Basic Commands: 
    - Basic command là các câu lệnh đơn giản được sử dụng để quản lý và di chuyển file trong máy tính của bạn.
    - Các câu lệnh cơ bản như:
      + cd + directory's name: Truy cập vào các directory. VD:
        . cd / : vào thư mục root.
        . cd ~ : vào thư mục home.
        . cd .. : trở lại thư mục cha của thư mục vừa ở.
      + ls: List các files và directories đang có trong directory hiện tại. VD:
        . ls -a : hiển thị toàn bộ file của thư mục đang ở bao gồm cả hidden file.
        . ls -l : hiển thị thông tin của toàn bộ file trong thư mục đang ở.
        . ls -la : hiển thị thông tin của toàn bộ file trong thư mục đang ở bao gồm cả hidden file.
      + pwd: xem vị trí chính xác của directory mà mình đang làm việc trên nó.
      + man + câu lệnh: hiện manual page của các câu lệnh đó.

  2. Moving files/ Directories:
    - Trong Linux, việc phải di chuyển các files/ Directories là một công việc vô cùng thiết yếu.
    - Để di chuyển các files/ Directories chúng ta sử dụng câu lệnh mv với syntax là: mv [option] source destination. Trong đó:
      + Source là files/ Directories chúng ta cần di chuyển.
      + Destination là đích đến, nơi lưu trữ files/ Directories được di chuyển.
    - Ngoài ra, câu lệnh mv còn được sử dụng để thay đổi tên của files/ Directory với systax mv [option] oldfilename/olddirectoryname newfilename/newdirectoryname. 
    - Câu lệnh mv được sử dụng rất rộng rãi bởi tính đơn giản và tính khả thi bất cứ khi nào bạn muốn tổ chức lại hoặc thay đổi tên cho các files/ Directories trên máy tính.
    

  3. Creating and deleting files/ Directories:
    - Với việc tạo ra các files/ Directories mới chúng ta có thể sử dụng theo syntax sau:
      + Tạo mới File: touch +filename.
      + Tạo mới Directory: mkdir directoryname.
    - Việc tạo ra các file và directory mới sẽ giúp chúng ta phân loại, tổ chức, quản lý các dữ liệu có trên máy tính tốt hơn.
    - Và ngược lại với lệnh tạo mới, chúng ta có lệnh xóa với syntax:
      + Xóa File: rm +filename.
      + Xóa Directory: rmdir +directoryname.
    - Lưu ý:
      + Lệnh xóa directory chỉ sử dụng được với các Directory trống, với các Directory có chứa data chúng ta phải thêm option -R ( hoặc -r) vào sau câu lệnh rm.
      + Việc xóa file/ Directory là một công việc vô cùng quan trọng và không được sử dụng bừa bãi, vậy nên để chắc chắn trước khi xóa hãy kiểm tra lại file/ Directory xem có chứa các data quan trọng hay không, và sau câu lệnh xóa cần có thêm option -i để đảm bảo việc           
        xác nhận xóa hoặc giữ lại file/ Directory.
    - Một số VD:
      + rm -R Directoryname : xóa Directory và mọi file có trong nó.
      + rm -i filename : Confirm lại trước khi xóa file.
      + rm -v Directoryname: giải thích câu lệnh đã làm gì.

  4. Directory Hierachy Overview:
    - Trong Linux, hiểu được hệ thống phân cấp thư mục là rất quan trọng để điều hướng và quản lý tệp hiệu quả. Cấu trúc thư mục của hệ thống Linux, còn được gọi là Tiêu chuẩn phân cấp hệ thống tệp (FHS), là một cấu trúc cây được xác định giúp ngăn chặn các tệp bị phân
      tán khắp hệ thống và thay vào đó sắp xếp chúng theo cách hợp lý và dễ điều hướng.
      + /: Root directory, the top level of the file system.
      + /home: User home directories.
      + /bin: Essential binary executables.
      + /sbin: System administration binaries.
      + /etc: Configuration files.
      + /var: Variable data (logs, spool files).
      + /usr: User programs and data.
      + /lib: Shared libraries.
      + /tmp: Temporary files.
