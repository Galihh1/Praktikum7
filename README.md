# Pertemuan 11
 Penjelasan tentang fungsi def adalah kumpulan perintah atau baris kode yang dikelompokkan menjadi satu kesatuan untuk kemudian bisa dipanggil atau digunakan berkali-kali.
 Sebuah fungsi bisa menerima parameter, bisa mengembalikan suatu nilai, dan bisa dipanggil berkali-kali secara independen.
 Dengan fungsi kita bisa memecah program besar yang kita tulis, menjadi bagian-bagian kecil dengan tugasnya masing-masing.
 Juga, fungsi akan membuat kode program kita menjadi lebih “reusable” dan lebih terstruktur
- Di dalam python, sintaks pembuatan fungsi terlihat seperti berikut :
```bash
 def <nama_fungsi>(parameters):
  statements
```
- Bagaimana cara memanggil fungsi yang telah kita definisikan?
 Cukup ketik nama fungsinya, ditambah dengan tanda kurung () seperti berikut :
```bash
<nama_fungsi>()
```
Untuk penjelasan materi lebih lengkapnya bisa anda lihat [disini](https://jagongoding.com/python/dasar/fungsi/) dan [disini](https://drive.google.com/file/d/13GLaT7Ms3tJ_sJRePUWyAA0Q8y92f6EL/view)

# Praktikum 7
**Program sederhana dengan mengaplikasikan penggunaan fungsi yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan :**
 - Fungsi tambah() untuk menambah data
 - Fungsi lihat() untuk menampilkan data
 - Fungsi hapus(nama) untuk menghapus data berdasarkan nama
 - Fungsi ubah(nama) untuk mengubah data berdasarkan nama

Buatlah kodingan programnya seperti dibawah ini
```bash
from os import system
d_nama = []
d_nim = []
d_tugas = []
d_uts = []
d_uas = []
d_akhir = []


def head():
    print('======================================================')
    print('|            PROGRAM DATA NILAI MAHASISWA            |')
    print('======================================================')

def menu():
    head()
    print('[(T)ambah, (U)bah, (L)ihat, (H)apus, (C)ari, (K)eluar]')
    pilih2 = input('Pilih Menu :  ')
    if pilih2 == 't':
        tambah()
    elif pilih2 == 'u':
        ubah()
    elif pilih2 == 'l':
        lihat()
    elif pilih2 == 'h':
        hapus()
    elif pilih2 == 'c':
        cari()
    elif pilih2 == 'k':
        keluar()
    else:
        tidak = input('Menu Tidak Ada ')
        system('cls')
        menu()

def tambah():
    system('cls')
    print('                 Tambah Data Mahasiswa                ')
    print('======================================================')
    nama = input('Nama        : ')
    d_nama.append(nama)
    nim = input('Nim         : ')
    d_nim.append(nim)

    tugas = float(input('Nilai Tugas : '))
    j_tugas = tugas * (30 / 100)
    d_tugas.append(j_tugas)

    uts = float(input('Nilai UTS   : '))
    j_uts = uts * (35 / 100)
    d_uts.append(j_uts)

    uas = float(input('Nilai UAS   : '))
    j_uas = uas * (35 / 100)
    d_uas.append(j_uas)

    total = j_tugas + j_uts + j_uas
    d_akhir.append(total)
    print('Data Tersimpan'.center(40))
    kembali = input('Kembali [enter]')
    menu()


def ubah():
    system('cls')
    print("----- Ubah Data Mahasiswa -----")
    namm = input('Masukkan Nama Mahasiswa : ')
    for i in range(len(d_nama)):
        if namm == d_nama[i]:
            namabaru = input('Nama : ')
            d_nama[i] = namabaru

            nimbaru = input('Nim : ')
            d_nim[i] = nimbaru

            tugasb = float(input('Nilai Tugas : '))
            j_tugasb = tugasb * (35 / 100)
            d_tugas[i] = j_tugasb

            utsb = float(input('Nilai UTS : '))
            j_utsb = utsb * (35 / 100)
            d_uts[i] = j_utsb

            uasb = float(input('Nilai UAS : '))
            j_uasb = uasb * (30 / 100)
            d_uas[i] = j_uasb

            totalb = j_tugasb + j_utsb + j_uasb
            d_akhir[i] = totalb
            print('Data Berhasil Dirubah')
            kembali = input('Kembali Tekan [enter]')
            menu()
    else:
        print('Data Tidak Ada')
        kembali = input('Kembali Tekan [Enter]')
        menu()

def lihat():
    head()

    for i in range(len(d_nim)):
        print('%d.  Nama        : %s' % (i + 1, d_nama[i]))
        print('    Nim         : %s' % d_nim[i])
        print('    Tugas       : %.2f' % d_tugas[i])
        print('    UTS         : %.2f' % d_uts[i])
        print('    UAS         : %.2f' % d_uas[i])
        print('    Nilai Akhir : %.2f' % d_akhir[i])
        print('---------------------------')
    kembali = input('Kembali Tekan [enter]')
    menu()

def hapus():
    system('cls')
    print('         Hapus Data Mahasiswa        ')
    print('=====================================')
    namm = input('Masukkan Nama Mahasiswa : ')
    for i in range(len(d_nama)):
        if namm == d_nama[i]:
            d_nim.remove(d_nim[i])
            d_nama.remove(d_nama[i])
            d_tugas.remove(d_tugas[i])
            d_uts.remove(d_uts[i])
            d_uas.remove(d_uas[i])
            d_akhir.remove(d_akhir[i])

            print('Data Berhasil Dihapus')
            kembali = input('Kembali Tekan [enter]')
            menu()
    else:
        print('Data Tidak Ada')
        kembali = input('Kembali Tekan [Enter]')
        menu()

def cari():
    system('cls')
    head()
    m_nim = input('Masukkan Nim : ')
    for i in range(len(d_nim)):
        if m_nim == d_nim[i]:
            print('--------------------------')
            print('Nama        : ', d_nama[i])
            print('Nim         : ', d_nim[i])
            print('Tugas       : ', d_tugas[i])
            print('UTS         : ', d_uts[i])
            print('UAS         : ', d_uas[i])
            print('--------------------------')
            print('Nilai Akhir : ', d_akhir[i])
            kembali = input('Kembali Tekan [Enter]')
            menu()

    else:
        print('Data Tidak Ada')
        kembali = input('Kembali Tekan [Enter]')
        menu()

def keluar():
    print('Terima Kasih telah menggunakan Program ini')


menu()
```
## Penjelasan kodingan diatas 
![image.png](screenshot/list.png)
# Pertama kita import os nya menggunakan syntax 'from os import system' : pemanggilan fungsi dengan nama os system('cls') :
 clearscreen pada command prompt anda. Memungkinkan kita mengimpor hanya satu definisi (fungsi)
 Lalu kita buat list kosong untuk di isi oleh tipe data yang sesuai dengan nama list tersebut.
 Contoh : nama = [] , list tersebut akan kita gunakan untuk menampung data yang berisi nama yang diinput
![image.png](screenshot/head.png)
# Jika kita ingin membuat judul dan judul tersebut bisa kita panggil setiap saat, maka kita memakai fungsi def <nama_fungsi>
 seperti contoh gambar diatas menggunakan fungsi `def head()`. Jika nanti kita ingin memanggil fungsi def diatas, cukup menggunakan kodinga `head()`
![image.png](screenshot/menu.png)
# selanjutnya buat fungsi def menu() 
 Didalam fungsi def menu, gunakan perulangan `if elif else` untuk pemberian opsi pilihan
 bagi pengguna apa yang akan di inputkan. Dan berilah tujuan apa yang diinputkan, contoh :
 if pilih2 == 't':
        tambah()
 elif pilih2 == 'u':
        ubah()
 Artinya, jika kita mengetikkan 't' maka akan menuju ke def tambah() 
![image.png](screenshot/tambah.png)
# Setelah pembuatan menu, buatlah pilihan fungsi def tambah()
 Didalam fungsi def tambah itu pengimputan semua data-data seperti nama, nim, tugas, uts, uas bahkan total nilai
 Apa yang kita inputkan otomatis ditambahkan ke list nya masing masing, contoh : diawal kita sudah inputkan list kosong
 dengan nama `d_nim` list ketika dalam penginputan akan disimpan di list tersebut menggunakan syntax `d_nim.append`
![image.png](screenshot/ubah.png)
# Lanjut membuat fungsi def lainnya, seperti fungsi def ubah()
 Fungsi def ubah() bertugas untuk merubah data yang sudah diinputkan tadi, jika pengguna belum menginputkan data sama sekali
 maka di fungsi def ubah() ini tidak akan bisa menemukan data tersebut. Mekanismenya dalam fungsi ini adalah merubah data yang sudah diinputkan dan disimpan di list yang sama dengan datanya namun diberi parameter *(sebutan nilai untuk inputan fungsi pada saat fungsi tersebut di definisikan)* data akan dimasukkan ke list yang sama namun di beri parameter [i], contoh semula d_nim[] maka untuk data yang baru akan dimasukan ke d_nim[i]
![image.png](screenshot/lihat.png)
# Lalu setelah membuat fungsi def menu, def tambah, def ubah
 Tambahkan fungsi def lihat() fungsinya untuk menampilkan data yang sudah diinputkan tadi, memanggilnya dengan cara `for i in range(len(d_nim))` yang artinya untuk `i` dalam jangkauan (len(d_nim)), len() digunakan untuk mengetahui panjang (jumlah item atau anggota) dari objek
![image.png](screenshot/hapus.png)
# Tambahkan fungsi def hapus() untuk penghapusan data yang sudah diinputkan
 Di dalam fungsi def hapus() ketika kita ingin mencari data yang akan dihapus yaitu memanggilnya dengan cara yang sama `for i in range(len(d_nama))` setelahnya masukan list yang akan dihapus dan dibelakang list tersebut gunakan metode remove, contoh untuk menghapus list d_nim[] : d_nim.remove(d_nim[i])
![image.png](screenshot/cari.png)
# Untuk mencari data, tambahkan fungsi def cari()
 Di dalam fungsi def cari() yaitu untuk mencari data yang akan dicari memanggilnya menggunakan dengan cara yang sama seperti sebelumnya yaitu `for i in range(len(d_nim)) logikanya ketika kita mencari data berdasarkan nim maka akan muncul sesuai data yang ada nim tersebut
![image.png](screenshot/keluar.png)
# Tahapan terakhir untuk keluar dari program, tambahkan fungsi def keluar()
 Di dalam fungsi ini tidak ada banyak syntax karna tujuan utamanya untuk keluar dari program, namun ada yang harus di perhatikan disini
 dibagian paling akhir atau bawah harus ada penutup dari menu, jika tidak maka ketika pengguna memanggi fungsi yang lain tidak akan
 terpanggil karna dibagian akhir kodingan tidak ada penutup. Maka kita tutup dengan syntax menu().

# Flowchart dari Program diatas :
![image.png](screenshot/flow.jpeg)

# Hasil Screenshot setiap program yang sudah dibuat
1. Menu
 ![image.png](screenshot/ss1.png)

2. Tambah Data
 ![image.png](screenshot/ss2.png)

3. Tampilkan Data
 ![image.png](screenshot/ss3.png)

4. Merubah Data
 ![image.png](screenshot/ss4.png)

5. Menghapus Data
 ![iamge.png](screenshot/ss5.png)

6. Mencari Data
 ![image.png](screenshot/ss6.png)

7. Keluar dari Program
 ![image.png](screenshot/ss7.png)
