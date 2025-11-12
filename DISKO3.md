##PicoCTF DISKO3
#step by step 
##tingkat kesusahan: medium

1.**ctf forensics**
```
mengambil soal di picoCTF dan disuruh mendownload sebuah image berformat .dd.gz
```
2.**buka file**
```
membuka file lewat terminal dengan cmd 'gunzip'
```
3.**buka folder**
```
saya akan menjalankan file dd tersebut menggunakan 'mount -o loop'
```
4.**lanjut**
```
sebelum itu buat dlu folder 'mkdir /a/b'
untuk menaruh file disko yang sudah di mount
```
5.**mencari flag**
```
dan setelah di mount akan ada folder 'log' lalu kita pindah ke file log dan banyak file berbeda jenis didalamnya
dan ada satu file bernama flag.gz, dan langsung saya gunzip dan cat
```
6.**hasil akhir**
```
picoCTF{n3v3r_z1p_2_h1d3_7e0a17da}
```

<img width="1359" height="767" alt="Screenshot 2025-11-12 125902" src="https://github.com/user-attachments/assets/30063fe4-18ad-4312-95f7-b277d041e137" />
<img width="1359" height="767" alt="Screenshot 2025-11-12 132433" src="https://github.com/user-attachments/assets/8b52d962-53ad-43c5-b4eb-fa606fc9bd19" />
<img width="1359" height="761" alt="Screenshot 2025-11-12 122548" src="https://github.com/user-attachments/assets/2b4889c5-6802-4b1b-a56f-20fab1b46cd9" />

