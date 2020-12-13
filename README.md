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


### A. Setting pada CPT ( Cisco Packet Tracer )

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/topologi(2).PNG">

Atur IP untuk masing-masing interface yang ada di setiap device sesuai dengan pembagian subnet pada pohon VLSM.

Pada CPT, interface dapat diatur pada menu Config > INTERFACE > “nama interface” (contoh: FastEthernet0/0). Isi alamat IP dan subnet mask dari subnet interface tersebut. Berikut contoh untuk mengatur IP pada subnet A4.

Atur IP pada interface SURABAYA yang mengarah ke PASURUAN dengan *192.168.0.5*

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/SBY.PNG">

Atur IP pada interface PASURUAN yang mengarah ke SURABAYA dengan *192.168.0.6*

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/pasuruan1.PNG">

Selanjutnya atur IP pada subnet A8. Atur IP pada interface PASURUAN yang mengarah ke client dengan *192.168.8.1*

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

### B. Routing

Pada CPT, Routing dapat dilakukan pada menu Config > Routing > Static pada device Router. Lalu isi Static Routes seperti gambar dibawah pada SURABAYA dan tekan tombol Add

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/routing_sby_cpt.PNG">

Pada static routing juga dibutuhkan default routing agar router dapat mengirimkan paket sesuai dengan tujuan. Default routing dibutuhkan untuk router yang berada di bawah router utama (router yang terhubung internet), contohnya PASURUAN

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/routing_pasuruan_cpt.PNG">

Lakukan hal yang sama untuk mengatur routing pada setiap router

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/routing_cpt.PNG">

Keterangan :
- Network adalah Network ID yang akan dihubungkan
- Mask adalah netmask dari subnet A4
- Next Hop (disebut gateway), adalah IP yang dituju ketika ingin menuju subnet poin 1, yaitu interface pada PASURUAN yang mengarah ke SURABAYA

### C. Testing

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/testing_cpt.PNG">

### 2. CIDR ( Classless Inter-Domain Routing )

Menggabungkan subnet-subnet mulai dari yang paling jauh dalam topologi, penggabungannya:

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/subnet1_cidr.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/subnet2_cidr.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/subnet3_cidr.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/subnet4_cidr.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/subnet5_cidr.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/subnet5_cidr.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/subnet7_cidr.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/subnet8_cidr.PNG">

Sehingga di dapatkan berikut pohon pembagian IP berdasarkan penggabungan subnet yang telah dilakukan:

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/CIDR_Tree_D11.PNG">

**Membuat TOPOLOGI**

```
# Switch
uml_switch -unix switch1 > /dev/null < /dev/null &
uml_switch -unix switch2 > /dev/null < /dev/null &
uml_switch -unix switch3 > /dev/null < /dev/null &
uml_switch -unix switch4 > /dev/null < /dev/null &
uml_switch -unix switch5 > /dev/null < /dev/null &
uml_switch -unix switch13 > /dev/null < /dev/null &
uml_switch -unix switch15 > /dev/null < /dev/null &
uml_switch -unix switch16 > /dev/null < /dev/null &
uml_switch -unix switch17 > /dev/null < /dev/null &
uml_switch -unix switch18 > /dev/null < /dev/null &
uml_switch -unix switch19 > /dev/null < /dev/null &
uml_switch -unix switch20 > /dev/null < /dev/null &
uml_switch -unix switch21 > /dev/null < /dev/null &
uml_switch -unix switch22 > /dev/null < /dev/null &
uml_switch -unix switch25 > /dev/null < /dev/null &

# Router
xterm -T SURABAYA -e linux ubd0=SURABAYA,jarkom umid=SURABAYA eth0=tuntap,,,10.151.78.49 eth1=daemon,,,switch1 eth2=daemon,,,switch2 eth3=daemon,,,switch4 eth4=daemon,,,switch13 mem=64M &
xterm -T PASURUAN -e linux ubd0=PASURUAN,jarkom umid=PASURUAN eth0=daemon,,,switch2 eth1=daemon,,,switch3 eth2=daemon,,,switch19 mem=64M &
xterm -T PROBOLINGGO -e linux ubd0=PROBOLINGGO,jarkom umid=PROBOLINGGO eth0=daemon,,,switch3 eth1=daemon,,,switch15 eth2=daemon,,,switch16 mem=64M &
xterm -T BATU -e linux ubd0=BATU,jarkom umid=BATU eth0=daemon,,,switch4 eth1=daemon,,,switch5 eth2=daemon,,,switch21 eth3=daemon,,,switch22 mem=64M &
xterm -T MADIUN -e linux ubd0=MADIUN,jarkom umid=MADIUN eth0=daemon,,,switch22 eth1=daemon,,,switch25 mem=64M &
xterm -T KEDIRI -e linux ubd0=KEDIRI,jarkom umid=KEDIRI eth0=daemon,,,switch5 eth1=daemon,,,switch17 eth2=daemon,,,switch18 mem=64M &
xterm -T BLITAR -e linux ubd0=BLITAR,jarkom umid=BLITAR eth0=daemon,,,switch17 eth1=daemon,,,switch20 mem=64M &

# Server
xterm -T MALANG -e linux ubd0=MALANG,jarkom umid=MALANG eth0=daemon,,,switch18 mem=64M &
xterm -T MOJOKERTO -e linux ubd0=MOJOKERTO,jarkom umid=MOJOKERTO eth0=daemon,,,switch13 mem=64M &

# Klien
xterm -T SAMPANG -e linux ubd0=SAMPANG,jarkom umid=SAMPANG eth0=daemon,,,switch1 mem=64M &
xterm -T SIDOARJO -e linux ubd0=SIDOARJO,jarkom umid=SIDOARJO eth0=daemon,,,switch19 mem=64M &
xterm -T BANYUWANGI -e linux ubd0=BANYUWANGI,jarkom umid=BANYUWANGI eth0=daemon,,,switch16 mem=64M &
xterm -T JEMBER -e linux ubd0=JEMBER,jarkom umid=JEMBER eth0=daemon,,,switch16 mem=64M &
xterm -T BONDOWOSO -e linux ubd0=BONDOWOSO,jarkom umid=BONDOWOSO eth0=daemon,,,switch15 mem=64M &
xterm -T BOJONEGORO -e linux ubd0=BOJONEGORO,jarkom umid=BOJONEGORO eth0=daemon,,,switch25 mem=64M &
xterm -T JOMBANG -e linux ubd0=JOMBANG,jarkom umid=JOMBANG eth0=daemon,,,switch22 mem=64M &
xterm -T NGANJUK -e linux ubd0=NGANJUK,jarkom umid=NGANJUK eth0=daemon,,,switch21 mem=64M &
xterm -T TULUNGAGUNG -e linux ubd0=TULUNGAGUNG,jarkom umid=TULUNGAGUNG eth0=daemon,,,switch20 mem=64M &
xterm -T LUMAJANG -e linux ubd0=LUMAJANG,jarkom umid=LUMAJANG eth0=daemon,,,switch17 mem=64M &
```

**Menyetting interface pada tiap UML:**

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/surabaya.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/pasuruan.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/batu.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/kediri.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/malang.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/mojokerto.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/tulungaggung.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/jombang.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/lumajang.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/sampang.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/bojonegoro.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/sidoarjo.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/jember.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/nganjuk.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/probolinggo.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/bondowoso.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/banyuwangi.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/madiun.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/blitar.PNG">

**Kemudian atur routing pada UML Surabaya, Pasuruan, Batu, Kediri:**

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/routesby.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/routepasur.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/routebatu.PNG">

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/routekediri.PNG">

**Kemudian lakukan pengujian pada UML, berikut beberapa contohnya:**

- Sidoarjo PING ke Mojokerto

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/bukti1.PNG">

- Jember PING ke its.ac.id

<img src="https://github.com/RsydRidloo/Jarkom_Modul4_Lapres_D11/blob/main/gambar/bukti2.PNG">
