# JARKOM_Modul1_T07
Lapres Praktikum Jarkom Modul 1<br />
<br />
![kelompok](https://img.shields.io/badge/Kelompok-T07-00a69a)<br />
<br />
Anggota:<br />
- ![fikri](https://img.shields.io/badge/Fikri%20Haykal-05311840000006-blueviolet)<br />
- ![syarif](https://img.shields.io/badge/Fancista%20Syarif%20H.-05311840000027-blueviolet)<br />

## Soal
Terdapat tiga buah file *.pcapng yang mendukung soal-soal display filter, yaitu:
- File pertama untuk menjawab soal nomor 1-5 dan nomor 10.
- File kedua untuk menjawab soal nomor 6, 7, dan 9.
- File ketiga untuk menjawab soal nomor 8.

<b>A. Display Filter</b><br />
<ol>
  <li>Sebutkan webserver yang digunakan pada "testing.mekanis.me"!</li>
  <li>Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!</li>
  <li>Cari username dan password ketika login di "ppid.dpr.go.id"!</li>
  <li>Temukan paket dari web-web yang menggunakan basic authentication method!</li>
  <li>Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!</li>
  <li>Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut)!</li>
  <li>Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut!<br />
  Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"</li>
  <li>Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!</li>
  <li>Cari username dan password ketika login FTP pada localhost!</li>
  <li>Cari file .pdf di wireshark lalu download dan buka file tersebut!<br />
  clue: "25 50 44 46"</li>
</ol>

<b>B. Capture Filter</b><br />
<ol start="11">
  <li>Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!</li>
  <li>Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!</li>
  <li>Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!</li>
  <li>Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!</li>
  <li>Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!</li>
</ol>

## Jawab
<b>A. Display Filter</b><br />
<ol>
  <li>Sebutkan webserver yang digunakan pada "testing.mekanis.me"!</li>
  
  <i>Display filter : </i>```http.host == testing.mekanis.me```<br />
  <i>Penjelasan : </i>Kita bisa mencari web server dengan filter ```http.host``` dan juga dengan menyertakan alamat webnya. Kemudian kita hanya perlu mencari web servernya setelah melakukan <b>Follow TCP Stream</b> pada salah satu paket.<br />
  </li>
  
  <li>Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!</li>
  
  <i>Display filter : </i>```http```<br />
  <i>Penjelasan : </i>Kita hanya perlu memfilter dengan ```http```, setelah itu kita melakukan ```Export Object``` lalu pilih ```http```. Selanjutnya kita tinggal mencari dan menyimpan gambar yang dimaksud<br />
  </li>
  
  <li>Cari username dan password ketika login di "ppid.dpr.go.id"!</li>
  
  <i>Display filter : </i>```http.request.method == POST```<br />
  <i>Penjelasan : </i>Untuk mendapatkan data yang diinputkan, kita perlu mencari paket yang memiliki request method ```POST```.<br />
  </li>
  
  <li>Temukan paket dari web-web yang menggunakan basic authentication method!</li>
  
  <i>Display filter : </i>```http.authbasic```<br />
  <i>Penjelasan : </i>Untuk mencari web dengan basic authentication, kita perlu menggunakan ```http.authbasic```.<br />
  </li>
  
  <li>Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!</li>
  
  <i>Display filter : </i>```http```<br />
  <i>Penjelasan : </i>Kita bisa mencari web server dengan filter ```http.host``` dan juga dengan menyertakan alamat webnya. Kemudian kita hanya perlu mencari web servernya setelah melakukan <b>Follow TCP Stream</b> pada salah satu paket.<br />
  </li>
  
  <li>Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut)!</li>
  
  <i>Display filter : </i>```ftp-data```<br />
  <i>Penjelasan : </i>Gunakan ```ftp-data``` untuk mencari suatu file. Setelah itu kita perlu mencari file dengan nama ```Answer.zip```. Langkah terakhir adalah melakukan <b>Follow TCP Stream</b> dan menyimpannya sebagai <b>RAW File</b>. Jangan lupa mencari file ```zipkey.txt``` untuk menemukan password zipnya.<br />
  </li>
  
  <li>Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut!<br />
  Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"</li>
  
  <i>Display filter : </i>```ftp-data contains "Yes.pdf"```<br />
  <i>Penjelasan : </i>Sama seperti soal sebelumnya, kita perlu mencari file dengan ```ftp-data``` tetapi jangan lupa menambahkan ```contains "Yes.pdf"``` sesuai petunjuk. Lalu save as <b>RAW File</b> seperti biasa<br />
  </li>
  
  <li>Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!</li>
  
  <i>Display filter : </i>```http```<br />
  <i>Penjelasan : </i>Kita bisa mencari web server dengan filter ```http.host``` dan juga dengan menyertakan alamat webnya. Kemudian kita hanya perlu mencari web servernya setelah melakukan <b>Follow TCP Stream</b> pada salah satu paket.<br />
  </li>
  
  <li>Cari username dan password ketika login FTP pada localhost!</li>
  
  <i>Display filter : </i>```ftp.request.command == USER or ftp.request.command == PASS```<br />
  <i>Penjelasan : </i>Cari dengan menggunakan command ```USER atau PASS``` seperti di atas.<br />
  </li>
  
  <li>Cari file .pdf di wireshark lalu download dan buka file tersebut!<br />
  clue: "25 50 44 46"</li>
  
  <i>Display filter : </i>```http contains ".pdf"```<br />
  <i>Penjelasan : </i>Kita hanya perlu memfilter dengan ```contains ".pdf"```. Kita juga bisa secara manual mencari dengan byte ```25 50 44 46``` sesuai petunjuk yang ada.<br />
  </li>
</ol>

<b>B. Capture Filter</b><br />
<ol start="11">
  <li>Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!</li>
  
  Pada nomor 11 ini kita mnggunakan ```Capture Filter = port 21``` Hasilnya dapat dilihat pada screenshot dibawah ini.
  <img src="https://github.com/fikrihaykal/JARKOM_Modul1_Lapres_T07/blob/main/Screenshot/11.PNG">
  
  NB : Tidak ada paket yang ditampilkan karena port 21 adalah private server.
  
  <li>Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!</li>
  
  Pada nomor 12 ini kita mnggunakan ```Capture Filter = src port 80``` Hasilnya dapat dilihat pada screenshot dibawah ini.
  <img src="https://github.com/fikrihaykal/JARKOM_Modul1_Lapres_T07/blob/main/Screenshot/12.PNG">
  
  <li>Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!</li>
  
  Pada nomor 13 ini kita mnggunakan ```Capture Filter = dst port 443``` Hasilnya dapat dilihat pada screenshot dibawah ini.
  <img src="https://github.com/fikrihaykal/JARKOM_Modul1_Lapres_T07/blob/main/Screenshot/13.PNG">
  
  <li>Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!</li>
  
  Pada nomor 14 ini kita mnggunakan ```Capture Filter = src 192.168.1.10``` ```192.168.1.10``` adalah IP dari laptop yang digunakan.
  Untuk mengecek berapa IP kita dapat melalui ```ipconfig``` di cmd. Hasilnya dapat dilihat pada screenshot dibawah ini.
  <img src="https://github.com/fikrihaykal/JARKOM_Modul1_Lapres_T07/blob/main/Screenshot/14.PNG">
  
  <li>Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!</li>
  
  Pada nomor 15 ini kita menggunakan ```Capture Filter = dst host monta.if.its.ac.id``` Hasilnya dapat dilihat pada screenshot dibawah ini.
  <img src="https://github.com/fikrihaykal/JARKOM_Modul1_Lapres_T07/blob/main/Screenshot/15.PNG">
