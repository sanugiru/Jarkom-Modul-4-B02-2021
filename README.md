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
#### Subnetting 
- **Langkah 1:** Menentukan subnet yang ada dalam topologi dan melakukan labelling netmask terhadap masing-masing subnet. Penggabungan dilakukan hingga didapatkan satu subnet besar.
![subnet-dan-labelling](/screenshots/cidr-1.jpg)
- **Langkah 2:** Menggabungkan subnet paling bawah di dalam topologi (paling jauh dari NAT)
	- iterasi 1
![subnet1](/screenshots/cidr-2.jpg)
	- iterasi 2
![subnet2](/screenshots/cidr-3.jpg)
	- iterasi 3
![subnet3](/screenshots/cidr-4.jpg)
	- iterasi 4
![subnet4](/screenshots/cidr-5.jpg)
	- iterasi 5
![subnet5g](/screenshots/cidr-6.jpg)
	- iterasi 6
![subnet6](/screenshots/cidr-7.jpg)
	- iterasi 7
![subnet7](/screenshots/cidr-8.jpg)


- **Langkah 3:** Dari proses penggabungan yang telah dilakukan, dari gambar di atas bisa kita lihat didapatkan sebuah subnet dengan netmask /15.
- **Langkah 4:** Selanjutnya dilakukan perhitungan pembagian IP menggunakan pohon ip
![pembagian-ip](/screenshots/cidr-9.jpg)  
- **Langkah 5:** berdasarkan perhitungan tersebut, maka didapatkan pembagian IP sebagai berikut.
![hasil](/screenshots/cidr-ip.png) 

##### Konfigurasi pada GNS3
- FOOSHA
- WATER7
- PUCCI
- GUANHAO
- ALABASTA
- OIMO
- SEASTONE

#### Routing

