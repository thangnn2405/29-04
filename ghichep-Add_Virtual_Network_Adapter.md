# Thêm card mạng trong VMware
----

##Mục lục
----

###[I.Các bước thêm card mạng trong VMware](#add-card)

###[II.Những lưu ý khi thêm card mạng](#luu-y)

----

###<a name ="add-card"></a>I.Các bước thêm card mạng trong VMware

Trước khi thêm card mạng ta cần tạo ra các **Switch ảo**

Trong màn hình chính của VMware ta chọn ***Edit* -> *Virtual Network Editor*** 

Ta cần quyền admin để có thể thay đổi cấu hình mạng , chọn **change settings**

Trong tab **Virtual Network Editor** ta có thể xem các thông số về card mạng, switch ảo

Ta tạo ra các **Switch ảo** bằng cách chọn ***Add Network***, sau đó chọn **Switch ảo** cần thêm(ở đây tôi chọn VMnet2), Nhấn **OK** để tạo

![](http://i.imgur.com/SzEvdgU.png)

Xem thêm bài [Các loại card mạng](https://github.com/thangnn2405/29-04/blob/master/ghichep-VMware-Workstation.md#card-mang-ao) để hiểu thêm về các loại card mạng trong vmware


**Bước 1:** Chọn máy ảo cần thêm card mạng, vào phần setting của máy

![](http://i.imgur.com/vozxKIj.png)

**Bước 2:** Trong phần setting ta chọn **Add..**.

![](http://i.imgur.com/zlD4NQB.png)

**Bước 3:** Trong tab **Add Hardware Wizard** ta chọn **Network Adapter**, sau đó chọn **Next**

![](http://i.imgur.com/J61EI8x.png)

**Bước 4:** Chọn loại card mạng bạn muốn thêm và nhấn **Finish** để hoàn thành

![](http://i.imgur.com/Wh50CH6.png)

![](http://i.imgur.com/aAwx7fV.png)


###<a name ="luu-y"></a>II.Những lưu ý khi thêm card mạng

Khi thêm card mạng trong VMware ta cần chú ý đến những điều sau:

**1.** Nên Shutdown máy ảo trước khi thêm card mạng


**2.** Khi thêm nhiều card mạng cùng lúc ta thường gặp trường hợp như trong hình

![](http://i.imgur.com/wPVgPYI.png)

Vậy nên khi **Add Network** nếu muốn add thêm nhiều card mạng cùng lúc thì nên add từng card sau đó chọn **OK** thoát hẳn ra ngoài rồi tiếp tục add card thứ 2, làm tương tự với các card muốn thêm tiếp theo. Nếu các card vmnet này được add cùng một lúc khi khởi tạo máy ảo thì sau này khi đặt IP cho các interface của máy ảo có thể xảy ra hiện tượng **đảo IP hai interface** rất khó chịu và khó khăn trong việc sửa lỗi


**3.**Trong trường hợp bạn cần làm lab Load balancing, bạn cần 2 kết nối internet thì trên máy ảo bạn có thể add 2 card mạng, một card chọn cơ chế NAT và một card chọn cơ chế Bridge.
