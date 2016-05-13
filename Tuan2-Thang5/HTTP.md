# Giao Thức HTTP

>Trước khi tiến hành đọc bài biết này, bạn cần có sự hiểu biết cơ bản về các khái niệm web, các trình duyệt web, các Server, và phần mềm xây dựng trên cơ sở cấu trúc Server-Client.

---
## Mục lục
###[I.HTTP là gì](#definition)

- ####[1.Các đặc điểm cơ bản](#basic-features)

- ####[2.Cấu trúc cơ bản](#basic-architecture)

####[II.Các tham số trong HTTP](#parameters)

- ####[1.Phiên bản HTTP](#http-version)

- ####[2.Uniform Resource Identifiers (URI)- Bộ nhận diện nguồn tài nguyên đồng nhất](#http-uri)

- ####[3.Date/Time Formats-Các định dạng Ngày/Thời gian](#http-format)

- ####[4.Character Sets(Các bộ ký tự)](#http-charset)

- ####[5.Content Encodings(Mã hóa nội dung)](#http-encode)

- ####[6.Media Types(Các kiểu đa phương tiện)](#http-mediatype)

- ####[7.Language Tags(Các thẻ ngôn ngữ)](#http-langtag)

####[III.Message trong HTTP](#http-message)

- ####[1.Dòng đầu thông báo (start-line)](#start-line)

- ####[2.Các trường Header](#header-field)

- ####[3.Phần thân thông báo(Message-body)](#message-body)

####[IV.Requests trong HTTP](#request)

- ####[1.Dòng yêu cầu(Request-Line)](#request-line)

- ####[2.Phương thức yêu cầu(Request-Method)](#request-method)

- ####[3.Bộ nhận diện Nguồn Đồng nhất(Request-URI)](#request-uri)

- ####[4.Các trường Request](#request-header)

####[IV.Responses trong HTTP](#http-responses)

- ####[1.Dòng trạng thái](#status-line)

- ####[2.Phiên bản HTTP](#http-version2)

- ####[3.Mã trạng thái(Status Code)](#status-code)

---

###<a name ="definition"></a>I.HTTP là gì
HTTP là viết tắt của Giao thức truyền tải siêu văn bản (Hypertext Transfer Protocol) là một giao thức cấp độ ứng dụng(application-level) cho các hệ thống thông tin phân phối, cộng tác và đa phương tiện. Đây là nền tảng cho giao tiếp thông tin cho World Wide Web từ 1990.

HTTP là một giao thức ở tầng ứng dụng trong các hệ thống thông tin phân tán, cộng tác, siêu phương tiện (hypermedia), cho phép một máy khách gửi yêu cầu đơn giản dạng tệp siêu văn bản đến máy chủ và nhận đáp ứng từ máy chủ

Tim Berners-Lee, một nhà khoa học máy tính người Anh và nhóm dự án “World Wide Web” là những người đầu tiên được công nhận phát minh ra HTTP cùng với ngôn ngữ đánh dấu siêu văn bản HTML (HyperText Markup Language), công nghệ liên quan đến máy chủ web và trình duyệt web dựa trên văn bản

HTTP cho phép một tập các phương thức hoặc câu lệnh (methods/commands) và các tiêu đề mở-đóng (open-ended header) để chỉ ra mục đích của một yêu cầu. HTTP được xây dựng trên nguyên tắc tham chiếu được cung cấp bởi định danh tài nguyên thống nhất (Uniform Resource Identifier - URI), hoặc định vị tài nguyên thống nhất (Uniform Resource Locator - URL) hay tên tài nguyên thống nhất (Uniform Resource Name - URN), nhằm chỉ ra nguồn tài nguyên áp dụng phương thức. Thông điệp được gửi theo định dạng tương tự với định dạng sử dụng thư Internet theo quy định của MIME.

HTTP cũng được sử dụng như một giao thức chung để truyền thông giữa tác nhân người dùng (User Agent - UA) và các proxy, gateway (Một máy chủ hoạt động như một điểm trung gian đối với máy chủ khác, tiếp nhận các yêu cầu từ máy khách với vai trò như một máy chủ gốc) đến các hệ thống Internet khác, gồm cả các hệ thống hỗ trợ giao thức truyền thư đơn giản (Simple Mail Transfer Protocol – SMTP), giao thức truyền tin tức liên mạng (Network News Transfer Protocol – NNTP), giao thức truyền tệp tin (File Tranfer Protocol – FTP), giao thức Gopher (được thiết kế chính để tìm kiếm và lưu trữ tài liệu phân tán) và WAIS (hệ thống tìm kiếm theo mô hình khách – chủ sử dụng tiêu chuẩn ANSI Z39.50). Bằng cách này, HTTP cho phép truy cập siêu phương tiện đến các tài nguyên sẵn có từ các ứng dụng đa dạng.

####<a name="basic-features"></a>1.Các đặc điểm cơ bản
Có 3 đặc trưng cơ bản biến HTTP trở thành một giao thức đơn giản nhưng mạnh mẽ:

- **HTTP là giao thức connectionless(kết nối không liên tục)**: HTTP client khởi tạo một yêu cầu HTTP sau đó ngắt kết nối đến Server và chờ đợi phản hồi. Server sẽ xử lý yêu cầu và tái thiết lập kết nối với client để gửi phản hồi trở lại.

- **HTTP là một phương tiện độc lập**:   Bất kỳ loại dữ liệu nào cũng có thể được gửi bởi HTTP miễn là Server và Client biết cách để kiểm soát nội dung dữ liệu.  Client cũng như Server phải xác định kiểu nội dung bằng cách sử dụng kiểu MIME thích hợp.

- **HTTP là giao thức stateless**: Như đã được đề cập ở trên, HTTP là connectionless và nó biến HTTP trở thành một giao thức Stateless. Server và Client nhận thức nhau chỉ trong một request.

####<a name="basic-architecture"></a>2.Cấu trúc cơ bản

Sơ đồ dưới đây chỉ cấu trúc rất đơn giản của một ứng dụng web và miêu tả vị trí của HTTP:

![](http://img.prntscr.com/img?url=http://i.imgur.com/ib9OX4v.gif)

Giao thức HTTP là một giao thức Yêu cầu/Phản hồi dựa trên cấu trúc Client/Server, nơi mà các trình duyệt web, các thiết bị tìm kiếm,… hoạt động như các Client, và các Server web hoạt động như một Server.

**Client**

Client gửi một yêu cầu tới Server theo dạng URI, phiên bản giao thức, một thông báo MIME chứa các request modifiers, thông tin Client, và nội dung đối tượng có thể qua một kết nối TCP/IP.

**Server**

Server phản hồi với một dòng trạng thái, bao gồm phiên bản giao thức của thông báo và một code thành công hoặc lỗi, theo sau bởi một thông báo MIME chứa thông tin Server, thông tin thực thể đa phương tiện và nội dung đối tượng có thể.


----
####<a name ="parameters"></a>II.Các tham số trong HTTP

####<a name ="http-version"></a>1.Phiên bản HTTP

HTTP sử dụng một sơ đồ đánh số  `<major>.<minor>` để chỉ phiên bản của giao thức. Phiên bản của một thông báo HTTP được chỉ bởi một trường HTTP-Version trong dòng đầu tiên. Đây là cú pháp chung trong việc xác định số phiên bản HTTP:

	HTTP-Version   = "HTTP" "/" 1*DIGIT "." 1*DIGIT

Ví dụ


	HTTP/1.0


	hoặc


	HTTP/1.1


####<a name ="http-uri"></a>2.Uniform Resource Identifiers (URI)- Bộ nhận diện nguồn tài nguyên đồng nhất

URI là một chuỗi được định dạng đơn giản chứa tên, vị trí,.. để xác định một nguồn, ví dụ, một website, một dịch vụ web, …. 

Cú pháp chung của URI được sử dụng cho HTTP như sau:

	URI = "http:" "//" host [ ":" port ] [ abs_path [ "?" query ]]

Ở đây, nếu port trống hoặc khôngncung cấp, thì port 80 là port mặc định cho HTTP và một abs_path trống là tương đương với một abs_path là “/”. Các ký tự khác trong các bộ thiết lập reserved và unsafe là tương đương với mã hóa “%” HEX HEX” của chúng.

Ví dụ

	http://abc.com:80/~vinc/home.html

	http://ABC.com/%7Vinc/home.html

	http://ABC.com:/%7Vinc/home.html


####<a name ="http-format"></a>3.Date/Time Formats-Các định dạng Ngày/Thời gian

Tất cả các nhãn Ngày/Thời gian HTTP Phải được biểu diễn trong Greenwich Mean Time (GMT), không có trường hợp ngoại lệ. Các ứng dụng HTTP cho phép sử dụng 3 nhãn đại diện Ngày/Thời gian sau:


	Sun, 06 Nov 1994 08:49:37 GMT  ; RFC 822, updated by RFC 1123

	Sunday, 06-Nov-94 08:49:37 GMT ; RFC 850, obsoleted by RFC 1036  

	Sun Nov  6 08:49:37 1994       ; ANSI C's asctime() format

####<a name ="http-charset"></a>4.Character Sets(Các bộ ký tự)

Chúng ta sử dụng các bộ ký tự để xác định các thiết lập ký tự mà Client ưa thích. Nhiều bộ thiết lập ký tự có thể được liệt kê riêng biệt bởi các dấu phẩy. Nếu một giá trị là không được xác định, mặc định là US-ASII.

Ví dụ

Dưới đây là các bộ ký tự có hợp lệ:

	US-ASCII

	hoặc

	ISO-8859-1

	hoặc

	ISO-8859-7

####<a name ="http-encode"></a>5.Content Encodings(Mã hóa nội dung)

Một giá trị mã hóa nội dung là giá trị được mã hóa nhờ một thuật toán mã hóa trước khi truyền nó tới mạng. Mã hóa nội dung được sử dụng lần đầu cho phép một tài liệu để được nén hoặc ngoài ra được truyền tải mà không thất lạc sự nhận diện.

Tất cả các giá trị mã hóa nội dung không phân biệt kiểu chữ (case-insensitive). HTTP/1.1 sử dụng các giá trị mã hóa nội dung trong các trường Accept-Encoding và Content-Encoding Header.

Ví dụ

Dưới đây là các sơ đồ mã hóa hợp lệ:

	Accept-encoding: gzip

hoặc 

	Accept-encoding: compress

hoặc

	Accept-encoding: deflate


####<a name ="http-mediatype"></a>6.Media Types(Các kiểu đa phương tiện)

HTTP sử dụng các Internet Media Types trong các trường Content-Type và Accept để cung cấp dữ liệu mở và có thể mở rộng. Tất cả các giá trị kiểu phương tiện được đăng ký với IANA (Internet Assigned Number Authority). Cú pháp chung để xác định kiểu phương tiện như sau:

	media-type     = type "/" subtype *( ";" parameter )

Các thuộc tính type, subtype, và parameter là case-insensitive.

Ví dụ:

	Accept: image/gif

####<a name ="http-langtag"></a>7.Language Tags(Các thẻ ngôn ngữ)

HTTP sử dụng các thẻ ngôn ngữ trong các trường **Accept-Language** và **Content-Language**. Một thẻ ngôn ngữ bao gồm một hoặc nhiều phần: Một thẻ ngôn ngữ sơ cấp và một dãy các thẻ phụ:

	language-tag  = primary-tag *( "-" subtag )

Các khoảng trắng không được cho phép trong thẻ và tất cả các thẻ là case-insentive.

Ví dụ:

Các thẻ ví dụ bao gồm:

	en, en-US, en-cockney, i-cherokee, x-pig-latin

Hai chữ *primary-tag* là một chữ viết tắt cho ngôn ngữ trong ISO-639 và hai ký tự đầu tiên trong thẻ phụ subtag là mã quốc gia.


----

####<a name="http-message"></a>III.Message trong HTTP


HTTP sử dụng URI để nhận diện một nguồn đã cho và để thiết lập một kết nối. Một khi một kết nối được thiết lập, Các Thông báo HTTP được truyền trong một định dạng tương tự như được sử dụng trong thư điện tử Internet Mail [RFC5322] và MIME (Multipurpose Internet Mail Extensions) [RFC2045]. Các thông báo này bao gồm các Yêu cầu từ Client tới Server và các Phản hồi từ Server tới Client mà sẽ theo định dạng sau:

	HTTP-message   = <Request> | <Response> ; HTTP/1.1 messages

Các yêu cầu HTTP và các phản hồi HTTP sử dụng một định dạng thông báo chung của RFC 822 cho truyền trải dữ liệu được yêu cầu.

####<a name="start-line"></a>1.Dòng đầu thông báo (start-line)

Dòng đầu sẽ có cú pháp chung như sau:

	start-line = Request-Line | Status-Line

Một số ví dụ về dòng bắt đầu trong trường hợp yêu cầu và phản hồi:

	GET /hello.jsp HTTP/1.1     (This is Request-Line sent by the client)

	HTTP/1.1 200 OK             (This is Status-Line sent by the server)


####<a name="header-field"></a>2.Các trường Header

Các trường Header cung cấp thông tin được yêu cầu về yêu cầu hoặc phản hồi, hoặc về đối tượng được gửi trong thông báo(message). Có 4 kiểu của Header trong các thông báo HTTP:

- **Kiểu chung (General-Header):** Các trường Header này có khả năng ứng dụng chung cho cả các thông báo yêu cầu và phản hồi.

- **Kiểu yêu cầu (Request-Header):** Các trường Header này chỉ có khả năng áp dụng cho các thông báo yêu cầu.

- **Kiểu phản hồi (Response-Header):** Các trường Header này chỉ có khả năng áp dụng cho các thông báo phản hồi.

- **Kiểu thực thể (Entity-Header):** Các trường này xác định thông tin về entity-body hoặc, nếu không có phần thân nào hiển thị, về nguồn được nhận diện bởi yêu cầu.

Tất cả các Header được đề cập ở trên theo một định dạng chung và mỗi một trường Header bao gồm một tên được theo sau bởi một dấu hai chấm (:) và giá trị trường như sau:

	message-header = field-name ":" [ field-value ]

Dưới đây là ví dụ về các trường Header đa dạng:

	User-Agent: curl/7.16.3 libcurl/7.16.3 OpenSSL/0.9.7l zlib/1.2.3
	Host: www.example.com
	Accept-Language: en, mi
	Date: Fri, 13 May 2016 12:28:53 GMT
	Server: Apache
	Last-Modified: Mon, 9 May 2016 19:15:56 GMT
	ETag: "34aa387-d-1568eb00"
	Accept-Ranges: bytes
	Content-Length: 51
	Vary: Accept-Encoding
	Content-Type: text/plain

####<a name="message-body"></a>3.Phần thân thông báo(Message-body)

Message body thì tùy ý cho một thông báo HTTP nhưng nếu nó có sẵn, thì khi đó nó được sử dụng để mang entity-body liên kết với yêu cầu hoặc phản hồi. Nếu entity-body được liên kết, thì sau đó thường các dòng Content-Type và Content-Length xác định bản chất của phần thân được liên kết.

Một phần thân thông báo là phần mà mang dữ liệu yêu cầu HTTP thực sự (bao gồm dữ liệu mẫu và được tải lên,…) và dữ liệu phản hồi HTTP từ Server (bao gồm các file, ảnh, …). Dưới đây là nội dung đơn giản của một phần thân thông báo:

	<html>
   	<body>
   
      <h1>Hello, World!</h1>
   
   	</body>
	</html>


----

####<a name="request"></a>IV.Requests trong HTTP

####<a name="request-line"></a>1.Dòng yêu cầu(Request-Line)

Request-Line bắt đầu với phương pháp thủ tục,  theo sau bởi một Request-URI và phiên bản giao thức, và kết thúc với CRLF. Các yếu tố được phân biệt riêng rẽ bởi các ký tự khoảng trống SP.

	Request-Line = Method SP Request-URI SP HTTP-Version CRLF

####<a name="request-method"></a>2.Phương thức yêu cầu(Request-Method)

Phương thức yêu cầu là phương thức được thực hiện trên nguồn được nhận diện bởi Request-URI . Phương thúc này là case-intensive và nên luôn luôn được viết bằng chữ hoa. Dưới đây là danh sách tất cả các method được hỗ trợ trong HTTP/1.1.

	GET
	Phương thức GET được sử dụng để lấy lại thông tin từ Server
	sử dụng URI. Các yêu cầu sử dụng GET chỉ nên nhận dữ liệu 
	và không làm ảnh hưởng gì tới dữ liệu.
	----
	HEAD
	Tương tự như GET, nhưng nó truyền tải dòng trạng thái và khu vực Header.
	----
	POST
	Một yêu cầu POST được sử dụng để gửi dữ liệu tới Server, ví dụ, thông tin khách hàng, file tải lên, …, sử dụng các mẫu HTML.
	----
	PUT
	Thay đổi tất cả các đại diện hiện tại của nguồn mục tiêu với nội dung được tải lên.
	DELETE
	Gỡ bỏ tất cả các đại diện hiện tại của nguồn mục tiêu bởi URI.
	----
	CONNECT
	Thiết lập một tunnel tới Server được xác định bởi URI đã cung cấp.
	----
	OPTIONS
	Miêu tả các chức năng giao tiếp cho nguồn mục tiêu.
	----
	TRACE
	Trình bày một vòng lặp kiểm tra thông báo song song với path tới nguồn mục tiêu.
	
####<a name="request-uri"></a>3.Bộ nhận diện Nguồn Đồng nhất(Request-URI)

Request-URI là một Bộ nhận diện Nguồn Đồng nhất (Uniform Resource Identifier) và xác định nguồn mà áp dụng yêu cầu. Dưới đây là các mẫu thường được sử dụng để xác định một URI:

	Request-URI = "*" | absoluteURI | abs_path | authority

	
####<a name="request-header"></a>4.Các trường Request

Các trường Request-Header cho phép Client truyền thông tin thêm về yêu cầu, và về chính Client đó, tới Server. Những trường này hoạt động như các bộ chỉnh sửa yêu cầu. Dưới đây là một danh sách các trường Request-Header quan trọng mà có thể được sử dụng dựa trên yêu cầu:

	Accept-Charset

	Accept-Encoding

	Accept-Language

	Authorization

	Expect

	From

	Host

	If-Match

	If-Modified-Since

	If-None-Match
		
	If-Range

	If-Unmodified-Since

	Max-Forwards

	Proxy-Authorization

	Range

	Referer

	TE

	User-Agent
	

####<a name="http-responses"></a>IV.Responses trong HTTP

####<a name="status-line"></a>1.Dòng trạng thái

Một dòng trạng thái bao gồm phiên bản giao thức được theo sau bởi một mã hóa trạng thái số và cụm từ thuần văn bản được liên kết của nó.

	Status-Line = HTTP-Version SP Status-Code SP Reason-Phrase CRLF

####<a name="http-version2"></a>2.Phiên bản HTTP

Một Server hỗ trợ phiên bản HTTP/1.1 sẽ trả lại thông tin phiên bản như sau:

	HTTP-Version = HTTP/1.1

####<a name="status-code"></a>3.Mã trạng thái(Status Code)

Yếu tố Status-Code là một số nguyên 3 ký tự, trong đó ký tự đầu tiên của mã trạng thái định nghĩa hạng (loại) phản hồi và hai ký tự cuối không có bất cứ vai trò phân loại nào. Có 5 giá trị của ký tự đầu tiên:

	1xx:	Thông tin
	Yêu cầu đã được nhận và tiến trình đang tiếp tục.
.

	2xx:	Thành công 
	Hoạt động đã được nhận, được hiểu, và được chấp nhận một cách thành công.

.

	3xx:	Điều hướng lại
	Hoạt động phải được thực hiện để hoàn thành yêu cầu.

.

	4xx:	Lỗi Client
	Têu cầu chứa cú pháp không chính xác hoặc không được thực hiện.

.
	
	5xx: Lỗi Server
	Server thất bại với việc thực hiện một yêu cầu.

Chi tiết từng mã trạng thái HTTP [tại đây](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)

