# Tugas_W11_Otomata_E_Kelompok_8

## Anggota:
| Nama                        | NRP         |
|-----------------------------|-------------|
| Ignatius Devon Andri Putra  | 5025231159  |
| Rachmat Ramadhan            | 5025231193  |
| Samuel Steve Mulyono        | 5025231197  |
| Ryan Marvin Sirait          | 5025231215  |

---

## Cocke–Younger–Kasami (CYK) Algorithm

### Deskripsi
Program ini menggunakan algoritma CYK (Cocke–Younger–Kasami) untuk memeriksa apakah sebuah string termasuk dalam bahasa yang dihasilkan oleh grammar bebas-konteks (CFG) dalam bentuk Chomsky Normal Form (CNF). Grammar dibaca dari file `grammar.txt` dan string input dibaca dari file `input.txt`.

### Struktur File

- `cyk_parser.py`  : File utama program Python
- `grammar.txt`    : File berisi aturan grammar dalam format CNF
- `input.txt`      : File berisi string yang ingin diuji
- `README.txt`     : Penjelasan tentang program ini

---

### Format File `grammar.txt`

Aturan grammar ditulis dalam bentuk:
```
N -> A B | C D
N -> a
```
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

---

### Format File `input.txt`

File ini hanya berisi satu baris string yang akan diperiksa.  
Contoh:
```
aaabbbccc
```

---

### Cara Menjalankan Program

1. Pastikan Python 3 sudah terpasang di sistem Anda.
2. Simpan aturan grammar ke dalam file `grammar.txt`.
3. Simpan string yang ingin diuji ke dalam file `input.txt`.
4. Jalankan program dengan perintah berikut di terminal:

```sh
python cyk_parser.py
```

---

### Contoh Output Program

Program akan mencetak tabel CYK dalam bentuk matriks segitiga bawah. Setiap sel berisi himpunan non-terminal yang dapat menghasilkan substring terkait. Setelah tabel, program akan menampilkan status keanggotaan string terhadap grammar.

Contoh output:
```
Input String: a a a b b b c c c

Posisi:    1       2       3       4       5       6       7       8       9
--------------------------------------------------------------------------------
1:     {'C'}   {'C'}   {'C'}   {'D'}   {'D'}   {'D'}   {'B','E'} {'B','E'} {'B','E'}
2:     {'A'}   {'A'}   {'A'}   {'F'}   {'F'}   {'F'}   {'B'}     {'B'}     {'B'}
3:     {'F'}   {'F'}   {'F'}   {'A'}   {'A'}   {'A'}   {'B'}     {'B'}
4:     ... (baris berikutnya hingga baris ke-n)
...
9:     {'S'}

Result: String belongs to this context free grammar.
```
- Jika simbol `S` terdapat di posisi paling atas dan paling kiri tabel (baris terakhir, kolom pertama), maka string **termasuk** dalam bahasa CFG.
- Jika tidak, maka string **tidak termasuk** dalam bahasa CFG.

---
