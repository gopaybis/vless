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
# Cloudflare-workers/pages proxy script
### 1. This project only supports localized deployment
### 2. This project configuration is all localized editing, and does not use third-party external link references such as subscribers and subscription conversions
### 3. No need to worry about the node subscription information being viewed by the subscriber author or subscription conversion author in the background
--------------------------------
## Script Features:
#### 1. For lazy people only! The default nodes are all CF official IPs, so there is no need to frequently update subscriptions to obtain the client's preferred IP.
#### 2. In order to reduce the extra costs for novices, this project does not recommend the use of custom domain names. If you must use a custom domain name, you can
#### 3. After clicking the deploy button in CF, you can directly manually rub the node or use the sharing link. You can set up a uuid/password at most, and do not need to change the others.
#### 4. Workers mode: support vless+ws+tls, trojan+ws+tls, vless+ws, trojan+ws proxy nodes
#### 5. Pages mode: support vless+ws+tls, trojan+ws+tls proxy nodes
#### 6. Support single node link, aggregated general node link, aggregated general node subscription, sing-box node subscription, clash node subscription
#### 7. Although only the garbled version is available, variables must be used only when modifying uuid/password
------------------------------------------------------------------

### Communication platform: [Yongge blog address](https://ygkkk.blogspot.com), [Yongge YouTube channel](https://www.youtube.com/@ygkkk), [Yongge TG Telegram Group](https://t.me/+jZHc6-A-1QQ5ZGVl), [Yongge TG Telegram Channel](https://t.me/+DkC9ZZUgEFQzMTZl)
--------------------------------

### It is recommended that novice users watch the following two introductory video tutorials first:

[CF vless/trojan free node obfuscation era is coming: workers/pages code obfuscation detailed settings update instructions; 1101 error summary; welfare plan: Yongge built multiple ProxyIP for everyone to use](https://youtu.be/QSFaP5EVI04)

[CF vless/trojan permanent free node (please replace the code content in the video with obfuscated code): no need for custom domain name, quick start to build; free client setting instructions for all platforms; exclusive preferred IP and ProxyIP meaning explanation; one-click generation of preferred official IP in the United States, Hong Kong, and Europe](https://youtu.be/WwAeLyEz6jY)

----------------------------------------

## 1: Variable contents that can be set in CF Vless nodes

| Variable function| Variable name| Variable value requirement| Variable default value| Variable requirement|
| :--- | :--- | :--- | :--- | :--- |
| 1. Necessary uuid | uuid (lowercase letters) | Comply with the specified uuid format | Wanrenqi uuid: 86c50e3a-5b87-49dd-bd20-03c7f2735e40 | Suggestions |
| 2. Global nodes can access CF websites | proxyip (lowercase letters) | 443 port: ipv4 address, [ipv6 address], domain name. Non-443 port: IPV4 address: port, [IPV6 address]: port, domain name: port | proxyip domain name: ts.hpc.tw public domain name | optional |
| 3. Subscription node: preferred IP | ip1 to ip13, a total of 13 | CF official IP, CF reverse generation IP, CF preferred domain name | CF official visa domain names in different regions | optional |
| 4. Subscription node: Preferred IP corresponding port | pt1 to pt13, a total of 13 | CF13 standard ports, reverse IP corresponding to any port | CF13 standard ports | Optional |


## 2: Variable contents that can be set in CF Trojan nodes

| Variable function| Variable name| Variable value requirement| Variable default value| Variable requirement|
| :--- | :--- | :--- | :--- | :--- |
| 1. Necessary password | pswd (lowercase letters) | Alphanumeric characters are recommended | 10,000 people’s password: trojan | Recommended |
| 2. Global nodes can access CF websites | proxyip (lowercase letters) | 443 port: ipv4 address, [ipv6 address], domain name. Non-443 port: IPV4 address: port, [IPV6 address]: port, domain name: port | proxyip domain name: ts.hpc.tw public domain name | optional |
| 3. Subscription node: preferred IP | ip1 to ip13, a total of 13 | CF official IP, CF reverse generation IP, CF preferred domain name | CF official visa domain names in different regions | optional |
| 4. Subscription node: Preferred IP corresponding port | pt1 to pt13, a total of 13 | CF13 standard ports, reverse IP corresponding to any port | CF13 standard ports | Optional |

#### Subscribe to the variables of IP and port in the node (3 and 4). Pay special attention [Newbies can ignore the variables (3 and 4) and use the defaults]

0. Since we can only use obfuscated code now, we cannot modify the file directly, we can only use variables

1. Remember: When you have to use a subscription client and want to change the preferred IP, you need to set the variables from ip1 to ip13 and pt1 to pt13

2. From ip1 to ip7, from pt1 to pt7, in the subscription sharing link, only TLS nodes with port 80 are supported

3. From ip8 to ip13, from pt8 to pt13, in the subscription sharing link, only the 443 port is supported to open the TLS node

4. Set the official IP, no need to set the port (13 CF standard ports are set by default); setting the reverse IP requires turning on and off TLS, and the port variable must also be set

5. For setting the subscription node variables, please refer to this [video tutorial](https://youtu.be/8s-ELRuFaeE?si=MjhcKbt20d2Q2eqp&t=447)

----------------------------------
## Three: Customize proxyip

Although the script comes with other big guys' proxyip by default, it also supports custom proxyip

Supports IPV4, IPV6, and domain name (when the port is 443, you can omit the :port)

1. Global node variable form (described in 1 and 2 above):

| proxyip port | IPv4 format | IPv6 format | domain name format |
| :--- | :--- | :--- | :--- |
| Port 443 | IPV4 address | [IPV6 address] | Domain name |
| Non-443 port | IPV4 address: port | [IPV6 address]: port | domain name: port |

2. Single node path format:

| proxyip port | IPv4 format | IPv6 format | domain name format |
| :--- | :--- | :--- | :--- |
| Port 443 | /pyip=IPV4 address |/pyip=[IPV6 address] |/pyip=domain name |
| Non-443 port| /pyip=IPV4 address:port|/pyip=[IPV6 address]:port|/pyip=domain name:port|

Notice:

1. Change proxyip of a single node path: only affects the single node that the current client is setting, and does not affect the proxyip of other single nodes or subscribed nodes

2. Global node proxyip change: affects all nodes that do not have path proxyip set

3. When the keyword ```/pyip=``` appears in the node's path, the proxyip of this node only recognizes the proxyip set in the path, and the global proxyip does not work.

----------------------------------
## 4: No need for socks5! Xiaobai uses the reality protocol to make a proxyip and reverse IP for any port in the 80 series/443 series in one click

### 1. Serv00 only:

[Project address](https://github.com/yonggekkk/sing-box-yg?tab=readme-ov-file#%E4%BA%8Cserv00%E4%B8%80%E9%94%AE%E4%B8%89%E5%8D%8F%E8%AE%AE%E5%85%B1%E5%AD%98%E8%84%9A%E6%9C%ACserv00%E4%B8%93%E7%94%A8)

Modified from Serv00 Laowang sing-box installation script, supports one-click three protocols: vless-reality, vmess-ws (argo), hysteria2.

Mainly add the reality protocol to support the proxyip of CF vless/trojan nodes by default and the preferred reverse IP function of non-standard ports

Serv00 dedicated one-key script (default automatic installation process keep alive), shortcut: ```bash serv00.sh```
```
bash <(curl -Ls https://raw.githubusercontent.com/yonggekkk/sing-box-yg/main/serv00.sh)
```

### 2. VPS Dedicated:

It is recommended to use a pure IPV6 vps that is close to China, cheap, and has a lot of traffic. Avoid using IPV4 as much as possible, because IPV4 is likely to be stolen by big guys to become their public welfare or paid anti-generation IP library. If you must use IPV4, please always pay attention to the traffic of your VPS. Using proxyip and client-preferred IP will consume VPS traffic.

Recommended scripts for setting up proxyip and reverse ip: [x-ui-yg script](https://github.com/yonggekkk/x-ui-yg), [sing-box-yg script](https://github.com/yonggekkk/sing-box-yg)

For related operations, please see [Video Tutorial Advanced 1](https://youtu.be/QOnMVULADko) and [Video Tutorial Advanced 2](https://youtu.be/CVZStM0t8BA)


### 3. The following four situations can be realized (recommended in TLS node environment):

Optional reality 1: Only used for client-side preferred IP, that is, the landing IP area of ​​CF nodes accessing non-CF websites is consistent with the VPS area, and the landing IP area for accessing CF websites is determined by proxyip

Optional reality 2: Only used for proxyip, that is, the landing IP area of ​​CF node accessing CF website is consistent with the VPS area, and the landing IP area for accessing non-CF website is determined by the client's preferred IP

Optional reality 3: Used for both client preferred IP and proxyIP, that is, the landing IP area of ​​CF node accessing CF website and the landing IP area of ​​non-CF website, both of which are consistent with the VPS area

Option 4: Install WARP global dual stack V4+V6 function on VPS, that is, the landing IP (104.28……/2a09:……) of the client preferred IP for accessing non-CF websites is fixed, or the landing IP (104.28……/2a09:……) of the proxy IP for accessing CF websites is fixed to achieve the effect of WARP unlocking function.

--------------------------------------------------

## Five: View configuration information and share links

CF Vless: Enter https:// workers domain name or pages domain name or custom domain name/custom uuid in the web address bar

CF Trojan: Enter https:// workers domain name or pages domain name or custom domain name/custom password in the web address bar

Notice:

1. If the workers domain name, pages domain name or custom domain name is blocked, you must use a proxy to open it

2. When using a custom domain, the configuration information and sharing links under the original workers domain or pages domain are still available

----------------------------------

## 6: Optimal IP Application

If you don't need the highest speed every day or select a country, you can use the default CF official IP or domain name without changing it

The recommended easy-to-remember lazy-person exclusive CF official IP is as follows (the IP landing area is the United States, supporting 13 standard port switching), which is called "the most front-running immortal IP"

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

2606:4700:: Requires IPV6 environment

By modifying the configuration variables, you can use the IP or domain name shared by others, or you can optimize it locally. For related optimization applications and scripts, please refer to the video tutorial

Recommended local computer projects (can be downloaded directly in the code area above):

1. CDN preferred domain name V23.8.18 (computer win64)

2. CF preferred anti-generation IP (computer version, with speed test)

3. CF preferred official IP (non-interactive PC version for America, Asia, and Europe! Highly recommended! Click [video tutorial](https://youtu.be/6kKIzObEZ2c))

4. CF preferred official IP (computer version, with speed test)

Note: When multiple CF nodes are using load balancing or automatic selection on the client, it is recommended that all application nodes be in the same country to avoid IP hopping between different countries.

----------------------------------

## 7: Client Recommendation

#### The benefit of enabling the fragment function: ignoring the domain name being blocked by TLS, so that workers and other blocked domain names can support TLS nodes
#### Tip: Custom domain names or pages domain names that are not blocked by TLS can use TLS nodes without enabling sharding
 
The following platforms and clients currently support this function (click the name to jump to the official download address)

1. Android Android: [v2rayNG](https://github.com/2dust/v2rayNG/tags), [Nekobox](https://github.com/starifly/NekoBoxForAndroid/releases), [Karing](https://github.com/KaringX/karing/tags), v2box

2. Computer Windows: [v2rayN](https://github.com/2dust/v2rayN/tags), [Hiddify](https://github.com/hiddify/hiddify-next/tags), [Karing](https://github.com/KaringX/karing/tags)

3. Apple iOS: Karing, Hiddify Proxy & VPN, Shadowrocket, Streisand, v2box

4. Soft router Openwrt: [homeproxy](https://github.com/yonggekkk/homeproxy/releases), it is recommended to use the system's own software library to search for updates

Note: If the sharding function is not enabled on other platform clients, the six 443 TLS nodes in the workers domain are unavailable

Note: Shadowrocket, v2box, v2rayn, and v2rayng clients have a problem of forcing TLS to be enabled for Trojan+WS, which causes Trojan+WS to be unavailable. And Clash subscription does not have a Trojan+WS node.

For client usage issues, please see [CF vless/trojan Permanent Free Node Tutorial (VI): The node cannot be used, what is the problem? Multi-platform free client setup guide and pitfall avoidance instructions](https://youtu.be/8E0l0nQWLxs)

----------------------------------

### CF video tutorial collection:

[CF workers permanent free vless node construction tutorial (I): the first demonstration of IP jumping phenomenon on the entire network, decryption of the two major node usage skills, and the advantages and disadvantages of the preferred IP and preferred domain name](https://youtu.be/9V9CQxmfwoA)

[CF workers permanent free vless node construction tutorial (Part 2): one-click script release for optimizing anti-generation IP, pages deployment tutorial, multi-platform client setting instructions, exclusive discussion of CF free proxy sensitive security issues](https://youtu.be/McdRoLZeTqg)

[CF workers permanent free Trojan node construction tutorial (Part 3): No need for custom domain name, workers and pages two schemes to deploy preferred IP nodes; CF Trojan and CF Vless comparison summary; How to view Trojan being identified](https://youtu.be/lmhhL8M1k0I)

Strongly recommended: [CF vless/trojan permanent free node tutorial (IV): Interpretation of the relationship and characteristics of the three preferred official IP, preferred reverse IP, and preferred domain name; the significance of the existence of ProxyIP](https://youtu.be/NaLd-orwFUE)

Highly recommended: [CF vless/trojan permanent free node tutorial (V): No need for custom domain name? No need for frequent IP optimization? No need for subscriber? Summarize the structural relationship diagram of CF node and domain name](https://youtu.be/8s-ELRuFaeE)

Highly recommended: [CF vless/trojan permanent free node tutorial (VI): The node cannot be used, what is the problem? Multi-platform free client setting guide and pitfall avoidance instructions](https://youtu.be/8E0l0nQWLxs)

Advanced recommendation: [CF vless/trojan permanent free node final tutorial (Part 7): The only demonstration of the real "fixed IP" in the whole network, solving the error reporting problem of twitch and chatgpt clients; one-click self-made anti-generation IP and ProxyIP; revealing the risk of your IP being stolen by others](https://youtu.be/QOnMVULADko)

Advanced recommendation: [CF vless/trojan permanent free node final tutorial (VIII): self-built universal ProxyIP for all ports, while supporting client address preferred anti-generation IP, self-built anti-generation IP final tutorial](https://youtu.be/CVZStM0t8BA)

[Review of selected live broadcasts: Four major features of CF workers vless free nodes, and the problem of nodes being blocked by interruptions](https://youtu.be/9OHGpWlfdJ0)

[ClouDNS permanent free domain name final tutorial: CF pages vless custom domain name direct deployment](https://youtu.be/PN0BLANXh4I)

Recommended application for Xiaobai's preferred IP: [CF's preferred IP to liberate Xiaobai's final solution: one-click automatic generation of preferred official IPs for the United States, Hong Kong, and Europe, one-click universal for multiple platforms including computer WIN, Android, and Apple iOS](https://youtu.be/6kKIzObEZ2c)

Latest recommendation: [CF vless/trojan free node obfuscation era is coming: workers/pages code obfuscation detailed settings update instructions; 1101 error summary; welfare plan: Yongge built multiple ProxyIP for everyone to use](https://youtu.be/QSFaP5EVI04)


----------------------------------
----------------------------------
----------------------------------
----------------------------------
## One-click script for preferred domain name, preferred official IP + reverse IP (run using termux or ish in local network environment):

1. For Android, please use the official termux project to download the client (download from Google Store is not available!): https://github.com/termux/termux-app/releases/tag/v0.118.1

After the first installation, please install the dependencies: ```pkg upgrade```, then run the following scripts you want to use

2. For Apple mobile phone users, since the latest version of ISH has a bug that causes the script to get stuck, please use the ISH_1.2.2 version. You can use Troll to install it first and then downgrade. There are also other tutorials on the Internet that specify the installation of the old version of IPA.

After the first installation, please install the dependencies: ```apk add curl bash```, then run the following scripts you want to use

------------------------------------------------------------------
### Script 1: CF-Preferred official IP (highly recommended by default in the Americas, Asia, and Europe!!!), dedicated for Android and Apple phones and tablets:
```
curl -sSL https://raw.githubusercontent.com/yonggekkk/Cloudflare_vless_trojan/main/cf/cf.sh -o cf.sh && chmod +x cf.sh && bash cf.sh
```
------------------------------------------------------------------

### Script 2: CF-CDN prefers public domain names of large companies, dedicated to Apple, Android, and tablets:
```
curl -sSL https://gitlab.com/rwkgyg/CFwarp/raw/main/point/CFcdnym.sh -o CFcdnym.sh && chmod +x CFcdnym.sh && bash CFcdnym.sh
```
--------------------------------------------------------------------------------
### Script 3: CF-optimized official IP + anti-generation IP two-in-one script (with speed test), dedicated to Apple Android phones and tablets:
```
curl -sSL https://gitlab.com/rwkgyg/CFwarp/raw/main/point/cfip.sh -o cfip.sh && chmod +x cfip.sh && bash cfip.sh
```

------------------------------------------------------------------
### Thank you for the star in the upper right corner🌟
[![Stargazers over time](https://starchart.cc/yonggekkk/Cloudflare-workers-pages-vless.svg)](https://starchart.cc/yonggekkk/Cloudflare-workers-pages-vless)
--------------------------------------------------------------------------------
### Code sources: [ca110us](https://github.com/ca110us/epeius), [emn178](https://github.com/emn178/js-sha256/blob/master/src/sha256.js), [3Kmfi6HP](https://github.com/3Kmfi6HP/EDtunnel), [badafans](https://github.com/badafans/Cloudflare-IP-SpeedTest), [XIU2](https://github.com/XIU2/CloudflareSpeedTest)
### Statement: All codes come from the Github community and are integrated through ChatGPT
