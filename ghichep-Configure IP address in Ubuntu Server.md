
# Cấu hình card mạng cho Ubuntu #
>
Bài viết này sẽ tập trung vào việc quản lý card mạng trên dòng lệnh.
Tác giả bài viết nhận định rằng người đọc đã làm quen với việc mở file, sửa file, và save file trên dòng lệnh.

## Mục lục ##

----
###[1.Giao diện mạng ( Network Interfaces )](#net-int)

###[2.Thiết lập địa chỉ IP tạm thời](#ip-temp)

###[3. Thiết lập địa chỉ IP tĩnh (Static IP address)](#sta-ip)

###[4.Cấu hình card mạng nhận IP động từ DHCP server](#dhcp-ip)



----

###<a name = "net-int"> </a>1.Giao diện mạng ( Network Interfaces )

Mỗi máy tính cần có một card mạng Ethernet có dây hoặc không dây

* Nhận dạng bởi tên: ethX

 * eth0 cho card mạng thứ nhất

 * eth1 cho card mạng thứ 2, ....

* Xem có bao nhiêu giao diện Ethernet

		ifconfig a | grep eth

* Xem các card mạng đã được cấu hình hay chưa

		ifconfig  

* Xem thông tin từng card mạng

		ifconfig ethX

* Xem tất cả thông số card mạng

		sudo lshw -class network

		  *-network
       	description: Ethernet interface
       	product: 82545EM Gigabit Ethernet Controller (Copper)
       	vendor: Intel Corporation
       	physical id: 1
       	bus info: pci@0000:02:01.0
       	logical name: eth0
       	version: 01
       	serial: 00:0c:29:bc:56:71
       	size: 1Gbit/s
       	capacity: 1Gbit/s
       	width: 64 bits
       	clock: 66MHz
       	capabilities: pm pcix bus_master cap_list rom ethernet physical logical tp 10bt 10bt	-fd 100bt 100bt-fd 1000bt-fd autonegotiation
       	configuration: autonegotiation=on broadcast=yes driver=e1000 driverversion=7.3.21-k8-NAPI duplex=full ip=10.0.0.15 latency=0 link=yes mingnt=255 multicast=yes port=twisted pair speed=1Gbit/s
       	resources: irq:19 memory:fd5c0000-fd5dffff memory:fdff0000-fdffffff ioport:2000(size=64) memory:fd500000-fd50ffff


* Xem các định tuyến đi qua các mạng

		route -n

* Các thiết lập về mạng và hostname trong Ubuntu được lưu trữ trong một số file
 

 - /etc/network/interfaces lưu trữ các giao diện mạng
 - /etc/hostname cấu hình thôn tin tên máy chủ
 - /etc/hosts phân giải địa chỉ IP sang tên máy chủ
 


###<a name = "ip-temp"> </a>1.Thiết lập địa chỉ IP tạm thời

Để thiết lập địa chỉ IP tạm thời, ta cần sử dụng câu lệnh như *ip*, *ifconfig* và *route*. Những lệnh này cho phép bạn cấu hình cài đặt có hiệu lực ngay lập tức, tuy nhiên thì nó không bền vững và sẽ mất đi nếu reboot.

Ta sử dụng lệnh *ifconfig* như bên dưới, chỉ cần thay địa chỉ IP và subnet mask phù hợp với yêu cầu về mạng.

    sudo ifconfig eth0 10.0.0.15 netmask 255.255.255.0

Để kiểm tra các thiết lập cho *eth0*, ta sử dụng lệnh *ifconfig* như sau

	ifconfig eth0
	eth0      Link encap:Ethernet  HWaddr 00:15:c5:4a:16:5a  
          inet addr:10.0.0.15  Bcast:10.0.0.255  Mask:255.255.255.0
          inet6 addr: fe80::20c:29ff:febc:5671/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:10 errors:0 dropped:0 overruns:0 frame:0
          TX packets:11 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:2574778386 (1.0 KB)  TX bytes:1618367329 (904.0 B)
         

Để thiết lập gateway, ta dùng lệnh *route* như sau. Thay địa chỉ gateway theo yêu cầu của mạng.

	sudo route add default gw 10.0.0.1 eth0

Để kiểm tra các thiết lập về default gateway, ta dùng lệnh *route* như sau
	
	route -n
	Kernel IP routing table
	Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
	10.0.0.0        0.0.0.0         255.255.255.0   U     1      0        0 eth0
	0.0.0.0         10.0.0.1        0.0.0.0         UG    0      0        0 eth0	


 Nếu cần DNS cho câu hình mạng tạm thời, ta thêm địa chỉ DNS server trong file cấu hình /etc/resolv.conf . Ví dụ dưới đây là cách thêm 2 DNS server vào file cấu hình /etc/resolv.conf .
	
	nameserver 8.8.8.8
	nameserver 8.8.4.4

Nếu không cần dùng những thiết lập này nữa mà muốn xóa nó đi, ta sử dụng lệnh *ip* như sau

	ip addr flush eth0    

	
> Xóa các thiết lập địa chỉ IP sử dụng câu lệnh *ip* không thể xóa được nội dung trong file cấu hình /etc/resolv.conf. Bạn phải xóa hoặc chỉnh sửa lại bằng tay, reboot cũng có thể làm được điều tương tự


###<a name = "sta-ip"> </a>2. Thiết lập địa chỉ IP tĩnh (Static IP address)

**Bước 1:** DÙng trình soạn thảo nào đó (vi) để mở file cấu hình mạng ( interfaces ):
	
	vi /etc/network/interfaces

**Bước 2:** Tìm đến đoạn lệnh

	auto lo

	iface lo inet loopback

	auto eth0

	iface eth0 inet dhcp

>Đoạn lệnh này cho biết, card eth0 đang nhận địa chỉ IP động từ DHCP Server.

**Bước 3:** Bây giờ nếu muốn gán địa chỉ IP tĩnh - **10.0.0.15/24** - cho card eth0 của máy ta thay đoạn lệnh trên bằng đoạn lệnh sau

	auto lo

	iface lo inet loopback

	auto eth0

	iface eth0 inet static

	address 10.0.0.15

	netmask 255.255.255.0

	gateway 10.0.0.1

	network 10.0.0.0

	broadcast 10.0.0.255

	dns-nameservers 8.8.8.8


>Thay các địa chỉ để phù hợp với cấu hình cần thiết

**Bước 4:** Lưu lại file cấu hình vừa sửa

**Bước 5:** Khởi động lại card mạng bằng lệnh networking restart như sau:

	/etc/init.d/networking restart

	Hoặc

	sudo service networking restart

	Hoặc 

	sudo ifdown eth0 && sudo ifup eth0

**Bước 6:** Kiểm tra mạng bằng lệnh ping 


###<a name = "dhcp-ip"> </a>3.Cấu hình card mạng nhận IP động từ DHCP server

Nếu muốn cấu hình card mạng nhận IP từ DHCP server chúng ta khai báo các dòng lệnh sau trong file /etc/network/interfaces thay cho 5 dòng lệnh cấu hình card mạng ở bước trên
	
	auto ethX
	iface ethX inet dhcp
	
Khời động lại dịch vụ mạng như bước 5 ở trên
