### pratikum5

#### Soal

- Buat program sederhana yang akan menampilkan daftar nilai
mahasiswa, dengan ketentuan
- Program dibuat dengan menggunakan Dictionary
- Tampilkan menu pilihan: (Tambah Data, Ubah Data, Hapus Data,
Tampilkan Data, Cari Data)
- Nilai Akhir diambil dari perhitungan 3 komponen nilai (tugas: 30%,
uts: 35%, uas: 35%)

#### FLOWCHART

![flowchartpratikum5](https://user-images.githubusercontent.com/115714443/204314193-013a842c-aaa6-4a9f-8973-8e2b68fd2f8c.png)

##### Code

```print("====================================")
print("======>  Program Input Data  <======")
print("====================================")
data = {}
while True:
    print("")
    m = input("===>> (L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar : <=== ")
    print("================================================================")
    print("| NO |  Nama     |   Nim    |  Tugas  |  UTS  |  UAS  |   Akir |")
    print("================================================================")
    print(">>>>>>>>>>>>>>>>>>>>>>>> TIDAK ADA DATA <<<<<<<<<<<<<<<<<<<<<<<<")
    if m.lower() == 'k':
        break
   elif m.lower() == 'l':
        print("----- DAFTAR NILAI -----")
        print("==================================================================================")
        print("| NO |   NAMA     |   NIM        |  TUGAS   |   UTS     |   UAS      |  AKHIR    |")
        print("==================================================================================")
        i = 0
        for x in data.items():
            i += 1
            print("|  1 |{0:9}   |{1:9}     |{2:9} |{3:9}  |{4:9}   |{5:9}  |" .format(x[0], x[1][0],
                                                                                       x[1][1], x[1][2], x[1][3],
                                                                                       x[1][4], i))
    else:
            print("====================>>>>>>>>>>>>> Tidak Ada Data <<<<<<<<<<<<<====================")

    elif m.lower() == 't':
        print("--------------- Tambah Data ---------------")
        nama = input("Nama                  : ")
        nim = input("Nim                   : ")
        tugas = float(input("Masukan Nilai Tugas   : "))
        uts = float(input("Masukan Nilai UTS     : "))
        uas = float(input("Masukan Nilai UAS     : "))
        akhir = (int(tugas) * .30) + (int(uts) * .35) + (int(uas) * .35)
        data[nama] = nim, tugas, uts, uas, akhir

    elif m.lower() == 'u':
        print("----- Ubah Data Mahasiswa -----")
        nama = input("Nama  : ")
        if nama in data.keys():
            nim = input("Nim : ")
            tugas = float(input("masukan nilai tugas : "))
            uts = float(input("masukan nilai Uts : "))
            uas = float(input("masukan nilai uas : "))
            akhir = (int(tugas) * .30) + (int(uts) * .35) + (int(uas) * .35)
            data[nama] = nim, tugas, uts, uas, akhir

        else:
            print("Tidak Ada data")

    elif m.lower() == 'h':
        print("Hapus Data Mahasiswa")
        nama = input("nama : ")
        if nama in data.keys():
            print("Datanya", nama, "adalah {0}".format(data[nama]))
        else:
            print("Tidaak Ada Data")

    else:
        print("Pilih menu yang tersedia")
```
##### Contoh jika code dimasukkan

![Screenshot (48)](https://user-images.githubusercontent.com/115714443/204310632-b9c1bcf7-f0b0-476e-be7f-9ced85f11dc5.png)

![Screenshot (49)](https://user-images.githubusercontent.com/115714443/204310650-d7d1ff21-6952-45b2-906c-78f4fed29c4f.png)

![Screenshot (50)](https://user-images.githubusercontent.com/115714443/204310666-ccdb267d-cf49-4804-a74c-074403f86744.png)

##### Penjelasan

- Pertama saya menginput judul yang print = progaam input data,option ya jika kalian mau bikin atau ga bikin juga tidak masalah,kemudian anda menginputkan data={ }, diisi dengan sesuai kenginan anda, dengan format dictionary 
- Gunakanlah perulangan While True untuk menampilkan data sebanyak banyaknya
- lalu Masukan perintah m = input("(T)ambah, (U)bah, (H)apus, (L)ihat,(C)ari, (K)eluar: "),untuk mendapatkan perintah Tambah, Ubah, Hapus,Lihat,Cari,Keluar.
- Untuk menambahkan data gunakan fungsi elif, lalu masukan nama, nim, tugas, uts, uas, nilaiakhir, nilai akhir didapat dari = ((tugas)*30/100+(uts)*35/100+(uas)*35/100)
- Lalu jika ingin memilih "lihat" gunakan fungsi 'elif' dan gunakan fungsi 'for x in data.items():' untuk memasukan data kedalam tabel data yang kita inputkan, dengan perintah "l". jika data yang tidak terdaftar = 0
- Untuk menampilkan pilihan "hapus"gunakan fungsi 'elif' kemudian gunakan fungsi 'if nama in data.keys():' kemudian fungsi'del.data[nama] jika nama yang kita hapus tidak ada dalam tabel maka gunakan fungsi 'else' untuk menampilkan data tidak ada.
- lalu untuk menampilan pilihan "cari"" gunakan fungsi 'elif' kemudian gunakan fungsi if nama in data.keys():' untuk mencari data nama kemudian gunakan fungsi 'else' untuk menampilkan data nama yang kita cari tidak ada.
- Kemudian jika ingin keluar dari program gunakan fungsi 'if' kemudian gunakan fungsi break untuk keluar dari data nilai/menghentikan program .Seleseai

##### Hasil RUN

![Screenshot (46)](https://user-images.githubusercontent.com/115714443/204308824-c8dece66-84a1-4b1a-ba21-1423be3fcb38.png)
