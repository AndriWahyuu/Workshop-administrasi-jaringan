# Webinar “Cloud and IoT Security”
## The Trend of Cloud Security 
##### by Mr. Muhammad Salahuddien Manggalann - Senin, 27 Februari 2023

Komputasi awan adalah model yang menawarkan layanan komputasi instan tanpa menanggung biaya.  Namun demikian, seperti teknologi lainnya, ini membawa kekurangannya.  Salah satu masalah utama adalah masalah keamanan dan privasi termasuk kebocoran data karena infrastruktur sumber daya komputasi bersama untuk memproses informasi bisnis rahasia - seperti kekayaan intelektual, rahasia dagang, dan informasi rahasia pelanggan, yang dapat menyebabkan aktor yang tidak sah dapat mengaksesnya.

### A.	The Threats
##### 1.	Kehilangan dan Kebocoran Data
Sebagian besar fitur perlindungan data cloud untuk perusahaan ditawarkan secara terpisah sebagai layanan opsional dan tambahan, mis. penyimpanan tambahan untuk retensi snapshot dan anti ransomware karena sumber dayanya luas dan mahal.
#### 2.	Penggunaan yang salah dan jaht
Karena Cloud Computing adalah ekosistem multi layanan, interaksi, dan saling ketergantungan, telah menjadi lebih umum. Eksploitasi (PaaS) untuk "Peretasan sebagai Layanan" dapat lebih menantang untuk dikurangi karena tersembunyi di infrastruktur yang sama.
#### 3.	interface yang tidak aman dan Penggunaan API's; 
Memanfaatkan API yang tidak aman di lingkungan multitenancy dapat meningkatkan risiko spionase bisnis, yang berpotensi mengakibatkan kompromi atau pencurian data sensitif dan pribadi.
#### 4.	Shared Technology Issues
Penyedia layanan cloud menggunakan infrastruktur yang dapat diskalakan untuk mendukung banyak penyewa yang berbagi infrastruktur yang mendasarinya. Pada lapisan terendah, di mana hypervisor dapat dieksploitasi dari mesin virtual yang disusupi di sewa lain untuk mendapatkan akses ke semua VM di lingkungan bersama yang sama.

- **Virtualisasi**
Virtualisasi perangkat keras adalah abstraksi sumber daya komputasi dari perangkat lunak yang menggunakan sumber daya tersebut. Virtualisasi perangkat keras juga disebut virtualisasi server, virtualisasi perangkat keras menginstal hypervisor atau manajer mesin virtual (VMM), yang menciptakan lapisan abstraksi antara perangkat lunak dan perangkat keras yang mendasarinya
Lingkungan virtualisasi dikelola oleh perangkat lunak atau firmware, yang dikenal sebagai hypervisor. Hypervisor rentan terhadap semua jenis serangan untuk infrastruktur normal

- **Hyper-Jacking**
Untuk menginfeksi sistem berbasis komputasi awan dengan dos hypervisor, penyerang harus memiliki kendali atas hypervisor, penyerang menggunakan rootkit yang diinstal pada VM (Mesin Virtual) untuk menyerang untuk mendapatkan kendali atas hypervisor, upaya seperti itu oleh penyerang dunia maya adalah didefinisikan sebagai hyper-jacking. jika seorang penyerang berhasil melakukan hyper jack kekuatan hypervisor, itu bisa mendapatkan kendali atas seluruh hosting. akibatnya, penyerang dapat mengubah perilaku dan menyebabkan kerusakan pada VM.

### B.	The Attacks
- **Virtual Machine Level Attack**
Serangan pada platform Cloud yang sama dapat mempengaruhi penyewa lainnya. Wajib bagi penyebaran Cloud apa pun untuk mengeraskan lapisan virtualisasi untuk mencegah serangan VM ke VM.
- **Service and Session Hijacking**
- **Man in the Cloud and DDoS**

### C.	The Security
- **Cloud Control Layers**
Gunakan lapisan kontrol tambahan dalam manajemen Cloud dari 3% penyedia solusi pihak, terutama untuk penyebaran multi-cloud.
- **Shared Responsibilities**
Gunakan "perjanjian back-to-back" dengan Penyedia Cloud Anda untuk memastikan kepatuhan standar keamanan penuh.

### D.	The Tools
- **Software Defined Security**
yakinkan kembali solusi Keamanan Cloud tertinggi yang tersedia. 
- **Software Defined Securit**
Kemajuan AAA untuk setiap Lapisan Cloud misalnya kombinasi biometrik wajib.
- **Inspection and Monitoring**
penilaian pendapat kedua.


### E.	The Tests
- **Cloud Resources Isolation**; 
mencegah serangan pivot VM ke VM.
- **Check Lock-in Issues**
cegah terjebak dalam produk yang rentan. 
- **Check Governance Issues**
yakinkan kembali standar praktik terbaik.
- **Check Compliance Issues**
hindari sanksi dan hukuman. 
- **Check Data Integrity, Retention, and Disposal**
mencegah kebocoran dan kerugian.

### F.	Summary
Diskusi ini menyampaikan masalah keamanan yang terkait dengan layanan cloud. Tercatat bahwa penjahat dunia maya telah mengambil keuntungan dari kerentanan dalam ekosistem bersama dan kurangnya kontrol keamanan yang efektif, yang menyebabkan penyalahgunaan platform. Peretas dapat secara ilegal mengakses informasi rahasia penyewa lain yang berada di infrastruktur cloud yang sama. Oleh karena itu, bisnis disarankan untuk melakukan penilaian risiko berkelanjutan untuk mengurangi potensi ancaman terhadap data sensitif mereka. Selanjutnya, penyedia keamanan cloud harus meningkatkan perlindungan keamanan melalui penerapan langkah-langkah keamanan proaktif yang lebih canggih dan canggih untuk mengatasi tantangan ini.