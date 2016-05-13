# DNS

----

##Mục lục





###[I.Giới thiệu ](#10)

* ####[1.DNS là gì](#11)

* ####[2.Công dụng](#12)

* ####[3.Ưu và nhược điểm của DNS](#13)


###[II.Cấu trúc ](#20)

* ####[1.Cấu trúc cơ sở dữ liệu](#21)

* ####[2.Cấu trúc của tên miền](#22)

* ####[3.Cấu trúc gói tin DNS](#23)

###[II.DNS Server ](#30)

* ####[1.Phân loại](#31)

* ####[2.Đồng bộ dữ liệu giữa các DNS server](#32)

 * ####[a.Các phương pháp đồng bộ dữ liệu giữa các DNS server](#32a)

 * ####[b.Cơ chế hoạt động đồng bộ dữ liệu giữa các DNS server](#32b)

* ####[3.Các bản ghi của DNS Server](#33)

 * ####[a.Bản ghi SOA(Start of Authority)](#33a)

 * ####[b.Bản ghi NS(Name Server)](#33b)

 * ####[c.Bản ghi A(Address record)](#33c)

 * ####[d.Bản ghi CNAME(Canonical name record)](#33d)

 * ####[e.Bản ghi MX(Mail Exchange record)](#33e)

 * ####[f.Bản ghi PTR(Pointer)](#33f)

 * ####[g.SERVICE LOCATION (SRV) RECORDS](#33g)

* ####[4.DNS Zone](#34)

* ####[5.Cơ chế phân giải tên miền](#35)


###[II.DNS Server ](#40)

* ####[1.Giới thiệu DNSSEC](#41)

* ####[2.Ứng dụng DNSSEC để bảo mật cho hệ thống DNS](#42)

* ####[3. Triển khai DNSSEC](#43)


---

###<a name = "10"></a>I.Giới thiệu

####<a name = "11"></a>1.Khái niệm
- DNS - Domain Name System


- Là hệ thống phân giải tên miền sang địa chỉ IP và ngược lại


- Được phát minh năm 1984 cho Internet

- Hệ thống tên miền (DNS) là một hệ thống đặt tên theo thứ tự cho máy vi tính, dịch vụ, hoặc bất kì nguồn lực tham gia vào Internet

- Liên kết nhiều thông tin đa dạng với tên miền được gán cho những người tham gia.



####<a name = "12"></a>2.Công dụng:
- Phân giải DNS là một dịch vụ nó sử dụng giao thức truy vấn thông tin có trong DNS server sử dụng port 53 UDP và TCP.

-  Hệ thống DNS là hệ thống phân giải tên phân phối phân cấp để định vị các host và các máy chủ dịch vụ.

- Thông tin được phân phối trên nhiều DNS server, tất cả chúng được liên kết thành một cấu trúc có phân cấp.

- Cho phép người dùng truy cập máy tính và tài nguyên mạng với những cái tên dể nhớ.


- Cho phép khối lượng công việc phân giải tên có thể được phân phối trên nhiều server và cơ sở sử liệu.


- Cho phép địa chỉ IP có thể thay đổi trong khi vẫn giữ nguyên tên máy, làm cho việc xác định vị trí tài nguyên mạng dễ dàng.


####<a name = "13"></a>3.Ưu và nhược điểm của DNS:

Giao thức DNS chống lại các loại tấn công như :

* Cache Poisoning or cache pollution : ngăn chặn cố gắng tấn công và đầu độc Cache DNS Server.
* Interference with DNS data on Secondary server : ngăn chặn attacker giả mạo làm DNS Primary Server để gửi các gói Update DNS qua cho các máy DNS Secondary Server để cập nhật
* Data interception : ngăn chặn kẻ tấn công can thiệp vào dữ liệu, khi dữ liệu đang được gửi đi. (Prevent Spoofing)

###<a name = "20"></a>II.Cấu trúc dịch vụ DNS

####<a name = "21"></a>1.Cấu trúc cơ sở dữ liệu

- Cơ sở dữ liệu của hệ thống DNS là hệ thống cơ sở dữ liệu phân tán và phân cấp hình cây

![](http://img.prntscr.com/img?url=http://i.imgur.com/aoxqQOx.png)

>Với .Root server là đỉnh của cây và sau đó các miền (domain) được phân nhánh dần xuống dưới và phân quyền quản lý. Khi một máy khách (client) truy vấn một tên miền nó sẽ đi lần lượt từ root phân cấp xuống dưới để đến DNS quản lý domain cần truy vấn. Tổ chức quản lý hệ thống tên miền trên thế giới là The Internet Coroperation for Assigned Names and Numbers (ICANN) .Tổ chức này quản lý mức cao nhất của hệ thống tên miền (mức root) do đó nó có quyền cấp phát các tên miền ở mức cao nhất gọi là Top-Level-Domain.
 
- Cấu trúc của dữ liệu được phân cấp hình cây root quản lý toàn bộ sơ đồ và phân quyền quản lý xuống dưới và tiếp đó các tên miền lại được chuyển xuống cấp thấp hơn (delegale) xuống dưới.

>Gốc (Domain root) : Nó là đỉnh của nhánh cây của tên miền. Nó có thể biểu diễn đơn giản chỉ là dấu chấm “.” 

> Tên miền cấp một (Top-level-domain) : gồm vài kí tự xác định một nước, khu vưc hoặc tổ chức. Nó đươc thể hiện là “.com” , “.edu” …. 

> Tên miền cấp hai (Second-level-domain): Nó rất đa dạng có thể là tên một công ty, một tổ chức hay một cá nhân. 

> Tên miền cấp nhỏ hơn (Subdomain) : Chia thêm ra của tên miền cấp hai trở xuống thường được sử dụng như chi nhánh, phòng ban của một cơ quan hay chủ đề nào đó. 





- Hệ thống tên miền(DNS) cho phép phân chia tên miền để quản lý và nó chia hệ thống tên miền thành zone và trong zone quản lý tên miền được phân chia đó.
>Các Zone chứa thông tin vê miền cấp thấp hơn, có khả năng chia thành các zone cấp thấp hơn và phân quyền cho các DNS server khác quản lý.


>Ví dụ : Zone “.vn” thì do DNS server quản lý zone “.vn” chứa thông tin về các bản ghi có đuôi là “.vn” và có khả năng chuyển quyền quản lý (delegate) các zone cấp thấp hơn cho các DNS khác quản lý như “.fpt.vn” là vùng (zone) do fpt quản lý.
Hệ thống cơ sở dữ liệu của DNS là hệ thống dữ liệu phân tán hình cây như cấu trúc đó là cấu trúc logic trên mạng Internet

####<a name = "22"></a>2.Cấu trúc của tên miền

* Cách đặt tên miền
 
 - Tên miền sẽ có dạng : Label.label.label….label

 - Độ dài tối đa của một tên miền là 255 ký tự

 - Mỗi một label tối đa là 63 ký tự bao gồm cả dấu “.”

 - Label phải được được bắt đầu bằng chữ số và chỉ được chứa chữ, số, dấu trừ (-)


* Phân loại tên miền

   - Com : Tên miền này được dùng cho các tổ chức thương mại. 

	- Edu : Tên miền này được dùng cho các cơ quan giáo dục, trường học. 

	- Net : Tên miền này được dùng cho các tổ chức mạng lớn. 

	- Gov : Tên miền này được dùng cho các tổ chức chính phủ. 

	- Org : Tên miền này được dùng cho các tổ chức khác. 

	- Int : Tên miền này dùng cho các tổ chức quốc tế

	- Info : Tên miền này dùng cho việc phục vụ thông tin

	- Arpa : Tên miền ngược

	- Mil : Tên miền dành cho các tổ chức quân sự, quốc phòng

	- Mã các nước trên thế giới tham gia vào mạng internet, các quốc gia này được qui định bằng hai chữ cái theo tiêu chuẩn ISO-3166 (Ví dụ : Việt Nam là .vn, Singapo la sg….)

* Tổ chức ICANN đã thông qua hai tên miền mới là 

	* Travel : Tên miền dành cho tổ chức du lịch
	* Post : Tên miền dành cho các tổ chức bưu chính


####<a name = "23"></a>3.Cấu trúc gói tin DNS

![](http://img.prntscr.com/img?url=http://i.imgur.com/l4qwi0A.png)

* **Identification**: Là một trường 16 bits, chứa mã nhận dạng, nó được tạo ra bởi một chương trình để thay cho truy vấn. Gói tin hồi đáp sẽ dựa vào mã nhận dạng này để hồi đáp lại. Chính vì vậy mà truy vấn và hồi đáp có thể phù hợp với nhau.

* **QR**: Là một trường 1 bit. Bít này sẽ được thiết lập là 0 nếu là gói tin truy vấn, được thiết lập là một nếu là gói tin hồi đáp.
* **Opcode**: Là một trường 4 bits, được thiết lập là 0 cho cờ hiệu truy vấn, được thiết lập là 1 cho truy vấn ngược, và được thiết lập là 2 cho tình trạng truy vấn.
* **AA**: Là trường 1 bit, nếu gói tin hồi đáp được thiết lập là 1, sau đó nó sẽ đi đến một server có thẫm quyền giải quyết truy vấn.
* **TC**: Là trường 1 bit, trường này sẽ cho biết là gói tin có bị cắt khúc ra do kích thước gói tin vượt quá băng thông cho phép hay không.
* **RD**: Là trường 1 bit, trường này sẽ cho biết là truy vấn muốn server tiếp tục truy vấn một cách đệ quy.
* **RA**: Trường 1 bit này sẽ cho biết truy vấn đệ quy có được thực thi trên server không.
* **Z**: Là trường 1 bit. Đây là một trường dự trữ, và được thiết lập là 0.
* **Rcode**: Là trường 4 bits, gói tin hồi đáp sẽ có thể nhận các giá trị sau:
	* 0: Cho biết là không có lỗi trong quá trình truy vấn.
	* 1: Cho biết định dạng gói tin bị lỗi, server không hiểu được truy vấn.	
	* 2: Server bị trục trặc, không thực hiện hồi đáp được.
	* 3: Tên bị lỗi. Chỉ có server có đủ thẩm quyền mới có thể thiết lập giá trị náy.
	* 4: Không thi hành. Server không thể thực hiện chức năng này.	
	* 5: Server từ chối thực thi truy vấn.
* **QDcount**: Số lần truy vấn của gói tin trong một vấn đề.
* **ANcount**: Số lượng tài nguyên tham gia trong phần trả lời.
* **NScount**: Chỉ ra số lượng tài nguyên được ghi lại trong các phần có thẩm quyền của gói tin.
* **ARcount**: Chỉ ra số lượng tài nguyên ghi lại trong phần thêm vào của gói tin.


###<a name = "30"></a>III.DNS Server
####<a name = "31"></a>1.Phân loại
Máy chủ phân giải tên miền (DNS Server) là những máy chủ được cài đặt, và cung cấp dịch vụ phân giải tên miền DNS. Có ba loại DNS server sau:

* Primary server
 - Nguồn xác thực thông tin chính thức cho các domain mà nó được phép quản lý
Thông tin về tên miền do nó được phân cấp quản lý thì được lưu trữ tại đây và sau đó có thể được chuyển sang cho các secondary server
 - Các tên miền do primary server quản lý thì được tạo và sửa đổi tai primary server và được cập nhật đến các secondary server
 - Primary server nên đặt gần với các client để có thể phục vụ truy vấn tên miền một cách dễ dàng và nhanh hơn. 
* Secondary server 

 - DNS được khuyến nghị nên sử dụng ít nhất là hai DNS server để lưu cho mỗi một zone. 
 - Primary DNS server quản lý các zone và secondary server sử dụng để lưu trữ dự phòng cho primary server. 
`Secondary DNS server được khuyến nghị dùng nhưng không nhất thiết phải có.`


 - Secondary server được phép quản lý những dữ liệu về tên miền (domain) nhưng không tạo ra các bản ghi về tên miền (domain) mà nó lấy về từ primary server.
 - Khi lượng truy vấn zone tăng cao tại primary server thì nó sẽ chuyển bớt tải sang cho secondary server .
 - Khi primary server gặp sự cố không hoạt động được thì secondary server sẽ hoạt động thay thế cho đến khi primary server hoạt động trở lại.
 - Secondary server nên được đặt ở gần với primary server và client để có thể phục vụ cho việc truy vấn tên miền dễ dàng hơn.
 - Không nên cài đặt secondary server trên cùng một mạng con (subnet) hoặc cùng một kết nối với primary server. Để khi primary server có kết nối bị hỏng thì cũng không có ảnh hưởng đến secondary server.
 - Primary server thường xuyên thay đổi hoặc thêm vào các zone mới. Nên DNS server sử dụng cơ chế cho phép secondary lấy thông tin từ primary server và lưu trữ nó. Có hai giải pháp lấy thông tin về các zone mới là lấy toàn bộ (full) hoặc chỉ lấy phần thay đổi.
* Caching-only server

 - Tất cả các DNS server đều có khả năng lưu trữ dữ liệu trên bộ nhớ cache của máy để trả lời truy vấn một cách nhanh chóng. Nhưng hê thống DNS còn có một loại Caching-only server.
 - Loại này chỉ sử dụng cho việc truy vấn, lưu giữ câu trả lời dựa trên thông tin có trên cache của máy và cho kết quả truy vấn. Chúng không hề quản lý một domain nào và thông tin mà nó chỉ giới hạn những gì được lưu trên cache của server.
 - Lúc ban đầu khi server bắt đầu chạy thì nó không lưu thông tin nào trong cache. Thông tin sẽ được cập nhật theo thời gian khi các client server truy vấn dịch vụ DNS. Nếu bạn sử dụng kết nối mạng WAN tốc độ thấp thì việc sử dụng caching-only DNS server là giải pháp hữu hiệu cho phép giảm lưu lượng thông tin truy vấn trên đường truyền.
 
 - Caching-only có khả năng trả lời các câu truy vấn đến client. Nhưng không chứa zone nào và cũng không có quyền quản lý bất kì domain nào. Nó sử dụng bộ cache của mình để lưu các truy vấn của DNS của client. Thông tin sẽ được lưu trong cache để trả lời các truy vấn đến client.
 - Stub Server: Là DNS Server chỉ chứa danh sách các DNS Server đã được authoritative từ Primary DNS. Sử dụng stub có thể tăng tốc độ phân giải tên và dễ quản lý.

####<a name = "32"></a>2.Đồng bộ dữ liệu giữa các DNS server
#####<a name = "32a"></a>a.Các phương pháp đồng bộ dữ liệu giữa các DNS server
Do đề phòng rủi ro khi DNS server không hoạt động hoặc kết nối bị đứt người ta khuyên nên dùng hơn một DNS server để quản lý một zone nhằm tránh trục trặc đường truyền. Do vậy ta phải có cơ chể chuyển dữ liệu các zone và đồng bộ giữa các DNS server khác nhau. Có hai cách để đồng bộ dữ liệu giữa các DNS server là primary server và secondary server như : Truyền toàn bộ zone(all zone transfer) và truyền phần thay đổi (Incremental zone transfer)

* Truyền toàn bộ zone (all zone transfer )

 - Khi một DNS server mới được thêm vào mạng thì nó được cấu hình như một secondary server mới cho một zone đã tồn tại. Nó sẽ tiến hành nhần toàn bộ dữ liệu từ primary server
 -  Đối với các DNS server phiên bản đầu tiên thường dùng giải pháp lấy toàn bộ các cơ sở dữ liệu khi có các thay đổi trong zone.

* Truyền phần thay đổi(Incremental zone)

 - Theo giải pháp này là chỉ truyền những những dữ liệu thay đổi của zone.
 -  Đồng bộ dữ liệu này được miêu tả chi tiết trong tiêu chuẩn RFC 1995. Nó cung cấp giải pháp hiệu quả cho việc đồng bộ những thay đổi, thêm, bớt của zone.


#####<a name = "32b"></a>b.Cơ chế hoạt động đồng bộ dữ liệu giữa các DNS server

Với trao đổi IXFR zone thì sự khác nhau giữa số serial của nguồn dữ liệu và bản sao của nó. Nếu cả hai đều có cùng số serial thì việc truyền dữ liệu của zone sẽ không thực hiên.

Nếu số serial cho dữ liệu nguồn lớn hơn số serial của secondary server thì nó sẽ thực hiện gửi những thay đổi của bản ghi nguồn (Resource record – RR) của zone ở primary server.

Để truy vấn IXFR thực hiên thành công và các thay đổi được gửi thì tai DNS server nguồn của zone phải được lưu giữ các phần thay đổi để sử dụng truyền đến nơi yêu cầu của truy vấn IXFR. Incremental sẽ cho phép lưu lượng truyền dữ liệu it và thực hiện nhanh hơn.

Zone transfer sẽ xảy ra khi có những hành động sau xảy ra:

- Khi quá trình làm mới của zone đã kết thúc (refresh exprire )
- Khi secondary server được thông báo zone đã thay đổi tại nguồn quản lý zone
- Khi thêm mới secondary server
- Tại secondary server yêu cầu chuyển zone

Các bước yêu cầu chuyển dữ liệu từ secondary server đến DNS server chứa zone để yêu cầu lấy dữ liệu về zone mà nó quản lý.

1. Khi cấu hình DNS server mới, thì nó sẽ gửi truy vấn yêu cầu gửi toàn bộ zone ( all zone transfer request (AXFR) ) đến DNS server chính quản lý dữ liệu của zone
2. DNS server chính quản lý dữ liệu của zone trả lời và chuyển toàn bộ dữ liệu về zone cho secondary server (destination) mới cấu hình. Để xác định có chuyển dữ liệu hay không thì nó dựa vào số serial được khai báo bằng bản ghi SOA.
3. Khi thời gian làm mới (refresh interval ) của zone đã hết, thì DNS server nhận dữ liệu sẽ truy vấn yêu cầu làm mới zone tới DNS server chính chứa dữ liêu zone.
4. DNS server chính quản lý dữ liệu sẽ trả lời truy vấn và gửi lại dữ liệu. Trả lời truy vấn dữ liệu gồm số serial của zone tại DNS server chính.
5. DNS server nhận dữ liệu về zone và sẽ kiểm tra số serial trong trả lời và quyết định xem có cần truyền dữ liêu không.  
 - Nếu giá trị của số serial của Primary Server bằng với số serial lưu tại nó thì sẽ kết thúc luôn. Và nó sẽ thiết lập lại với các thông số cũ lưu trong máy
 - Nếu giá trị của số serial tại Primary Server lớn hơn giá trị serial hiện tại DNS nhận dữ liệu. Thì nó kết luận zone cần được cập nhật và cần đồng bộ dữ liệu giữa hai DNS server.
 
- Nếu DNS server nhận kết luận rằng zone cần phải lấy dữ liệu thì nó sẽ gửi yêu cầu IXFR tới DNS server chính để yêu cầu truyền dữ liệu của zone.

- DNS server chính sẽ trả lời với việc gửi những thay đổi của zone hoặc toàn bộ zone
 - Nếu DNS server chính có hỗ trợ việc gửi những thay đổi của zone thì nó sẽ gửi những phần thay đổi của nó (Incremental zone transfer of the zone).
 - Nếu DNS server chính không hỗ trợ thì nó sẽ gửi toàn bộ zone (Full AXFR transfer of the zone ).

####<a name = "33"></a>3.Các bản ghi của DNS Server

#####<a name = "33a"></a>a.Bản ghi SOA(Start of Authority)
SOA chứa thông tin xác nhận về zone. Vì vậy chỉ có một bản ghi SOA duy  nhất cho zone, chúng chứa các thông tin sau:

* **Authoritative server**: Chứa thông tin của Primary DNS server của vùng.
* **Responsible person**: Thể hiện địa chỉ email của người quản trị, người chịu trách nhiệm của zone. Thay vì sử dụng @ thì nó sử dụng dấu chấm(.).
* **Serial**: Hiển thị phiên bản (version) hay là số lần mà zone được thay đổi, cứ mỗi lần dữ liệu trong zone thay đổi thì con số này lại tăng lên. Nó được dùng để so sánh và cập nhật dữ liệu giữa các máy chủ secondary DNS và máy chủ Master. Nếu serial của master server lớn hơn, máy secondary sẽ tiến hành cập nhật.
* **Refresh**: Chỉ ra khoảng thời gian máy chủ Secondary kiểm tra dữ liệu zone trên máy Primary để cập nhật nếu cần.
* **Retry**: Chỉ ra khoảng thời gian sau khi gởi yêu cầu trao đổi dữ liệu, giá trị Retry dùng để xác định thời gian bao lâu secondary zone chờ đợi để có thể gởi lại một yêu cầu khác.
* **Expire**: Sau khoảng thời gian qui định trong Expire mà máy chủ Secondary không kết nối được với máy chủ thì dữ liệu zone trên máy Secondary sẽ bị quá hạn. Một khi dữ liệu trên máy Secondary bị quá hạn thì máy chủ này sẽ không trả lời mọi truy vấn về zone này nữa.
* **TTL (Time to Live)**: Giá trị này áp dụng cho mọi record trong zone và được đính kèm trong thông tin trả lời một truy vấn. Mục đích của nó là chỉ ra thời gian mà các máy chủ name sever khác cache lại thông tin trả lời. Việc cache thông tin trả lời giúp giảm lưu lương truy vấn DNS trên mạng.

   [tên-miền] IN SOA [tên-server-dns] [địa-chỉ-email] (
	
	
	Serial number;
	
	Refresh number;
	
	Retry number;
	
	Expire number;
	
	Minimum TTL)

#####<a name = "33b"></a>b.Bản ghi NS(Name Server)
* NS xác định một DNS server xác thực cho zone, bao gồm các primary server  và secondary server. Bởi vì một zone có thể được thiết lập trên nhiều server khác nhau, mỗi server của zone có một record.
* Cú pháp: `[domain-name] IN NS [name-server]`
* Ví dụ : `thangnn.hanu.vn IN NS hanu.vn`



#####<a name = "33c"></a>c.Bản ghi A(Address record)
Trả về một địa chỉ IPv4 32bit, được sử dụng để ánh xạ giữa tên của máy tính trong mạng tới 1 địa chỉ IP của một máy tính. Ngoải ra bản ghi này còn sử dụng cho DNSBLs(A DNS-based Blackhole List) dùng để ngăn chặn email spam. Nó cũng có thể được dùng để lưu trữ các subnet mask trong RFC 1101,...

Cú pháp `[Domain] IN A [IP]`
Ví dụ: `thangnn.hanu IN A 192.168.1.10`

>Bản ghi AAAA(Address record) tương tự bản ghi A nhưng dùng cho IPv6 

#####<a name = "33d"></a>d.Bản ghi CNAME(Canonical name record)
CNAME hay Alias, một bí danh hay có thể hiểu là một cách định danh khác cho một host name. Nó thường được dùng để ẩn đi một số thông tin trong mạng của bạn khi một client kết nối đến, đặc biệt nếu bạn cần phải thực hiện một số thay đổi trong tương lai. Một ví dụ điển hình để minh họa là bạn có một web server chứa website với host name của nó là web.hoanghiepktv.com bay giờ bạn muốn người dùng truy cập bằng www.hoanghiepktv.com thì bạn định nghĩa cho nó một CNAME hay Alias là www.

Cú pháp : `[alias-domain] IN CNAME [canonical-domain]`

Ví dụ: `mail IN CNAME hanu.vn`

#####<a name = "33e"></a>e.Bản ghi MX(Mail Exchange record)
Record này xác định một máy chủ email của tổ chức, dịch vụ, hay thiết bị tiếp nhận mail thông qua Simple Mail Transfer Protocol (SMTP). Để có khả năng chống chịu lỗi, bạn có thể chỉ định một server mail thứ hai. Vì vậy, nếu server mail thứ nhất không sẵn sàng, email có thể được gởi đến server thứ hai. Mặc dù là mỗi máy chủ email được yêu cầu phải có một MX record riêng, nhưng máy có số ưu tiên (Mail server priority) nhỏ hơn thì sẽ có độ ưu tiên lớn hơn.

Cú pháp: `[tên miền] IN MX [giá trị ưu tiên] [máy chủ thư điện tử]`

Ví dụ : `hanu.vn IN MX 1 mail.hanu.vn`

#####<a name = "33f"></a>f.Bản ghi PTR(Pointer)

Được dùng để phân giải ngược một địa chỉ IP thành host name. Điểm khác biệt với Host (A và AAAA) là địa chỉ IP được ghi ngược. Ví dụ: mail.hanu.vn có IP là 192.168.100.254 thì nó sẽ được viết như sau:
`254.100.168.192.in-addr.arpa. IN PTR mail.hanu.vn.`

#####<a name = "33g"></a>g.SERVICE LOCATION (SRV) RECORDS
SRV là những record đặc biệt, thường xuất hiện trong máy chủ DNS server của Windows. SRV thường được dùng chỉ ra và tìm kiếm các máy chủ dịch vụ . Ví dụ, bạn cài đặt Active Directory thông qua một domain controller, SRV record tự động được thêm vào DNS zone. Nếu các user công thể kết nối đến dịch vụ DNS hoặc SRV record không có trong zone, các user không thể log in vào miền Active Directory.
Cú pháp: `_[service]._[proto].[name]. [TTL] [class] SRV [priority] [weight] [port] [target].`

Ví dụ: `_sip._tcp.hanu.vn. 86400 IN SRV 0 5 5060 sipserver.hanu.vn.`

####<a name = "34"></a>4.DNS Zone

- Tập hợp các ánh xạ từ host đến địa chỉ IP và từ IP đến host của một phần liên tục trong một nhánh của domain.
- Thông tin của DNS Zones là những record gồm tên Host và địa chỉ IP được lưu trong DNS Server, DNS Server quản lý và trả lời những yêu cầu từ Client liên quan đến DNS Zones này.
- Hệ thống tên miền (DNS) cho phép phân chia tên miền để quản lý và nó chia hệ thống tên miền thành Zone và trong Zone quản lý tên miền được phân chia đó.
Các Zone chứa thông tin vê miền cấp thấp hơn, có khả năng chia thành các Zone cấp thấp hơn và phân quyền cho các DNS Server khác quản lý.
- **Forward Lookup Zone**: Dùng để phân giải host name thành địa chỉ IP
- **Reverse Lookup Zone** : Dùng để phân giải ngược giống như In-addr.arpa Zone. Cho phép phân giải địa chỉ IP thành host name

####<a name = "35"></a>5.Cơ chế phân giải tên miền

Mỗi khi người dùng truy cập tài nguyên mạng bằng tên miền hoặc host name (tên máy), và cái tên truy cập đó sẽ được phân giải thành địa chỉ IP, tên và địa chỉ IP này được cache lại nên máy tính người dùng không cần thiết phải liên hệ với máy DNS server liên tục để phân giải tên. Nếu tên này chưa có trong cache (bộ nhớ đệm), client sẽ liên hệ với DNS server đã được cấu hình ở phần khai báo IP của hệ thống. Nếu server này ở trạng thái sẵn sàng và nó không thể xác định được địa chỉ, client sẽ không hỏi thêm một server nào khác. Tuy nhiên, bởi vì DNS là hệ thống phân phối phân cấp, DNS server cục bộ sẽ cần liên hệ với những DNS server khác để có thể phân giải IP mà client yêu cầu.

DNS client được hiểu như là người có nhu cầu cần phân giải DNS. Bởi vì một một client hay một server đều cần sự phân giải địa chỉ IP của DNS server và xác định được dịch vụ mạng, các client và các server đều có thể là DNS client.

Khi một DNS client truy vấn một DNS server, nó thực hiện một truy vấn đệ quy (recursive query), trong khi có các yêu từ các host, DNS server có thể trả các yêu cầu dữ liệu này hoặc trả lời tên miền không tồn tại. DNS server cũng có thể thực hiện các truy vấn đệ quy đến các máy chủ DNS khác nếu nó được cấu hình chuyển tiếp yêu cấu đến DNS server khác bởi vì nó không có câu trả lời.
![](http://img.prntscr.com/img?url=http://i.imgur.com/ihyhvcd.png)

Khi DNS server nhận được yêu cầu, trước tiên nó sẽ kiểm tra có cache của mình. Sau đó nó kiểm tra để xem nó có thẩm quyền hay không đối với yêu cầu domain. Nếu có biết câu trả lời, nó sẽ hồi đáp với câu trả lời.

Nếu DNS server không biết câu trả lời (lúc này nó sẽ đóng vai trò là client DNS server, thay client thực hiện truy vấn) và nó không được cấu hình chuyển tiếp yêu cầu đến một DNS server khác, client DNS server sẽ sử dụng cơ chế phân cấp của DNS để tìm câu trả lời chính xác. Thay vì thực hiện truy vấn đệ quy, client DNS server sẽ thực hiện truy vấn lập đi lập lại (iterative query), với truy vấn này sẽ trả lại một câu trả lời tốt nhất hiện nay nếu client DNS server không biết câu trả lời tốt nhất. Ví dụ như, khi user gõ www.hanu.vn vào trình duyệt, client DNS server  không có câu trả lời, client DNS server sẽ liên hệ với một root DNS server để biết được địa chỉ của máy chủ tên miền com. Client DNS server sau đó liên hệ với máy chủ tên miền com để lấy máy chủ tên của hanu.vn. Client DNS server tiếp tục liên hệ với máy chủ tên miền của hanu.vn để lấy địa chỉ IP của www.hanu.vn. Client DNS server trả lời cho client với địa chỉ IP đã phân giải. Ngoài ra, nó cũng thêm địa chỉ này vào cache của nó cho các truy vấn sau này.

Trong một vài trường hợp, client DNS server không biết câu trả lời và nó không thể tìm thấy câu trả lời, nên client DNS server trả lời cho client rằng nó không thể tìm thấy hoặc là truy vấn domain không tồn tại.

Hầu hết các DNS client cấu hình với 2 hoặc nhiều DNS server (trong phần cấu hình IP của client). DNS server thứ 2 sẽ liên hệ truy vấn DNS chỉ khi server đầu tiên không sẵn sàng. Nếu DNS server đầu tiên (có hoạt động) không có câu trả lời cho truy vấn, thì DNS server thứ hai sẽ không được dùng đến.



###<a name = "40"></a>IV.DNSSEC

DNSSEC là công nghệ an toàn mở rộng cho hệ thống DNS. Trong đó DNSSEC sẽ cung cấp một cơ chế xác thực giữa các máy chủ DNS với nhau và xác thực cho từng zone dữ liệu để đảm bảo toàn vẹn dữ liệu.

####<a name = "41"></a>1.Giới thiệu DNSSEC

Trong khi giao thức DNS thông thường không có công cụ để xác thực nguồn dữ liệu. Trước nguy cơ dữ liệu DNS bị giả mạo và bị làm sai lệch trong các tương tác giữa máy chủ DNS với các máy trạm (resolver) hoặc máy chủ chuyển tiếp (forwarder), công nghệ bảo mật mới DNSSEC đã được nghiên cứu, triển khai áp dụng để hỗ trợ cho DNS bảo vệ chống lại các nguy cơ giả mạo làm sai lệch nguồn dữ liệu. Trong đó DNSSEC sẽ cung cấp một cơ chế xác thực giữa các máy chủ DNS với nhau và xác thực cho từng zone dữ liệu để đảm bảo toàn vẹn dữ liệu.

DNSSEC là công nghệ an toàn mở rộng của DNS, về bản chất DNSSEC cung cấp các cơ chế có khả năng chứng thực và đảm bảo toàn vẹn dữ liệu cho hệ thống DNS, theo đó DNSSEC đưa ra 4 loại bản ghi mới:

- Bản ghi khóa công cộng DNS (DNSKEY - DNS Public Key): sử dụng để chứng thực zone dữ liệu.
- Bản ghi chữ ký tài nguyên (RRSIG - Resource Record Signature): sử dụng để chứng thực cho các bản ghi tài nguyên trong zone dữ liệu.
- Bản ghi bảo mật kế tiếp (NSEC - Next Secure): sử dụng trong quá trình xác thực đối với các bản ghi có cùng sở hữu tập các bản ghi tài nguyên hoặc bản ghi CNAME. Kết hợp với bản ghi RRSIG để xác thực cho zone dữ liệu.
- Bản ghi ký ủy quyền (DS - Delegation Signer): thiết lập chứng thực giữa các zone dữ liệu, sử dụng trong việc ký xác thực trong quá trình chuyển giao DNS.

Mục tiêu đặt ra là DNSSEC không làm thay đổi tiến trình truyền dữ liệu DNS và quá trình chuyển giao từ các DNS cấp cao xuống các DNS cấp thấp hơn, mặt khác đối với các máy trạm (resolver) cần yêu cầu đáp ứng hỗ trợ các cơ chế mở rộng này. Một zone dữ liệu được ký xác thực sẽ chứa đựng một trong các bản ghi RRSIG, DNSKEY, NSEC và DS.

Như vậy bằng cách thức tổ chức thêm những bản ghi mới và những giao thức đã được chỉnh sửa nhằm chứng thực nguồn gốc và tính toàn vẹn dữ liệu cho hệ thống, với DNSSEC, hệ thống DNS đã được mở rộng thêm các tính năng bảo mật và được tăng cường độ an toàn, tin cậy, khắc phục được những nhược điểm của thiết kế sơ khai ban đầu. Vừa đáp ứng được các yêu cầu thông tin định tuyến về tên miền, giao thức làm việc giữa các máy chủ DNS với nhau, vừa đáp ứng được các yêu cầu bảo mật, tăng cường khả năng dự phòng cho hệ thống.

####<a name = "42"></a>2.Ứng dụng DNSSEC để bảo mật cho hệ thống DNS

Các bản ghi trong DNSSEC được khai báo trong các zone dữ liệu để chứng thực thông tin trong zone dữ liệu đó, đảm bảo độ tin cậy trong quá trình trao đổi thông tin cũng như truy vấn tìm kiếm DNS. Trong khi vẫn đảm bảo hoạt động bình thường của các bản ghi tài nguyên DNS thông thường thì các bản ghi DNSSEC cần khai báo chính xác và thông tin xác thực phải đồng bộ.

DNSSEC đưa ra khái niệm ký zone (Zone Signing): một zone được ký bao gồm khóa công cộng DNS (DNS Public Key), chữ ký bản ghi tài nguyên (RRSIG), bảo mật tiếp theo (NSEC), và ký chuyển giao (Delegation Signer). Một zone mà không thêm những bản ghi này vào là một zone chưa được ký. Đồng thời DNSSEC đòi hỏi thay đổi định nghĩa của bản ghi tài nguyên CNAME bằng 2 bản ghi chứng thực là bản ghi RRSIG và bản ghi NSEC.

* Thêm bản ghi DNSKEY vào một zone

Để ký một zone, người quản trị zone sẽ tạo một hay nhiều cặp khóa công cộng/dành riêng (public/private), cặp khóa công cộng dùng cho zone chính và khóa riêng để ký cho những bản ghi cần xác thực trong zone. Mỗi zone phải thêm một bản ghi DNSKEY (zone DNSKEY RR) chứa đựng khóa công cộng tương ứng, và mỗi khóa riêng được dùng để tạo bản ghi RRSIG trong zone.

Bản ghi chứng thực DNSKEY cho zone phải có bit Zone Key của trường dữ liệu cờ đặt giá trị là 1.  Nếu quản trị zone có ý định ký một zone để chứng thực thì zone chính phải chứa đựng ít nhất một bản ghi DNSKEY để hoạt động như một điểm bảo mật ở trong zone. Điểm bảo mật được dùng cùng với bản ghi DS tương ứng ở zone cha trong hoạt động chuyển giao DNS.

* Thêm các bản ghi RRSIG vào một zone

Với một zone đã được ký bởi bản ghi DNSKEY, thì các bản ghi tài nguyên trong zone đó cần có một bản ghi RRSIG ký xác thực. Một bản ghi tài nguyên có thể có nhiều bản ghi RRSIG kết hợp với nó. Các bản ghi RRSIG chứa chữ ký điện tử kết hợp chặt chẽ với các bản ghi tài nguyên để xác thực cho các bản ghi tài nguyên đó. Đặc biệt, giá trị TTL trong các bản ghi RRSIG với một tên miền sở hữu không giống với giá trị TTL của bản ghi tài nguyên.

Trong trường hợp các bản ghi tài nguyên cùng sở hữu một tên miền thì cần kết hợp bản ghi RRSIG với bản ghi NSEC để xác thực, trường hợp này cũng tương tự đối với bản ghi CNAME.

Tập bản ghi tài nguyên NS trong zone phải được ký xác thực, khi bản ghi NS là bản ghi chuyển giao từ máy chủ tên miền cha xuống máy chủ tên miền con thì cần kết hợp bản ghi RRSIG với bản ghi xác thực DS. Bản ghi glue cũng cần xác thực bằng RRSIG.

* Thêm bản ghi NSEC vào một zone

Mỗi tên miền sở hữu nhiều hơn 1 bản ghi tài nguyên cùng loại trong một zone hoặc một tập bản ghi NS chuyển giao thì phải có một bản ghi NSEC để xác thực. Trong đó, giá trị TTL nhỏ nhất cho một bản ghi NSEC phải bằng với giá trị TTL trong bản ghi SOA của zone đó.

Một bản ghi NSEC và bản ghi RRSIG kết hợp với nó không nhất thiết là bản ghi duy nhất cho bất cứ tên miền sở hữu bản ghi bảo mật nào. Vì thế, qui trình ký không phải tạo bất cứ bản ghi RRSIG hoặc NSEC nào cho những tên miền sở hữu bản ghi mà không sở hữu bất cứ tập bản ghi nào trước khi vùng được ký. Lý do chính là muốn ổn định giữa không gian đã ký và không gian chưa ký của một zone và mong giảm rủi ro đối với những mâu thuẫn trong phản hồi những máy chủ truy vấn đệ qui không được cấu hình bảo mật.

Các bản ghi RRSIG hiện diện tại tên miền sở hữu các tập bản ghi mà nó nắm giữ. Các bản ghi NSEC hiện diện tại tên miền sở hữu và còn hiện diện tại điểm chuyển giao của các tên miền con của chúng. Vì thế, bất cứ tên miền nào có một tập bản ghi NSEC sẽ có các bản ghi RRSIG trong vùng được ký.

* Thêm bản ghi DS vào trong một zone

Bản ghi DS thiết lập chứng thực giữa những zone DNS. Một bản ghi DS được biểu diễn cho bản ghi chuyển giao khi vùng con được ký. Bản ghi DS kết hợp với bản ghi RRSIG để chứng thực cho zone được chuyển giao tại máy chủ tên miền cha. Bản ghi DS được khai báo trước , và bản ghi RRSIG khai báo sau giống như khai báo để xác thực cho một bản ghi tài nguyên thông thường.

Trường TTL của tập bản ghi DS phải ứng với trường TTL của tập bản ghi NS ủy quyền (có nghĩa là tập bản ghi NS trong cùng vùng chứa tập bản ghi DS). Việc xây dựng một bản ghi DS đòi hỏi phải có hiểu biết của bản ghi DNSKEY tương ứng trong vùng con để đưa ra được các giao tiếp giữa vùng con và vùng cha.

* Những thay đổi đối với bản ghi CNAME

Nếu một tập bản ghi CNAME hiện diện tại một tên miền trong một vùng được ký, sẽ thay thế bằng tập bản ghi RRSIG và NSEC tương ứng trong tên miền đó. Đây là một phiên bản đã được chỉnh sửa của định nghĩa CNAME nguyên gốc. Định nghĩa nguyên gốc của bản ghi CNAME không cho phép bất cứ kiểu nào khác cùng tồn tại với bản ghi CNAME, nhưng một vùng được ký đòi hỏi những bản ghi NSEC và bản ghi RRSIG cho mọi tên miền. Để giải quyết xung đột này, định nghĩa của bản ghi CNAME của hệ thống DNS đã được chỉnh sửa lại để cho phép nó cùng tồn tại với các bản ghi NSEC và bản ghi RRSIG.

DNSKEY được thiết lập để tạo khóa công cộng nhằm thực hiện xác thực với các máy chủ DNS khác có cùng khóa công cộng này. Các bản ghi chứng thực RRSIG sử dụng để ký xác thực cho các bản ghi tài nguyên SOA, A, MX… Đối với các bản ghi NS khai báo quyền sở hữu tên miền đối với tên miền gốc thì sử dụng bản ghi NSEC kết hợp với bản ghi RRSIG để xác thực. Đối với các bản ghi chuyển giao từ DNS cha xuống các máy chủ tên miền DNS con thì kết hợp với bản ghi DS với bản ghi RRSIG để xác thực.

#### <a name = "43"></a>3. Triển khai DNSSEC


![](http://img.prntscr.com/img?url=http://i.imgur.com/gc019gx.png)

Quá trình triển khai DNSSEC bao gồm: ký chuyển giao tên miền .VN từ DNS Root về máy chủ DNS quốc gia quản lý và ký chuyền giao tên miền từ máy chủ DNS quốc gia cho các đơn vị khác quản lý. Việc triển khai DNSSEC trên hệ thống DNS quốc gia gồm các bước như sau:

Trên máy chủ DNS:

* BƯỚC 1: Tạo cặp khóa riêng và khóa công khai
* BƯỚC 2: Lưu trữ  bảo mật khóa riêng
* BƯỚC 3: Phân phối khóa công khai
* BƯỚC 4: Ký zone
* BƯỚC 5: Thay đổi khóa
* BƯỚC 6: Ký lại zone


Trên resolver:

* BƯỚC 7: Cấu hình Trust Anchors
* BƯỚC 8: Thiết lập chuỗi tin cậy và xác thực chữ ký
