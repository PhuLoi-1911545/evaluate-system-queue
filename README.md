# evaluate-system-queue

**Đề tài **

Xây dựng 1 chương trình mô phỏng hàng M/G/1, 
trong đó thời gian phục vụ của server = d + S (S biến ngẫu nhiên phân bố theo hàm mũ và d tương tự như thời gian bắt buộc phải có khi xử lý 1 customer). 

Hãy so sánh hiệu năng với hàng M/M/1 với cùng tốc độ phục vụ trung bình 


## Nội dung mô phỏng

**Mục tiêu**
1. Xây dựng hàng chờ M/G/1 trong đó thời gian phục vụ của server = d + S (S biến ngẫu nhiên phân bố theo hàm mũ và d tương tự như thời gian bắt buộc phải có khi xử lý 1 customer)
2. So sánh hiệu năng hàng chờ M/M/1 và M/G/1 

**Giới hạn**

Nhóm sử dụng trang web cá nhân localhost : "React(frontend) + Java(backend) + MySQL" và một số các nguồn tài liệu khác trên mạng để chọn lựa dữ liệu các tham số cũng như các công thức tính.

Trong bài làm, nhóm xem 1 người dùng sẽ tạo ra 1 job cho mỗi công việc của người dùng đó, VD: việc đọc thông tin của 1 trang web là 1 job. Trong 1 job sẽ chỉ có 1 request gửi đến server và 1 request sẽ bao gồm tất cả các package, data gửi đi/nhận về.

Vì việc mô phỏng nhằm mục đích hỗ trợ cho việc đánh giá hệ thống đơn giản nên nhóm chỉ thực hiện trong vòng 1 phút (=60000 ms) và giả sử 1 server có thể đáp ứng trung bình 15 request trong 1 giây (trang localhost), nhận trung bình 12 request mới mỗi giây (trang OpenStreetMap.com)

Hệ thống sẽ thực hiện theo mô hình **FIFO** 

Tại hàng chờ M/G/1, phân phối theo General sẽ có tham số **d** (deviation) là thời gian bắt buộc phải có thì nhóm giả sử đây là thời gian này sẽ bằng 10% của service time trung bình ([hardware delay](https://dgway.com/blog_E/2021/02/22/measuring-latency-time/))


**Dữ liệu sử dụng**

Vì đây là hiện thực mô phỏng đơn giản nên nhóm sẽ sử dụng các dữ liệu cơ bản gồm: 
1. MAXSIMTIME  (60000ms)
2. MU (~12)          được lấy từ thời gian xử lý của trang web localhost
3. LAMBDA (~15)      được tham khảo từ các nguồn tài liệu trên mạng
4. DEVIATION 


**Các nguồn tham khảo dữ liệu**
- Trang web localhost:
    - [Frontend](https://github.com/luongcaothanh/LearningSystemFrontend)
    - [Backend](https://github.com/luongcaothanh/LearningSystemBackend)

- Các nguồn khác:
    - [Architectures under E-Commerce Workloads](https://www.ele.uri.edu/Research/hpcl/DRALIC/JPDC.pdf)
    - [Avarage request per second](https://stackoverflow.com/questions/373098/whats-the-average-requests-per-second-for-a-production-web-application)
    - [How many user online at a time](https://www.quora.com/How-many-average-users-online-at-a-time-does-it-take-to-make-500-requests-per-second-or-30-000-requests-per-minute)
    - [Analyses of M/M/1 and M/G/1](https://antaresc.github.io/src/documents/classes/cs162-mm1-mg1.pdf)
    - [Analysis of the M/G/1 queue with exponentially working vacations](http://gljc.sxu.edu.cn/docs/2013-11/20131129080953362966.pdf)

