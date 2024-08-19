Text Processing:
  - Text Processing là một nhiệm vụ thiết yếu đối với quản trị viên hệ thống và nhà phát triển. Linux, là một hệ điều hành mạnh mẽ, cung cấp các công cụ mạnh mẽ để tìm kiếm, thao tác và xử lý văn bản.
  - Người dùng có thể sử dụng các lệnh như awk, sed, grep và cut để lọc văn bản, thay thế và xử lý các biểu thức chính quy.

  - stdout/stderr:
    + Các khái niệm stdout và stderr trong Linux thuộc về các nguyên tắc cơ bản của xử lý văn bản Linux.
    + Trong Linux, khi một chương trình được thực thi, ba kênh giao tiếp thường được mở, cụ thể là STDIN (Đầu vào chuẩn), STDOUT (Đầu ra chuẩn) và STDERR (Lỗi chuẩn). Trong đó
      . STDOUT là kênh mà đầu ra từ hầu hết các lệnh shell được gửi qua.
      . STDERR được sử dụng riêng để gửi thông báo lỗi.
    + Sự khác biệt này rất hữu ích khi viết kịch bản hoặc lập trình, vì nó cho phép bạn xử lý đầu ra bình thường và thông báo lỗi theo những cách khác nhau.
    +VD: sử dụng câu lệnh list và muốn lưu kết quả của lệnh đó vào 1 file text sử dụng lệnh: ls -l > list.txt.

  - cut:
    + Lệnh cắt là một tiện ích xử lý văn bản cho phép bạn cắt các phần của mỗi dòng từ tệp hoặc đầu ra và hiển thị trên đầu ra chuẩn (thường là thiết bị đầu cuối).
    + Lệnh này thường được sử dụng trong các scripts và pipelines, đặc biệt là đối với các hoạt động tệp và thao tác văn bản.
    + Lệnh cut sử dụng cú pháp cơ bản sau: cut <option> <file>.
    + VD: sử dụng lệnh cut để lấy ra các ký tự trong chuỗi Hello world: echo '"Hello world" | cut -b 1,2,3,4,5 -> kết quả hiển thị là Hello.

  - paste:
    + paste là một tiện ích xử lý văn bản mạnh mẽ chủ yếu được sử dụng để hợp nhất các dòng từ nhiều tệp.
    + Nó cho phép người dùng kết hợp dữ liệu theo cột thay vì theo hàng, tăng tính linh hoạt to lớn cho việc thao tác dữ liệu văn bản.
    + VD: muốn ghép data của 2 file text là ubuntu và centos chỉ cần dùng câu lệnh: paste ubuntu contos > combined.txt -> data từ 2 file ubuntu và centos đã được lưu trong file combined.txt.

  - sort:
    + Lệnh sort trong Linux được sử dụng để sắp xếp nội dung của tệp văn bản theo từng dòng.
    + Có thể sử dụng lệnh này để sắp xếp dữ liệu trong tệp theo nhiều cách khác nhau như theo thứ tự bảng chữ cái, theo số, theo thứ tự ngược lại hoặc thậm chí theo tháng.
    + Lệnh sort lấy một tệp làm đầu vào và in nội dung đã sắp xếp trên đầu ra chuẩn (màn hình).
    + VD : file number.txt có 1 cột các số ngẫu nhiên, để sắp xếp chúng theo thứ tự tăng dần sử dụng lệnh: sort -n number.txt, hoặc muốn sắp xếp theo thứ tự giảm dần: sort -rn number.txt.

  - pipe:
    + Pipe (|) là một tính năng mạnh mẽ trong Linux dùng để kết nối hai hoặc nhiều lệnh với nhau.
    + Đối với xử lý văn bản, sử dụng pipe đặc biệt hữu ích vì nó cho phép bạn thao tác, phân tích và chuyển đổi dữ liệu văn bản mà không cần tạo các tệp hoặc chương trình trung gian.
    + VD: để sắp xếp đầu ra của lệnh ls theo kích thước của tệp: ls -la | sort -k5 -rn.

  - grep:
    + nó là 1 câu lệnh tiện ích để tìm kiến các tệp văng bản bằng cách sử dụng các biểu thức chính quy.
    + Ngoài ra, nó cho phép bạn tìm các dòng khớp với một mẫu hoặc biểu thức cụ thể.
    + VD: chúng ta có 1 file text là tools.txt có data là Linux, Docker,Git,Github,Kubernetes. 
      . Sử dụng lện grep để tìm ra các từ chứ chữ Git trong file tools.txt: grep "Git" tools.txt
      . Kết quả trả về là Git và Github.

  - sed:
    + sed là trình soạn thảo luồng cho phép thao tác văn bản không tương tác.
    + Nó cho phép bạn sửa đổi, thay thế hoặc xóa các mẫu văn bản trong tệp.
    + sed hoạt động bằng cách xử lý văn bản theo từng dòng, áp dụng một tập lệnh chỉnh sửa được chỉ định trong tập lệnh hoặc trực tiếp trên dòng lệnh.
    + VD:
      . Gõ câu lệnh: sed 's/từ cần thay thế/từ thay thế/g. Trong đó:
        _ s có nghĩa là chúng ta muốn thay thế 1 từ (substiute).
        _ g là thực thi lệnh trên toàn bộ các trường hợp có chứa từ cần thay thế (globally). 
      . Gõ câu lệnh: sed '1d' text.txt -> lệnh sẽ xóa dòng đầu tiên trong file text.txt.

  - awk:
    + awk là một công cụ xử lý văn bản đa năng để trích xuất và thao tác dữ liệu.
    + Nó xử lý các tệp văn bản theo từng dòng, cho phép bạn thực hiện các phép tính, định dạng đầu ra và tạo báo cáo.
    + Nó sử dụng mô hình hành động mẫu, trong đó bạn chỉ định các mẫu để khớp và các hành động để thực hiện trên các dòng khớp.
    + Vd có 1 file data.csv, sử dụng lệnh cat data.csv đó và kết quả hiển thị: 
          index,ean,stock,price
          1,2010743556564,669,135
          2,2668829157992,476,584
          3,0429683856399,875,44    
          4,2548029150224,77,251
          5,3442300385932,742,737
      .sử dụng lệnh awk để lấy data chỉ riêng dòng thứ 3 của file: awk -F, {print $3} data.csv, kết quả hiển thị: 
          stock
          669
          476
          875
          77
          742

