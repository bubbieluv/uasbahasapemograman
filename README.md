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
