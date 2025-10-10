# CTF HASHCRACK


## Langkah-Langkah Penyelesaian

1.  **Memulai Tantangan**

      * [cite\_start]Saya membuka situs web **picoCTF** dan memilih misi **Hashcrack**[cite: 1].
      * [cite\_start]Tantangan dimulai dan memberikan petunjuk koneksi: `nc verbal-sleep.picoctf.net 61774`[cite: 1].
      * [cite\_start]Saya membuka terminal, menempelkan perintah tersebut, dan muncul sebuah *hash* yang diikuti permintaan *password*[cite: 1].

2.  **Petunjuk dan Alat Bantu**

      * [cite\_start]Petunjuk dari misi mengisyaratkan penggunaan **CrackStation**[cite: 1]. [cite\_start]Saya menggunakannya untuk memecahkan *hash* yang diberikan[cite: 1].

3.  **Memecahkan Hash Pertama**

      * [cite\_start]**Hash Awal**: `482c811da5d5b4bc6d497ffa98491e38`[cite: 1].
      * [cite\_start]Setelah saya masukkan ke CrackStation, *password* yang muncul adalah **`password123`**[cite: 1].
      * Setelah memasukkan *password* ini, muncul *hash* kedua.

4.  **Memecahkan Hash Kedua**

      * **Hash Kedua**: `b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3`.
      * Setelah dimasukkan lagi ke CrackStation, *password* yang muncul adalah **`letmein`**.
      * Setelah memasukkan *password* ini, muncul *hash* ketiga.

5.  **Memecahkan Hash Ketiga**

      * **Hash Ketiga**: `916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745`.
      * Setelah dimasukkan ke CrackStation untuk yang terakhir kalinya, *password* yang muncul adalah **`qwerty098`**.

6.  **Mendapatkan Flag**

      * Setelah saya memasukkan *password* terakhir, **flag** pun muncul:

    <!-- end list -->

    ```
    picoCTF{UseStr0nG_h@shEs_&PaSswDs!_ccc21957}
    ```

