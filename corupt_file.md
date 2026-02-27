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

```
saya mendownload file rusak tersebut
```
```
langsung saya cek header file pakai hex editor online 
```
```
lalu saya cari info di google hex dari jpeg, karena cluenya menyinggung jpg
```
```
dan ternyata ada yg salah di header file yang tidak sesuai dengan hex jpg 
```
```
saya ubah perbaiki header file 
```
```
dan saya buka di terminal lalu saya cek type file ini pake cmd: file file_corrupt
```
```
output nya mengatakan ini file jpg
```
```
saya uubah file nya pakai mv menjadi jpg 
```
```
dan saya buka file nya dan saya menemukan flag nya

```
---
## **berikut dokumentasinya**




<img width="1920" height="1080" alt="Screenshot_2026-02-27_18_00_25" src="https://github.com/user-attachments/assets/975e9d40-3a80-4950-af6c-836800504638" />




<img width="1920" height="1080" alt="Screenshot_2026-02-27_17_57_50" src="https://github.com/user-attachments/assets/fb780c33-b7c1-421b-9ead-16b8c5ff6914" />

<img width="1920" height="1080" alt="Screenshot_2026-02-27_17_55_20" src="https://github.com/user-attachments/assets/100d64a2-afb9-464a-86e5-c0f2e3495c11" />


<img width="1920" height="1080" alt="Screenshot_2026-02-27_17_55_04" src="https://github.com/user-attachments/assets/4e6b4646-9179-44b5-a495-399a1c74bc33" />

<img width="1920" height="1080" alt="Screenshot_2026-02-27_17_54_20" src="https://github.com/user-attachments/assets/f8ab391d-43f9-4aa5-8ea4-5bb67b51bfa5" />



<img width="1920" height="1080" alt="Screenshot_2026-02-27_18_16_34" src="https://github.com/user-attachments/assets/fe2a4608-16d0-406b-b1f9-ae3dbe0ed3e7" />



