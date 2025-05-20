# Tugas_W11_Otomata_E_Kelompok_8
## Anggota:
| Nama | NRP |
| ---- | --- |
| Ignatius Devon Andri Putra | 5025231159 |
| Rachmat Ramadhan | 5025231193 |
| Samuel Steve Mulyono | 5025231197 |
| Ryan Marvin Sirait | 5025231215 |
### Cocke–Younger–Kasami (CYK) algorithm

---

CYK Algorithm - Pengecekan Keanggotaan String dalam Grammar Bebas-Konteks (CFG)

Deskripsi:
Program ini menggunakan algoritma CYK (Cocke–Younger–Kasami) untuk memeriksa apakah sebuah string termasuk dalam bahasa yang dihasilkan oleh grammar bebas-konteks (CFG) dalam bentuk Chomsky Normal Form (CNF). Grammar dibaca dari file `grammar.txt` dan string input dibaca dari file `input.txt`.

Struktur File:

* cyk\_parser.py -> File utama program Python
* grammar.txt -> File berisi aturan grammar dalam format CNF
* input.txt -> File berisi string yang ingin diuji
* README.txt -> Penjelasan tentang program ini

Format grammar.txt:
Aturan grammar ditulis dalam bentuk:
N -> A B | C D
atau
N -> a

Contoh:
S -> AB
A -> CD | CF
B -> c | EB
C -> a
D -> b
E -> c
F -> AD

Format input.txt:
File ini hanya berisi satu baris string yang akan diperiksa.
Contoh:
aaabbbccc

Cara Menjalankan Program:

1. Pastikan Python 3 sudah terpasang di sistem Anda.
2. Simpan aturan grammar ke dalam file `grammar.txt`.
3. Simpan string yang ingin diuji ke dalam file `input.txt`.
4. Jalankan program dengan perintah berikut di terminal:

python cyk\_parser.py

Program akan mencetak tabel CYK dan memberi tahu apakah string tersebut merupakan bagian dari grammar yang diberikan.

        a       a       a       b       b       b       c       c       c
1       {'C'}   {'C'}   {'C'}   {'D'}   {'D'}   {'D'}   {'B', 'E'} {'B', 'E'} {'B', 'E'}
2       {'A'}   {'A'}   {'A'}   {'F'}   {'F'}   {'F'}   {'B'}   {'B'}   {'B'}
3       {'F'}   {'F'}   {'F'}   {'A'}   {'A'}   {'A'}   {'B'}   {'B'}   _
...
9       {'S'}
Belong to this context free grammar



Jika simbol 'S' terdapat di posisi paling atas dan paling kiri tabel (indeks terakhir), maka string tersebut termasuk dalam bahasa CFG. Jika tidak, maka tidak termasuk.
