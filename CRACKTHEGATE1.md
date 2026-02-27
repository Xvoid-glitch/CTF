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
berikut ini dokumentasi nya 
<img width="1920" height="1080" alt="Screenshot_2026-02-27_17_02_32" src="https://github.com/user-attachments/assets/a1e6f9cb-c040-40f6-aafd-c8b853a3f60e" />
<img width="1920" height="1080" alt="Screenshot_2026-02-27_17_03_37" src="https://github.com/user-attachments/assets/bfc2fdc7-a2eb-4940-9721-fc399fcffcee"  width="1920" height="1080" alt="Screenshot_2026-02-27_17_05_45" src="https://github.com/user-attachments/assets/b2b63412-d26a-420c-9bd6-a53cfd43a2db" />
/><img width="1920" height="1080" alt="<imgScreenshot_2026-02-27_17_04_25" src="https://github.com/user-attachments/assets/1ce74243-e166-4a7b-8466-32c7d4177632" />

















