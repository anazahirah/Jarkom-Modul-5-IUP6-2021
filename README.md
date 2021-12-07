# Jarkom-Modul-5-IUP6-2021

### **A. Tugas pertama kalian yaitu membuat topologi jaringan sesuai dengan rancangan yang diberikan Luffy dibawah ini**

**Keterangan :** <BR>
Doriki adalah DNS Server <BR>
		Jipangu adalah DHCP Server  <BR>
		Maingate dan Jorge adalah Web Server  <BR>
		Jumlah Host pada Blueno adalah 100 host  <BR>
		Jumlah Host pada Cipher adalah 700 host  <BR>
		Jumlah Host pada Elena adalah 300 host  <BR>
		Jumlah Host pada Fukurou adalah 200 host  <BR>
	
<img width="618" alt="2021-12-07 (3)" src="https://user-images.githubusercontent.com/91376801/145005688-367ed2f1-a1fd-4986-a770-9e33547142ad.png">
    
 
### **B. Karena kalian telah belajar subnetting dan routing, Luffy ingin meminta kalian untuk membuat topologi tersebut menggunakan teknik CIDR atau VLSM. setelah melakukan subnetting**   

<img src="https://user-images.githubusercontent.com/91376801/145010530-32bd9dd9-1e97-4513-8fe2-d103c9dffc2a.jpg" width="800"> <br>
<img src="https://user-images.githubusercontent.com/91376801/145008155-75316b35-544a-40a1-aabc-e191dea7f859.jpg" width="500">
	
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

### **C.Kalian juga diharuskan melakukan Routing agar setiap perangkat pada jaringan tersebut dapat terhubung.** 

### **D.Tugas berikutnya adalah memberikan ip pada subnet Blueno, Cipher, Fukurou, dan Elena secara dinamis menggunakan bantuan DHCP server. Kemudian kalian ingat bahwa kalian harus setting DHCP Relay pada router yang menghubungkannya.** 

### **1.Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Foosha menggunakan iptables, tetapi Luffy tidak ingin menggunakan MASQUERADE.** 

### **2.Kalian diminta untuk mendrop semua akses HTTP dari luar Topologi kalian pada server yang merupakan DHCP Server dan DNS Server demi menjaga keamanan.** 

### **3.Karena kelompok kalian maksimal terdiri dari 3 orang. Luffy meminta kalian untuk membatasi DHCP dan DNS Server hanya boleh menerima maksimal 3 koneksi ICMP secara bersamaan menggunakan iptables, selebihnya didrop.** 
