Working with files
  - Làm việc với Files là 1 kỹ năng vô cùng thiết yếu mà mọi người dùng linux cần phải hiểu và ứng dụng thành thạo.
  - có thể chia các kỹ năng làm việc với file ra thành 4 phần:
    + File Permissions.
    + Archiving and Compressing.
    + Copying and Renaming.
    + Soft Links/ Hard Links.

1. File Permission:
  - Trong Linux, các thao tác, tác động đến file được gán cho các files và directories dưới dạng quyền.
  - Các quyền này sẽ đưa ra các user nào có thể đọc, ghi, sửa, xóa, thực thi, etc trên các File, Directory đã được gắn các quyền đó.
  - Trên thực tế, quyền được gán cho các file để ngăn chặn những user không có quyền thực hiện tác động, thay đổi hệ thống có thể ảnh hưởng đến hoạt động của hệ thống cũng như những user khác.
  - VD: 
    + Thực hiện lệnh touch file1 file2 file3 để tạo ra 3 life là file1 file2 file3.
    + Sau đó sử dụng lệnh ls -l file1 ta sẽ có kết quả là: -rw-rw-r-- 1 ubuntu1 ubuntu1 0 Aug 17 20:37 file1. Trong đó:
      . ở cột đầu tiên -rw-rw-r-- có dấu - ở đầu tiên tương đương với việc file 1 là 1 file thường ( nếu nó là d thì sẽ là 1 directory, l sẽ là symbiolink, etc).
      . Tiếp theo là rw- sau dấu - đầu tiên sẽ là quyền của các user là đọc và viết, 3 ký tự rw- sau đó tương ứng với quyền của nhóm chứa các user được tác động lên file này là quyền đọc và viết, cuối cùng là 3 ký tự r-- là các user không nằm trong nhóm được phân quyền sẽ chỉ có quyền là đọc file1.
      . Tiếp theo là số link = 1, sau đó là owner và group sẽ là ubuntu1, kế tiếp là size của file1, cuối cùng là thời gian được tạo của file.
    + Sau khi đã xem thông tin, chúng ta có thể sử dụng lệnh chmod để thay đổi quyền của file với syntax: chmod +quyền +tên file. VD:
      . Chuyển quyền của file1 thành đọc,viết và thực thi cho user, đọc cho group và không có quyền gì cho các user khác: sudo chmod 740 file1, trong đó 3 số 740 với số 7 đầu tiên là cho owner với toàn quyền tác động lên file, 4 là đahi diện cho group với quyền chỉ đọc, và cuối cùng 0 là đại diện cho các user khác không có quyền trên file1.
      . Sau khi chạy lệnh trên, chúng ta kiểm tra lại với lệnh ls -l và thấy quyền của file 1 đã được thay đổi.
      . Chúng ta còn 1 cách khác là sử dụng câu lệnh: sudo chmod u=rwx,g=r,o=- file1, trong đó u là đại diện cho user sở hữu, g là đại diện cho group, o là other. Kết quả ta nhận được giống với câu lệnh bên trên.
    + Ngoài ra chúng ta có thể tác động lên file bằng cách thay đổi owner hoặc group có quyền tác động lên file.
      . sử dụng lệnh sudo chown để thay đổi owner: sudo chown tên user.
      . sử dụng lệnh sudo chgrp để thay đổi group có quyền lên file: sudo chgrp tên group.

2. Archiving and Compressing:
  - Linux cung cấp các tiện ích mạnh mẽ để lưu trữ, trong đó nhiều tệp và thư mục được kết hợp thành một tệp duy nhất, chủ yếu để sao lưu và đơn giản hóa việc phân phối.
  - Các công cụ chính được sử dụng cho mục đích này là tar, gzip và bzip2.
  - Lệnh tar là một công cụ đa năng có thể quản lý và sắp xếp các tệp thành một kho lưu trữ.
  - gzip và bzip2 được sử dụng để nén tệp, giảm kích thước tệp và giúp truyền dữ liệu dễ dàng hơn.
  - VD:
      + sử dụng lệnh tar để nén file, giải nén, giả sử chúng ta có 6 file là file1, file2, file3, file4, file5 và file 6:
        . sử dụng lệnh tar để nén file1/file2 và thành 1 file nén file12: tar cvf file12.tar file1 file2, sau đó check lại bằng lệnh ls -l, ta có thể thấy file nén đã được tạo.
        . sử dụng lệnh tar để giải nén: tar xvf file12.tar.
        . sử dụng lệnh: tar zcvf tên-file-nén.tar.gz + file1 + file2 để tạo file nén đuôi gzip.
        . sử dụng lệnh: tar cvjf tên-file-nén.tar.bz2 + các file cần nén để tạo file nén đuôi bzip2.

3. Copying and Renaming:
  - sử dụng các lệnh cp để copy, mv để đổi tên file.
  - VD : 
    + copy file text1.txt từ /Desktop/dir1 sang /Desktop/dir2, sử dụng lệnh: cp ~/Desktop/dir1/text1.txt ~/Desktop/dir2/text1.txt.
    + đổi tên file text2.txt trong dir1 thành text2.txt sử dụng lệnh: mv ~/Desktop/dir2/text1.txt ~/Desktop/dir2/text2.txt.

4. Soft links/ Hard links:
  - Trong linux, soft links và hard links có thể tương đương với shortcut và copy file như trong windows.
  - Để tạo soft link sử dụng câu lệnh: ln -s filename soft_link name.
  - Để tạo harc link sử dụng câu lệnh: ln filename hard_link name.
  
