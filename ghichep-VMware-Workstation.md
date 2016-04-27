# Các ghi chép về VMware Workstation
----
## Mục Lục

###[I.Giới thiệu về VMware Workstation](#gioi-thieu)


* [1.Giới thiệu về VMware Workstation](#gioi-thieu1)


* [2.Các tính năng của VMware Workstation](#gioi-thieu2)

###[II.Hướng dẫn cài đặt và cấu hình](#cau-hinh)

* [1.Cấu hình tối thiểu](#cau-hinh1)

* [2.Cài đặt VMware Workstation trên Windows](#cau-hinh2)

* [3.Cài đặt VMware Workstation trên Linux](#cau-hinh3)
 
###[III.Card mạng trong VMware Workstation](#network)

* [1.Switch ảo ( Virtual Switch)](#switch-ao)

* [2.Card mạng ảo ( Virtual Network Adapter)](#card-mang-ao)
 
* [3.DHCP server ảo (Virtual DHCP Server)](#dhcp-ao)

##[Tổng kết](#tong-ket)
----


### <a name="gioi-thieu"></a>I.Giới thiệu về VMware Workstation

#### <a name="gioi-thieu1"></a>1.Giới thiệu về VMware Workstation

VMware Workstation là một phần mềm ảo hóa desktop mạnh mẽ dành cho các nhà phát triển/kiểm tra phần mềm và các chuyên gia IT cần chạy nhiều HĐH một lúc trên một máy vật lý. Mỗi máy ảo có thể chạy một hệ điều hành riêng biệt bao gồm các phiên bản của Microsoft Windows, Linux, BSD, và MS-DOS. VMware Workstation được phát hành và phát triển bởi VMware, một thành viên của EMC Corporation. 

Với hàng triệu khách hàng và hàng loạt các giải thưởng quan trọng trong nhiều năm qua, VMware Workstation đã được chứng minh là một công ghệ giúp tăng năng suất và sự linh họat trong công việc. Đây là một công cụ không thể thiếu cho các nhà phát triển phần mềm và các chuyên gia IT trên toàn thế giới.

 * Ưu điểm
  <ul>
  <li>Giữa các máy ảo: Tính bảo mật cao do các máy ảo làm việc độc lập với nhau</li>
  <li>Các tài nguyên vật lý được bảo vệ hoàn toàn vì các máy ảo có thiết bị ảo</li>
  <li>Có thể lấy từ Internet về một chương trình lạ và thử vận hành trên máy ảo mà không sợ bị ảnh hưởng đến máy thật</li>
  <li>Giải pháp giảm chi phí cho người dùng</li>
  </ul>

 * Nhược điểm
  <ul>
  <li>Nếu hacker nắm quyền điều khiển máy tính chứa các máy ảo thì hacker có thể kiểm soát được tất cả các máy ảo trong nó</li>
  <li>Máy tính có cấu hình phần cứng thấp cài nhiều chương trình máy ảo, máy sẽ chậm và ảnh hưởng đến các chương trình khác</li>
  <li>Nếu máy tính chứa các máy ảo bị hư thì các máy ảo thiết lập trên nó cũng bị ảnh hưởng</li>
  </ul>

####<a name="gioi-thieu2"></a>2.Các tính năng của VMware Workstation

- Những tính năng chính
  <ul>
  <li>Khởi chạy đồng thời nhiều hệ điều hành khách trên một máy tính. </li>
  <li>Chạy khi đã được cài đặt sẵn sàng trên hệ điều hành máy tính mà không cần cài đặt lại hoặc tái cấu hình.</li>
  <li> Khởi động ứng dụng hệ điều hành Windows trên một máy tính Linux, và ngược lại.</li>
  <li>Tạo và thử nghiệm các ứng dụng đồng thời cho các hệ thống khác nhau.</li>
  <li>Chạy các ứng dụng chưa được kiểm tra không có nguy cơ gây nguy hiểm cho sự ổn định của hệ thống hoặc mất dữ liệu quan trọng.</li>
  <li>Chia sẻ tập tin và các ứng dụng cho các máy ảo khác nhau bằng cách sử dụng một mạng ảo.</li>
  <li>Tính năng Snapshot feature bảo tồn trạng thái các máy ảo cho phép quay lại bất cứ lúc nào. Tính năng clone cho phép tạo không giới hạn các bản sao của máy ảo ngay từ lúc cài đặt và cấu hình</li>
  </ul>
- Tính năng mới
  <ul>
  <li>Hỗ trợ Windows 10, Ubuntu 15.04, Red Hat Enterprise Linux 7.1, Fedora 22, </li>
  <li>Hỗ trợ tốt DirectX 10 và OpenGL 3.3,mang lại trải nghiệm tuyệt vời khi chạy các các ứng dụng 3D như AutoCAD,SOLIDWORKS</li>
  <li>VMWare Workstation đã được tối ưu hóa, hỗ trợ hiển thị độ phân giải cao </li>
  <li>Tạo được các máy ảo lên đến 16 vCPUs, 8 TB dung lượng ổ đĩa ảo, và 64 GB bộ nhớ</li>
  <li>Tân dụng tối đa phần cứng, hỗ trợ HD audio lên đến 7.1 sound, USB 3.0, và thiết bị Bluetooth dễ dàng thiết lập webcam, headset, hay printer kết nối đến máy ảo. </li>
  <li>Hỗ trợ kết nối đến VMware vSphere và dịch vụ vCloud Air cho phép mở rộng quy mô máy ảo trên cloud </li>
  </ul>

----

###<a name="cau-hinh"></a> II.Hướng dẫn sử dụng và cấu hình


####<a name="cau-hinh1"></a>1.Cấu hình tối thiểu

Theo như nhà phát hành thì cấu hình có thể sử dụng VMware Workstation Pro 12 đó là:
  <ul>
  <li>Hệ điều hành chạy trên nền tảng 64-bit. </li>
  <li>Chip Intel Core 2 Duo Processor, AMD Athlon ™ 64 FX Dual Core Processor hoặc cao hơn.</li>
  <li>Tốc độ xử lý tối thiểu là 1.3GHz.</li>
  <li>Ram tối thiểu là 2GB.</li>
  </ul>
Cấu hình lí tưởng:
  <ul>
  <li>Đối với Laptop: Corei5 trở lên và Ram 4GB trở lên. </li>
  <li>Đối với máy tính PC (máy bàn): Corei3 và RAM 4GB trở lên.</li>
  </ul>
####<a name="cau-hinh2"></a>2.Cài đặt VMware Workstation trên Windowns

**Bước 1:** Mở file cài đặt nhấn **"Next"**.

<img src="https://cloud.githubusercontent.com/assets/16606859/14797489/3f34e0b0-0b5d-11e6-8996-524f7a06b82c.png">

**Bước 2:** Tíck chọn **"I accept the terms in the license agreement"** và nhấn **"Next"**.

<img src="https://cloud.githubusercontent.com/assets/16606859/14797491/41ad1eac-0b5d-11e6-9cb2-53f6ecb3afc8.png">

**Bước 3:** Nhấn **"Change"** nếu muốn thay đổi đường dẫn, nhấn **"Next"** để tiếp tục.

<img src="https://cloud.githubusercontent.com/assets/16606859/14797494/42941c1c-0b5d-11e6-93df-132c0e7a07fa.png">

**Bước 4:** Nhấp vào 2 ô **"Check for product updates on startup"** và **"Help improve VMware Workstation Pro"**, nhấn **"Next"** để tiếp tục.

<img src="https://cloud.githubusercontent.com/assets/16606859/14797496/43bc9dda-0b5d-11e6-8e42-8ae5addbc1f3.png">

**Bước 5:** Nhấp vào ô **"Desktop"**, nhấn **"Next"** để tiếp tục.

<img src="https://cloud.githubusercontent.com/assets/16606859/14797499/44e3edb2-0b5d-11e6-8cf1-5f838075d320.png">

**Bước 6:** Nhấn **"Install"** để tiếp tục cài đặt.

<img src="https://cloud.githubusercontent.com/assets/16606859/14797501/4604fefc-0b5d-11e6-8bd2-3fa1e72b2010.png">

**Bước 7:** Nhấn **"Finish"**.

<img src="https://cloud.githubusercontent.com/assets/16606859/14797502/477a3676-0b5d-11e6-89a0-1b4ed44e3f35.png">

**Bước 8:** Nhập license key vào ô màu đỏ và nhấn **"continue"** để tiếp tục.

<img src="https://cloud.githubusercontent.com/assets/16606859/14797505/494eb27e-0b5d-11e6-921b-503da07b6da7.png">

**Bước 9:** Nhấn **"Finish"** để kết thúc cài đặt.

<img src="https://cloud.githubusercontent.com/assets/16606859/14797506/4a234e4e-0b5d-11e6-9e06-619426e332e9.png">

**Thành quả**

<img src="https://cloud.githubusercontent.com/assets/16606859/14797508/4b9d01f2-0b5d-11e6-8f8d-57168677144c.png">

####<a name="cau-hinh3"></a>3.Cài đặt VMware Workstation trên Linux

* Các host đáp ứng các yêu cầu về hệ thống máy chủ. [Xem Yêu cầu hệ thống máy chủ](https://pubs.vmware.com/workstation-12/index.jsp?topic=%2Fcom.vmware.ws.using.doc%2FGUID-47896F7A-2C4F-457E-8ED1-6E5AEFDDD64A.html).

*  Không có sản phẩm VMware không tương thích được cài đặt trên hệ thống máy chủ. Xem [Cài đặt Workstation Pro với các sản phẩm VMware khác](https://pubs.vmware.com/workstation-12/index.jsp?topic=%2Fcom.vmware.ws.using.doc%2FGUID-105FF68B-D0AA-424C-8F4D-7B25845604C5.html).

*  Phần mềm VMware Workstation Pro và key bản quyền. Xem [Phần mềm VMware Workstation Pro và License Key](https://pubs.vmware.com/workstation-12/index.jsp?topic=%2Fcom.vmware.ws.using.doc%2FGUID-47B91650-BCBE-49EE-997B-91AA0DBBAF04.html).

*  Nếu bạn định sử dụng tích hợp Virtual Debugger cho Eclipse, cài đặt nó trên hệ thống máy chủ. Xem [Cài đặt tích hợp Virtual Debugger cho Eclipse](https://pubs.vmware.com/workstation-12/index.jsp?topic=%2Fcom.vmware.ws.using.doc%2FGUID-97F446E4-DB57-4641-A73C-36ABC2BD406D.html).

*  Làm quen với các tùy chọn cài đặt dòng lệnh Linux. Bạn phải sử dụng các tùy chọn --custom để xác định các thiết lập cấu hình nhất định. Xem [Linux Command Line Tùy chọn cài đặt](https://pubs.vmware.com/workstation-12/index.jsp#com.vmware.ws.using.doc/GUID-42F4754B-7547-4A4D-AC08-353D321A051B.html#GUID-42F4754B-7547-4A4D-AC08-353D321A051B).

*  Có quyền truy cập root trên hệ thống máy chủ.

#####Các bước cài đặt

**Bước 1:** Truy cập vào trang web [Download VMWare Workstation Pro](http://www.vmware.com/products/workstation/workstation-evaluation), Nhấp vào ô **"Download Now"** để tiến hành cài đặt.


<img src="https://cloud.githubusercontent.com/assets/16606859/14807438/ea33be34-0ba6-11e6-83cf-8cba679e9665.png">

**Bước 2:** Chuyển sang tài khoản root với dòng lệnh:
`su -`  

Cài đặt các Tools hỗ trợ với lệnh:

`yum groupinstall "Development tools"`

Ubuntu không cần lệnh này

**Bước 3:** Cài VMware Tools:

Trên Cent OS

`yum install kernel-headers kernel-devel -y`

Trên Ubuntu 14.10

``sudo apt-get install build-essential linux-headers-`uname -r``

**Bước 4:** Sau khi tải thành công file download ở Bước 1. Truy cập tới thư mục chứa file và tiến hành phân quyền cho file
`chmod u+x tênfile`

Ví dụ:

<img src="https://cloud.githubusercontent.com/assets/16606859/14807446/f579fa4c-0ba6-11e6-8643-da91fe290df6.png">

**Bước 5:** Tiến hành giải nén file cài đặt

Trên CentOS ta chạy dòng lệnh

`./tênfile`

Trên Ubuntu ta chạy:
`sudo sh ./tênfile`

và

`export LD_LIBRARY_PATH=/usr/lib/vmware/lib/libglibmm-2.4.so.1/:$LD_LIBRARY_PATH
vmware`

Ví dụ:

<img src="https://cloud.githubusercontent.com/assets/16606859/14807449/f8da98c2-0ba6-11e6-955a-43a7a318df7c.png">

Các bước cài đặt tiếp theo:

<img src="https://cloud.githubusercontent.com/assets/16606859/14807451/faed0500-0ba6-11e6-83f6-a4d3a473dbd3.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807453/fbcc6e8e-0ba6-11e6-96c2-88d7b01692f3.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807454/fc90b5aa-0ba6-11e6-98db-cb16251944c4.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807455/fd669f80-0ba6-11e6-989b-382a2d09e1c1.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807457/ff790c7c-0ba6-11e6-9bbb-75140ffcad1e.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807460/010332ca-0ba7-11e6-823f-3180e12f0156.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807461/01b572c8-0ba7-11e6-9432-b34f922128e9.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807462/026ef8f6-0ba7-11e6-948f-ecd8855bb5c8.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807463/035e1a94-0ba7-11e6-8a5a-0803196abd93.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807464/04351d78-0ba7-11e6-9049-2d77aff16a22.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807465/05024b22-0ba7-11e6-8b84-b899458b550f.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807466/05f29afa-0ba7-11e6-809a-b674b77db9f2.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807467/06d8a3ec-0ba7-11e6-8029-bce2d7751b7c.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14807468/07981196-0ba7-11e6-869d-f507943148e1.png">

----

###<a name="network"></a>III.Card mạng và Network

####<a name="card-mang"></a>1.Card mạng trong VMware

Sử dụng máy ảo để triển khai một môi trường đa hệ điều hành, hoặc để thực thi các ứng dụng đơn nền khác nhau, trên cùng một máy tính vật lý là một giải pháp được chọn phổ biến hiện nay, bởi tính đơn giản và hiệu quả của nó.Với những người đang học tập, nghiên cứu về mạng máy tính hoặc đang triển khai các hệ thống dựa trên mạng máy tính thì giải pháp máy ảo là thực sự cần thiết với họ. Các phần mềm máy ảo giúp họ dễ dàng tạo ra một mạng máy tính “như thật” trên một máy tính vật lý.
Các thành phần hình thành nên mạng ảo trong VMware gồm **switch ảo**, **card mạng ảo**, **DHCP server ảo** và **thiết bị NAT**.


#####<a name="switch-ao"></a>1.Switch ảo (Virtual Switch)
**Switch ảo (Virtual Switch)** cũng giống như switch vật lý, một Virtual Switch kết nối các thành phần mạng ảo lại với nhau. Những  switch ảo hay còn gọi là mạng ảo, chúng có tên là VMnet0, VMnet1, VMnet2… một số switch ảo được gắn vào mạng một cách mặc định. Mặc định khi ta cài Wmware thì có sẵn 3 Switch ảo như sau: VMnet0 chế độ Bridged (cầu nối), VMnet8 chế độ NAT và VMnet1 chế độ Host-only. (Ta có thể thêm, bớt, chỉnh các option của VMnet bằng cách vào menu **Edit -> Virtual Network Editor**...)

<img src="https://cloud.githubusercontent.com/assets/16606859/14812610/0ad3c5c8-0bc8-11e6-8fb2-5efc83d28152.png">

Khi ta tạo các VMnet thì trên máy thật của ta sẽ tạo ra những card mạng ảo tương ứng, riêng VMnet0 kết nối trực tiếp với card mạng vật lý nên không tạo ra card VMnet.

<img src="https://cloud.githubusercontent.com/assets/16606859/14815534/1d64d110-0bd6-11e6-856a-bd6943c12fe4.png">

#####<a name="card-mang-ao"></a>2.Card mạng ảo (Virtual Network Adapter)

Khi tạo một máy ảo mới (New Virtual Machine wizard), card mạng ảo được tạo ra cho máy ảo. Những card mạng này hiển thị trên hệ điều hành máy ảo như là AMD PCNET PCI hay Intel Pro/1000 MT Server Adapter

Để thêm hoặc bớt VMnet ta có thể chọn **Add Network...** và **Remove Network...**

**Lưu ý**: khi **Add Network** nếu muốn add thêm card mạng thì nên add từng card sau đó thoát hẳn ra ngoài rồi tiếp tục add card thứ 2, làm tương tự với các card muốn thêm tiếp theo. Nếu các card vmnet này được add cùng một lúc khi khởi tạo máy ảo thì sau này khi đặt IP cho các interface của máy ảo có thể xảy ra hiện tượng **đảo IP hai interface** rất khó chịu và khó khăn trong việc sửa lỗi

<img src="https://cloud.githubusercontent.com/assets/16606859/14813158/9fcc4f2c-0bca-11e6-9caa-27f2c26afdbf.png">

Chế độ Briged : ở chế độ này thì card mạng trên máy ảo sẹ được gắn vào VMnet0 và VMnet0 này liên kết trực tiếp với card mạng vật lý. Ở chế độ này máy ảo sẽ kết nối internet thông qua lớp card mạng vật lý và có chung lớp mạng với card mạng vật lý.. Khi đó, địa chỉ IP của máy ảo phải nằm cùng subnet với địa chỉ IP mà card mạng máy thật đang dùng. Đây là lựa chọn thường được sử dụng nhiều nhất khi tạo một mạng máy tính ảo.

<img src="https://cloud.githubusercontent.com/assets/16606859/14816074/1ba6632c-0bd9-11e6-9932-cc52d6a49b9b.png">

Chế độ NAT: ở chế độ này thì card mạng của máy ảo kết nối với VMnet8, VMnet8 cho phép máy ảo đi internet thông qua cơ chế NAT (NAT device). Lúc này lớp mạng bên trong máy ảo khác hẳn với lớp mạng của card vật lý bên ngoài. IP của card mạng sẽ được cấp bởi DHCP VMnet8 cấp, trong trường hợp bạn muốn thiết lập IP tĩnh cho card mạng máy ảo bạn phải đảm bảo chung lớp mạng với VNnet8 thì máy ảo mới có thể đi internet.

<img src="https://cloud.githubusercontent.com/assets/16606859/14816047/f5505e30-0bd8-11e6-8911-636c6fb354c5.png">

Cơ chế host-only : ở cơ chế này máy ảo được kết nối với VMnet có tính có tính năng Host-only, trong trường hợp hình này là VMnet1 (bạn có thể add nhiều VMnet Host-only). VNnet Host-only kết nối ra một card mạng ảo tương ứng ngoài máy thật (như đã nói ở phần trên, khi ta add một VMnet thì có một card tương ứng với VMnet sẽ được tạo ra ở phần trên. Trường hợp này là VMware Network Adapter VMnet1).

<img src="https://cloud.githubusercontent.com/assets/16606859/14816049/f6243e30-0bd8-11e6-8d30-3d7043e3d0de.png">


Một điều lưu ý là khi bạn copy một máy ảo thì chúng ta nên thay đổi địa chỉ MAC của nó, như chúng ta đều biết là đại chỉ MAC là đại chỉ duy nhất và chúng ta nên làm điều này để tránh lỗi khi làm việc với hệ thống máy ảo. Việc trùng lấp MAC sẽ ảnh hưởng có khi khiến hệ thống không hoạt động được. Để thay đổi địa chỉ MAC ta chọn **Advanced** sau đó chọn **Generate**, phần mềm sẽ tự động tạo địa chỉ MAC cho chúng ta.

<img src="https://cloud.githubusercontent.com/assets/16606859/14815640/c04a65d4-0bd6-11e6-9f51-6b5ba8eeea66.png">


`Mẹo: Trong trường hợp bạn cần làm lab Load balancing, bạn cần 2 kết nối internet thì trên máy ảo bạn có thể add 2 card mạng, một card chọn cơ chế NAT và một card chọn cơ chế Bridge.`

### <a name="dhcp-ao"></a>3.DHCP Server ảo (Virtual DHCP Server)

**DHCP (Dynamic Host Configuration) server ảo** cung cấp địa chỉ IP cho các máy ảo trong việc kết nối máy ảo vào các Switch ảo không có tính năng Bridged (VMnet0). Ví dụ như DHCP ảo cấp đến các máy ảo có kết nối đến Host-only và NAT.

<img src="https://cloud.githubusercontent.com/assets/16606859/14815783/831686ce-0bd7-11e6-9c9c-603c3b47b4be.png">

Nếu bạn muốn bỏ chế độ DHCP của VMnet nào, bạn chỉ cần bỏ dấu check tại **Use local DHCP service to distribute IP address to VMs**. Bạn có thể tinh chỉnh lại DHCP bạn có thể chọn vào **DHCP Setting**, trong này bạn có thể chỉnh lại các tham số thời gian, tham số Scope IP (lưu ý: bạn chỉ có thể sửa lại vùng địa chỉ host chứ không được chỉnh lại vùng network)

----

##<a name="tong-ket"></a>Tổng kết
Bài viết trên tôi tổng hợp lại những kiến thức thu được khi cài đặt và sử dụng VMware Workstation, hi vọng nó giúp các bạn một phần nào đó.

Chắc chắn bài viết còn có nhiều thiếu sót, mong các bạn thông cảm và gửi feedback cho tôi để hoàn thiện thêm.

Liên lạc của tôi:

`thangnn.hanu@gmail.com`

Xin chân thành cảm ơn!



