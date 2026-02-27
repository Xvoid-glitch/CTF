# PicoCTF - Header Injection Challenge

**Category:** forensic 
**Challenge:** PicoCtf Corupt file


---


## **Deskripsi**
diberikan file rusak yang harus kita buka isi dalam nya dan clue nya adalah disuruh cek header file, jpeg, dan cek hex editor bisa mengedit byte file

---

## **Tools**
- Firefox Browser
- hex Editor Online
- Terminal Kali 

---

## **Langkah-Langkah**
saya mendownload file rusak tersebut
langsung saya cek header file pakai hex editor online 
lalu saya cari info di google hex dari jpeg, karena cluenya menyinggung jpg
dan ternyata ada yg salah di header file yang tidak sesuai dengan hex jpg 
saya ubah perbaiki header file 
dan saya buka di terminal lalu saya cek type file ini pake cmd: file file_corrupt
output nya mengatakan ini file jpg
saya uubah file nya pakai mv menjadi jpg 
dan saya buka file nya dan saya menemukan flag nya 
---
berikut dokumentasinya

<img width="1920" height="1080" alt="Screenshot_2026-02-27_17_02_26" src="https://github.com/user-attachments/assets/868e471d-a6ac-4918-8b50-39ef30fd4f97" />
<img width="1920" height="1080" alt="Screenshot_2026-02-27_17_02_26" src="https://github.com/user-attachments/assets/868e471d-a6ac-4918-8b50-39ef30fd4f97" />
