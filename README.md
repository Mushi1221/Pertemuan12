# Pertemuan13
Nama : Muhammad Shiddiq<br>
NIM : 312210125<br>
Kelas : TI.22.B1<br>

1. Pertama kita buat file bernamakan praktikum8.py
2. selanjutnya kita langsung saja buat program singkat.
```from tabulate import tabulate

class Mahasiswa :
    def __init__(self):
        self.dataMahasiswa = {
            'No' : [],
            'Nim' : [],
            'Nama' : [],
            'Tugas' : [],
            'Uts' : [],
            'Uas' : [],
            'Nilai Akhir' : []
        }

    def tampilkan(self):
        print("Berikut data yang ada")
        print(tabulate(self.dataMahasiswa, headers=[
            'No', 'Nim', 'Nama', 'Tugas', 'UTS', 'UAS', 'Nilai Akhir'], tablefmt='fancy_grid'))

    def tambah(self):
        nim = int(input("Masukkan Nim : "))
        nama = input("Masukkan Nama : ")
        tugas = int(input("Masukkan Nilai Tugas : "))
        uts = int(input("Masukkan Nilai UTS : "))
        uas = int(input("Masukkan Nilai UAS : "))
        nilai_akhir = (tugas *30 / 100) + (uts * 35 / 100) + (uas * 35 / 100)

        self.dataMahasiswa['No'].append(no)
        self.dataMahasiswa['Nim'].append(nim)
        self.dataMahasiswa['Nama'].append(nama)
        self.dataMahasiswa['Tugas'].append(tugas)
        self.dataMahasiswa['Uts'].append(uts)
        self.dataMahasiswa['Uas'].append(uas)
        self.dataMahasiswa['Nilai_Akhir'].append(nilai_akhir)
        print("Data Berhasil ditambahkan!")

    def ubah(self, nama):
        if nama in self.dataMahasiswa['Nama']:
            namaIndex = self.dataMahasiswa['Nama'].index(nama)
            print("Pilih data yang mau diedit")
            while True:
                editApa = int(input(
                    "(1)Nim, \n (2)Nama, \n (3)Nilai Tugas, \n (4)Nilai UTS, \n (5)Nilai UAS, (0)Save perubahan dan exit \n :"))
                print("")

                if editApa == 1:
                    newNim = int(input("Masukkan Nim : "))
                    self.dataMahasiswa['Nim'][namaIndex] = newNim
                elif editApa == 2:
                    newNama = input("Masukkan Nama : ")
                    self.dataMahasiswa['Nama'][namaIndex] = newNama
                elif editApa == 3:
                    newTugas = int(input("Masukkan Nilai Tugas : "))
                    nilai_akhir = (newTugas * 30 / 100 )+ (self.dataMahasiswa['Uts'][namaIndex] * 35 / 100) + (
                        self.dataMahasiswa['Uas'][namaIndex] * 35 / 100)
                    self.dataMahasiswa['Tugas'][namaIndex] = newTugas
                    self.dataMahasiswa['Nilai Akhir'][namaIndex] = nilai_akhir
                elif editApa == 4:
                    newUts = int(input("Masukkan Nilai UTS : "))
                    nilai_akhir = (self.dataMahasiswa['Tugas'][namaIndex] * 30 / 100) + (newUts * 35 / 100) + (
                        self.dataMahasiswa['Uas'][namaIndex] * 35 / 100)
                    self.dataMahasiswa['Uts'][namaIndex] = newUts
                    self.dataMahasiswa["Nilai Akhir"][namaIndex] = nilai_akhir
                elif editApa == 5:
                    newUas = int(input("Masukkan Nilai UAS : "))
                    nilai_akhir = (self.dataMahasiswa['Tugas'][namaIndex] * 30 / 100) + (newUas * 35 / 100) + (
                        self.dataMahasiswa['Uts'][namaIndex] * 35 / 100)
                    self.dataMahasiswa['Uas'][namaIndex] = newUas
                    self.dataMahasiswa["Nilai Akhir"][namaIndex] = nilai_akhir
                elif editApa == 0:
                    print("Perubahan Data berhasil disimpan,")
                    break
        else :
            print("Data tidak Ditemukan")

    def hapus(self, nama):
        if nama in self.dataMahasiswa['Nama']:
            namaIndex = self.dataMahasiswa['Nama'].index(nama)
            del self.dataMahasiswa['No'][namaIndex]
            del self.dataMahasiswa['Nim'][namaIndex]
            del self.dataMahasiswa['Nama'][namaIndex]
            del self.dataMahasiswa['Tugas'][namaIndex]
            del self.dataMahasiswa['Uts'][namaIndex]
            del self.dataMahasiswa['Uas'][namaIndex]
            del self.dataMahasiswa['Nilai Akhir'][namaIndex]
            print("Data berhasil dihapus. ")
        else : 
            print("Data tidak ditemukan")
    
no = 0
instanceMhs = Mahasiswa()
while True:
    tanya = input(
        " (C)Menambah Data, \n (R)Melihat Semua Data, \n (U)Update data, \n (D)Menghapus data, \n (F)Mencari Data, \n (Q)Keluar Program :")
    if tanya == "C":
        while True:
            no += 1
            instanceMhs.tambah(no)  
            tambahDataLagi = input("Tambah Data Lagi? (y/n) : ")
            if tambahDataLagi == 'n':
                break
    elif tanya == "R" :
        instanceMhs.tampilkan()
        print("")
    elif tanya =="U":
        print(tabulate(instanceMhs.dataMahasiswa, headers = [
            'No', 'Nim', 'Nama', 'Tugas', 'UTS', 'UAS', 'Nilai Akhir'], tablefmt = "fancy_grid"))
        nama = input("Masukkan Nama yang mau diedit : ")
        print("")
        instanceMhs.hapus(nama)
    elif tanya =='D':
        print(tabulate(instanceMhs.dataMahasiswa, headers = [
            'No', 'Nim', 'Nama', 'Tugas', 'UTS', 'UAS', 'Nilai Akhir'], tablefmt = "fancy_grid"))
        nama = input("Masukkan Nama yang mau dihapus : ")
        print("")
        instanceMhs.hapus(nama)
    elif tanya =='Q':
        print("")
        print("Anda telah keluar dari program. ")
        break
```
Lalu kita run dan dan masukkan data data yang mau diinput dan hasilnya seperti ini :

![Screenshot (83)](https://user-images.githubusercontent.com/115475520/206903063-d6b4fe51-ebd2-4ce8-8b2c-d876f821cfa8.png)

3. hasil running berdasarkan opsi :
a. opsi Menambahkan data (C):

![Screenshot (85)](https://user-images.githubusercontent.com/115475520/206903438-b9c97bac-b79a-4341-82ad-1e41daaf9cae.png)

b. opsi Melihat Semua data (R) :

![Screenshot (86)](https://user-images.githubusercontent.com/115475520/206903581-982393c2-bd65-472a-874a-0042cf13a07f.png)

c. opsi Update data (U) :

![Screenshot (88)](https://user-images.githubusercontent.com/115475520/206903641-35d744db-f96b-4b25-b6bf-d85d0ad0106e.png)

d. opsi Menghapus data (D) :

![Screenshot (90)](https://user-images.githubusercontent.com/115475520/206903719-18ff7964-cf5a-4f4a-8e09-ba4054fa98fc.png)

e. opsi Mencari data (F) :

![Screenshot (92)](https://user-images.githubusercontent.com/115475520/206903874-b617cdcc-ea50-4c7b-8e77-037dd2fc832f.png)

# Sekian, Terima Kasih.
