## PicoCTF: EVEN RSA CAN BE BROKEN??? 

| Kategori | Kriptografi |
| :---: | :---: |
| **Flag** | `picoCTF{tw0_1$_pr!m3de643ad5}` |

---

1.  **Akses Tantangan (Netcat)**
    ```
    kita diberikan nc verbal-sleep.picoctf.net 57686
    ```

2.  **Output**
    ```
    salin dan tempel di terminal, outputnya :

    N: 18451243413236839815570623818243975684168741782787549079204671585184935001790369469084379497576128158503959037696965200439297423384834617944685557751432866
    e: 65537
    cyphertext: 6863331915766924027129812438798760616562454967447563744810804116925844876307133764730029839900286363712860527268101818399901715102117220724755934865272819
    ```

3.  **Identifikasi**
    ```
    karena judulnya rsa
    ```

4.  **Penggunaan Tool Online**
    ```
    buka rsa identifier di website
    ```

5.  **Input Data**
    ```
    c untuk cyphertext, e sudah default, N untuk N di chipper, lalu tempel desimalnya dan analis
    ```

6.  **Hasil Akhir**
    ```
    muncullah flag nya
    ```
