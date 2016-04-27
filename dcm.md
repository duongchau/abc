#Tìm hiểu VMware Workstation 
============

-[Mục lục ] (#content)
     <ul>
    <li> [1.Máy ảo ] (#máy ảo)
        <ul>
        <li> [ 1.1 Máy ảo là gì? ] (#đn)
        <li> [ 1.2 Tác dụng của máy ảo ] (#td)
        </ul>
     </ul>
    - [2.VMware Workstation ] (#VMware)
        -[2.1. Giới thiệu về phần mềm VMware Workstation ] (#định nghĩa)
        -[2.2. Nhập môn VMware ] (#nhập môn)
            -[2.2.1. Card mạng trong VMware ] (#vmnet)
                -[Thêm card mạng] (#thêm)
                -[Xóa card mạng] (#xóa)
            -[2.2.2. Sửa dải IP trong VMware ] (#IP)
            -[2.2.3. Thêm card mạng vào máy ảo ] (#cardmang)
            -[2.2.4. Cách thay đổi gateway cho card mạng NAT ] (#gateway)
    -[3.Những điều cần biết khi sử dụng VMware Workstation ] (#cài máy ảo)
        -[3.1. Cài máy ảo như thế nào? ] (#CentOS7)
        -[3.2. Chức năng cấp phát IP động (DHCP) trong VMware ] (#DHCP)
        -[3.3. Chia sẻ dữ liệu giữ máy thật và máy ảo ] (#aothat)
    -[4. Lời cảm ơn] (#tks)

VMware Workstation là phần mềm tạo máy ảo hàng đầu hiện nay với tính năng mạnh mẽ, cải thiện về giao diện cũng như độ tương thích với các phần mềm khác. Chắc hẳn không ít người đang sử dụng công cụ tạo máy ảo, và cái tên VMware Workstation, gọi tắt là VMware được quan tâm và đánh giá rất cao.

Trong bài viết này, tôi sẽ trình bày chức năng cơ bản và cách sử dụng phần mềm VMware Workstation. Hy vọng nó sẽ giúp ích cho các bạn.

#Note: 
- Phiên Bản VMware được giới thiệu trong bài là VMware Workstation 10
- Host cài đặt: Win 8.1- 64bit
- Quy ước: card mạng ảo trong VMware Workstation được gọi là VMnetx (x là số thứ tự card mạng )

<a name="máy ảo"></a>
## 1. Máy ảo 
<a name="đn"></a>
### 1.1. Máy ảo là gì?
 - Một máy ảo là một chương trình đóng vai trò như một máy vi tính ảo. Nó chạy trên hệ điều hành hiện tại - hệ điều hành chủ và cung cấp phần cứng ảo tới hệ điều hành khách. Các hệ điều hành khách chạy trên các cửa sổ của hệ điều hành chủ, giống như bất kỳ chương trình nào khác của máy. Đối với những hệ điều hành khách, máy ảo lại hiện diện như một cỗ máy vật lý thực sự.
 
 - Các máy ảo cung cấp phần cứng ảo, bao gồm CPU ảo, RAM ảo, ổ đĩa cứng, giao diện mạng và những thiết bị khác. Các thiết bị phần cứng ảo được cung cấp bởi máy ảo và được ánh xạ tới phần cứng thực trên máy thật.
 
 - Bạn có thể cài đặt nhiều máy ảo lên máy thực và chỉ bị hạn chế bởi dung lượng bộ lưu trữ hiện có cho chúng.
 
<a name="td"></a>
###1.2. Tác dụng của máy ảo:

**Kiểm thử các phiên bản hệ điều hành:** Bạn có thể chạy phiên bản thử nghiệm Windows 8 bằng máy ảo trên máy chạy Windows 7. Điều này cho phép bạn thử nghiệm Windows 8 mà không phải cài đặt một phiên bản Windows bất ổn định trên máy mình.

**Thử nghiệm các hệ điều hành khác:** Bạn có thể cài nhiều bản phân phối Linux khác nhau và các hệ điều hành ít biết đến hơn bằng một máy ảo để thử nghiệm chúng và tìm hiểu cách chúng hoạt động. Nếu bạn hứng thú với Ubuntu, bạn có thể cài đặt nó vào máy ảo và sử dụng tại một cửa sổ trên màn hình desktop bình thường.

**Sử dụng phần mềm đòi hỏi một hệ điều hành cũ:** Nếu bạn có một ứng dụng quan trọng mà chỉ chạy trên Windows XP, bạn có thể cài đặt XP trên máy ảo và chạy ứng dụng trên máy ảo.

**Chạy phần mềm được thiết kế cho những hệ điều hành khác:** Những người dùng Mac và Linux có thể chạy Windows trên một máy ảo để sử dụng những phần mềm cho Windows trên máy tính.

**Tăng cường cho server:** Đối với các doanh nghiệp sử dụng nhiều server, thì các server có thể được đặt vào những máy ảo và chạy trên một máy tính đơn lẻ. Mỗi máy ảo là một thư mục cách ly, vì vậy điều này không gây những nguy cơ về bảo mật liên quan tới việc chạy nhiều server khác nhau trên cùng hệ điều hành. Các máy ảo cũng có thể được di dời giữa những server thật.

<a name="VMware"></a>
## 2.VMware Workstation

<a name="#định nghĩa"></a>
### 2.1. Giới thiệu về phần mềm VMware Workstation:

 **VMware Workstation** họat động bằng cách cho phép nhiều HĐH và các ứng dụng của chúng chạy đồng thời trên một máy duy nhất. Các HĐH và ứng dụng này được tách ra vào trong các máy ảo. Những máy ảo này cùng tồn tại trên một phần cứng duy nhất. Các layer ảo của VMware sẽ kết nối các phần cứng vật lý với các máy ảo, do đó mỗi máy ảo sẽ có CPU, bộ nhớ, các ổ đĩa, thiết bị nhập/xuất riêng.

 **Tính năng cho người dùng**
  -Thiết lập và thử nghiệm các ứng dụng đa lớp, cập nhật ứng dụng và các miếng vá cho HĐH chỉ trên một PC duy nhất.
  -Dễ dàng phục hồi và chia sẻ các môi trường thử nghiệm được lưu trữ; giảm thiểu các thiết lập trùng lặp và thời gian thiết lập.
  -Làm cho việc học tập trên máy tính thuận lợi hơn do sinh viên luôn đuợc sử dụng máy với tình trạng “sạch sẽ” và thử nghiệm với nhiều HĐH, ứng dụng cá các công cụ trên những máy ảo an tòan và độc lập.
  -Chạy các bản demo phần mềm với các thiết lập phức tạp hoặc đa lớp trên một chiếc laptop.
  -Tăng tốc độ giải quyết các rắc rối của người dùng cuối dựa trên một thư viện các máy ảo được thiết lập sẵn.
  
 **Những tính năng chính:**
  -Hỗ trợ nhiều màn hình – Bạn có thể thiết lập để một VM trải rộng ra nhiều màn hình, hoặc nhiều VM, với mỗi VM trên một màn hình riêng biệt.
  -Hỗ trợ các thiết bị USB 2.0 – Bây giờ bạn đã có thể sử dụng các thiết bị ngọai vi yêu cầu tốc độ làm việc cao trên VM, như máy MP3 và các thiết bị lưu trữ di động khác
  -VM Snapshot – Bạn có thể sử dụng tính năng này để thu lại các hoạt động của VM và được đảm bảo là sẽ tái lập lại tình trạng của VM chính xác 100%.
  
<a name="nhập môn"></a>
### 2.2. Nhập môn VMware

<a name="VMnet"></a>
#### 2.2.1. Card mạng trong VMware:

<a name="thêm"></a>
    **Thêm card mạng**
Vào Edit chọn Virtual Network Editor

<img src=http://i.imgur.com/CTKod9y.png>

        - Bước 1: chọn Add Network
        - Bước 2: chọn card cần add thêm (ở đây là VMnet2) 
        - Bước 3: ấn OK
        
Lúc này trên cửa sổ Virtual Network Editor sẽ xuất hiện thêm card VMnet1 và được gắn tự động một dải IP, như hình dưới đây:

<img src=http://i.imgur.com/EmMjegJ.png>

Làm tương tự để add thêm các vmnet tiếp theo.

<a name="xóa"></a>
    **Xóa card mạng**
Vào Edit chọn Virtual Network Editor

<img src=http://i.imgur.com/a7KftPT.png>

<a name="IP"></a>
###2.2.2 Sửa dải IP trong VMware:

Các dải IP tự sinh ra khi tạo card mạng rất khó nhớ, vì vậy, chúng ta có thể sửa dải card mạng để dễ nhỡ, dễ sử dụng.

chọn card mạng muốn thay đổi dải IP, sau khi nhập dải IP mới, click "Apply" và OK

<img src=http://i.imgur.com/tRcJt23.png>

<a name="cardmang"></a>
### 2.2.3. Thêm card mạng vào máy ảo:

Thêm 1 card mạng vào máy ảo, vào setting, chọn Add

<img src=http://i.imgur.com/9xrbLjl.png>

Network adapter -> Next 

<img src=http://i.imgur.com/Aie3tzc.png>

-> Finish, có thêm card mạng mới được tạo

<img src=http://i.imgur.com/jtSMgLF.png>    <img src=http://i.imgur.com/jjj1adL.png> 




 
 

        
            
