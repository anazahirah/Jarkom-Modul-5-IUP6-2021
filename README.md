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
	![messageImage_1638870077013](https://user-images.githubusercontent.com/91376801/145005768-fce3141d-d6ba-443c-9c17-719f19d1996c.jpg)

### **C.Kalian juga diharuskan melakukan Routing agar setiap perangkat pada jaringan tersebut dapat terhubung.** 

### **D.Tugas berikutnya adalah memberikan ip pada subnet Blueno, Cipher, Fukurou, dan Elena secara dinamis menggunakan bantuan DHCP server. Kemudian kalian ingat bahwa kalian harus setting DHCP Relay pada router yang menghubungkannya.** 

### **1.Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Foosha menggunakan iptables, tetapi Luffy tidak ingin menggunakan MASQUERADE.** 

### **2.Kalian diminta untuk mendrop semua akses HTTP dari luar Topologi kalian pada server yang merupakan DHCP Server dan DNS Server demi menjaga keamanan.** 

### **3.Karena kelompok kalian maksimal terdiri dari 3 orang. Luffy meminta kalian untuk membatasi DHCP dan DNS Server hanya boleh menerima maksimal 3 koneksi ICMP secara bersamaan menggunakan iptables, selebihnya didrop.** 
