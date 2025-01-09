# uas bahasa pemograman

# codingan program

#Class untuk menyimpan data mahasiswa

class Mahasiswa:

    def __init__(self, nama, nim, nilai):
    
        self.nama = nama
        
        self.nim = nim
        
        self.nilai = nilai

#Class untuk mengelola tampilan (view)

class View:

    @staticmethod
    
    def tampilkan_tabel(data_mahasiswa):
    
        print("+----------------------+------------+--------+")
        
        print("| Nama                 | NIM        | Nilai  |")
        
        print("+----------------------+------------+--------+")
        
        for mahasiswa in data_mahasiswa:
        
            print(f"| {mahasiswa.nama:<20} | {mahasiswa.nim:<10} | {mahasiswa.nilai:<6} |")
        
        print("+----------------------+------------+--------+")

#Class untuk memproses data mahasiswa

class Process:

    @staticmethod
    
    def tambah_mahasiswa(data_mahasiswa):
    
        try:
        
            nama = input("Masukkan nama: ")
            
            nim = input("Masukkan NIM: ")
            
            if not nim.isdigit():
            
                raise ValueError("NIM harus berupa angka!")

            nilai = float(input("Masukkan nilai: "))
            
            if nilai < 0 or nilai > 100:
            
                raise ValueError("Nilai harus di antara 0 dan 100!")

            mahasiswa = Mahasiswa(nama, nim, nilai)
            
            data_mahasiswa.append(mahasiswa)
            
            print("Mahasiswa berhasil ditambahkan!")
        
        except ValueError as e:
            
            print(f"Error: {e}")

#Fungsi utama

if __name__ == "__main__":

    data_mahasiswa = []
    
    while True:
    
        print("\nMenu:")
        
        print("1. Tambah Mahasiswa")
        
        print("2. Tampilkan Data Mahasiswa")
        
        print("3. Keluar")

        pilihan = input("Pilih menu: ")
       
        if pilihan == "1":
          
            Process.tambah_mahasiswa(data_mahasiswa)
      
        elif pilihan == "2":
           
            if data_mahasiswa:
               
                View.tampilkan_tabel(data_mahasiswa)
          
            else:
              
                print("Data mahasiswa kosong!")
     
        elif pilihan == "3":
           
            print("Program selesai.")
            
            break
      
        else:
        
            print("Pilihan tidak valid!")

 # Penjelasan
 1. Class Mahasiswa
    
Class ini berfungsi untuk menyimpan data mahasiswa.

Attributes:

nama: menyimpan nama mahasiswa.

nim: menyimpan NIM mahasiswa.

nilai: menyimpan nilai mahasiswa.

2. Class View

Class ini bertanggung jawab untuk menampilkan data mahasiswa dalam bentuk tabel.

Method tampilkan_tabel:

Input: list objek Mahasiswa.

Output: Tabel berisi nama, NIM, dan nilai mahasiswa.

Menampilkan data dalam format tabel dengan header dan garis pembatas.

3. Class Process
   
Class ini bertanggung jawab untuk memproses data mahasiswa, termasuk menambahkan mahasiswa baru.

- Method tambah_mahasiswa:

- Input: list untuk menyimpan data mahasiswa.

Proses:

Meminta input dari pengguna untuk nama, NIM, dan nilai.

Memvalidasi input:

NIM harus berupa angka.

Nilai harus di antara 0 dan 100.

Jika validasi berhasil, membuat objek Mahasiswa dan menambahkannya ke list.

Jika terjadi kesalahan, menampilkan pesan error.

Output: Menampilkan pesan berhasil atau error.

4. Fungsi main

Bagian ini merupakan antarmuka utama program (menu interaktif).


Inisialisasi: data_mahasiswa sebagai list kosong untuk menyimpan data.

Menu interaktif:

Pilihan 1: Menambahkan data mahasiswa menggunakan Process.tambah_mahasiswa.

Pilihan 2: Menampilkan data mahasiswa menggunakan View.tampilkan_tabel.

Pilihan 3: Keluar dari program.

# Hasil Run
