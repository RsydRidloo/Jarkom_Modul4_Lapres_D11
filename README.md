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


