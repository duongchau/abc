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
    <li> [2.VMware Wor kstation ] (#VMware)
        <ul>
        <li> [2.1. Giới thiệu về phần mềm VMware Workstation ] (#định nghĩa)
        <li> [2.2. Nhập môn VMware ] (#nhập môn)
            <ul>
            <li> [2.2.1. Card mạng trong VMware ] (#vmnet)
                -[Thêm card mạng] (#thêm)
                -[Xóa card mạng] (#xóa)
            <li> [2.2.2. Sửa dải IP trong VMware ] (#IP)
            <li> [2.2.3. Thêm card mạng vào máy ảo ] (#cardmang)
            <li> [2.2.4. Cách thay đổi gateway cho card mạng NAT ] (#gateway)
            </ul>
          </ul>
       <ul>
   <li> [3.Những điều cần biết khi sử dụng VMware Workstation ] (#cài máy ảo)
          <ul>
        <li> [3.1. Cài máy ảo như thế nào? ] (#CentOS7)
        <li> [3.2. Chức năng cấp phát IP động (DHCP) trong VMware ] (#DHCP)
        <li> [3.3. Chia sẻ dữ liệu giữ máy thật và máy ảo ] (#aothat)
          </ul>
       </ul>
       <ul>
    <li> [4. Lời cảm ơn] (#tks)
    </ul>

VMware Workstation là phần mềm tạo máy ảo hàng đầu hiện nay với tính năng mạnh mẽ, cải thiện về giao diện cũng như độ tương thích với các phần mềm khác. Chắc hẳn không ít người đang sử dụng công cụ tạo máy ảo, và cái tên VMware Workstation, gọi tắt là VMware được quan tâm và đánh giá rất cao.

Trong bài viết này, tôi sẽ trình bày chức năng cơ bản và cách sử dụng phần mềm VMware Workstation. Hy vọng nó sẽ giúp ích cho các bạn.

#Note: 
- Phiên Bản VMware được giới thiệu trong bài là VMware Workstation 12
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
####2.2.2 Sửa dải IP trong VMware:

Các dải IP tự sinh ra khi tạo card mạng rất khó nhớ, vì vậy, chúng ta có thể sửa dải card mạng để dễ nhỡ, dễ sử dụng.

chọn card mạng muốn thay đổi dải IP, sau khi nhập dải IP mới, click "Apply" và OK

<img src=http://i.imgur.com/tRcJt23.png>

<a name="cardmang"></a>
#### 2.2.3. Thêm card mạng vào máy ảo:

Thêm 1 card mạng vào máy ảo, vào setting, chọn Add

<img src=http://i.imgur.com/9xrbLjl.png>

Network adapter -> Next 

<img src=http://i.imgur.com/Aie3tzc.png>

-> Finish, có thêm card mạng mới được tạo

<img src=http://i.imgur.com/jtSMgLF.png>    <img src=http://i.imgur.com/jjj1adL.png> 

-> Power on máy ảo, kiểm tra card mạng bằng lệnh **ip addr**

 <img src=http://i.imgur.com/57S6i7T.png> 
 
 Trong bài sau mình sẽ hướng dẫn các bạn cách cấu hình card mạng trong CentOS 7
 
 <a name="gateway"></a>
 #### 2.2.4. Cách thay đổi gateway cho card mạng NAT:

Trong VMware, card mạng có 3 chế độ là Bridge, NAT và Host-only. Mỗi chế độ đóng vai trò và chức năng khác nhau.

**Chế độ Bridge:** Ở chế độ này thì card mạng trên máy ảo sẹ được gắn vào VMnet0 và VMnet0 này liên kết trực tiếp với card mạng vật lý. Ở chế độ này máy ảo sẽ kết nối internet thông qua lớp card mạng vật lý và có chung lớp mạng với card mạng vật lý.

 <img src=http://i.imgur.com/lWJD9oP.png> 

**Chế độ NAT:** Ở chế độ này thì card mạng của máy ảo kết nối với VMnet8, VNnet8 cho phép máy ảo đi internet thông qua cơ chế NAT (NAT device). Lúc này lớp mạng bên trong máy ảo khác hoàn toàn với lớp mạng của card vật lý bên ngoài. IP của card mạng sẽ được cấp bởi DHCP VMnet8 cấp, trong trường hợp bạn muốn thiết lập IP tĩnh cho card mạng máy ảo bạn phải đảm bảo chung lớp mạng với VNnet8 thì máy ảo mới có thể đi internet.

 <img src=http://i.imgur.com/kfvq4LJ.png> 
 
 **Cơ chế Host-only:** Ở cơ chế này máy ảo được kết nối với VMnet có tính có tính năng Host-only, trong trường hợp hình này là VMnet1 (bạn có thể add nhiều VMnet Host-only). VNnet Host-only kết nối ra một card mạng ảo tương ứng ngoài máy thật (như đã nói ở phần trên, khi ta add một VMnet thì có một card tương ứng với VMnet sẽ được tạo ra ở phần trên. Trường hợp này là VMware Network Adapter VMnet1).

Ở chế độ này máy ảo không có kết nối internet. IP của máy ảo được cấp bởi DHCP của VMnet tương ứng.Trong nhiều trường hợp đặc biệt cần cấu hình riêng, ta có thể tắt DHCP trên VMnet và cấu hình IP bằng tay cho máy ảo.

 <img src=http://i.imgur.com/f5Z6f9H.png> 

Do công việc, học tập, chúng ta cần phải thay đổi môi trường làm việc khác nhau. Vì vậy, để tránh phải cấu hình địa chỉ IP tại các môi trường khác nhau, ta có thể sử dụng card NAT để sử dụng linh hoạt hơn. Do mặc định card NAT để gateway là .2, nên ta cần cấu hình lại gateway cho giống với mạng bridge thật (giả sử gateway là .1). Cách làm như sau:

Vào Virtual Network Editor chọn card NAT và sửa dải IP như mục 2.2.2

Chọn **change stting**

<img src=http://i.imgur.com/lUw6d0L.png> 

-> **NAT setting**

<img src=http://i.imgur.com/WLQanSP.png>

Thay địa chỉ Gateway .1 -> ok

<img src=http://i.imgur.com/pestFbS.png>

 <a name="cài máy ảo"></a>
## 3.Những điều cần biết khi sử dụng VMware Workstation:
 <a name="CentOS7"></a>
### 3.1. Cài máy ảo như thế nào?

Bây giờ mình sẽ hướng dẫn cách tạo một máy ảo trên VMware Workstation:

**Bước 1:** File -> New Virtual Machine

<img src=http://i.imgur.com/NBBBLxI.png>

**Bước 2:** Nếu không cần thiết bị khác những thiết bị mặc định, chọn cấu hình mặc định cho máy ảo.

<img src=http://i.imgur.com/crpjR96.png>

**Bước 3:** Có 2 lựa chọn cài đặt OS (Operating System) cho máy ảo: từ disc, từ disc image file (iso). Hoặc có thể cài đặt sau nhé (click chọn “I will install the operating system later”).

<img src=http://i.imgur.com/1b1VFln.png>

**Bước 4:**  Chọn hệ điều hành sẽ được cài lên máy ảo, VMware hỗ trợ hầu hết các OS (và các version của OS tương ứng) thông dụng hiện nay rất tiện lợi cho việc kiểm thử (mình chọn Linux bản CentOS 64-bit)

<img src=http://i.imgur.com/592xf3B.png>

**Bước 5:**  Đặt tên và chọn vị trí lưu các file cấu hình của VMWare, file ổ cứng ảo, file bộ nhớ ảo.

<img src=http://i.imgur.com/upkh5dZ.png>

**Bước 6:**  Chọn dung lượng RAM (VMware sẽ đề nghị cho bạn dung lượng cần tương ứng với OS mà bạn cài đặt nhé, để mặc định hoặc thêm nhiều hơn).

<img src=http://i.imgur.com/Bhf6084.png>

**Bước 7:**  Chọn dung lượng ổ cứng ảo (VMware sẽ đề nghị cho bạn dung lượng cần tương ứng với OS mà bạn cài đặt nhé, để mặc định hoặc thêm nhiều hơn).

<img src=http://i.imgur.com/gdTRSNZ.png>

**Bước 8:** Browse file iso vào ổ đĩa

<img src=http://i.imgur.com/6WFHzjP.png>

**Bước 9:** Kiểm tra lại các thông số của máy ảo -> Finish

<img src=http://i.imgur.com/lBT3ZKW.png>

**Bước 10:** Máy ảo đã được tạo ra, power on để cài đặt máy ảo

<img src=http://i.imgur.com/LwzUeTg.png>

 <a name="DHCP"></a>
###3.2. Chức năng cấp phát IP động (DHCP) trong VMware:

VMware có tính năng cấp IP động (DHCP), bạn có thể click vào Edit -> chọn Virtual Network Editor trên thanh tool bar để cấu hình.

<img src=http://i.imgur.com/fsKKFb8.png>

 <a name="aothat"></a>
###3.3. Chia sẻ dữ liệu giữ máy thật và máy ảo:

**Bước 1:**  Trong hộp thoại hiệu chỉnh cấu hình máy ảo, chọn tab Options -> chọn mục Shared Folders -> chọn nút  -> Add để tạo một chia sẻ một thư mục trên máy tính thật cho máy ảo.

<img src=http://i.imgur.com/2GE6SyJ.png>

**Bước 2:**  Chọn tên cho shared folder và chọn thư mục muốn share.

<img src=http://i.imgur.com/Uua2tWE.png>

**Bước 3:**  Chọn Enable this share để từ máy ảo có thể truy cập ngay vào thư mục share trên máy thật. Chọn Read-only để không cho phép máy ảo sửa đổi dữ liệu trong thư mục share.
 
 <img src=http://i.imgur.com/510BDMH.png>
 
 <a name="tks"></a> 
## 4.Lời cảm ơn:
 
 Mình đã giới thiệu đôi nét về VMware Workstation cũng như một số thao tác trên nó mong giúp ích cho các bạn trong quá trình sử dụng.
 
 Cảm ơn các bạn đã đọc hết bài viết này. Tôi hoan nghênh mọi ý kiến đóng, góp xin hãy post lên blog của tôi hoặc có thể commit lên github này.

        
            
