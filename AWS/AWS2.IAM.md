IAM:
  - IAM, hay Identity and Access Management, trong AWS là một dịch vụ cho phép bạn quản lý quyền truy cập vào các dịch vụ và tài nguyên AWS một cách an toàn.
  - Nó cho phép bạn tạo và quản lý người dùng và nhóm AWS, và sử dụng các quyền để cho phép và từ chối quyền truy cập của họ vào các tài nguyên AWS.
  - Dịch vụ này bao gồm các tính năng như quyền truy cập được chia sẻ vào tài khoản AWS của bạn, các quyền chi tiết, liên kết danh tính (bao gồm tích hợp thư mục hoạt động), xác thực đa yếu tố (MFA) và cung cấp quyền truy cập tạm thời cho người dùng, cùng nhiều tính năng khác.
  - IAM là một Universal system, nghĩa là nó có thể truy cập toàn cầu và không phụ thuộc vào các khu vực cụ thể.

1. Policies:
  - Chính sách trong Amazon IAM (Identity and Access Mângement) là các tài liệu đóng vai trò như các vùng chứa cho các quyền.
  - Chúng được thể hiện ở định dạng JSON trong IAM và chúng xác định các hành động, hiệu ứng, tài nguyên và các điều kiện tùy chọn.
  - Có hai loại chính sách:
    + identity-based policies: được đính kèm vào danh tính IAM.
    + resource-based policies: được đính kèm vào tài nguyên.
  - Các chính sách này chỉ định những hành động nào được phép hoặc bị từ chối trên những tài nguyên nào, trong những điều kiện nào.
  - Chúng là công cụ chính của bạn trong việc xác định và quản lý các quyền trong AWS.
  1.1. Identity-based policies:
    - là một trong những loại chính sách bạn có thể tạo trong AWS (Amazon Web Services).
    - Chúng được đính kèm trực tiếp vào một danh tính (như người dùng, nhóm hoặc vai trò IAM) và kiểm soát những hành động mà danh tính đó có thể thực hiện, trên tài nguyên nào và trong điều kiện nào.
    - Có hai loại - nội tuyến và được quản lý:
      + Chính sách nội tuyến được tạo và quản lý riêng lẻ.
      + Chính sách được quản lý là chính sách độc lập có thể đính kèm vào nhiều danh tính.
    - Điều này cung cấp một khuôn khổ linh hoạt để quản lý quyền trên các tài nguyên AWS.
    - Các chính sách này được viết bằng ngôn ngữ gọi là JSON (JavaScript Object Notation).
  1.2. Resource-based policies:
    - Chính sách dựa trên tài nguyên được đính kèm trực tiếp vào các tài nguyên AWS nhận được quyền.
    - Sau đó, chính sách sẽ chỉ định những hành động nào được phép hoặc bị từ chối trên tài nguyên cụ thể đó.
    - Trong các chính sách dựa trên tài nguyên, bạn bao gồm một phần tử Principal trong chính sách để chỉ ra người dùng hoặc vai trò IAM được cấp quyền.
    - Mặc dù không phải tất cả các dịch vụ AWS đều hỗ trợ chính sách dựa trên tài nguyên, nhưng các dịch vụ phổ biến có hỗ trợ bao gồm Amazon S3 cho bucket policies, AWS KMS cho key policies và Amazon SNS cho topic policies.
   
2. Users / User Groups:
   - Trong AWS IAM, một Users Group là một tập hợp những người dùng.
   - Các nhóm cho phép bạn chỉ định quyền cho nhiều người dùng, giúp bạn dễ dàng quản lý quyền cho những người dùng đó.
   - Ví dụ:
     + Có một nhóm có tên là "Developers" và cấp cho nhóm đó các quyền cần thiết để phát triển trong môi trường của bạn.
     + Nếu một nhà phát triển mới tham gia tổ chức của bạn, thay vì chỉ định quyền cho người dùng đó, bạn có thể thêm người dùng đó vào nhóm "Developers" để chỉ định các quyền đó.
    - Hãy nhớ rằng, mỗi người dùng AWS IAM trong một nhóm sẽ kế thừa các chính sách quyền được đính kèm vào nhóm.
  
3. Roles:
   - Role trong AWS là một dạng kiểm soát truy cập an toàn không liên kết trực tiếp với người dùng hoặc nhóm cụ thể.
   - Thay vào đó, các thực thể đáng tin cậy như người dùng AWS, ứng dụng hoặc dịch vụ (như EC2) có thể đảm nhiệm vai trò để có được thông tin xác thực bảo mật tạm thời để thực hiện các yêu cầu API AWS.
   - Cấu trúc của vai trò cho phép bạn phân quyền truy cập với các quyền được xác định, giúp giữ cho môi trường của bạn an toàn.
   - Hơn nữa, vì vai trò tạo ra thông tin xác thực tạm thời để điều hướng trong AWS, bạn sẽ không phải xử lý các khóa dài hạn.
   3.1. Instance profiles:
     - Là các thực thể AWS IAM mà bạn có thể sử dụng để cấp quyền cho các ứng dụng đang chạy trên phiên bản EC2 của mình.
     - Chúng cho phép các phiên bản của bạn thực hiện các yêu cầu API an toàn.
     - Về cơ bản nó là một vùng chứa cho vai trò AWS Identity and Access Management (IAM) mà bạn có thể sử dụng để chuyển vai trò cho phiên bản EC2 tại thời điểm khởi chạy.
     - Sau khi vai trò IAM được liên kết với phiên bản tại thời điểm khởi chạy, không thể thay đổi vai trò.
     - Tuy nhiên, bạn có thể sửa đổi các chính sách quyền được đính kèm vào vai trò và các quyền được cập nhật sẽ có hiệu lực ngay lập tức.
    3.2. Assuming roles:
     - Cho phép một danh tính AWS thực hiện các hành động và truy cập tài nguyên trong một tài khoản AWS khác mà không cần phải chia sẻ thông tin xác thực bảo mật.
     - Điều này đạt được bằng cách sử dụng thông tin xác thực bảo mật tạm thời.
     - Bạn đảm nhiệm một vai trò bằng cách gọi API AssumeRole của AWS Security Token Service (STS), chuyển ARN của vai trò cần đảm nhiệm.
     - Sau khi đảm nhiệm thành công một vai trò, STS sẽ trả về thông tin xác thực bảo mật tạm thời mà bạn có thể sử dụng để thực hiện yêu cầu tới bất kỳ dịch vụ AWS nào.
     - Vai trò được đảm nhiệm cung cấp các quyền cụ thể xác định những gì người dùng vai trò có thể và không thể làm.
     - Do đó, người dùng có thể chuyển đổi giữa các vai trò bằng AWS Management Console, AWS CLI hoặc AWS API.
