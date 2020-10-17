# Jarkom_Modul1_Lapres_A14
Laporan Resmi Modul 1 Praktikum Jaringan Komputer
#
- Rofita Siti Musdalifah    (05111840000034)
- Vachri Attala Putra       (05111840000043)
#
## Display Filter
1. [Soal1](#soal1)
2. [Soal2](#soal2)
3. [Soal3](#soal3)
4. [Soal4](#soal4)
5. [Soal5](#soal5)
6. [Soal6](#soal6)
7. [Soal7](#soal7)


### Soal1
1.	Sebutkan webserver yang digunakan pada "testing.mekanis.me"!
    -	Masukkan command ```http.host == testing.mekanis.me``` pada Display Fitur 
    -	Pada bagian Hypertext Transfer Protocol, terlihat bahwa webserver yang digunakan adalah **nginx/1/14/0 (Ubuntu)**, dengan destination port 80 (HTTP)

![image](1.jpeg)
#

### Soal2
2.	Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
    -	Pilih File -> Export Objects -> HTTP
    -	Kemudian pada text filter dituliskan nama file **Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg**.
    -	Pilih file tersebut kemudian Save pada direktori yang diinginkan.

![image](2.jpeg)
#

### Soal3
3.	Cari username dan password ketika login di "ppid.dpr.go.id"!
-	Menggunakan command filter: ```http.host == ppid.dpr.go.id && http.request.method == POST && http.request.uri contains login ```
-   Pada bagian HTML Form URL Encoded: application/x-www-form-urlencoded, bisa dilihat bahwa Username dan Passwordny adalah
    -	Username: **10pemuda**
    -	Password: **guncangdunia**

![image](3.jpeg)
#

### Soal4
4.	Temukan paket dari web-web yang menggunakan basic authentication method!
-	Masukkan command ```http.authbasic``` pada Display Filter

![image](4.jpeg)
#

### Soal5
5.	Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
- Masukkan command ```http.host == aku.pengen.pw && http.authbasic``` pada Display Filter

![image](5.jpeg)

- Pada salah satu paket, lihat pada bagian (Hypertext Transfer Protocol -> Authorization ->  Credential, username dan password:
    - Username: **kakakgamtenk**
    - Password: **hartatahtabermuda**

![image](5.jpeg)
#

### Soal6
6.	Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
- Masukkan command ```ftp-data.command contains Answer.zip``` pada Display Filter untuk menemukan file zip Answer.zip

![image](6.jpg)

- untuk mendapatkan file zip Answer.zip klik kanan pada paket lalu pilih Follow -> TCP Stream, kemudian pilih tipe ```Raw``` kemudian Save As zip file
- Dikarenakan file zip tersebut bertipe password protected, maka kita harus mencari password itu yang tersimpan pada file **zipkey.txt**

- untuk mendapatkan passwordnya, masukkan command ```ftp-data.command contains zipkey.txt``` pada Display Filter
- kemudian klik kanan pada paket lalu pilih Follow -> TCP Stream, kemudian pilih tipe ```Raw``` kemudian Save As txt file

![image](6pass.jpg)

- didapat password hey997400323051 kemudian gunakan untuk membuka file "Open This.pdf" di Answer.zip

![image](6kocheng.jpg)
#

### Soal7
7.	Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.
Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
-	masukkan command ```ftp-data contains Yes.pdf``` pada Display Filter untuk mencari file pdf yang diinginkan.

![image](7filter.jpg)

-	Kemudian klik kanan pada paket lalu pilih Follow -> TCP Stream, kemudian pilih tipe ```Raw``` kemudian Save As zip file
-	Kemudian dapat di-unzip dan muncul file **Yes.pdf**

![image](7.jpg)
#

