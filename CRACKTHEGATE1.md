# PicoCTF - Header Injection Challenge

**Category:** Web Exploitation  
**Challenge:** PicoCtf Crack The Gate 1 
**URL:** http://amiable-citadel.picoctf.net:54084/

---


## **Deskripsi**
Ctf ini dari picoctf yang memberikan halaman login dan saya dikasih email: ctf-player@picoctf.org dan cluenya adalah cek headers, developer ninggalin note rahasia, rot 13

---

## **Tools**
- Firefox Browser
- Firefox DevTools (F12)
- ROT13 decoder 

---

## **Langkah-Langkah**

### **1. Recon**
Buka URL challenge: http://amiable-citadel.picoctf.net:54084/ 
lalu saya masukan email dan passwordnya ngasal
dan output nya salah
saya inspect dan saya menemukan sesuatu teks aneh di header nya dan coba decode pakai rot13 web
saya menemukan clue yaitu header X-Dev-Access: yes
saya mencoba untuk menambahkan headers baru di post dengan cara saya muat ulang web dan saya masukan emaail dan pw ngasal 
lalu saya inspect dan ke bagian network tab, saya tambahkan nama headersnya X-Dev-Access dan value nya yes
lalu saya kirim ulang dan saya cek response 
dan saya menemukan flag nya
berikut ini dokumentasi nya <img width="1920" height="1080" alt="Screenshot_2026-02-27_17_02_26" src="https://github.com/user-attachments/assets/9be1dc1f-6e66-4b94-9507-7a0c2faa6c1f" />














