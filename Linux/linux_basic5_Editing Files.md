1. Editing Files:
  - Linux, giống như các hệ điều hành khác, cho phép chỉnh sửa tệp cho nhiều mục đích, cho dù bạn cần cấu hình một số chức năng hệ thống hay viết tập lệnh. 
  - Có nhiều trình soạn thảo văn bản có sẵn trong Linux theo mặc định, bao gồm: nano, vi/ vim, emacs và gedit.
  - Ví dụ, nano là trình soạn thảo văn bản cơ bản, dễ sử dụng và hoàn hảo để chỉnh sửa tệp văn bản đơn giản. 
  - Mặt khác, vi/ vim tiên tiến hơn và cung cấp nhiều tính năng và lệnh.
  - Để sử dụng các lệnh này chúng ta thực hiện theo syntax sau:
    + nano + filename.
    + vi/vim + filename.
    + gedit + filename.

2. vi/ vim:
  - Lệnh vi/ vim + filename sẽ sử dụng để chỉnh sửa nội dung file, nếu file chưa tồn tại trong Directory thì sẽ tạo mới.
  - Lệnh vi/ vim chạy ở 2 chế độ khác nhau là command mode và insert mode:
    + Để chuyển từ command mode sang insert mode, chúng ta sử dụng các phím i, a, o. trong đó
      . i để thêm ký tự trước con trỏ.
      . a để thêm ký tự sau con trỏ.
      . o để chèn thêm dòng mới sau con trỏ.
    + Để chuyển từ insert mode sang command mode, chúng ta sử dụng phím ESC ( có thể dịch chuyển qua lại giữa 2 mode này bằng phím ESC)
    + Một số lệnh cơ bản với vi trong command mode:
      . :w lưu tập tin.
      . :x lưu tập tin và thoát.
      . :wq lưu tập tin và thoát.
      . :q thoát và không lưu.
      . :set nu hiện số dòng.
      . :set nonu bỏ hiện số dòng.

3. nano:
  - Tương tự như lệnh vi/ vim, nano cũng được sử dụng để chỉnh sửa nội dung file và tạo mới nếu file chưa tồn tại.
  - nano là lệnh để dùng trình soạn thảo văn bản cơ bản nên sẽ dễ dàng sử dụng hơn vi/ vim.
  - Khi sử dụng lệnh nano, bên dưới đã có các option để hướng dẫn người dùng sử dụng với dấu ^ kèm theo 1 ký tự (dấu ^ đại diện cho nút Ctrl).
