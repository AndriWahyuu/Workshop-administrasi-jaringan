<p align = center>
LAPORAN RESMI <br>
WORKSHOP ADMINISTRASI JARINGAN </br>

<p align = center>
Dosen Pengampu <br>
Dr. Ferry Astika Saputra ST, M.Sc<br><br>

<p align = center>
Disusun Oleh<br>
Muhammad Fajrul Falah Subakti3121600035<br>
Andriana Wahyu Hapsari3121600040<br>
Alan Tri Arbani Hidayat 3121600056<br>
2 D4 IT B<br><br>


### **Setting IP di Interface**
#
### **Seting Default gateway 0.0.0.0/0**
#
### **Setting IP Route dengan gateway 10.252.108.212**
#
### **Setting DHCP Server via DHCP Setup menjadi 192.168.X.100 - 192.168.X.254** <hr>
1. Pilih menu IP -> DHCP Server -> Klik DHCP Setup
2. Pada jendela DHCP Server Interface pilih ether2
3. Selanjutnya, ketika diminta menentukan IP Address yang akan digunakan sebagai default-gateway oleh DHCP Client masukkan IP 192.168.2.100 - 192.168.2.254** <br> <br>
<img src=https://github.com/AndriWahyuu/Workshop-administrasi-jaringan/blob/62929b8f3045fb2bf4ce99615caed6b33c8df07b/Minggu%205/images/No%203.png width="" height="500" /> <br> <br>

### **Sambungkan PC atau laptop ke jaringan, cek IP address pastikan IP add dari PC mendapatkan IP add dari dhcp server**
<hr>

- Mengecek apakah komputer sudah mendaptkan dengan menggunakan perintah 
```
ip a
```

Komputer sudah mendapatkan IP dari DHCP Server <br> <br>
<img src=https://github.com/AndriWahyuu/Workshop-administrasi-jaringan/blob/62929b8f3045fb2bf4ce99615caed6b33c8df07b/Minggu%205/images/No%204.png width="" height="500" /> <br>


### Power up nyalakan VM, pastikan konfigurasi jaringan BRIDGE dan pastikan mendapatkan IP add dari dhcp server 
#
<br><img src=https://github.com/AndriWahyuu/Workshop-administrasi-jaringan/blob/62929b8f3045fb2bf4ce99615caed6b33c8df07b/Minggu%205/images/No%205.png width="" height="500" /> <br><br>
Jika ternyata belum mendapatkan IP maka jalankan perintah : <br>
```
sudo dhclient -v
```
<br><img src=https://github.com/AndriWahyuu/Workshop-administrasi-jaringan/blob/62929b8f3045fb2bf4ce99615caed6b33c8df07b/Minggu%205/images/No%205.1.png width="" height="500" /> <br><br>

### **Konfigurasi IP VM Menjadi Static IP : 192.168.X.10** <br>
#
Konfigurasi IP VM dapat melalui GUI maupun CLI, berikut cara setting IP address static di Ubuntu Dekstop : <br>

**1. Buka menu pengaturan, pilih tab jaringan. Kemudian klik ikon pengaturan jaringan.** <br>
**2. Selanjutnya pilih tab IPv4. Setelah di bawah Metode IPv4 pilih opsi Manual.** <br>
**3. Mengisikan IP Adress, Netmask, dan Gateway sesuai dengan yang ditentukan. Setelah itu apply**
<br><br>
<img src=https://github.com/AndriWahyuu/Workshop-administrasi-jaringan/blob/62929b8f3045fb2bf4ce99615caed6b33c8df07b/Minggu%205/images/No%206.png width="" height="500" /><br><br>

### **Konfigurasi NTP ke 0. id.pool.ntp.org 1. id.pool.ntp.org**
<hr>

**Set Up NTP CLient**
**1. Mengubah Pengaturan jam Sistem**
- Untuk melihat daftar zona waktu menjalankan perintah : <br>
```
sudo timedatectl set-timezone Asia/Jakarta
```

- Mengatur RTC ke UTC, menjalankan perintah <br>
```
sudo timedatectl set-local-rtc false
```
 
<br> 

**2. install NTP server** 
<br>
Sebelum melakukan install maka perlu mengubah kembali IP jaringan yang sebelumnya static menjadi DHCP kembali. <br>
- Pertama update terlebih dahulu server dengan menggunakan perintah <br>
```
sudo apt update && sudo apt -y upgrade
```

- menginstall NTP Srver menggunakan perintah : <br>
```
sudo apt -y install ntp
```
<br>

**3. Konfigurasi NTP Server**
- mengedit `ntp.conf` dengan menggunkan perintah : <br>
```
sudo nano /etc/ntp.conf
``` 
- memberikan command pada <br>
```
pool 0.ubuntu.pool.ntp.org iburst 
pool 1.ubuntu.pool.ntp.org iburst 
pool 2.ubuntu.pool.ntp.org iburst
pool 3.ubuntu.pool.ntp.org iburst 
pool 4.ubuntu.pool.ntp.org iburst 
pool 5.ubuntu.pool.ntp.org iburst` 
```

<br>

- Menambahkan baris  <br>
```
server 0.id.pool.ntp.org
server 1.id.pool.ntp.org
server 2.id.pool.ntp.org
server 4.id.pool.ntp.org
``` 
jika sudah, simpan konfigurasi dan keluar dar teks editor. <br><br>

- Restrat NTP service menggunakan perintah : <br>
```
sudo systemctl restart ntp
``` 


- Mengkonfirmasi apakah NTP service telah aktif menggunkan perintah : <br>
```
systemctl status ntp
``` 
- Cek keberhasilan konfigurasi dengan menggunakan command :
```
ntpq -p
``` 

- Mengecek kembali settingan waktu dan tanggal menggunakan perintah : <br>

``` 
timedatectl
```
<br>

### Hasilnya <br> <br>
<img src=https://github.com/AndriWahyuu/Workshop-administrasi-jaringan/blob/7d2694c7939f4f7544cb516cd80c9b39f06d1489/Minggu%205/images/No%207.1.png width="" height="500" /> <br><br>

### 8. Konfigurasi sudo
### 9. Ganti hostname VM **server10.kelompokX.takehome.com
