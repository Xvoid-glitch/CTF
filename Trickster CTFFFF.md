## CTF TRICKSTER 
| Kategori | webex|
| :---: | :---: |
| **Flag** | `picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_73198bd9}` |

1.**Mencari clue**
```
disini saya tidak punya resmi sama sekali, jadi saya mengandalkan judul dan deksripsi soal
dan di soal katanya dia punya web pemroses only PNG, berarti file png saja yang bisa dimasukkan di web upload gambar itu
```
2.**mencoba masuk ke file web**
```
saya mencoba masuk ke file web dengan cara http://atlas.picoctf.net:59987/(dan ini saya tambahkan robots.txt)
ini outputnya User-agent: *
Disallow: /instructions.txt
Disallow: /uploads/
```
3.**mencoba buka instruction,txt**
```
lalu saya ganti robots.txt dengan instructions.txt dan hasilnya sebuah petunjuk jelas:
Let's create a web app for PNG Images processing.
It needs to:
Allow users to upload PNG images
	look for ".png" extension in the submitted files
	make sure the magic bytes match (not sure what this is exactly but wikipedia says that the first few bytes contain 'PNG' in hexadecimal: "50 4E 47" )
after validation, store the uploaded files so that the admin can retrieve them later and do the necessary processing.
```
4.**mencoba membuat web app**
```
saya disuruh buat web app tetapi kan yang bisa di upload di web ini cuma png
saya mempunyai ide untuk membuat webshells php agar bisa mencari file nya dengan mudah
```
5.**membuat webshells**
```
saya mencari sc simple webshells di github(ak blm bisa bahasa php bg wkwk) dan mendapatkan sc nya
lalu ku taro di notepad dan seperti ini atasnya
PNG
<html>
<body>
<form met.........
```
6.**memanipulasi**
```
saya menambahkan kata PNG diatas html agar web bisa membaca awalannya itu adalah gambar, dan bisa diupload ke web
```
7.**eksekusi**
```
saya save file nya dengan nama "niggers.png.php"
dan upload ke web
```
8.**menjalankan program**
```
setelah berhasil di upload saya menjalankan program dengan mengandalkan clue 'upload'
http://atlas.picoctf.net:59987/uploads/niggers.png.php
dan saya ls -al untuk melihat seluruh file
dan saya gunakan webroot untuk melihat dir awal dari sebuah web 'ls -al /var/www/html
dan saya menemukan file aneh bernama G4ZTCOJYMJSDS.txt
saya coba buka pakai cat /var/www/html/G4ZTCOJYMJSDS.txt
```
9.**dan bom**
```
flagnya pun ketemu: picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_73198bd9}
```
10.**sewkian terimagaji**


