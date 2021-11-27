# LAPRES JARKOM B02 MODUL 4 2021  
### Modul 4: Subnetting & Routing
**Anggota:**
- 05111940000006 	[Daffa Tristan Firdaus](https://www.github.com/DaffaTristan)  
- 05111940000086 	[Nabil Fikri Arief](https://www.github.com/alwaysyu)
- 05111940000158 	[Shahnaaz Anisa Firdaus](https://www.github.com/sanugiru)

## Topologi dan Soal
![Topologi](/screenshots/topologi.png)

### A. VLSM Menggunakan CPT
- **Langkah 1 -** Menentukan subnet yang ada pada topologi
![Topologi-VLSM](/screenshots/topologi-vlsm.png)
 dan kemudian menentukan jumlah IP dan netmask pada tiap subnet
![VLSM-IP-Netmask](/screenshots/vlsm-1.png)
- **Langkah 2 -** Menghitung pembagian IP berdasarkan pohon berikut
![VLSM-Tree](/screenshots/vlsm-tree.png)
- **Langkah 3 -** Menentukan Network ID, Netmask, dan Broadcast Address
![VLSM-Tabel-1](/screenshots/vlsm-tabel-1.png)
![VLSM-Tabel-2](/screenshots/vlsm-tabel-2.png)
![VLSM-Tabel-3](/screenshots/vlsm-tabel-3.png)
- **Langkah 4 -** Lalu, memasukkan konfigurasi IP ke router atau PC
<br>Foosha melalui Fa1/0 terhubung dengan Water7
![VLSM-Konfigurasi-1](/screenshots/vlsm-konf-1.png)
<br>Foosha melalui Fa0/1 terhubung dengan BLUENO
![VLSM-Konfigurasi-3](/screenshots/vlsm-konf-3.png)
<br>BLUENO terhubung dengan Foosha
![VLSM-Konfigurasi-2](/screenshots/vlsm-konf-2.png)
- **Langkah 5 -** Kemudian, menentukan routing untuk tiap router
<br>  - **Foosha**
<br>![VLSM-Routing-Foosha](/screenshots/vlsm-foosha.png)
<br>  - **Guanhao**
<br>![VLSM-Routing-Guanhao](/screenshots/vlsm-guanhao.png)
<br>  - **Water7**
<br>![VLSM-Routing-Water7](/screenshots/vlsm-water7.png)
<br>  - **Pucci**
<br>![VLSM-Routing-Pucci](/screenshots/vlsm-pucci.png)
<br>  - **Oimo**
<br>![VLSM-Routing-Oimo](/screenshots/vlsm-oimo.png)
<br>  - **Seastone**
<br>![VLSM-Routing-Seastone](/screenshots/vlsm-seastone.png)
<br>  - **Alabasta**
<br>![VLSM-Routing-Alabasta](/screenshots/vlsm-alabasta.png)
- **Langkah 6 -** Melakukan Ping antar Server, Router atau PC
![VLSM-Ping-1](/screenshots/vlsm-ping-1.png)
![VLSM-Ping-2](/screenshots/vlsm-ping-2.png)
### B. CIDR Menggunakan GNS3
