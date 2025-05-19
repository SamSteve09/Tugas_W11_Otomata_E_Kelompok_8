# Tugas_W11_Otomata_E_Kelompok_8
## Anggota:
| Nama | NRP |
| ---- | --- |
| Ignatius Devon Andri Putra | 5025231159 |
| Rachmat Ramadhan | 5025231193 |
| Samuel Steve Mulyono | 5025231197 |
| Ryan Marvin Sirait | 5025231215 |
### Cocke–Younger–Kasami (CYK) algorithm


### Cara Menggunakan Program
1. Buat file bernama grammar.txt yang berisi grammar yang ingin digunakan
Contoh:
```
S -> AB
A -> CD | CF
B -> c | EB
C -> a
D -> b
E -> c
F -> AD
```
2. Buat file bernama input.txt yang berisi input string yang ingin diuji
Contoh:
```
aaabbbccc
```
3. Jalankan cyk_algorithm.py
4. Program akan mengeluarkan output "Belong to this context free grammar" bila input valid dengan grammar, dan output "Doesn't belong to this context free grammar" bila tidak valid.
