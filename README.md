# Jarkom_Modul4_Lapres_D11
Lapres praktikum jarkom modul 4 kelompok D11

Anggota Kelompok:
- M. Farras Pangestu - 05111840000134
- Rasyid Ridlo W. - 05111840000135

## TOPOLOGI CPT

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/topologi(2).PNG" >

Kita memiliki topologi jaringan seperti gambar di atas. Lalu, kita tentukan jumlah subnet yang ada di dalam topologi tersebut.

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/TopologyVLsm_pembagian%20subnet(3).PNG" >

### Kelopok kami menggunakan VLSM pada CPT, dan CIDR pada UML

### 1. VLSM (Variable Length Subnet Masking)

Inti utama dari penggunaan teknik VLSM adalah untuk mengefisienkan pembagian IP di dalam jaringan. Besar netmask disesuaikan dengan banyaknya komputer/ host yang membutuhkan alamat IP.

- Langkah 1 - Tentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan lakukan labelling netmask berdasarkan jumlah IP yang dibutuhkan.

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/jumlah%20ip%20(1).PNG" >

- Langkah 2 - Subnet besar yang dibentuk memiliki NID 192.168.0.0 dengan netmask /19. Pembagian IP berdasarkan NID dan netmask dihitung menggunakan pohon pada gambar di bawah:

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/VLSM_Tree_D11.png">


### Setting pada CPT ( Cisco Packet Tracer )

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/topologi(2).PNG">

Atur IP untuk masing-masing interface yang ada di setiap device sesuai dengan pembagian subnet pada pohon VLSM.

Pada CPT, interface dapat diatur pada menu Config > INTERFACE > “nama interface” (contoh: FastEthernet0/0). Isi alamat IP dan subnet mask dari subnet interface tersebut. Berikut contoh untuk mengatur IP pada subnet A4.

Atur IP pada interface SURABAYA yang mengarah ke PASURUAN dengan 192.168.0.5.

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/SBY.PNG">

Atur IP pada interface PASURUAN yang mengarah ke SURABAYA dengan 192.168.0.6.

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/pasuruan1.PNG">

Selanjutnya atur IP pada subnet A8. Atur IP pada interface PASURUAN yang mengarah ke client dengan 192.168.8.1

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/pasuruan2.PNG">

Atur IP pada client (nama UML nya) dengan cara :
- Masuk ke client
- Pilih tab Desktop
- Pilih IP Configuration

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/client1_cpt.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/client2_cpt.PNG">

Lakukan hal yang sama untuk mengatur alamat IP setiap interface pada device yang ada dalam topologi. 

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/setting_interfaces_cpt.PNG">

Setelah selesai, lakukan langkah selanjutnya yaitu Routing agar topologi dapat berfungsi dengan semestinya.

### Routing

Pada CPT, Routing dapat dilakukan pada menu Config > Routing > Static pada device Router. Lalu isi Static Routes seperti gambar dibawah pada SURABAYA dan tekan tombol Add

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/routing_sby_cpt.PNG">

Pada static routing juga dibutuhkan default routing agar router dapat mengirimkan paket sesuai dengan tujuan. Default routing dibutuhkan untuk router yang berada di bawah router utama (router yang terhubung internet), contohnya TULUNGAGUNG

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/routing_pasuruan_cpt.PNG">

Lakukan hal yang sama untuk mengatur routing pada setiap router

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/routing_cpt.PNG">

Keterangan :
- Network adalah Network ID yang akan dihubungkan
- Mask adalah netmask dari subnet A4
- Next Hop (disebut gateway), adalah IP yang dituju ketika ingin menuju subnet poin 1, yaitu interface pada PASURUAN yang mengarah ke SURABAYA


