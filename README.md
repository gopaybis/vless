# vless
# Skrip proksi Cloudflare-workers/pages
### 1. Proyek ini hanya mendukung penyebaran lokal
### 2. Konfigurasi proyek ini semua pengeditan lokal, dan tidak menggunakan referensi tautan eksternal pihak ketiga seperti pelanggan dan konversi langganan
### 3. Tidak perlu khawatir tentang informasi langganan node yang dilihat oleh penulis pelanggan atau penulis konversi langganan di latar belakang
--------------------------------
## Fitur Skrip:
#### 1. Hanya untuk pemula yang malas! Semua node default adalah IP resmi CF, jadi tidak perlu sering memperbarui langganan untuk mendapatkan IP pilihan klien.
#### 2. Untuk mengurangi biaya tambahan bagi pemula, proyek ini tidak merekomendasikan penggunaan nama domain khusus. Jika Anda harus menggunakan nama domain khusus, Anda dapat
#### 3. Setelah mengklik tombol deploy di CF, Anda dapat langsung menggosok node secara manual atau menggunakan tautan berbagi. Anda dapat mengatur uuid/password paling banyak, dan tidak perlu mengubah yang lain.
#### 4. Mode pekerja: mendukung node proxy vless+ws+tls, trojan+ws+tls, vless+ws, trojan+ws
#### 5. Mode halaman: mendukung node proxy vless+ws+tls, trojan+ws+tls
#### 6. Mendukung tautan simpul tunggal, tautan simpul umum agregat, langganan simpul umum agregat, langganan simpul sing-box, langganan simpul bentrok
#### 7. Meskipun hanya versi yang kacau yang tersedia, variabel harus digunakan hanya saat memodifikasi uuid/kata sandi
-------------------------------------------------------------

### Platform komunikasi: [Alamat blog Yongge](https://ygkkk.blogspot.com), [Saluran YouTube Yongge](https://www.youtube.com/@ygkkk), [Grup Telegram Yongge TG](https://t.me/+jZHc6-A-1QQ5ZGVl), [Saluran Telegram Yongge TG](https://t.me/+DkC9ZZUgEFQzMTZl)
--------------------------------

### Disarankan agar pengguna pemula menonton dua video tutorial pengantar berikut terlebih dahulu:

[Era pengaburan simpul bebas CF vless/trojan akan segera tiba: instruksi pembaruan pengaturan terperinci pengaburan kode pekerja/halaman; ringkasan kesalahan 1101; rencana kesejahteraan: Yongge membangun beberapa ProxyIP agar dapat digunakan semua orang](https://youtu.be/QSFaP5EVI04)

[CF vless/trojan node gratis permanen (silakan ganti konten kode dalam video dengan kode yang dikaburkan): tidak perlu nama domain khusus, mulai membangun dengan cepat; petunjuk pengaturan klien gratis untuk semua platform; penjelasan arti IP pilihan dan ProxyIP eksklusif; pembuatan IP resmi pilihan di Amerika Serikat, Hong Kong, dan Eropa dalam satu klik](https://youtu.be/WwAeLyEz6jY)

---------------------------------------------

## 1: Konten variabel yang dapat diatur di node CF Vless

| Fungsi variabel| Nama variabel| Persyaratan nilai variabel| Nilai default variabel| Persyaratan variabel|
:--- | :--- | :--- | :--- | :--- |
| 1. uuid yang diperlukan | uuid (huruf kecil) | Patuhi format uuid yang ditentukan | Wanrenqi uuid: 86c50e3a-5b87-49dd-bd20-03c7f2735e40 | Saran |
| 2. Node global dapat mengakses situs web CF | proxyip (huruf kecil) | Port 443: alamat ipv4, [alamat ipv6], nama domain. Port non-443: alamat IPV4: port, [alamat IPV6]: port, nama domain: port | proxyip nama domain: ts.hpc.tw nama domain publik | opsional |
| 3. Node langganan: IP pilihan | ip1 hingga ip13, totalnya 13 | IP resmi CF, IP pembangkitan balik CF, nama domain pilihan CF | Nama domain visa resmi CF di berbagai wilayah | opsional |
| 4. Node langganan: IP pilihan yang sesuai dengan port | pt1 hingga pt13, totalnya 13 | Port standar CF 13, IP terbalik yang sesuai dengan port mana pun | Port standar CF 13 | Opsional |


## 2: Konten variabel yang dapat diatur di node CF Trojan

| Fungsi variabel| Nama variabel| Persyaratan nilai variabel| Nilai default variabel| Persyaratan variabel|
:--- | :--- | :--- | :--- | :--- |
| 1. Kata sandi yang diperlukan | pswd (huruf kecil) | Karakter alfanumerik direkomendasikan | Kata sandi 10.000 orang: trojan | Direkomendasikan |
| 2. Node global dapat mengakses situs web CF | proxyip (huruf kecil) | Port 443: alamat ipv4, [alamat ipv6], nama domain. Port non-443: alamat IPV4: port, [alamat IPV6]: port, nama domain: port | proxyip nama domain: ts.hpc.tw nama domain publik | opsional |
| 3. Node langganan: IP pilihan | ip1 hingga ip13, totalnya 13 | IP resmi CF, IP pembangkitan balik CF, nama domain pilihan CF | Nama domain visa resmi CF di berbagai wilayah | opsional |
| 4. Node langganan: IP pilihan yang sesuai dengan port | pt1 hingga pt13, totalnya 13 | Port standar CF 13, IP terbalik yang sesuai dengan port mana pun | Port standar CF 13 | Opsional |

#### Berlangganan variabel IP dan port di node (3 dan 4). Berikan perhatian khusus [Pemula dapat mengabaikan variabel (3 dan 4) dan menggunakan default]

0. Karena kita hanya dapat menggunakan kode yang dikaburkan sekarang, kita tidak dapat memodifikasi file secara langsung, kita hanya dapat menggunakan variabel

1. Ingat: Saat Anda harus menggunakan klien berlangganan dan ingin mengubah IP pilihan, Anda perlu mengatur variabel dari ip1 ke ip13 dan pt1 ke pt13

2. Dari ip1 ke ip7, dari pt1 ke pt7, dalam tautan berbagi langganan, hanya node TLS dengan port 80 yang didukung

3. Dari ip8 ke ip13, dari pt8 ke pt13, dalam tautan berbagi langganan, hanya port 443 yang didukung untuk membuka node TLS

4. Atur IP resmi, tidak perlu mengatur port (13 port standar CF diatur secara default); pengaturan IP terbalik memerlukan pengaktifan dan penonaktifan TLS, dan variabel port juga harus diatur

5. Untuk pengaturan variabel node langganan, silakan lihat [tutorial video](https://youtu.be/8s-ELRuFaeE?si=MjhcKbt20d2Q2eqp&t=447) ini

---------------------------------
## Tiga: Sesuaikan proxyip

Meskipun skrip ini dilengkapi dengan proxyip milik perusahaan besar lainnya secara default, skrip ini juga mendukung proxyip khusus

Mendukung IPV4, IPV6, dan nama domain (ketika portnya 443, Anda dapat menghilangkan :port)

1. Bentuk variabel simpul global (dijelaskan pada 1 dan 2 di atas):

| port proxyip | format IPv4 | format IPv6 | format nama domain |
:--- | :--- | :--- | :--- |
| Port 443 | Alamat IPV4 | [Alamat IPV6] | Nama domain |
| Port non-443 | Alamat IPV4: port | [alamat IPV6]: port | nama domain: port |

2. Format jalur simpul tunggal:

| port proxyip | format IPv4 | format IPv6 | format nama domain |
:--- | :--- | :--- | :--- |
| Port 443 | /pyip=alamat IPV4 |/pyip=[alamat IPV6] |/pyip=nama domain |
| Port non-443| /pyip=alamat IPV4:port|/pyip=[alamat IPV6]:port|/pyip=nama domain:port|

Melihat:

1. Ubah proxyip dari jalur node tunggal: hanya memengaruhi node tunggal yang ditetapkan oleh klien saat ini, dan tidak memengaruhi proxyip dari node tunggal lain atau node yang berlangganan.

2. Perubahan proxyip node global: memengaruhi semua node yang tidak memiliki jalur proxyip yang ditetapkan

3. Ketika kata kunci ```/pyip=``` muncul di jalur node, proxyip node ini hanya mengenali proxyip yang ditetapkan di jalur tersebut, dan proxyip global tidak berfungsi.

---------------------------------
## 4: Tidak perlu kaus kaki5! Xiaobai menggunakan protokol realitas untuk membuat proxyip dan IP terbalik untuk port mana pun di seri 80/seri 443 dalam satu klik

### 1. Hanya Serv00:

[Alamat proyek](https://github.com/yonggekkk/sing-box-yg?tab=readme-ov-file#%E4%BA%8Cserv00%E4%B8%80%E9%94%AE%E4%B8%89%E5%8D%8F%E8%AE%AE%E5%85%B1%E5%AD%98%E8%84%9A%E6%9C%ACserv00%E4%B8%93%E7%94%A8)

Dimodifikasi dari skrip instalasi Serv00 Laowang sing-box, mendukung tiga protokol satu-klik: vless-reality, vmess-ws (argo), hysteria2.

Terutama menambahkan protokol realitas untuk mendukung proxyip node CF vless/trojan secara default dan fungsi IP terbalik yang disukai dari port non-standar

Skrip satu tombol khusus Serv00 (proses instalasi otomatis default tetap aktif), pintasan: ```bash serv00.sh```
Bahasa Indonesia:
bash <(curl -Ls https://raw.githubusercontent.com/yonggekkk/sing-box-yg/main/serv00.sh)
Bahasa Indonesia:

### 2. VPS Dedicated:

Disarankan untuk menggunakan VPS IPv6 murni yang dekat dengan China, murah, dan memiliki lalu lintas tinggi untuk konstruksi. Sebaiknya hindari penggunaan IPV4 dalam waktu dekat, karena ada kemungkinan besar IPV4 akan dipindai secara diam-diam oleh orang-orang besar untuk mendapatkan IP anti-generasi, dan menjadi basis data IP anti-generasi kesejahteraan publik atau berbayar. Jika Anda harus menggunakan IPV4, harap selalu perhatikan lalu lintas VPS Anda. Penggunaan proxyip dan IP pilihan klien akan menghabiskan lalu lintas VPS.

Skrip yang direkomendasikan untuk mengatur proxyip dan reverse ip: [skrip x-ui-yg](https://github.com/yonggekkk/x-ui-yg), [skrip sing-box-yg](https://github.com/yonggekkk/sing-box-yg)

Untuk operasi terkait, silakan lihat [Video Tutorial Lanjutan 1](https://youtu.be/QOnMVULADko) dan [Video Tutorial Lanjutan 2](https://youtu.be/CVZStM0t8BA)


### 3. Empat situasi berikut dapat diwujudkan (disarankan dalam lingkungan node TLS):

Realitas opsional 1: Hanya digunakan untuk IP pilihan klien, yaitu area IP pendaratan node CF yang mengakses situs web non-CF konsisten dengan area VPS, dan area IP pendaratan untuk mengakses situs web CF ditentukan oleh proxyip

Realitas opsional 2: Hanya digunakan untuk proxyip, yaitu area IP pendaratan node CF yang mengakses situs web CF konsisten dengan area VPS, dan area IP pendaratan untuk mengakses situs web non-CF ditentukan oleh IP pilihan klien.

Realitas opsional 3: Digunakan untuk IP pilihan klien dan proxyIP, yaitu area IP pendaratan node CF yang mengakses situs web CF dan area IP pendaratan situs web non-CF, keduanya konsisten dengan area VPS

Opsi 4: Instal fungsi WARP global dual stack V4+V6 di VPS, artinya, IP pendaratan (104.28……/2a09:……) dari IP pilihan klien untuk mengakses situs web non-CF ditetapkan, atau IP pendaratan (104.28……/2a09:……) dari IP proksi untuk mengakses situs web CF ditetapkan untuk mencapai efek fungsi pembukaan kunci WARP.

-------------------------------------------

## Lima: Lihat informasi konfigurasi dan bagikan tautan

CF Vless: Masukkan https:// nama domain pekerja atau nama domain halaman atau nama domain khusus/uuid khusus di bilah alamat web

CF Trojan: Masukkan https:// nama domain pekerja atau nama domain halaman atau nama domain khusus/kata sandi khusus di bilah alamat web

Melihat:

1. Jika nama domain pekerja, nama domain halaman, atau nama domain khusus diblokir, Anda harus menggunakan proxy untuk membukanya

2. Saat menggunakan domain kustom, informasi konfigurasi dan tautan berbagi di bawah domain pekerja asli atau domain halaman masih tersedia

---------------------------------

## 6: Aplikasi IP yang Optimal

Jika Anda tidak memerlukan kecepatan tertinggi setiap hari atau memilih negara, Anda dapat menggunakan IP resmi CF atau nama domain default tanpa mengubahnya

IP resmi CF eksklusif orang malas yang mudah diingat yang direkomendasikan adalah sebagai berikut (area pendaratan IP adalah Amerika Serikat, mendukung 13 peralihan port standar), yang disebut "IP abadi paling terdepan"

104.16.0.0

104.17.0.0

104.18.0.0

104.19.0.0

104.20.0.0

104.21.0.0

104.22.0.0

104.24.0.0

104.25.0.0

104.26.0.0

104.27.0.0

172.66.0.0

172.67.0.0

162.159.0.0

2606:4700:: Memerlukan lingkungan IPV6

Dengan memodifikasi variabel konfigurasi, Anda dapat menggunakan IP atau nama domain yang dibagikan oleh orang lain, atau Anda dapat mengoptimalkannya secara lokal. Untuk aplikasi dan skrip pengoptimalan terkait, silakan lihat tutorial video

Proyek komputer lokal yang direkomendasikan (dapat diunduh langsung di area kode di atas):

1. Nama domain pilihan CDN V23.8.18 (komputer win64)

2. CF lebih menyukai IP anti-generasi (versi komputer, dengan uji kecepatan)

3. CF prefered official IP (versi PC non-interaktif untuk Amerika, Asia, dan Eropa! Sangat direkomendasikan! Klik [video tutorial](https://youtu.be/6kKIzObEZ2c))

4. CF lebih memilih IP resmi (versi komputer, dengan uji kecepatan)

Catatan: Bila beberapa node CF menggunakan penyeimbangan beban atau pemilihan otomatis pada klien, sebaiknya semua node aplikasi berada di negara yang sama guna menghindari perpindahan IP antar negara yang berbeda.

---------------------------------

## 7: Rekomendasi Klien

#### Manfaat mengaktifkan fungsi fragmen: mengabaikan nama domain yang diblokir oleh TLS, sehingga pekerja dan nama domain lain yang diblokir dapat mendukung node TLS
#### Tip: Nama domain kustom atau nama domain halaman yang tidak diblokir oleh TLS dapat menggunakan node TLS tanpa mengaktifkan sharding
 
Klien platform yang saat ini mendukung fungsi ini adalah sebagai berikut (klik nama untuk melompat ke alamat unduhan resmi)

1. Android: [v2rayNG](https://github.com/2dust/v2rayNG/tags), [Nekobox](https://github.com/starifly/NekoBoxForAndroid/releases), [Karing](https://github.com/KaringX/karing/tags), v2box

2. Komputer Windows: [v2rayN](https://github.com/2dust/v2rayN/tags), [Hiddify](https://github.com/hiddify/hiddify-next/tags), [Karing](https://github.com/KaringX/karing/tags)

3. Apple iOS: Karing, Hiddify Proxy & VPN, Shadowrocket, Streisand, v2box

4. Soft router Openwrt: [homeproxy](https://github.com/yonggekkk/homeproxy/releases), disarankan untuk menggunakan pustaka perangkat lunak sistem sendiri untuk mencari pembaruan

Catatan: Jika fungsi sharding tidak diaktifkan pada klien platform lain, enam 443 node TLS di domain pekerja tidak tersedia

Catatan: Klien Shadowrocket, v2box, v2rayn, dan v2rayng memiliki masalah dalam memaksa TLS diaktifkan untuk Trojan+ws, yang menyebabkan Trojan+ws tidak tersedia. Dan langganan clash tidak memiliki node trojan+ws. Catatan khusus

Untuk masalah penggunaan klien, silakan lihat [Tutorial node bebas permanen CF vless/trojan (VI): Node tidak dapat digunakan, apa masalahnya? Panduan pengaturan klien gratis multi-platform dan petunjuk menghindari jebakan](https://youtu.be/8E0l0nQWLxs)

---------------------------------

### Koleksi tutorial video CF:

[Tutorial konstruksi node vless gratis permanen pekerja CF (I): demonstrasi pertama fenomena lompatan IP di seluruh jaringan, dekripsi dua keterampilan penggunaan node utama, dan kelebihan serta kekurangan IP pilihan dan nama domain pilihan](https://youtu.be/9V9CQxmfwoA)

[Tutorial konstruksi node vless gratis permanen bagi pekerja CF (Bagian 2): rilis skrip satu klik untuk mengoptimalkan IP anti-generasi, tutorial penyebaran halaman, instruksi pengaturan klien multi-platform, diskusi eksklusif tentang masalah keamanan sensitif proxy gratis CF](https://youtu.be/McdRoLZeTqg)

[Tutorial konstruksi node Trojan gratis permanen pekerja CF (Bagian 3): Tidak perlu nama domain khusus, pekerja dan halaman dua skema untuk menyebarkan node IP pilihan; Ringkasan perbandingan Trojan CF dan CF Vless; Cara melihat Trojan yang diidentifikasi](https://youtu.be/lmhhL8M1k0I)

Sangat direkomendasikan: [Tutorial node bebas permanen CF vless/trojan (IV): Interpretasi hubungan dan karakteristik dari tiga IP resmi pilihan, IP terbalik pilihan, dan nama domain pilihan; pentingnya keberadaan ProxyIP](https://youtu.be/NaLd-orwFUE)

Sangat direkomendasikan: [Tutorial node gratis permanen CF vless/trojan (V): Tidak perlu nama domain khusus? Tidak perlu sering memilih alamat IP? Tidak perlu pelanggan? Rangkum hubungan struktural antara node CF dan nama domain](https://youtu.be/8s-ELRuFaeE)

Sangat direkomendasikan: [Tutorial node gratis permanen CF vless/trojan (VI): Node tidak dapat digunakan, apa masalahnya? Panduan pengaturan klien gratis multi-platform dan petunjuk menghindari jebakan](https://youtu.be/8E0l0nQWLxs)

Rekomendasi lanjutan: [Tutorial akhir CF vless/trojan permanent free node (Bagian 7): Satu-satunya demonstrasi "IP tetap" yang sebenarnya di seluruh jaringan, memecahkan masalah pelaporan kesalahan klien twitch dan chatgpt; IP anti-generasi dan ProxyIP buatan sendiri dalam satu klik; mengungkap risiko IP Anda dicuri oleh orang lain](https://youtu.be/QOnMVULADko)

Rekomendasi lanjutan: [Tutorial akhir simpul bebas permanen CF vless/trojan (VIII): ProxyIP universal yang dibuat sendiri untuk semua port, sambil mendukung alamat klien yang disukai anti-generasi IP, tutorial akhir IP anti-generasi yang dibuat sendiri](https://youtu.be/CVZStM0t8BA)

[Ulasan siaran langsung terpilih: Empat fitur utama node bebas vless pekerja CF, dan masalah node yang diblokir oleh interupsi](https://youtu.be/9OHGpWlfdJ0)

[Tutorial akhir nama domain gratis permanen Cloudns: Penyebaran langsung nama domain kustom vless halaman CF](https://youtu.be/PN0BLANXh4I)

Aplikasi yang direkomendasikan untuk IP pilihan Xiaobai: [IP pilihan CF untuk membebaskan solusi akhir Xiaobai: pembuatan otomatis satu klik dari IP resmi pilihan untuk Amerika Serikat, Hong Kong, dan Eropa, universal satu klik untuk berbagai platform termasuk komputer WIN, Android, dan Apple iOS](https://youtu.be/6kKIzObEZ2c)

Rekomendasi terkini: [Era pengaburan node bebas CF vless/trojan akan segera tiba: instruksi pembaruan pengaturan terperinci pengaburan kode pekerja/halaman; ringkasan kesalahan 1101; rencana kesejahteraan: Yongge membangun beberapa ProxyIP agar dapat digunakan semua orang](https://youtu.be/QSFaP5EVI04)


---------------------------------
---------------------------------
---------------------------------
---------------------------------
## Skrip satu klik untuk nama domain pilihan, IP resmi pilihan + IP terbalik (dijalankan menggunakan termux atau ish di lingkungan jaringan lokal):

1. Untuk Android, silakan gunakan proyek termux resmi untuk mengunduh klien (unduhan dari Google Store tidak tersedia!): https://github.com/termux/termux-app/releases/tag/v0.118.1

Setelah instalasi pertama, silakan instal dependensi: ```pkg upgrade```, lalu jalankan skrip berikut yang ingin Anda gunakan

2. Bagi pengguna ponsel Apple, karena versi ISH terbaru memiliki bug yang menyebabkan skrip macet, silakan gunakan versi ISH_1.2.2. Anda dapat menggunakan Troll untuk menginstalnya terlebih dahulu, lalu menurunkan versi. Ada juga tutorial lain di Internet yang menjelaskan cara menginstal IPA versi lama.

Setelah instalasi pertama, silakan instal dependensi terlebih dahulu: ```apk add curl bash```, lalu jalankan skrip berikut yang ingin Anda gunakan

-------------------------------------------------------------
### Skrip 1: IP resmi CF-Preferred (sangat direkomendasikan secara default di Amerika, Asia, dan Eropa!!!), didedikasikan untuk ponsel dan tablet Android dan Apple:
Bahasa Indonesia:
curl -sSL https://raw.githubusercontent.com/yonggekkk/Cloudflare_vless_trojan/main/cf/cf.sh -o cf.sh dan chmod +x cf.sh dan bash cf.sh
Bahasa Indonesia:
-------------------------------------------------------------

### Skrip 2: CF-CDN lebih menyukai nama domain publik perusahaan besar, yang didedikasikan untuk Apple, Android, dan tablet:
Bahasa Indonesia:
curl -sSL https://gitlab.com/rwkgyg/CFwarp/raw/main/point/CFcdnym.sh -o CFcdnym.sh dan chmod +x CFcdnym.sh dan bash CFcdnym.sh
Bahasa Indonesia:
------------------------------------------------------------------------
### Skrip 3: IP resmi yang dioptimalkan CF + IP anti-generasi dua-dalam-satu (dengan uji kecepatan), didedikasikan untuk ponsel dan tablet Apple Android:
Bahasa Indonesia:
curl -sSL https://gitlab.com/rwkgyg/CFwarp/raw/main/point/cfip.sh -o cfip.sh dan chmod +x cfip.sh dan bash cfip.sh
Bahasa Indonesia:

-------------------------------------------------------------
### Terima kasih atas bintang di pojok kanan atas🌟
[![Pengamat bintang dari waktu ke waktu](https://starchart.cc/yonggekkk/Cloudflare-workers-pages-vless.svg)](https://starchart.cc/yonggekkk/Cloudflare-workers-pages-vless)
------------------------------------------------------------------------
### Sumber kode: [ca110us](https://github.com/ca110us/epeius), [emn178](https://github.com/emn178/js-sha256/blob/master/src/sha256.js), [3Kmfi6HP](https://github.com/3Kmfi6HP/EDtunnel), [badafans](https://github.com/badafans/Cloudflare-IP-SpeedTest), [XIU2](https://github.com/XIU2/CloudflareSpeedTest)
### Pernyataan: Semua kode berasal dari komunitas Github dan diintegrasikan melalui ChatGPT
