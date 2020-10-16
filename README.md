# Display Filter

## 1.	Sebutkan webserver yang digunakan pada "testing.mekanis.me"!
-	Wireshark filter = http.host == testing.mekanis.me
-	Server: nginx/1.14.0 (Ubuntu)

![Gbr 1](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/1.png)

![gbr 1.2](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/88.png)

- Di sini kita langsung memasukan ekspresi ``http.host == testing.mekanis.me``. Kemudian kita klik kanan pada filenya, kemudian follow tcp stream untuk mendapatkan tampilan di gambar kedua, dari situ terlihat bahwa web server yang digunakan adalah nginx/1.14.0 (Ubuntu).
 
## 2.	Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
-	Wireshark filter = Tidak menggunakan wireshark filter, langsung export dan mencari file yang diminta

![Gbr 2](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/2.png)

![Gbr 2.1](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/99.png)

- Untuk kasus ini, kita langsung melakukan export objects kemudian kita melakukan pencarian Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg dan langsung mengexport file tersebut. Hasilnya ada di gambar 2.

## 3.	Cari username dan password ketika login di "ppid.dpr.go.id"!
-	Wireshark filter expression = http.request.method == POST && http.host == ppid.dpr.go.id
-	Username = 10pemuda
-	Password = guncangdunia

![Gbr 3](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/3.png)

- Di sini kita langsung memasukkan ekspresi "http.request.method == POST && http.host == ppid.dpr.go.id". Dimana method POST adalah method yang digunakan ketika melakukan login. Dari situ sudah terlihatr ada form item username dan password.

## 4.	Temukan paket dari web-web yang menggunakan basic authentication method!
-	Wireshark filter expression = http.authbasic

![Gbr 4](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/4.png)

- Di sini kita langsung saja memasukkan ekspresi "http.authbasic" dan list dari paket dari web-web yang menggunakan basic authentication akan terlihat.

## 5.	Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
-	Wireshark filter expression = http.host == aku.pengen.pw

![Gbr 5](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/5.png)

![Gbr 6](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/6.jpg)

- Langkah pertama adalah membuka situs aku.pengen.pw. Kemudian kita mencari username dan password di wireshark dengan menggunakan ekspresi ``http.host == aku.pengen.pw``. Terlihart ada username dan password di bagian Credentials (tertera pada gambar kedua). Kemudian kita masukkan username dan passwordnya dan di websitenya kita diminta untuk memasukkan urutan konfigurasi pengkabelan T568B yang adalah Putih Oranye - Oranye - Putih Hijau - Biru - Putih Biru - Hijau - Putih Cokelat - Cokelat.
 
## 6.	Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
-	Wireshark filter expression = ftp-data.command contains Answer.zip (untuk mencari file Answer.zip)
-	Wireshark filter expression = ftp-data.command contains zipkey.txt (untuk mencari password)

![Gbr 7](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/7.png)

![Gbr 8](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/8.png)

![Gbr 9](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/9.jpg)

- Langkah pertama adalah kita mencari ftp data yang mengandung Answer.zip dengan ekspresi ``ftp-data.command contains Answer.zip``. Kemudian ternyata Open This.pdf ada passwordnya, sehingga kita kembali mencari passwordnya yang berada di zipkey.txt dengan ekspresi ``ftp-data.command contains zipkey.txt``. disitu kita akan mendapat passwordnya dan ketika kita buka, pdf tersebut berisi seperti yang dilampirkan di gambar 3.

## 7.	Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.
Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
-	Wireshark filter expression = menggunakan find hex decimal

![Gbr 10](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/10.png)

![Gbr 11](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/11.jpg)

- Di sini kita diberikan hint "Yes.pdf", sehingga kami mencoba untuk mengkonvert kata "Yes.pdf" ini menjadi hex dengan menggunakan ASCII to Hex converter online. Kemudian setelah mendapat Hex nya, kami melakukan pencarian berdasarkan Hex Value, dan kemdian kita follow tcp stream pada file terkait dan kita save raw sebagai file pdf dan didapat isi dari file tersebut adalah di gambar 2.

## 8.	Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service
-	Wireshark filter expression = ftp.request.command == RETR

![Gbr 12](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/12.jpg)

![Gbr 13](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/13.png)

- Di sini kita langsung memasukkan ekspresi ``ftp.request.command == RETR``. Terdapat 2 ftp data dari hasil ekspresi tersebut, kemudian kita cek kedua data tersebut dengan follow tcp stream, dan ditemui yang didownload dari koneksi FTP dengan Microsoft FTP Service adalah file Readme.

## 9.	Cari username dan password ketika login FTP pada localhost!
-	Wireshark filter expression = ftp.request.command == USER || ftp.request.command == PASS
-	USER = dhana
-	PASS = dhana123

![Gbr 14](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/14.png)

- Di sini kita lansgung saja memasukkan ekspresi ``ftp.request.command == USER || ftp.request.command == PASS`` untuk mencari command user dan password. Terlihat pada gambar kedua jawabannya.

## 10.	Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46"
-	Wireshark filter expression = menggunakan find hex decimal 25 50 44 46

![Gbr 15](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/15.png)

![Gbr 16](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/16.jpg)

- Di sini kita langsung saja melakukan pencarian berdasarkan Hex Value yang telah diberikan. Kemudian kita follow tcp stream dan kita save raw sebagai file pdf, dan hasilnya dapat dilihat di gambar kedua.
 
# Capture Filter
## 11.	Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
-	port 21

![gbr 17](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/17.png)

- Ekspresi ``port 21`` digunakan untuk mengambil paket yang mengandung port 21. Pengecekkan dapat dilakukan ketika menggunakan ftp.
 
## 12.	Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
-	Wireshark capture picture = src port 80

![18](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/18.png)

- Ekspresi ``src port 80`` digunakan untuk mengambil paket yang berasal dari port 80. Pengecekkan dapat dilakukan ketika membuka website HTTP.

## 13.	Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
-	Wireshark capture filter = dst port 443

![19](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/19.png)

- Ekspresi ``dst port 443`` digunakan untuk mengambil paket yang menuju ke port 443. Pengecekkan dapat dilakukan ketika membuka website HTTPS.

## 14.	Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
-	Wireshark filter expression = src host 192.168.0.100

![Gbr 20](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/20.png)

- Langkah pertama adalah kita mengecek ip kita, dengan menggunakan command ipconfig pada cmd. Setelah dapat kita masukkan ekspresinya ``src host 192.168.0.100``. Pada kasus ini ip kita adalah 192.168.0.100. 

## 15.	Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
-	dst host monta.if.its.ac.id

![gbr 21](https://github.com/riskiferdian/JARKOM_A13/blob/main/images/21.png)

- Ekspresi ``dst host monta.if.its.ac.id`` digunakan untuk mengambil paket yang menuju ke monta.if.its.ac.id. Pengecekkan dapat dilakukan dengan membuka website monta.if.its.ac.id.
