# Tugas Besar 1 Strategi Algoritma - Stimanana
## Pemanfaatan Algoritma Greedy dalam Permainan Diamonds

## Kelompok Stimanana
| No. | Nama                     |    NIM    |
|:---:|:-------------------------|:---------:|
| 1.  | Kristof Tsunami Ginting  | 123140117 |
| 2.  | Mulya Delani             | 123140019 |
| 3.  | Mega Zayyani             | 123140180 |

## Daftar Isi
1. [Deskripsi Umum](#deskripsi-umum)
2. [Penjelasan Algoritma](#penjelasan-algoritma)
3. [Penggunaan Program](#penggunaan-program)

## Deskripsi Umum
Tugas Besar  STIGMA ini bertujuan untuk mengimplementasikan bot pada permainan _Diamonds_. Permainan _Diamonds_ merupakan permainan sederhana yang memiliki objektif bagi pemain untuk mendapatkan _Diamonds_ sebanyak-banyaknya pada papan permainan.

Bot yang dibuat akan menggunakan algoritma _**Greedy**_ dengan tujuan utama mendapatkan _Diamond_ sebanyak-banyaknya agar dapat memenangkan permainan.

## Penjelasan Algoritma
Kelompok Stimanana menggunakan beberapa strategi greedy untuk menentukan langkah selanjutnya. Berikut adalah beberapa metode utama yang diimplementasikan dalam file `Stimanana.py`:

1. **Greedy by Escape** Jika bot membawa ≥3 diamond dan ada musuh dalam jarak ≤2, bot langsung pulang ke base untuk mengamankan diamond.

2. **Greedy by Return (Waktu):** Jika waktu tersisa kurang dari atau sama dengan jarak ke base (mempertimbangkan teleporter jika lebih cepat), bot langsung pulang ke base.

3. **Greedy by Return (Langkah):** Jika waktu tersisa sama atau kurang dari jumlah langkah ke base, bot langsung pulang ke base.

4. **Greedy by Tackle:** Jika ada musuh bersebelahan (jarak 1) yang membawa ≥2 diamond, bot akan menyerang (tackle) musuh tersebut.

5. **Greedy by Red Button:** Jika red button lebih dekat daripada diamond terdekat dan diamond di board < 10, bot akan menekan red button.

6. **Greedy by Distance (Inventory Penuh):** Jika inventory penuh (≥5 diamond) atau waktu hampir habis, bot langsung pulang ke base (memilih jalur teleporter jika lebih efisien).

7. **Greedy by Red Diamond:** Jika sudah membawa ≥3 diamond, bot akan pulang ke base, tetapi jika ada red diamond yang dekat (≤3 langkah) dan masih muat di inventory, bot akan mengambilnya dulu.

8. **Greedy by Diamond:** Jika inventory belum penuh, bot akan mencari diamond terdekat (prioritas red diamond jika muat, lalu blue diamond).

9. **Greedy by Return (Mampir Base):** Jika bot sedang menuju tujuan lain, tetapi melewati base dan membawa diamond, bot akan mampir ke base untuk mengamankan diamond.

Implementasi dari algoritma tersebut dapat ditemukan di file _Stimanana.py_ pada struktur:
```
src/game/logic/Stimanana.py
```

## Penggunaan Program
Sebelum proses instalasi, pengguna harus memasang _requirements_ sebagai berikut:
- NodeJS (npm)
- Docker
- yarn

1. Clone repository ini sebagai algoritma bot yang akan digunakan
```
https://github.com/Christ204/TUBES-STIGMA_STIMANANANA.git
```
2. Clone repository ini sebagai _game engine_.
```
git clone https://github.com/haziqam/tubes1-IF2211-game-engine.git
```
3. Pemain dapat menjalankan bot dengan membuat file run.bat atau run.sh
4. Kemudian untuk menjalankan keseluruhan bot dalam file tersebut, buka terminal dan jalankan perintah: 
```
./run-bots.bat
```
atau
```
chmod +x ./run-bots.sh
./run-bots.sh
```
5. Pemain dapat menjalankan bot secara manual dengan memasukkan _command_ :
```
python main.py --logic Stimanana --email=stimanana@email.com --name=stimanana --password=stimanana --team etimo
```
