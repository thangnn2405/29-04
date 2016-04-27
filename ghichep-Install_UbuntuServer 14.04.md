# Cài đặt Ubuntu Server 14.04 trên máy ảo vmware
----
## Mục Lục

###[I.Giới thiệu về Ubuntu Server](#gioi-thieu)

###[II.Hướng dẫn cài đặt](#cai-dat)

* [1.Cấu hình tối thiểu](#cau-hinh)

* [2.Các bước cài đặt](#cai-dat2)

###[Tổng kết](#tong-ket)

----


###<a name="gioi-thieu"></a>I.Giới thiệu về Ubuntu Server
----
Giấp phép: GNU GPL

Trang chủ dự án: http://www.ubuntu.com/server
  <ul>
  <li>Ubuntu Linux là một hệ điều hành máy tính dựa trên Debian GNU/Linux, là một trong bản phân phối end-user phổ biến nhất của Linux.</li>
  <li>Ubuntu là một hệ điều hành do cộng đồng phát triển và là tuyệt vời cho các máy tính xách tay, máy tính để bàn và cả máy chủ. Bất kỳ bạn sử dụng nó ở đâu, Ubuntu đều có tất cả các ứng dụng mà bạn luôn cần, từ các ứng dụng soạn thảo văn bản tới thư điện tử, từ phần mềm máy chủ web tới các công cụ lập trình.</li>
  <li>Ubuntu là và sẽ luôn là miễn phí (free of charge). Bạn không phải trả bất kỳ phí bản quyền nào. Bạn có thể tải nó về, sử dụng và chia sẻ Ubuntu với bạn bè, gia đình, nhà trường hoặc doanh nghiệp của bạn mà không vì bất cứ thứ gì một cách tuyệt đối.</li>
  <li>Ubuntu được tài trợ bởi Canonical Ltd (chủ sở hữu là một người Nam Phi Mark Shuttleworth). Thay vì bán Ubuntu, Canonical tạo ra doanh thu bằng cách bán hỗ trợ kĩ thuật. </li>
  <li>Ubuntu server là một phiên bản của ubuntu được sử dụng cho các server.</li>
  </ul>
  
  
###<a name="cai-dat"></a>II.Hướng dẫn cài đặt

----
####<a name="cau-hinh"></a>1.Cấu hình tối thiểu
Cấu hình tối thiểu cho việc cài đặt phiên bản server là máy có bộ vi xử lí 300 MHz x86, RAM 256 MB,[12] và card màn hình VGA hỗ trợ độ phân giải 640x480 trở lên.

####<a name="cai-dat2"></a>2.Các bước cài đặt

#####a.Chọn ngôn ngữ cho Ubuntu server

<img src="https://cloud.githubusercontent.com/assets/16606859/14824519/87b7462c-0c00-11e6-817c-5ec5ce6501b3.png">

#####b.Sau khi chọn ngôn ngữ, ta tiến hành cài đặt, chọn **Install Ubuntu Server**

<img src="https://cloud.githubusercontent.com/assets/16606859/14824578/c2825594-0c00-11e6-8500-e606af1e0b84.png">

#####c.Chọn ngôn ngữ hiển thị lúc tiến hành cài đặt

<img src ="https://cloud.githubusercontent.com/assets/16606859/14824579/c38a9230-0c00-11e6-933d-b15369756fa5.png">

#####d.Chọn Khu vực sinh sống, Ubuntu sẽ lấy timezone theo khu vực này

<img src="https://cloud.githubusercontent.com/assets/16606859/14824581/c44b7892-0c00-11e6-8394-a09e8b284fac.png">

#####e.Nếu khu vực địa lý chọn ở trên không tương ứng với ngôn ngữ đã chọn, phải chọn thủ công

<img src="https://cloud.githubusercontent.com/assets/16606859/14824590/c8195386-0c00-11e6-8634-3ac98119bc25.png">

#####f.Bạn muốn tự động dò mẫu bàn phím? Chọn **No** nếu muốn tự cài đặt bàn phím

<img src ="https://cloud.githubusercontent.com/assets/16606859/14824591/c8396d60-0c00-11e6-800e-f9edda6b33b7.png">

#####g.Nếu DHCP tốn thời gian để phản hồi hoặc máy không được cấp phát IP động, phải đặt địa chỉ IP tĩnh.Chọn **Configure network manually**.

<img src="https://cloud.githubusercontent.com/assets/16606859/14824595/c8642aaa-0c00-11e6-989d-68137b75f8db.png">

#####h.Đặt lại địa chỉ IP, gateway, name server( để trống nếu không muốn đặt ), hostname, domain name( để trống nếu không muốn đặt ).

<img src="https://cloud.githubusercontent.com/assets/16606859/14824594/c86288a8-0c00-11e6-9961-2b6c88c1fd63.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14824596/c8645412-0c00-11e6-857e-aee9cf10ce3a.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14824593/c861f154-0c00-11e6-9eeb-08e43bf29d66.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14824597/c868d546-0c00-11e6-9569-7b216b388237.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14824598/c87cc286-0c00-11e6-9c2b-b1694ed3d906.png">

#####i.Tiến hành tạo tài khoản user, mật khẩu 
<img src="https://cloud.githubusercontent.com/assets/16606859/14824599/c89173ac-0c00-11e6-8ede-ec0c47f97180.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14824600/c892b47e-0c00-11e6-992b-6b403ff345ed.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14824603/c8960a34-0c00-11e6-8bab-6cd4dd519c9f.png">

#####k.Bạn muốn tiến hành mã hóa thư mục home không? Nếu không thì chọn **No** để tiếp tục

<img src="https://cloud.githubusercontent.com/assets/16606859/14824601/c89424ee-0c00-11e6-9403-290cea6d93db.png">

#####l.Tiến hành chia ổ đĩa 

<img src="https://cloud.githubusercontent.com/assets/16606859/14824617/c90e3bd0-0c00-11e6-9676-f3e36643fffb.png">

<img src="https://cloud.githubusercontent.com/assets/16606859/14824618/c92a4fd2-0c00-11e6-91d8-af1155c454b4.png">

#####m.Nếu cần thiết lập proxy kết nối Internet thì điền thông tin vào ô, để trống nếu không cần

<img src="https://cloud.githubusercontent.com/assets/16606859/14824619/c92deb56-0c00-11e6-9d06-4d086eea6d9b.png">

#####n.Quản lý việc update trên hệ thống

<img src="https://cloud.githubusercontent.com/assets/16606859/14824620/c92eda98-0c00-11e6-86ad-b7ab61f4442d.png">

#####o.Chọn các gói có sẵn để cài đặt

<img src="https://cloud.githubusercontent.com/assets/16606859/14824621/c93102b4-0c00-11e6-93e6-e1b831d4a4d3.png">

#####p. Cài đặt GRUB boot loader trên ổ đĩa

<img src="https://cloud.githubusercontent.com/assets/16606859/14824622/c934bc56-0c00-11e6-881f-4d50d8241622.png">

#####q.Hoàn thành cài đặt

<img src="https://cloud.githubusercontent.com/assets/16606859/14824624/c93e590a-0c00-11e6-8592-da20e6968379.png">

###<a name ="tong-ket"></a>Tổng kết

Bài viết trên tôi tổng hợp lại những kiến thức thu được khi cài đặt và sử dụng VMware Workstation, hi vọng nó giúp các bạn một phần nào đó.

Chắc chắn bài viết còn có nhiều thiếu sót, mong các bạn thông cảm và gửi feedback cho tôi để hoàn thiện thêm.

Liên lạc của tôi:

`thangnn.hanu@gmail.com`

Xin chân thành cảm ơn!
