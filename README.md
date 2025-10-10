# CTF
## HASHCRACK

Ini adalah catatan langkah-langkah yang saya ambil untuk menyelesaikan tantangan **Hashcrack** dari picoCTF.

### Langkah-Langkah Penyelesaian

1.  [cite\_start]Saya membuka situs web **picoCTF** dan memilih misi **Hashcrack**[cite: 1].

2.  [cite\_start]Tantangan dimulai dan memberikan petunjuk koneksi: `nc verbal-sleep.picoctf.net 61774`[cite: 1].

3.  [cite\_start]Saya membuka terminal, menempelkan perintah tersebut, dan muncul sebuah **hash** yang diikuti permintaan **password**[cite: 1].

4.  [cite\_start]Petunjuk ketiga menyebutkan bahwa **"mungkin crackstation bisa membantu"**[cite: 1].

5.  [cite\_start]Saya membuka **CrackStation** dan memasukkan *hash* pertama: `482c811da5d5b4bc6d497ffa98491e38`[cite: 1].

6.  [cite\_start]*Password* yang muncul adalah **`password123`**[cite: 1]. [cite\_start]Setelah memasukkan *password* ini, muncul *hash* baru: `b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3`[cite: 1].

7.  [cite\_start]Saya memasukkan *hash* baru tersebut ke **CrackStation** lagi dan *password* yang muncul adalah **`letmein`**[cite: 1]. [cite\_start]Setelah memasukkan *password* ini, muncul *hash* baru lagi[cite: 1].

8.  [cite\_start]*Hash* berikutnya adalah: `916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745`[cite: 1]. [cite\_start]Saya memasukkannya ke **CrackStation** lagi, dan *password* yang muncul adalah **`qwerty098`**[cite: 1].

9.  [cite\_start]Setelah memasukkan *password* terakhir, **flag** pun muncul[cite: 1]:

    ```
    picoCTF{UseStr0nG_h@shEs_&PaSswDs!_ccc21957}
    ```

-----

### Ringkasan Hash dan Password

| No. | Hash Awal | Password Ditemukan | Hash Berikutnya |
| :---: | :---: | :---: | :---: |
| 1 | `482c811da5d5b4bc6d497ffa98491e38` | `password123` | `b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3` |
| 2 | `b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3` | `letmein` | `916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745` |
| 3 | `916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745` | `qwerty098` | - |
