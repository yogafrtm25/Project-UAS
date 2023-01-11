# Project-UAS
# https://youtu.be/L288l3Z_XF4


Buatlah Package dengan Modul seperti berikut :
 
![Screenshot_20230110_153844](https://user-images.githubusercontent.com/115678171/211850844-cb14a577-0951-46ef-815b-19de78bf4971.png) 
 
Jawaban : 
Dibawah ini adalah Script daftar_nilai.py 
```python
from view.input_nilai import *

dataMahasiswa = {}
 
def tambah_data(): global dataMahasiswa nama = input_nama() nim = input_nim()
nilaiTugas = input_nilaiTugas() nilaiUts = input_nilaiUts() nilaiUas = input_nilaiUas()
nilaiAkhir = (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas) dataMahasiswa[nama] = nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir print("\nData Berhasil Ditambahkan!")
return dataMahasiswa


def ubah_data():
nama = input("Masukkan Nama: ") if nama in dataMahasiswa.keys():
nim = input_nim()
nilaiTugas = input_nilaiTugas() nilaiUts = input_nilaiUts() nilaiUas = input_nilaiUas()
nilaiAkhir = (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas) dataMahasiswa[nama] = nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir print("\nData Berhasil Di Update!")
else:
print("Data tidak ditemukan!")



def hapus_data():
nama = input("Masukkan Nama: ") if nama in dataMahasiswa.keys():
del dataMahasiswa[nama]
 
print("Data",nama, "Telah dihapus!") else:
print("Data Mahasiswa Tidak Ada".format(nama))
```


-	Berikut adalah script untuk view_nilai.py atau Cetak Nilai

```python
from model.daftar_nilai import *


def cetak_daftar_nilai():
if dataMahasiswa.items():
print("\n	DAFTAR NILAI MAHASISWA	")

print("==============================================================
====")
print("| No |	Nama	|	NIM	| Tugas | UTS | UAS | Akhir |")

print("==============================================================
====")
i = 0
for x in dataMahasiswa.items(): i += 1
print("| {6:2} | {0:12s} | {1:9s} | {2:5} | {3:5} | {4:5} | {5:6} |".format(x[0], x[1][0], x[1][1], x[1][2], x[1][3], x[1][4], i))

print("==============================================================
====")
else:
print("\n	DAFTAR NILAI MAHASISWA	")

print("==============================================================
====")
print("| No |	Nama	|	NIM	| Tugas | UTS | UAS | Akhir |")
 
print("==============================================================
====")
print("|	TIDAK ADA DATA!	|")

print("==============================================================
====")



def cetak_hasil_pencarian():
nama = input("Masukkan Nama	: ") if nama in dataMahasiswa.keys():
print("\n	DAFTAR NILAI MAHASISWA	")

print("============================================================== ")
print("|	Nama	|	NIM	| Tugas | UTS | UAS | Akhir |")

print("============================================================== ")
print("| {0:12s} | {1:9s} | {2:5} | {3:5} | {4:5} | {5:6} |".format(nama, dataMahasiswa[nama][0],	dataMahasiswa[nama][1],	dataMahasiswa[nama][2], dataMahasiswa[nama][3], dataMahasiswa[nama][4]))

print("============================================================== ")
  
else:
print("Datanya {0} Tidak Ada ".format(nama))
```


-	Berikut adalah script untuk input_nilai.py
```python
def input_nama(): global nama
nama = input("Masukkan Nama	: ")
 
return nama



def input_nim(): global nim
nim = input("Masukkan NIM	: ") return nim



def input_nilaiTugas(): global nilaiTugas
nilaiTugas = int(input("Masukkan Nilai Tugas : ")) return nilaiTugas



def input_nilaiUts(): global nilaiUts
nilaiUts = int(input("Masukkan Nilai UTS : ")) return nilaiUts



def input_nilaiUas(): global nilaiUas
nilaiUas = int(input("Masukkan Nilai UAS : ")) return nilaiUas
```


-	Dan berikut adalah script untuk main.py
```python
from view.cetak_nilai import *
 



def menu(): print('=====================================')
print('Input Data Nilai Mahasiswa'.center(40)) print('=====================================')
print('|	1. Tambah Data		|')
print('|	2. Cari Data	|')	
print('|	3. Tampilkan Data Mahasiswa	|')
print('|	4. Ubah Data Mahasiswa	|')
print('|	5. Hapus Data Mahasiswa	|')
print('|	6. Selesai	|')	
print('=====================================')



while True: menu()
choose = input('Pilih Menu : ')


if choose == '1': tambah_data()
input('Untuk kembali ke menu utama, tekan enter')


elif choose == '2': cetak_hasil_pencarian()
input('Untuk kembali ke menu utama, tekan enter')


elif choose == '3': cetak_daftar_nilai()
input('Untuk kembali ke menu utama, tekan enter')
 

elif choose == '4': ubah_data()
input('Untuk kembali ke menu utama, tekan enter')


elif choose == '5': hapus_data()
input('Untuk kembali ke menu utama, tekan enter')


elif choose == '6': exit()

else:
print("Menu yang anda maksud tidak tersedia, Silahkan pilih menu yang tersedia")
```


-	Dibawah adalah hasil output dari program ketika dijalankan, dan menampilkan menu utama

![Screenshot_20230111_135709](https://user-images.githubusercontent.com/115678171/211851521-73cbd739-06cc-48c1-baca-eedac9297d4d.png)

-	Dibawah adalah hasil ketika program dijalankan, dan input angka 1 pada keyboard, untuk menambah data
 
 ![Screenshot_20230111_140604](https://user-images.githubusercontent.com/115678171/211852066-589b13c7-6b2e-40d3-b634-abb54f629a41.png)

-	Dibawah adalah hasil program ketika dijalankan, dan input angka 2 pada keyboard, untuk mencari data dengan perintah masukkan nama yang ingin di cari

![Screenshot_20230111_140630](https://user-images.githubusercontent.com/115678171/211852136-702c3b38-f060-4e7b-95c7-8c77c8d93e5b.png)

-	Dibawah adalah hasil ketika program dijalankan, dan input angka 1 pada keyboard, untuk melakukan penambahan data, disini kita tambahkan data Adit 
 
![Screenshot_20230111_141129](https://user-images.githubusercontent.com/115678171/211852235-6161dad1-13e2-4658-bb90-006f4a3f1688.png)

-	Dibawah adalah hasil ketika program dijalankan, dan input angka 3 pada keyboard, untuk melihat semua daftar data yang ada

![Screenshot_20230111_141253](https://user-images.githubusercontent.com/115678171/211852350-4df6ec82-601d-4675-826b-798f58aa9096.png)

-	Dibawah adalah hasil ketika program dijalankan, dan input angka 4 pada keyboard, untuk merubah data, disini kita ubah data nilai pada nama Yoga Pratama

![Screenshot_20230111_141450](https://user-images.githubusercontent.com/115678171/211852482-e203bef4-98ab-4dc4-933c-09dfc0cec54d.png)

-	Dan untuk melihat apakah data telah terupdate, maka kita input angka 3 pada keyboard, untuk melihat daftar data yang ada, disini sudah terlihat bahwa data Yoga Pratama sudah terupdate nilai nya
 
![Screenshot_20230111_141638](https://user-images.githubusercontent.com/115678171/211852709-a6528eef-f318-4367-9349-7acb8bac6117.png)

-	Dibawah adalah hasil ketika program dijalankan, dan input angka 5 pada keyboard, untuk perintah hapus data, dengan perintah masukkan nama data yang ingin di hapus, disini kita akan menghapus data dengan nama Adit

![Screenshot_20230111_141836](https://user-images.githubusercontent.com/115678171/211852876-46eb3131-76e7-4654-ba07-be6fccc0147b.png)

-	Dibawah adalah hasil ketika program dijalankan, dan input angka 3 pada keyboard, untuk melihat daftar yang ada, karena adanya penghapusan data, apakah data dengan nama Adit sudah terhapus atau belum

![Screenshot_20230111_142053](https://user-images.githubusercontent.com/115678171/211852988-1829b603-a5ba-45a6-aab0-abe0105c6bf1.png)

-	diBawah adalah ketika program dijalankan, dan input angka 6 pada keyboard, untuk selesai atau keluar dari program

![Screenshot_20230111_225356](https://user-images.githubusercontent.com/115678171/211853222-b1a1e34c-518c-45bd-bf76-dffff0e6b6d4.png)

 
Sekian dari saya Terima Kasih 
Berikut adalah Link Tutorial dari Program Di Atas
Link :   https://youtu.be/L288l3Z_XF4
