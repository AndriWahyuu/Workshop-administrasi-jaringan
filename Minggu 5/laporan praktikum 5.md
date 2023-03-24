<p align = center>
LAPORAN RESMI <br>
WORKSHOP ADMINISTRASI JARINGAN </br>

<p align = center>
Dosen Pengampu <br>
Dr. Ferry Astika Saputra ST, M.Sc<br><br>

<p align = center>
Disusun Oleh<br>
Muhammad Fajrul Falah 3121600035<br>
Andriana Wahyu Hapsari 3121600040<br>
Alan Tri Arbani Hidayat 3121600056<br>
2 D4 IT B<br><br>


### Setting IP di Interface
### Seting Default gateway 0.0.0.0/0
### Setting IP Route dengan gateway 10.252.108.212
### Setting DHCP Server via DHCP Setup menjadi 192.168.X.100 - 192.168.X.254
### Sambungkan PC atau laptop ke jaringan, cek IP address pastikan IP add dari PC mendapatkan IP add dari dhcp server
### Power up nyalakan VM, pastikan konfigurasi jaringan FRIDGE dan pastikan mendapatkan IP add dari dhcp server
### Konfigurasi IP VM menjadi static**
   **IP : 192.168.X.10**<br>

### Konfigurasi NTP ke
   0 : id.pool.ntp.org** <br>
   1 : id.pool.ntp.org** <br>

#### **Set Up NTP CLient**
1. **Mengubah Pengaturan jam Sistem**
- Untuk melihat daftar zona waktu menjalankan perintah : <br>
```
sudo timedatectl set-timezone Asia/Jakarta
```

- Mengatur RTC ke UTC, menjalankan perintah <br>
```sudo timedatectl set-local-rtc false``` <br> <br>

2. **Konfigurasi NTP Client**
- Untuk mensinkronisasi waktu perlu mengaktifkan NTP Client dengan menjalankan perintah : <br>
```
sudo timedatectl set-ntp true
``` 
<br>

- Menentukan server NTPyangakandgunakan dengan mengedit file `timesyncd.conf`.<br>
```
sudo nano /etc/systemd/timesyncd.conf
``` 
<br>

kemudian tambahkan baris berikut dan save : <br>
``` 
#NTP= NTP=0.id.pool.ntp.org, 1.id.poo.ntp.org
``` 
<br>

### Build a local NTP Server
1. **install NTP server**
sebelum melakukan install maka perlumengubah kembali IP jaringan yang sebelumnya static menjadi DHCP kembali,
- Pertama update terlebih dahulu server dengan menggunakan perintah <br>
```sudo apt update && sudo apt -y upgrade```

- menginstall NTP Srver menggunakan perintah : <br>
```sudo apt -y install ntp``
<br><br>

2. **Konfigurasi NTP Server**
- mengedit `ntp.conf` dengan menggunkan perintah : <br>
```sudo nano /etc/ntp.conf``` <br>
- memberikan command pada 
`pool 0.ubuntu.pool.ntp.org iburst` , `pool 1.ubuntu.pool.ntp.org iburst` `pool 2.ubuntu.pool.ntp.org iburst` `pool 3.ubuntu.pool.ntp.org iburst` `pool 4.ubuntu.pool.ntp.org iburst`, `pool 5.ubuntu.pool.ntp.org iburst`  <br>
- Menambahkan baris <br>
```
server 0.id.pool.ntp.org
server 1.id.pool.ntp.org
server 2.id.pool.ntp.org
server 4.id.pool.ntp.org
``` 
<br>jika sudah, simpan konfigurasi dan keluar dar teks editor. <br>

- Merestrat NTP service menggunakan perintah : <br>
```
sudo nano /etc/ntp.conf
``` 
<br>

- Mengkonfirmasi apakah NTPservice telah aktif menggunkan perintah : <br>
`systemctl status ntp` <br>
- Cek keberhasilan konfigurasi dengan menggunakan command `ntpq -p` <br>

Hasilnya 



### 8. Konfigurasi sudo**
### 9. Ganti hostname VM**
   **server10.kelompokX.takehome.com**
