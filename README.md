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
Konfigurasi dilakukan menggunakan langkah yang pernah dilakukan pada modul GNS3
- FOOSHA
```
# Config for eth0 (NAT)
auto eth0
iface eth0 inet dhcp

# Static config for eth1
auto eth1
iface eth1 inet static
	address 10.9.128.1
	netmask 255.255.252.0

# Static config for eth2
auto eth2
iface eth2 inet static
	address 10.9.64.1
	netmask 255.255.255.252

# Static config for eth3
auto eth3
iface eth3 inet static
	address 10.8.64.1
	netmask 255.255.255.252

# Static config for eth4
auto eth4
iface eth4 inet static
	address 10.8.128.1 
	netmask 255.255.255.128
```
- WATER7
```
# Static config for eth0
auto eth0
iface eth0 inet static
	address 10.9.64.2
	netmask 255.255.255.252
	gateway 10.9.64.1

# Static config for eth1
auto eth1
iface eth1 inet static
	address 10.9.16.1
	netmask 255.255.255.252

# Static config for eth2
auto eth2
iface eth2 inet static
	address 10.9.32.1
	netmask 255.255.252.0
```
- PUCCI  
```
# Static config for eth0
auto eth0
iface eth0 inet static
	address 10.9.16.2
	netmask 255.255.255.252
	gateway 10.9.16.1

# Static config for eth1 (A15)
auto eth1
iface eth1 inet static
	address 10.9.8.1
	netmask 255.255.255.128

# Static config for eth2 (A14)
auto eth2
iface eth2 inet static
	address 10.9.0.1
	netmask 255.255.248.0
```
- GUANHAO  
```
# Static config for eth0 (A8)
auto eth0
iface eth0 inet static
	address 10.8.64.2
	netmask 255.255.255.252
	gateway 10.8.64.1

# Static config for eth1 (A4)
auto eth1
iface eth1 inet static
	address 10.8.16.1
	netmask 255.255.255.252

# Static config for eth2 (A7)
auto eth2
iface eth2 inet static
	address 10.8.36.1
	netmask 255.255.252.0

# Static config for eth3 (A5)
auto eth3
iface eth3 inet static
	address 10.8.32.1
	netmask 255.255.254.0
```
- ALABASTA  
```
# Static config for eth0 (A5)
auto eth0
iface eth0 inet static
	address 10.8.32.3
	netmask 255.255.254.0
	gateway 10.8.32.1

# Static config for eth1 (A6)
auto eth1
iface eth1 inet static
	address 10.8.34.1
	netmask 255.255.255.240
```
- OIMO  
```
# Static config for eth0 (A4)
auto eth0
iface eth0 inet static
	address 10.8.16.2
	netmask 255.255.255.252
	gateway 10.8.16.1

# Static config for eth1 (A2)
auto eth1
iface eth1 inet static
	address 10.8.4.1
	netmask 255.255.255.0


# Static config for eth2 (A3)
auto eth2
iface eth2 inet static
	address 10.8.8.1
	netmask 255.255.255.252
```
- SEASTONE  
```
# Static config for eth0 (A2)
auto eth0
iface eth0 inet static
	address 10.8.4.2
	netmask 255.255.255.0
	gateway 10.8.4.1

# Static config for eth1 (A1)
auto eth1
iface eth1 inet static
	address 10.8.0.1
	netmask 255.255.252.0
```

#### Routing
Lakukan routing pada router-router dengan menjalankan command pada console masing-masing router.
- FOOSHA
```
route add -net 10.8.0.0 netmask 255.255.128.0 gw 10.8.64.2
route add -net 10.9.0.0 netmask 255.255.128.0 gw 10.9.64.2
```
- WATER7
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.9.64.1
route add -net 10.9.0.0 netmask 255.255.224.0 gw 10.9.16.1
```
- PUCCI  
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.9.16.1
```
- GUANHAO  
```
route add -net 10.8.32.0 netmask 255.255.252.0 gw 10.8.32.3
route add -net 10.8.0.0 netmask 255.255.224.0 gw 10.8.16.2
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.8.64.1
```
- ALABASTA  
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.8.32.1
```
- OIMO  
```
route add -net 10.8.0.0 netmask 255.255.248.0 gw 10.8.4.2
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.8.16.1
```
- SEASTONE  
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.8.4.1
```

