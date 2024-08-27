Containerization:
  - Containerization là một phương pháp ảo hóa liên quan đến việc đóng gói một ứng dụng trong một container với môi trường hoạt động riêng biệt.
  - Phương pháp tiên tiến này cho phép các ứng dụng chạy một cách đáng tin cậy và nhanh chóng khi được di chuyển từ môi trường điện toán này sang môi trường điện toán khác.
  - Trong Linux, công nghệ này có thể được sử dụng bằng nhiều nền tảng nguồn mở khác nhau như Docker và Kubernetes.
  - Không giống như VM cần toàn bộ hệ điều hành để chạy ứng dụng, container chia sẻ không gian người dùng của hệ thống lưu trữ -> nhanh và nhẹ hơn.
  - Sử dụng lệnh: docker run -it ubuntu bash -> kéo Ubuntu image từ Docker Hub và chạy nó như một container trên hệ thống của bạn, cung cấp cho bạn một terminal tương tác (-it) bên trong container.

  - Ulimits:
    + Ulimits (giới hạn người dùng) là một tính năng của hạt nhân Linux hạn chế các tài nguyên mà bất kỳ người dùng nào có thể sử dụng.
    + Các tài nguyên này bao gồm các xử lý tệp mở, bộ nhớ vật lý bị khóa và các tài nguyên khác.
    + Sử dụng hiệu quả, ulimits có thể ngăn chặn một quy trình bất hợp pháp hoặc sai sót trong một container cụ thể làm cạn kiệt tài nguyên của máy chủ và tạo ra tình huống từ chối dịch vụ cho các container hoặc quy trình khác.
    + Trong môi trường container hóa, việc quản lý khéo léo các giới hạn tài nguyên này là rất quan trọng để đảm bảo hiệu suất và bảo mật tối ưu cho tất cả các container.
    + VD:
      + # Để xem chỉ số ulimits hiện tại:
        ulimit -a

        # Để thiết lập một ulimit cụ thể (giới hạn mềm):
        ulimit -n 1024

  - Cgroups:
    + Cgroups, viết tắt của control groups, là một tính năng của hạt nhân Linux cho phép các quy trình được tổ chức thành các nhóm phân cấp.
    + Vai trò quan trọng của nó trong container hóa là khả năng giới hạn, tính toán và cô lập việc sử dụng tài nguyên (CPU, bộ nhớ, I/O đĩa, v.v.) của các nhóm quy trình này.
    + Trong bối cảnh container hóa, nơi các môi trường cô lập nhẹ đang chạy trên cùng một máy chủ, cgroups trở nên tối quan trọng đối với việc quản lý tài nguyên hiệu quả.
    + Bằng cách sử dụng cgroups, người ta có thể đảm bảo rằng mỗi container không độc quyền tài nguyên máy chủ, dẫn đến cải thiện hiệu suất và tính ổn định của toàn bộ hệ thống.
    + VD:
      + # tạo cgroup mới:
        sudo cgcreate -g cpu:/my_new_container

        # Gán tiến trình của shell hiện tại cho cgroup mới:
        echo $$ | sudo tee /sys/fs/cgroup/cpu/my_new_container/tasks
        
        # Giới hạn mức sử dụng CPU của cgroup ở mức 20%:
        echo 200000 | sudo tee /sys/fs/cgroup/cpu/my_new_container/cpu.cfs_quota_us

  - Container runtime:
    + Container runtime cung cấp các tính năng và lợi ích cụ thể, với các khả năng chung bao gồm vận chuyển và lưu trữ hình ảnh, thực thi và giám sát container, tương tác mạng và khối lượng cấp thấp, v.v.
    + Trong Linux, các tùy chọn container runtime phổ biến bao gồm:
      + Docker: Docker có lẽ là container runtime phổ biến nhất, có hệ sinh thái tuyệt vời và hỗ trợ cộng đồng tuyệt vời.
      + Containerd: Ban đầu được phát triển như một lớp container runtime cấp cao để sử dụng trong Docker, Containerd hiện thường được sử dụng như một runtime độc ​​lập.
      + CRI-O: Một container runtime nhẹ được tối ưu hóa riêng cho Kubernetes.
    + Trong container hóa, việc hiểu vai trò của container runtime là không thể thiếu vì nó giúp thiết kế và chạy tốt hơn các ứng dụng container của bạn.
    + Mỗi container runtime có thể phù hợp với các trường hợp sử dụng khác nhau nên tốt nhất là hiểu ưu và nhược điểm của chúng để sử dụng chúng hiệu quả.
  
  - Docker:
    + Docker là một nền tảng mã nguồn mở được sử dụng rộng rãi, tận dụng ảo hóa cấp hệ điều hành, thường được gọi là "containerization", để phát triển, vận chuyển và chạy các ứng dụng một cách hiệu quả.
    + Docker và containerization, đặc biệt là trong hệ sinh thái Linux, đã cách mạng hóa quy trình phát triển phần mềm bằng cách cung cấp các môi trường hoạt động nhẹ và biệt lập, được gọi là container, cho các ứng dụng và các phần phụ thuộc của chúng.
    + Docker cho phép các nhóm phát triển đóng gói một ứng dụng với tất cả các phần cần thiết, chẳng hạn như thư viện và các phần phụ thuộc khác, và triển khai ứng dụng đó dưới dạng một gói duy nhất.
    + Trong Linux, mỗi container Docker tương tác trực tiếp với hạt nhân Linux.
    + Do sử dụng thông minh các tính năng của hạt nhân Linux như không gian tên và nhóm c, các container này cung cấp các không gian biệt lập để chạy các quy trình trong khi chia sẻ cùng một hệ điều hành, dẫn đến ít chi phí hơn so với các máy ảo truyền thống.
    + VD:
      + # Kéo Docker image từ Docker Hub
        sudo docker pull hello-world
        
        # Chạy container Docker
        sudo docker run hello-world
