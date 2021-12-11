# Jarkom-Modul-5-IUP6-2021
Mukhoram Dimasputra Bagawan - 05111942000006

Fitriana Zahirah Tsabit - 05111942000011

Muhammad Rafi Hayla Arifa - 05111942000014

## A. Tugas pertama kalian yaitu membuat topologi jaringan sesuai dengan rancangan yang diberikan Luffy dibawah ini.

**Keterangan :** <BR>
Doriki adalah DNS Server <BR>
		Jipangu adalah DHCP Server  <BR>
		Maingate dan Jorge adalah Web Server  <BR>
		Jumlah Host pada Blueno adalah 100 host  <BR>
		Jumlah Host pada Cipher adalah 700 host  <BR>
		Jumlah Host pada Elena adalah 300 host  <BR>
		Jumlah Host pada Fukurou adalah 200 host  <BR>
	
<img width="619" alt="Screen Shot 2021-12-07 at 21 30 40" src="https://user-images.githubusercontent.com/74056954/145047723-47b16819-1a78-41d1-a3e0-ad74ab8f40d9.png">

## B. Karena kalian telah belajar subnetting dan routing, Luffy ingin meminta kalian untuk membuat topologi tersebut menggunakan teknik CIDR atau VLSM. setelah melakukan subnetting.

<img width="627" alt="Screen Shot 2021-12-07 at 21 14 36" src="https://user-images.githubusercontent.com/74056954/145047632-537d9a2a-6186-486f-8df8-e39f69c343e2.png">
<img src="https://user-images.githubusercontent.com/91376801/145010530-32bd9dd9-1e97-4513-8fe2-d103c9dffc2a.jpg" width="800"> <br>
<img src="https://user-images.githubusercontent.com/91376801/145019318-9db633ab-bc1d-4061-80db-b53c9a29df24.png" width="600">
	
| Subnet | Node | IP  | Length |
| ------------- | ------------- | ------------- | ------------- |	
| A1  | DORIKI - WATER7 - JIPANGU  | 3  | /29 |
| A2  | BLUENO - WATER7             | 101  | /25  |
| A3  | WATER7 - CIPHER             | 701  | /22  |
| A4  | WATER7 - FOOSHA              | 2 | /30  |
| A5  | FOOSHA - GUANHAO            | 2  | /30  |
| A6  | ELENA - GUANHAO  	| 301 | /23  |
| A7  | GUANHAO - FUKUROU  | 201  | /24  |
| A8  | JORGE - GUANHAO - MAINGATE              | 3  | /29  |
|  | Total               | 1314  | /21  |

	
## Node Configuration
**Foosha**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 192.211.7.145
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 192.211.7.149
	netmask 255.255.255.252
```
	
**Water7**
```
auto eth0
iface eth0 inet static
 	address 192.211.7.146
 	netmask 255.255.255.252
   	gateway 192.211.7.145
  
auto eth1
iface eth1 inet static
 	address 192.211.7.129
 	netmask 255.255.255.248
  
auto eth2
iface eth2 inet static
  	address 192.211.7.1
  	netmask 255.255.255.128

auto eth3
iface eth3 inet static
  	address 192.211.0.1
  	netmask 255.255.252.0
```
	
**Guanhao**
```
auto eth0
iface eth0 inet static
    	address 192.211.7.150
    	netmask 255.255.255.252
    	gateway 192.211.7.149

auto eth1
iface eth1 inet static
    	address 192.211.4.1
    	netmask 255.255.254.0

auto eth2
iface eth2 inet static
    	address 192.211.6.1
    	netmask 255.255.255.0

auto eth3
iface eth3 inet static
    	address 192.211.7.137
    	netmask 255.255.255.248
```
	
**Jipangu**
```
auto eth0
iface eth0 inet static
	address 192.211.7.131
	netmask 255.255.255.248
	gateway 192.211.7.129
```
	
**Doriki**
```
auto eth0
iface eth0 inet static
	address 192.211.7.130
	netmask 255.255.255.248
	gateway 192.211.7.129
```
	
**Blueno**
```
auto eth0
iface eth0 inet dhcp
	# address 192.211.7.2
	# netmask 255.255.255.128
	# gateway 192.211.7.1
```

**Cipher**
```
auto eth0
iface eth0 inet dhcp
	#address 192.211.0.2
	#netmask 255.255.252.0
	#gateway 192.211.0.1
```
	
**Elena**
```
auto eth0
iface eth0 inet dhcp
	#address 192.211.4.2
	#netmask 255.255.254.0
	#gateway 192.211.4.1
```
	
**Fukurou**
```
auto eth0
iface eth0 inet dhcp
	address 192.211.6.2
	netmask 255.255.255.0
	gateway 192.211.6.1
```	
	
**Jorge**
```
auto eth0
iface eth0 inet static
	address 192.211.7.138
	netmask 255.255.255.248
	gateway 192.211.7.137
```	
	
**Maingate**
```
auto eth0
iface eth0 inet static
	address 192.211.7.139
	netmask 255.255.255.248
	gateway 192.211.7.137
```	
	
## C.Kalian juga diharuskan melakukan Routing agar setiap perangkat pada jaringan tersebut dapat terhubung.
**Foosha**
```
route add -net 192.211.7.128 netmask 255.255.255.248 gw 192.211.7.145
route add -net 192.211.7.0 netmask 255.255.255.128 gw 192.211.7.145
route add -net 192.211.0.0 netmask 255.255.252.0 gw 192.211.7.145


route add -net 192.211.4.0 netmask 255.255.254.0 gw 192.211.7.150
route add -net 192.211.6.0 netmask 255.255.255.0 gw 192.211.7.150
route add -net 192.211.7.136  netmask 255.255.255.248 gw 192.211.7.150
```

**Water7 & Guanhao**
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.211.7.146
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.211.7.149
```
	
## D.Tugas berikutnya adalah memberikan ip pada subnet Blueno, Cipher, Fukurou, dan Elena secara dinamis menggunakan bantuan DHCP server. Kemudian kalian ingat bahwa kalian harus setting DHCP Relay pada router yang menghubungkannya.

**Doriki - DNS Server**
```
apt update
apt install bind9 -y
apt install dnsutils -y
	
cp /root/named.conf.options /etc/bind/named.conf.options
	
servuce bind9 restart
```
![messageImage_1639195465125](https://user-images.githubusercontent.com/74056954/145663179-80fc74cc-81e9-4481-bce8-8f437abf5f6d.jpg)

**Jipangu - DHCP Server**
```
apt update
apt install nano
apt install isc-dhcp-server -y

cp /root/isc-dhcp-server /etc/default/isc-dhcp-server
cp /root/dhcpd.conf /etc/dhcp.dhcpd.conf
	
service isc-dhcp-server restart
```
![messageImage_1639196095002](https://user-images.githubusercontent.com/74056954/145663436-5cab35d1-3666-491c-a27f-d9334bd9b2e6.jpg)

```
subnet 192.211.7.0 netmask 255.255.255.128 {
    range 192.211.7.2 192.211.7.126;
    option routers 192.211.7.1;
    option broadcast-address 192.211.7.127;
    option domain-name-servers 192.211.7.130;
    default-lease-time 600;
    max-lease-time 7200;
}
subnet 192.211.0.0 netmask 255.255.252.0 {
    range 192.211.0.2 192.211.3.254;
    option routers 192.211.0.1;
    option broadcast-address 192.211.3.255;
    option domain-name-servers 192.211.7.130;
    default-lease-time 600;
    max-lease-time 7200;
}
subnet 192.211.4.0 netmask 255.255.254.0 {
    range 192.211.4.2 192.211.5.254;
    option routers 192.211.4.1;
    option broadcast-address 192.211.5.255;
    option domain-name-servers 192.211.7.130;
    default-lease-time 600;
    max-lease-time 7200;
}
subnet 192.211.6.0 netmask 255.255.255.0 {
    range 192.211.6.2 192.211.6.254;
    option routers 192.211.6.1;
    option broadcast-address 192.211.6.255;
    option domain-name-servers 192.211.7.130;
    default-lease-time 600;
    max-lease-time 7200;
}

subnet 192.211.7.128 netmask 255.255.255.248 {
    option routers 192.211.7.129;
}
```
![messageImage_1639195353736](https://user-images.githubusercontent.com/74056954/145663446-72563e69-e411-49a8-8047-d25e3e03b6b3.jpg)


## 1.Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Foosha menggunakan iptables, tetapi Luffy tidak ingin menggunakan MASQUERADE.

## 2.Kalian diminta untuk mendrop semua akses HTTP dari luar Topologi kalian pada server yang merupakan DHCP Server dan DNS Server demi menjaga keamanan.

## 3.Karena kelompok kalian maksimal terdiri dari 3 orang. Luffy meminta kalian untuk membatasi DHCP dan DNS Server hanya boleh menerima maksimal 3 koneksi ICMP secara bersamaan menggunakan iptables, selebihnya didrop.
