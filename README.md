# 🏴 OverTheWire Bandit – Perjalanan Belajar Linux & Keamanan Siber

Repository ini berisi write-up terstruktur dari **OverTheWire Bandit Wargame**, yang mendokumentasikan proses penyelesaian setiap level menggunakan perintah Linux dan konsep dasar keamanan sistem.

---

## 📑 Daftar Isi
- [Introduction (Level 0)](#introduction-(level-0))
- [Bandit Level 0 → 1](#bandit-level-0--1)
- [Bandit Level 1 → 2](#bandit-level-1--2)
- [Bandit Level 2 → 3](#bandit-level-2--3)
- [Bandit Level 3 → 4](#bandit-level-3--4)
- [Bandit Level 4 → 5](#bandit-level-4--5)
- [Bandit Level 5 → 6](#bandit-level-5--6)
- [Bandit Level 6 → 7](#bandit-level-6--7)
- [Bandit Level 7 → 8](#bandit-level-7--8)
- [Bandit Level 8 → 9](#bandit-level-8--9)
- [Bandit Level 9 → 10](#bandit-level-9--10)
- [Bandit Level 10 → 11](#bandit-level-10--11)
- [Bandit Level 11 → 12](#bandit-level-11--12)
- [Bandit Level 12 → 13](#bandit-level-12--13)
- [Bandit Level 13 → 14](#bandit-level-13--14)
- [Bandit Level 14 → 15](#bandit-level-14--15)
- [Bandit Level 15 → 16](#bandit-level-15--16)
- [Bandit Level 16 → 17](#bandit-level-16--17)
- [Bandit Level 17 → 18](#bandit-level-17--18)
- [Bandit Level 18 → 19](#bandit-level-18--19)
- [Bandit Level 19 → 20](#bandit-level-19--20)
- [Bandit Level 20 → 21](#bandit-level-20--21)

---
## Introduction (Level 0)
### 📌 Deskripsi Level
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

### 🧠 Step & Explanation
Pada level 0 ini kita hanya perlu masuk  ke Lab Virtual yang sudah disediakan OverTheWire menggunakan SSH melalui port 2220 melalui terminal Mesin kita. Saya disini memakai Virtual Box dengan ISO Kali Linux. Sehingga saya menjalankan nya di terminal Kali Linux virtual. 
#_Command_
```bash
ssh -p 2220 bandit0@bandit.labs.overthewire.org

```
OverTheWire pada deskripsi Level sudah memberitahukan username dan password awal. Yaitu bandit0.

Jadi, ketika command diatas sudah dieksekusi, jika ada pertanyaan konfirmasi, ketik saja **yes**. Lalu ketika diminta password, Masukkan password **bandit0**. 

**Cara bermain** ini akan terus dilakukan sampai dengan Level-Level berikutnya. Dimana tujuan kita disini adalah mencari password yang ada di setiap Level untuk dapat mengakses Level yang lebih tinggi. 

## Bandit Level 0 → 1
### 📌 Deskripsi Level
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

### 🧠 Step & Explanation
<img width="624" height="43" alt="image" src="https://github.com/user-attachments/assets/390375cf-c936-46ec-b8f3-670b2a185dd5" />
Seperti yang dijelaskan pada deskripsi, Bahwa password ada pada file dengan nama **readme** di **home directory** .

Maka dari itu kita cek dengan perintah:
```bash
ls

```
**ls** adalah singkatan dari **list** digunakan untuk menampilkan isi direktori saat ini.

Seperti terlihat pada gambar, pada output terlihat ada file bernama **readme**. 
Sehingga selanjutnya kita hanya perlu menjalankan perintah yang dapat menampilkan isi file teks. 

<img width="624" height="159" alt="image" src="https://github.com/user-attachments/assets/40ff9692-9849-4b3c-80e9-5b751f267b00" />

```bash
cat readme

```
**cat** digunakan untuk menampilkan isi file teks ke terminal.
Karena file tidak terenkrispi, maka kita dapat langsung membaca isi file. 

Dan pada output, terlihat ada password yang muncul. Password ini lah yang akan kita gunakan untuk login ke user bandit1 untuk dapat melanjutkan permainan. 

```bash
exit
ssh -p 2220 bandit1@bandit.labs.overthewire.org

```
Ini untuk melanjutkan ke level 1. 

## Bandit Level 1 → 2
### 📌 Deskripsi Level
The password for the next level is stored in a file called - located in the home directory

### 🧠 Step & Explanation
Pada deskripsi soal dijelaskan bahwa password di simpan pada file **-** pada home directory.
<img width="624" height="43" alt="image" src="https://github.com/user-attachments/assets/2d59c7ee-d20c-4bb8-974a-1ba8a82d5fd1" />
Kita cek dengan perintah ls. Dan ternyata memang ada. 

Dan nyatanya teman-teman, pada banyak command linux, **-** dianggap sebagai stdin/stdout. Jadi kita tidak dapat langsung memakai perintah **cat -** Karena Linux tidak akan membaca isi file. 

<img width="605" height="88" alt="image" src="https://github.com/user-attachments/assets/955f45d2-fc8a-40f1-8156-c340c93d7a0d" />

Maka kita gunakan cara seperti pada dokumentasi diatas. Kita perlu menambahkan path, agar Terminal dapat membaca ini sebagai file, bukan stdin. 
Dan voila, kita  berhasil mendapat password nya. 

<img width="450" height="50" alt="image" src="https://github.com/user-attachments/assets/61d70129-33e1-4cdc-afec-6aa216e75dda" />
Bisa juga dengan  cara diatas, yaitu memberi path secara eksplisit jika memang perlu. 

Setelah itu gunakan password untuk ke level selanjutnya. 
```bash
exit

```

## Bandit Level 2 → 3
### 📌 Deskripsi Level
The password for the next level is stored in a file called --spaces in this filename-- located in the home directory

### 🧠 Langkah Pengerjaan
Pada deskripsi dijelaskan bahwa password ada pada file dengan nama --spaces in this filename-- . Ini adalah jenis nama file yang unik karena nama file mengandung spasi. Yang dimana jika dijalankan langsung dengan perintah **cat** maka linux akan menganggap sebagai 4 argumen file berbeda (spaces, in, this,filename).

Maka kita lakukan cara berikut:
<img width="624" height="58" alt="image" src="https://github.com/user-attachments/assets/4e444ec5-ee29-41c5-a59f-4cedd5de20d2" />
Seperti biasa, Lakukan pengecekan file dengan **ls**.

<img width="580" height="52" alt="image" src="https://github.com/user-attachments/assets/f3dbeb73-e25c-4b7d-a0dd-c72766b941a4" />
Agar file dapat dibaca sebagai satu-kesatuan maka kita gunakna tanda ' ' . Seperti pada dokumentasi diatas. Dan akhirnya kita mendapat password untuk Level 3. 

```bash
exit

```

## Bandit Level 3 → 4
### 📌 Deskripsi Level
The password for the next level is stored in a hidden file in the inhere directory.

### 🧠 Langkah Pengerjaan
<img width="295" height="50" alt="image" src="https://github.com/user-attachments/assets/3baea242-d876-46c6-8714-ba607c3619f6" />

<img width="624" height="107" alt="image" src="https://github.com/user-attachments/assets/b90ae0e7-3304-4fbd-a47d-5dcaa325bcd7" />

<img width="624" height="92" alt="image" src="https://github.com/user-attachments/assets/4f6b2783-a88d-4658-aef0-774ac1382c60" />

<img width="562" height="137" alt="image" src="https://github.com/user-attachments/assets/47c589fa-a185-4b3a-809f-01d34113c628" />

```bash
# perintah yang digunakan

```
## Bandit Level 4 → 5

### 📌 Deskripsi Level
<!-- Deskripsi singkat tantangan -->

### 🧠 Langkah Pengerjaan
<img width="501" height="236" alt="image" src="https://github.com/user-attachments/assets/3c51f58a-2af3-4bd2-823a-2200b65d6557" />

<img width="442" height="46" alt="image" src="https://github.com/user-attachments/assets/1ed30cea-0521-4265-9836-bb83d959b170" />

<img width="624" height="155" alt="image" src="https://github.com/user-attachments/assets/89d064b5-f382-4896-9849-6c59c3cb9124" />

```bash
# perintah yang digunakan

```
## Bandit Level 5 → 6


### 📌 Deskripsi Level
<!-- Deskripsi singkat tantangan -->

### 🧠 Langkah Pengerjaan
<img width="624" height="39" alt="image" src="https://github.com/user-attachments/assets/89e4717d-4b87-4532-9cf5-a81709abcf76" />

<img width="624" height="103" alt="image" src="https://github.com/user-attachments/assets/617a9057-b9eb-43eb-a0ad-c8dcd9456653" />

<img width="624" height="148" alt="image" src="https://github.com/user-attachments/assets/6fe47a6a-d8cb-4c43-bdcf-3861ae1fec43" />

```bash
# perintah yang digunakan

```
## Bandit Level 6 → 7  
### 📌 Deskripsi Level
<!-- Deskripsi singkat tantangan -->

### 🧠 Langkah Pengerjaan
<img width="624" height="36" alt="image" src="https://github.com/user-attachments/assets/b90c6a96-3349-4027-b0b1-aafe519a73ff" />

<img width="624" height="74" alt="image" src="https://github.com/user-attachments/assets/75b1d323-fbfc-4692-9ffd-ab0a69d29fb9" />

<img width="624" height="378" alt="image" src="https://github.com/user-attachments/assets/10fc6590-7118-4c8d-8afe-b1b05f3c725c" />

```bash
# perintah yang digunakan

```
## Bandit Level 7 → 8

### 📌 Deskripsi Level
<!-- Deskripsi singkat tantangan -->

### 🧠 Langkah Pengerjaan
<img width="624" height="78" alt="image" src="https://github.com/user-attachments/assets/b6599779-9563-4b26-838f-760d489db980" />

<img width="624" height="417" alt="image" src="https://github.com/user-attachments/assets/ec72ba3f-db6a-48f2-ab8c-077de9448844" />

```bash
# perintah yang digunakan

```
## Bandit Level 8 → 9


### 📌 Deskripsi Level
<!-- Deskripsi singkat tantangan -->

### 🧠 Langkah Pengerjaan
<img width="508" height="52" alt="image" src="https://github.com/user-attachments/assets/767d52de-745d-495a-be6d-01990851c5c4" />

<img width="624" height="508" alt="image" src="https://github.com/user-attachments/assets/f44e5196-a709-44c7-9580-b9c53eb31983" />

```bash
# perintah yang digunakan

```
## Bandit Level 9 → 10

### 📌 Deskripsi Level
<!-- Deskripsi singkat tantangan -->

### 🧠 Langkah Pengerjaan
<img width="624" height="202" alt="image" src="https://github.com/user-attachments/assets/65b834a3-5c23-4be6-a977-b3631f3c38d8" />

<img width="624" height="76" alt="image" src="https://github.com/user-attachments/assets/0af8071c-57f8-4da5-9115-980329d7ce9f" />

```bash
# perintah yang digunakan

```
## Bandit Level 10 → 11
### 📌 Deskripsi Level
The password for the next level is stored in the file data.txt, which contains base64 encoded data.

### 🧠 Langkah Pengerjaan
Base64 encoded sendiri adalah bentuk untuk mengubah teks biasa menjadi bentuk kode acak biner.
<https://en.wikipedia.org/wiki/Base64>
Yang berarti data.txt sebenarnya adalah teks biasa yang sudah di enskripsi ke bentuk base64. Biasanya base64 sering ditandai dengan akhirannya ===. 

<img width="624" height="63" alt="image" src="https://github.com/user-attachments/assets/73719efc-a69a-4a73-b07e-b1ed70e7ad63" />
Terlihat pada command-command yang saya jalankan diatas, terlihat bahwa memang data.txt adala base64.

<img width="621" height="92" alt="image" src="https://github.com/user-attachments/assets/05b7ea88-739d-490d-9d41-34980c4e3e5a" />
Agar isi file data.txt berubah kembali ke bentuk kode aslinya (sebelum encoded) maka kita lakukan decoded. Caranya seperti pada dokumentasi diatas, yaitu perintah:
```bash
cat data.txt | base64 -d
```
cat data.txt >> mengambil isi file
base64 -d  >> Perintah untuk men-decoded base64. 
Sehingga disini kita melakuka 2 Perintah sekaligus. 

Dan voila, seperti pada output dokumentasi diatas, kita berhasil melihat bentuk asli dari teks data.txt

## Bandit Level 11 → 12
### 📌 Deskripsi Level
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

### 🧠 Langkah Pengerjaan
<img width="975" height="411" alt="image" src="https://github.com/user-attachments/assets/ded1ad04-dcd1-4e54-abea-c3a1af1c15a8" />
Kita cek keberadaan file nya dengan ls dan cek isi file nya terlebih dahulu dengan perintah cat. 
Dan ternyata memang file ini adalah file CipherText bentuk ROT13. Dimana huruf di geser 13 posisi dari posisi aslinya. Ini guna agar isi teks tidak dapat dibaca secara langsung. 
<https://en.wikipedia.org/wiki/ROT13>

**Penyelesaian**
Untuk cara mengubah nya ke bentuk asli, kita dapat melakukan 2 cara, dapat dengan tools online yang sudah ada, Maupun memakai command di terminal linux

# Memakai tools
<img width="624" height="52" alt="image" src="https://github.com/user-attachments/assets/b6f6e1bc-6dbe-4712-87ad-41b996cd9175" />
Disini saya memakai website cryptii yang dapat mendecode ROT13. caranya, saya cukup hanya memasukkan text data.txt tadi ke bagian cipher text. Dan pada plaintext, terlihat bentuk aslinya. 
Website : <https://cryptii.com/pipes/rot13-decoder>

<img width="624" height="126" alt="image" src="https://github.com/user-attachments/assets/be91af3e-ffe9-4906-ad32-caa08fe6f2f6" />
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
- tr = translate karakter
- A-Za-z → N-ZA-Mn-za-m = rumus ROT13
- Pipeline (|) mengalirkan output cat ke tr

Dan akhirnya kita mendapatkan password untuk level berikut nya. 

## Bandit Level 12 → 13
### 📌 Deskripsi Level
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

### 🧠 Langkah Pengerjaan
Pada Level kali ini, password di simpan pada data.txt . Dimana pada data.txt ini kita disajikan file dengan hex encoded. Dan setelah di decode, file ini punya berlapis-lapis kompresi. Sehingga butuh beberapa perintah untuk menjalankan nya. 

<img width="624" height="193" alt="image" src="https://github.com/user-attachments/assets/f52edd7c-1d7b-46c3-b0e8-8aeaac35cc13" />
Kita mulai dengan membuat folder tempat kita akan menyimpan file yang nanti akan kita bolak balik decode. Gunakan:
```bash
mkdir /tmp/(namafile)
cd /tmp/(namafile)
```
mkdir = make directory, yaitu membuat directory. 
cd = change directory, yaitu berpindah directory.

kita gunakan /tmp karena proses ekstraksi akan menghasilkan banyak file sementara. 

<img width="621" height="125" alt="image" src="https://github.com/user-attachments/assets/14995949-184b-4d9d-9eca-ffecf1f3cc16" />
<img width="664" height="70" alt="image" src="https://github.com/user-attachments/assets/207108b9-9f64-4daa-9ca8-b4b463863865" />

Setelah masuk ke dalam directory nya, Lnajut kita copy file dengan cp. Dan rename dengan move/mv.

```bash
cp ~/data.txt
mv data.txt data
xxd -r data > x
ls
```
fungsi **xxd -r **mengubah hex dump kembali ke binary. Lalu File hasil decode disimpan sebagai **x**(Ini nama file bebas aja). 

<img width="624" height="443" alt="image" src="https://github.com/user-attachments/assets/7031665c-b24f-4731-bf03-dec6e7765a31" />
Selanjutnya kita identfikasi nama file dengan perintah **file**. seperti diatas.

Jika jenis file **gzip** :
```bash
mv x x.gz
gunzip x.gz

```

Jika jenis file **bzip2** :
```bash
mv x x.gz
gunzip x.gz

```
Jika jenis file **tar archive** :
```bash
tar -xf x
```

kita ulangi pola nya. Sampai kita menemukan file .bin

<img width="624" height="40" alt="image" src="https://github.com/user-attachments/assets/41c5088f-ee58-4c99-af27-b3f68aa43a99" />
Setelah menemukan file .bin, Kita lakukan ekstrak seperti sebelumnya.
Agar tidak pusing dan menumpuk, disini saya juga menghapus file yang tidak perlu dengan **rm**.

Kita lakukan sampai menemukan file dengan tipe **ASCII text**

<img width="556" height="59" alt="image" src="https://github.com/user-attachments/assets/bb109f33-bc38-423d-801e-f08dfed05735" />

Setelah menemukan file tersebut, kita cukup gunakan perintah cat seperti biasa. Dan, voila. Kita mendapatkan password nya setelah ngulang-ngulang ekstrak😪. 


## Bandit Level 13 → 14
### 📌 Deskripsi Level
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to use the key for this level.

### 🧠 Langkah Pengerjaan
Pada Level kali ini, dijelaskan bahwa kita tidak mendapat password ke level selanjutnya. Tapi kita mendapat private key untuk dapat "mem-bypass" ke level selanjutnta menggunakan SSH. 
Caranya sebagai berikut:
<img width="472" height="49" alt="image" src="https://github.com/user-attachments/assets/c04db17a-a52c-4570-874c-02e5be3f65c5" />

```bash
cat sshkey.private
(salin private key)
exit
```
Kita salin dulu isi dari sshkey.private, salin dari bagian begin sampai end.
```
----BEGIN RSA PRIVATE KEY-----

---END RSA PRIVATE KEY-------
```

lalu 
```bash
exit
```
<img width="975" height="836" alt="image" src="https://github.com/user-attachments/assets/e2c54dd6-2986-49f0-8dec-cca5c2e5365a" />

Di terminal Kali Linux:
```bash
nano bandit14.key
(Paste private key yang tadi disalin, CTRL + S & CTRL + X)
chmod 600 bandit14.key
```
<img width="624" height="309" alt="image" src="https://github.com/user-attachments/assets/34c25063-0e64-4aa5-823d-65e74291ca42" />
Ini mengubah permission karena private key harus ketat. 

Setelah itu jalankan perintah:
```bash
ssh -i bandit14.key -p 2220 bandit14@bandit.labs.overthewire.org
```
# Output:
<img width="624" height="40" alt="image" src="https://github.com/user-attachments/assets/6641ab20-9a57-4f7e-af0e-8b90b1dce266" />
Dan uhuy, kita berhasil lanjut langsung ke level 14.

## Bandit Level 14 → 15
### 📌 Deskripsi Level
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

### 🧠 Langkah Pengerjaan
Pada Level kali ini, Password disimpan di user bandit15. Sehingga kita pelru untuk mengirim password bandit14 yang benar pada port 30000 di localhost.

<img width="624" height="162" alt="image" src="https://github.com/user-attachments/assets/0b2dcc29-29b4-4819-9ee6-4a42897fa847" />
Pertama, kita ambil dulu password user bandit14. Dengan perintah seperti diatas. 

<img width="624" height="106" alt="image" src="https://github.com/user-attachments/assets/29011fab-8f37-4a52-8398-2cf7e001aca4" />
Nah, untuk mengirimkan nya, kita pakai nc (netcat).
nc digunakan untuk Membuka koneksi TCP sederhana

```bash
nc localhost 30000
(paste password bandit14 >> enter)

```
Jika benar, Port 30000 akan merespon dengan memberi output seperti pada dokumentasi. 

## Bandit Level 15 → 16
### 📌 Deskripsi Level
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

### 🧠 Langkah Pengerjaan
Hampir sama seperti pada Level 15 tadi, Tapi pada level ini Koneksi yang terhubung wajib memakai SSL/TLS.

<img width="528" height="186" alt="image" src="https://github.com/user-attachments/assets/38b687ff-3e19-4216-9521-5b9d5475ec6d" />
kita lihat diatas, untu ssl kita tidak dapat menggunakan perintah nc. 

<img width="624" height="534" alt="image" src="https://github.com/user-attachments/assets/4a8f9b8e-254c-42b6-a24f-a0b9c8456d80" />
Perintah yang benar adalah ncat. karena ini dianggap lebih modern dan aman untuk ssl. 

Jalankan :
```bash
ncat --ssl localhost 30001
(paste password bandit15 >> enter)

```
Dan voila! Jika benar service pada port 30001 akan merespons dengan memberi password untuk level selanjutnya. 

## Bandit Level 16 → 17

### 📌 Deskripsi Level
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

### 🧠 Langkah Pengerjaan
Pada level ini, Kita perlu mengetahui mana saja  port yang terbuka dan yang punya protokol SSL/TLS atau tidak pada rentang port antara 31000 - 32000. Akan sangat melelahkan jika kita scanning satu-satu. Oleh karena itu, kita gunakan nmap agar lebih mudah dan efektif. 

<img width="538" height="52" alt="image" src="https://github.com/user-attachments/assets/1649629b-1368-4040-a939-5537a95edef4" />
Jalankan perintah: 
```bash
nmap -sV -T4 -p 31000-32000 localhost
```
Fungsi dan Arti setiap parameter: 
-sV =	Service & version detection
-T4	= Mempercepat scanning (agresif tapi aman)
-p = 31000-32000	Scan port 31000–32000
localhost	= Target scan (server Bandit sendiri)

Dan terlihat pada output bahwa port target kita adalah 31790. 
Kenapa? Karena terlihat pada nmap fingerprint : Wrong! Please enter the correct current password.
Pada bagian **SF-Port31790**

<img width="624" height="515" alt="image" src="https://github.com/user-attachments/assets/fa7cb246-bf70-49ab-b0ed-ed7894578cbb" />
Lalu kita ambil dulu password bandit16 dan salin. 

<img width="624" height="356" alt="image" src="https://github.com/user-attachments/assets/71d74f1b-1e30-4ea5-a077-af46f2547d92" />
Karena kita sudah tau port target nya, Langsung saja kita eksekusi kodenya. 

```bash
ncat --ssl localhost 31790
(Paste password bandit16 dan enter)

```
Dan kita mendapat Private key untuk lanjut ke level berikutnya. 

<img width="838" height="77" alt="image" src="https://github.com/user-attachments/assets/b14c4534-53a6-47fa-b5a9-cf8b9879c74f" />
Kita cukup login dan gunakan cara yang sama seperti pada level bandit14. 

## Bandit Level 17 → 18
### 📌 Deskripsi Level
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new
NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

### 🧠 Langkah Pengerjaan
<img width="364" height="45" alt="image" src="https://github.com/user-attachments/assets/a8a518e8-e190-4a71-96f0-6b5db195475f" />

<img width="314" height="192" alt="image" src="https://github.com/user-attachments/assets/d06620f6-9401-4aac-ad17-61eb79fdba53" />

<img width="296" height="188" alt="image" src="https://github.com/user-attachments/assets/5cacdaac-a8f6-4056-aaa6-aa13f9cec2bf" />

<img width="624" height="96" alt="image" src="https://github.com/user-attachments/assets/25785832-001d-4bc9-b2dc-beb2ae702dcb" />

```bash
# perintah yang digunakan

```

## Bandit Level 18 → 19
### 📌 Deskripsi Level
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

### 🧠 Langkah Pengerjaan
<img width="624" height="316" alt="image" src="https://github.com/user-attachments/assets/3afdd175-7d74-4971-bc0c-f10d7e53bcea" />

<img width="624" height="287" alt="image" src="https://github.com/user-attachments/assets/6a3cc6e0-3f15-4df3-99ea-905fc9b81c14" />

```bash
# perintah yang digunakan

```
## Bandit Level 19 → 20

### 📌 Deskripsi Level
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

### 🧠 Langkah Pengerjaan
<img width="624" height="84" alt="image" src="https://github.com/user-attachments/assets/297af0a2-249e-486d-8596-4c6f6df4813f" />

 <img width="624" height="133" alt="image" src="https://github.com/user-attachments/assets/768c5ba1-b78e-4a91-87ed-fac6f7096d8b" />

```bash
# perintah yang digunakan

```

## Bandit Level 20 - 21

### 📌 Deskripsi Level
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
NOTE: Try connecting to your own network daemon to see if it works as you think

### 🧠 Langkah Pengerjaan
Terminal 1
<img width="624" height="209" alt="image" src="https://github.com/user-attachments/assets/982c059b-0f0f-4d95-8257-9899597f8c41" />

Terminal 2
<img width="550" height="233" alt="image" src="https://github.com/user-attachments/assets/73974ce5-ba61-4fa8-865e-bfb4b9f4f02e" />

Terminal 1
<img width="609" height="188" alt="image" src="https://github.com/user-attachments/assets/70b51c91-6c2a-47c7-821d-c0804048bf89" />

--
<img width="624" height="147" alt="image" src="https://github.com/user-attachments/assets/ff4608ae-05a1-4ea9-b8ca-17b1c3e749ec" />

```bash
# perintah yang digunakan

```
