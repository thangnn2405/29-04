# Các ghi chép về Ubuntu 16.04

Ubuntu 16.04 là một hỗ trợ dài hạn (LTS) Phiên bản và là lần thứ 6 của các LTS loạt.
Ubuntu 16.04 mang đến một số tính năng mới, đáng chú ý nhất là một trong những là GNOME phần mềm thay thế Trung tâm phần mềm Ubuntu(Ubuntu Software Center).
Phiên bản Ubuntu 16.04 LTS (Xenial Xerus) chính thức được ra mắt vào ngày 21/04/2016.
Ubuntu 16.04 LTS (Xenial Xerus) sẽ là phiên bản LTS thứ 6 kể từ phiên bản LTS đầu tiên được phát hành vào năm 2006.
Như thường lệ, phiên bản LTS sẽ được Canonical hỗ trợ cập nhật, vá lỗi bảo mật trong vòng 5 năm thay vì 9 tháng như phiên bản none-LTS.
Trong chu kì phát triển sẽ có các bản phát hành Alpha 1, Alpha 2, Beta 1 và Final Beta dành cho người dùng và các nhà phát triển nhằm trải nghiệm cũng như kiểm lỗi trên hệ điều hành Ubuntu mới này. Các flavors cũng (Kubuntu, Lubuntu, Xubuntu, Ubuntu Mate, …) cũng đi theo đúng lịch trình phát hành Ubuntu 16.04 LTS.

## Tải về Ubuntu 16.04
Tải trên trang chủ của Ubuntu http://releases.ubuntu.com/16.04.

## Có gì mới trong bản Ubuntu 16.04

Những thay đổi trong Ubuntu 16.04 LTS: Ubuntu Software Center sẽ được thay thế bằng GNOME Software, phát triển tính năng Click Lock, Startup Disk Creator được làm mới, chương trình ghi đĩa và ứng dụng nhắn tin Empathy sẽ không còn được cài đặt mặc định, ứng dụng lịch GNOME Calendar sẽ được cài mặc định, ....

###Ubuntu 16.04 LTS với giao diện Unity 7 sẽ hỗ trợ gói Snappy

Gói phần mềm Snappy được hỗ trợ trong phiên bản Ubuntu mới, Ubuntu 16.04 LTS (với giao diện Unity 7). Thông báo này được công bố từ Will Cooke (leader trong Ubuntu Desktop) trong cuộc nói chuyện “Ubuntu Online Submmit”.

Will Cooke muốn đội ngũ snappy và đội ngũ phát triển Ubuntu desktop cùng làm việc với nhau để làm tốt Software Center nhằm đưa gói snaps lên Ubuntu Desktop. Will Cooke muốn có nhiều ứng dụng chuyển sang gói snapps như LibreOffice, Firefox, Chrome, …. Điều này phụ thuộc rất nhiều vào các hãng thứ ba.

Trong thời điểm ra mắt các phiên bản Ubuntu như Ubuntu 15.04, Ubuntu 15.10, các bạn không thấy có quá nhiều điểm nổi bật so với phiên bản trước, lý do cho việc này là Canonical đang tập trung thời gian và đặt cược cho điện toán đám mây và Internet of Things (IoT). IoT được đề cập đến là hệ điều hành Ubuntu Snappy Core, hệ điều hành sử dụng gói phần mềm Snappy (hay còn gọi là Snappy Personal hay snaps), gói phần mềm này có lợi thế hơn gói deb là giúp hệ thống và phần mềm không gặp lỗi hay xung đột nào. Các bạn có thể tìm hiểu thêm về hệ điều hành Ubuntu Snappy Core ở đường link bên dưới.

`http://ubunsys.com/?p=959`

Mặc dù Canonical bỏ rất nhiều thời gian vào gói phần mềm snappy, gói snaps sẽ được sử dụng chung với gói deb trên hệ thống chứ Canonical không loại bỏ hoàn toàn gói deb.

###Ubuntu Software Center sẽ bị thay thế bằng GNOME Software
Trong bản Ubuntu 16.04, Các nhà phát triển Ubuntu đã loại bỏ Ubuntu Software Center và thay thế bằng GNOME Software. 
Ubuntu Software Center vốn bị bỏ không khá lâu và không còn được duy trì cũng như nâng cấp,
phiên bản mới nhất của Ubuntu Software Center là 13.10, phiên bản ra mắt cùng với Ubuntu 13.10, tức là đã hơn 2 năm,
2 năm không có bất kì thay đổi nào (ngoại trừ vá lỗi bảo mật) dành cho Ubuntu Software Center.
Việc sử dụng GNOME Software giúp nó được nâng cấp thường xuyên theo GNOME,
qua đó dành thời gian để các nhà phát triển làm nhiều việc khác, công việc hiện tại đang khá bận rộn đó là Ubuntu Touch,
Ubuntu Snappy Core, Cloud, ….

Như mình đã nói ở trên gói snappy sẽ hỗ trợ trong phiên bản mới, vì vậy một Store ổn định và cập nhật thường xuyên là hết sức cần thiết, và đây là một trong nhưng lý do quan trọng để thay thế Ubuntu Software Center bằng GNOME Software. Toàn bộ những thông tin bên Ubuntu Sofware Center sẽ được mang sang GNOME Software, chẳng hạn như ratings (xếp hạng sao), reviews (đánh giá), …

Phiên bản Ubuntu Software Center khá nặng nề và có gì đó làm mình ko thích, mình cũng không rõ, mình thường sử dụng Terminal để cài đặt phần mềm. Trước đó đội ngũ Ubuntu Mate cũng đã quyết định loại bỏ nó kể từ phiên bản Ubuntu 15.10. Việc thay thế chứ không phải loại bỏ hoàn toàn là việc làm đúng đắn, Một Store là tương đối quan trọng với người dùng mới, giúp họ tiếp cận với phần mềm một cách dễ dàng và trực quan hơn.

###Tính năng Click Lock (trên Windows) sẽ có mặt trong Ubuntu 

![](http://i.imgur.com/wmA2TWe.png)

Trên Windows có một tính năng tên là Click Lock, nó cho phép người dùng di chuyển files/thư mục mà không cần bấm giữ chuột. Đây là tính năng khá hữu ích nhưng nó hoàn toàn chưa có trên hệ thống Linux, vì vậy các nhà phát triển Ubuntu đang làm việc để đưa tính năng Click Lock lên phiên bản mới, Ubuntu 16.04 LTS

Nói thêm một chút về tính năng Click Lock, bình thường nếu bạn muốn di chuyển files/thư mục đến nơi khác, bạn phải bấm giữ chuột và đưa nó tới đích, nhưng với tính năng Click Lock, bạn chỉ cần bấm giữ khoảng 2-3 giây (có thể tùy chỉnh lại) lên files/thư mục, sau đó di chuyển tới bất kì đâu bạn muốn (bằng chuột) mà không cần bấm giữ chuột. Nếu bạn sử dụng chuột rời thì không cần thiết lắm nhưng nếu bạn đang sử dụng touchpad thì đây là một tính năng khá hữu ích.

Như đã nói ở trên, vì tính năng Click Lock chưa hề có mặt trên hệ thống Linux nên các nhà phát triển sẽ phải bắt đầu từ đầu, và gần như họ sẽ phải liên hệ với các nhà phát triển khác để hoàn thiện tính năng này.

###Startup Disk Creator được làm mới 

![](http://i.imgur.com/Kff9Ryo.png)

Những ứng dụng trên hệ thống Ubuntu đã không có quá nhiều thay đổi từ vài năm trở lại đây, trong đó phải nhắc đến Startup Disk Creator.

Phiên bản Startup Disk Creator đã được các nhà phát triển làm mới trên nền tảng golang và QML. Phiên bản Startup DIsk Creator cũ chỉ gồm những dòng chữ, trong khi đó phiên bản mới (như trong hình) sẽ có những biểu tượng sinh động, bắt mắt hơn, cùng với đó là thiết kế hoàn toàn mới so với cũ.

Ở phiên bản Startup Disk Creator cũ chỉ cho phép tạo một bộ cài đặt hệ điều hành Ubuntu trên USB, chứ không thể tạo trên 2 hay nhiều bộ cài đặt hệ điều hành Ubuntu trong USB. Phiên bản Startup Disk Creator mới này sẽ có tính năng tạo nhiều bộ cài đặt hệ điều hành Ubuntu trên USB. Mình thật sự rất thích tính năng này.



