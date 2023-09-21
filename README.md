# Jarkom-Modul-1-B08-

# Jarkom-Modul-1-B08-2023

|Nama|NRP|Kelas|
|:--:|:-:|:---:|
|Adrian Karuna Soetikno|5025211019|Jarkom B|
|Thariq Agfi Hermawan|5025211215|Jarkom B|
------------------------------------------


## Soal 1
### User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

### a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 

Pertama dicari terlebih dahulu aktivitas mengunggah sebuah file, biasanya ditandai dengan adanya STOR, untuk mempermudah kita dapat menggunakan filter ftp dan ftp-data untuk meng-specify dan filter semua protokol FTP yang memberikan responses/request contohnya STOR. Kemudian bisa dilihat dari packet detail transmission control protocol

![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/24c8d25a-cbc3-4c56-a7b2-f9605b0602c2)

### b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
cara melihatnya kurang lebih sama seperti pada nomor a, dibawahnya sequence number

![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/1ea27e3b-8f93-4cb7-bdd1-e9544d16d89e)

### c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
untuk mengecek response nya, kita dapat follow aktivitas STOR tersebut dan melihat aktivitas apa yang menjadi response nya

![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/a81ba0f9-5863-4e65-bac0-6d49a9533c3a)

### d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/05bb5cdc-637b-4dd7-8d33-d293e0203414)

- ketika sudah didapatkan semua, maka dimasukkan kedalam bash dan didapatkan hasil 
![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/fb1b9ae8-00fa-469d-85f7-0fb4bc7d41a6)


### Soal 2
### Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

### Soal 3
### Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

### a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
untuk menghitung paket yang didapatkan pada address dan port tersebut kita dapat menggunakan filter : 
```
(ip.src == 239.255.255.250 && udp.srcport == 3702) || (ip.dst == 239.255.255.250 && udp.dstport == 3702)
```
![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/11e79153-601f-4636-bb33-628f52dad983)

dapat dihitung bahwa didapatkan 21 paket

### b. Protokol layer transport apa yang digunakan?

![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/11e79153-601f-4636-bb33-628f52dad983)

dapat dilihat semua protokol yang digunakan semuanya adalah UDP

- kemudian di inputkan pada bash
![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/6e9e1c94-0658-4576-b079-1bb5d143d429)


### Soal 4
### Berapa nilai checksum yang didapat dari header pada paket nomor 130?

pada soal ini cukup straightforward, dimana kita hanya perlu mencari paket yang memiliki nomor 130, kemudian kita liat detailsnya pada User Datagram Protocol, dan kita bisa lihat row Checksum yang menunjukkan : 0x18e5

![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/3681593a-e667-4750-8502-3d9315846841)

- dan apabila dimasukkan kedalam bash akan mendapatkan hasil benar :
![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/ff482092-3dc7-49e9-aa26-72cad01fc8f9)



### Soal 5
### Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
Pada soal ini kita harus mencari ```nc``` yang tersembunyi pada file zip yang dikunci, passwordnya tersembunyi pada file pcap. Setelah ditelusuri pada file ini, terdapat paket misterius yang berbentuk email (text plain). 

![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/3cda048a-cba8-452c-9e9a-ee521486e64c)

kemudian apabila di follow/di analisa detailnya didapatkan pesan berikut : 

![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/f334d870-bdd0-4da1-b0c7-b2a3bbf6d26f)

yang apabila kita decrypt maka didapatkan password untuk file zip: 

![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/076fcef2-1549-4c2b-8c90-f01579d73835)

yang dapat digunakan untuk membuka file zip, dan didapatkan nc 

![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/3508834d-17d8-458d-acb3-bfed812a305a)

### a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?

paket yang di capture dapat dilihat adalah 60
![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/e2f3c1a8-c0bc-420e-84a6-c7af4ce1531c)


### b. Port berapakah pada server yang digunakan untuk service SMTP?

port yang digunakan untuk SMTP adalah 25


### c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

dari hasil capture paket, dapat dilihat bahwa ip public nya adalah 74.53.140.153

![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/b632d81d-c145-4acd-9ffd-77e05db5de10)

kemudian didapatkan tokennya

![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/a92cc95c-d9d9-4f7f-a448-8642e9dc1e5e)


### Soal 6
### Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

### Soal 7
### Berapa jumlah packet yang menuju IP 184.87.193.88?

### Soal 8
### Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

### Soal 9
### Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

untuk mendapatkan filter yang mengambil alamat 10.51.40.1 tetapi tidak menuju alamat 10.39.55.34! dapat digunakan query :
```
ip.src == 10.51.40.1 && ip.dst != 10.39.55.34
```

dan apabila diinput pada bash maka didapatkan flagnya.
![image](https://github.com/Adrian0429/Jarkom-Modul-1-B08-2023/assets/86884506/d7ec3355-9828-4ea9-b057-50c075c7702f)


### Soal 10
### Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
