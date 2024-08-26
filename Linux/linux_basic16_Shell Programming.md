Shell Programming:
  - Shell script là một chương trình mà shell của hệ thống thực thi.
  - Mặc dù có thể không mạnh bằng các ngôn ngữ biên dịch như C hoặc C++, nhưng lập trình shell khá hiệu quả đối với các tác vụ cấp quản trị, tự động hóa các tác vụ lặp đi lặp lại và giám sát hệ thống.
  - Hầu hết các bản phân phối Linux đều có bash (Bourne Again Shell) làm shell mặc định, không chỉ là một shell dòng lệnh tuyệt vời mà còn là một ngôn ngữ scripting nổi bật.
  - Các tập lệnh shell thường được viết trong trình soạn thảo văn bản và sau đó có thể chạy trực tiếp từ dòng lệnh Linux.
  - VD:
              + #!/bin/bash
                # My first script
                echo "Hello, World!"
    -> Lệnh ‘echo’ in đối số của nó, trong trường hợp này là “Hello, World!”, ra thiết bị đầu cuối.

  - Literal:
    + Thuật ngữ 'literal', trong khoa học máy tính và lập trình shell, đề cập đến ký hiệu để biểu diễn một giá trị cố định trong mã nguồn.
    + Trong shell script, các giá trị cố định này có thể bao gồm string literals, numeric literals hoặc boolean. Khi đọc và hiểu các script hiện có hoặc viết các script mới, điều quan trọng là phải hiểu cách thức và thời điểm sử dụng các literals này.
    + String Literals: Chúng có thể được định nghĩa bằng cách đặt văn bản giữa dấu ngoặc đơn hoặc dấu ngoặc kép. Ví dụ: 'Hello, world!' hoặc "Hello, world!".
    + Number Literals: Chúng biểu diễn một chuỗi các chữ số. Ví dụ: 25, 100 hoặc 1234.
    + Boolean Literals: Trong hầu hết các script shell Linux, 1 biểu diễn true và 0 biểu diễn false.
    + VD:
      + #!/bin/bash
        # Example of literals in shell script
 
        StringLiteral="This is a string literal"
        NumericLiteral=125
        echo $StringLiteral
        echo $NumericLiteral
      + StringLiteral và NumericLiteral là literal và echo được sử dụng để in chúng.

  - Variables:
    + Biến đóng vai trò quan trọng trong bất kỳ mô hình lập trình nào và tập lệnh shell cũng không ngoại lệ.
    + Biến được chia thành hai loại chính: Biến hệ thống và Biến do người dùng định nghĩa.
    + Biến hệ thống được tạo và duy trì bởi chính hệ thống.
    + Biến do người dùng định nghĩa được tạo và kiểm soát bởi người dùng.
    + Biến trong tập lệnh shell được định nghĩa bằng toán tử ’=’ (bằng) và giá trị có thể được truy xuất bằng cách thêm tiền tố ’$’ (đô la) vào tên biến.
    + VD:
      + # tạo biến người dùng định nghĩa
        MY_VARIABLE="Hello World"

        # in giá trị của biến ra thiết bị đầu cuối
        echo $MY_VARIABLE  # Output: Hello World

  - Loops:
    + Vòng lặp trong lập trình shell là một khái niệm cơ bản cho phép một khối mã nhất định được thực thi nhiều lần dựa trên một điều kiện nhất định.
    + Chúng rất quan trọng để tự động hóa các tác vụ lặp đi lặp lại, do đó làm cho quá trình mã hóa hiệu quả hơn và ít xảy ra lỗi hơn.
    + Trong Linux, các tập lệnh shell thường sử dụng ba loại vòng lặp - for, while và until.
    + for lặp lại danh sách các mục và thực hiện các hành động trên từng mục.
    + while thực thi các lệnh miễn là điều kiện điều khiển vẫn đúng.
    + until chạy các lệnh cho đến khi điều kiện điều khiển trở thành đúng.
    + VD:
      + for i in 1 2 3
        do
        echo "$i"
        done
      + Kết quả trả về sẽ là 1, 2, 3.

  - Conditionals:
    + Một câu lệnh có điều kiện có thể được định nghĩa là một phần không thể thiếu của tập lệnh shell hướng dẫn trình thông dịch vào đúng đường dẫn thực thi tùy thuộc vào các điều kiện đã cho.
    + Trong shell, các lệnh chính được sử dụng cho các câu lệnh có điều kiện là if, elif (else if) và else.
    + Các lệnh này được sử dụng để kiểm soát quy trình dựa trên kết quả của các bài kiểm tra có điều kiện có thể đánh giá giá trị của các biến chuỗi, các bài kiểm tra số học hoặc trạng thái của một quy trình.
    + VD:
      + #!/bin/sh
        a=10
        b=20
        
        if [ $a -lt 20 ]
        then
           echo "a is less than b"
        elif [ $a -gt 20 ]
        then
           echo "a is greater than b"
        else
           echo "a is equal to b"
        fi
      + Nếu điều kiện là đúng, thì khối mã bên trong câu lệnh if được thực thi, nếu không, nó sẽ chuyển sang điều kiện elif, v.v.
      + Nếu không có điều kiện nào trong số đó được thỏa mãn, thì khối mã bên trong câu lệnh else sẽ được thực thi.
  
  - Debugging:
    + Lập trình shell trong Linux cho phép bạn tự động hóa các tác vụ và quản lý hệ thống với hiệu quả cao.
    + Tuy nhiên, xét đến bản chất phức tạp của các tập lệnh shell, gỡ lỗi là một kỹ năng thiết yếu để xử lý lỗi và cải thiện hiệu suất mã.
    + Khi gặp sự cố trong tập lệnh shell, bạn có một số công cụ gỡ lỗi theo ý mình trong môi trường Linux.
    + Một số công cụ gỡ lỗi này bao gồm các tùy chọn -x (hoặc -v) của bash shell, cho phép theo dõi thực thi.
    + Các công cụ khác như trap, set command hoặc thậm chí tận dụng các công cụ gỡ lỗi bên ngoài như shellcheck cũng có thể rất hiệu quả.
