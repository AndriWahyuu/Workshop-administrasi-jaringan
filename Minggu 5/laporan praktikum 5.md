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
```
sudo timedatectl set-local-rtc false
```
 
<br> 

2. **install NTP server**  <br>
sebelum melakukan install maka perlumengubah kembali IP jaringan yang sebelumnya static menjadi DHCP kembali, <br>
- Pertama update terlebih dahulu server dengan menggunakan perintah <br>
```
sudo apt update && sudo apt -y upgrade
```

- menginstall NTP Srver menggunakan perintah : <br>
```
sudo apt -y install ntp
```
<br>

3. **Konfigurasi NTP Server**
- mengedit `ntp.conf` dengan menggunkan perintah : <br>
```sudo nano /etc/ntp.conf``` <br>
- memberikan command pada <br>
`pool 0.ubuntu.pool.ntp.org iburst` <br>
`pool 1.ubuntu.pool.ntp.org iburst` <br>
`pool 2.ubuntu.pool.ntp.org iburst` <br>
`pool 3.ubuntu.pool.ntp.org iburst` <br>
`pool 4.ubuntu.pool.ntp.org iburst`<br> 
`pool 5.ubuntu.pool.ntp.org iburst` <br><br>

- Menambahkan baris <br>
```
server 0.id.pool.ntp.org
server 1.id.pool.ntp.org
server 2.id.pool.ntp.org
server 4.id.pool.ntp.org
``` 
jika sudah, simpan konfigurasi dan keluar dar teks editor. <br><br>

- Merestrat NTP service menggunakan perintah : <br>
```
sudo systemctl restart ntp
``` 
<br>

- Mengkonfirmasi apakah NTPservice telah aktif menggunkan perintah : <br>
```
systemctl status ntp
``` 
- Cek keberhasilan konfigurasi dengan menggunakan command 
```
ntpq -p
``` 

<br>
- Mengecek kembali settingan waktu dan tanggal menggunakan perintah : <br>
``` 
timedatectl
```
<br>

### Hasilnya <br> <br>
<img src=https://github.com/AndriWahyuu/Workshop-administrasi-jaringan/blob/7d2694c7939f4f7544cb516cd80c9b39f06d1489/Minggu%205/images/No%207.1.png width="" height="500" />



### 8. Konfigurasi sudo**
### 9. Ganti hostname VM**
   **server10.kelompokX.takehome.com**
