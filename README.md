# Latihan 1
## Deskripsi program
User disuruh untuk:
1. input n yang lebih kecil dari 0.5
2. nilai n diisi pada saat runtime
3. loop for dan while
4. import random ()

## Kode program
```python
import random

# Meminta input dari pengguna untuk menentukan nilai n
n = int(input("Masukkan jumlah bilangan acak yang ingin ditampilkan: "))

# List untuk menyimpan bilangan acak yang lebih kecil dari 0.5
bilangan_acak = []
count = 0

# Loop while untuk menghasilkan bilangan acak hingga mencapai n bilangan yang valid
while count < n:
    bilangan = random.random()  # Menghasilkan bilangan acak antara 0 dan 1
    if bilangan < 0.5:
        bilangan_acak.append(bilangan)
        count += 1

# Menampilkan bilangan acak yang dihasilkan
print(f"{n} bilangan acak yang lebih kecil dari 0.5:")
for i, bil in enumerate(bilangan_acak, 1):
    print(f"{i}. {bil}")

```

## Output program
![Screenshot 2024-11-10 111222](https://github.com/user-attachments/assets/4ad5f84d-4b88-449b-905d-f94ac89eacd2)

## Penjelasan program
1. import random: Mengimpor modul random untuk fungsi random().
2. Input n: Program meminta input dari pengguna untuk menentukan jumlah bilangan acak yang diinginkan.
3. Loop while:
- Menghasilkan bilangan acak menggunakan random.random() dalam rentang [0,1).
- Mengecek apakah bilangan tersebut lebih kecil dari 0.5.
- Jika ya, bilangan ditambahkan ke dalam list bilangan_acak, dan count meningkat satu
4. Loop for: Menampilkan semua bilangan acak yang valid dalam list bilangan_acak.

# Latihan 2
## Deskripsi program
Seorang pengusaha menginvestasikan uangnya untuk memulai usahanya dengan modal
awal 100 juta, pada bulan pertama dan kedua belum mendapatkan laba. pada bulan ketiga
baru mulai mendapatkan laba sebesar 1% dan pada bulan ke 5, pendapatan meningkat 5%,
selanjutnya pada bulan ke 8 mengalami penurunan keuntungan sebesar 2%, sehingga laba
menjadi 3%. Hitung total keuntungan selama 8 bulan berjalan usahanya.

## Kode program
```python
# Modal awal
modal_awal = 100_000_000  # 100 juta
keuntungan = 0

# Buat daftar persentase keuntungan untuk setiap bulan
persentase_keuntungan = [0, 0, 0.01, 0.01, 0.05, 0.05, 0.05, 0.03]

# Iterasi selama 8 bulan untuk menghitung total keuntungan
for bulan, persentase in enumerate(persentase_keuntungan, start=1):
    laba_bulan_ini = modal_awal * persentase
    keuntungan += laba_bulan_ini
    print(f"Bulan {bulan}: Persentase Keuntungan = {persentase * 100}% , Laba = Rp{laba_bulan_ini:.0f}")

# Tampilkan total keuntungan selama 8 bulan
print(f"\nTotal Keuntungan selama 8 bulan = Rp{keuntungan:.0f}")
```

## Output program
![Screenshot 2024-11-10 114216](https://github.com/user-attachments/assets/571015f4-c302-4e19-8ad1-ab5cff9e063b)

## Penjelasan program
1. Variabel modal_awal: Menyimpan modal awal sebesar 100 juta.
2. Variabel keuntungan: Inisialisasi total keuntungan pada awalnya 0.
3. List persentase_keuntungan:
- Menyimpan persentase keuntungan setiap bulan sesuai dengan kriteria yang diberikan:
- Bulan 1 dan 2: 0% (tidak ada keuntungan).
- Bulan 3 dan 4: 1%.
- Bulan 5 sampai 7: 5%.
- Bulan 8: 3%.
4. Loop for:
- Melakukan iterasi selama 8 bulan, menghitung laba bulanan (laba_bulan_ini) berdasarkan persentase keuntungan bulan tersebut.
Menambahkan laba bulanan ke total keuntungan.
5. Output:
- Menampilkan laba setiap bulan serta total keuntungan selama 8 bulan.

# Latihan 3
## Deskripsi program
Buat program yang mensimulasikan mesin ATM sederhana. Pengguna memiliki saldo awal
sebesar Rp 1.000.000, dan dapat menarik uang hingga saldo habis atau memilih untuk
keluar.

## Kode program
```python
class ATM:
    def __init__(self, saldo_awal=1_000_000):
        self.saldo = saldo_awal

    def tampilkan_saldo(self):
        print(f"Saldo Anda saat ini: Rp{self.saldo:,}")

    def tarik_tunai(self, jumlah):
        if jumlah > self.saldo:
            print("Saldo tidak mencukupi untuk melakukan penarikan.")
        elif jumlah <= 0:
            print("Jumlah penarikan harus lebih besar dari nol.")
        else:
            self.saldo -= jumlah
            print(f"Anda telah berhasil menarik Rp{jumlah:,}.")
            self.tampilkan_saldo()

    def mulai(self):
        while True:
            print("\n=== Selamat datang di ATM ===")
            print("1. Cek Saldo")
            print("2. Tarik Tunai")
            print("3. Keluar")
            pilihan = input("Pilih opsi (1/2/3): ")

            if pilihan == '1':
                self.tampilkan_saldo()
            elif pilihan == '2':
                try:
                    jumlah = int(input("Masukkan jumlah yang ingin ditarik: Rp"))
                    self.tarik_tunai(jumlah)
                except ValueError:
                    print("Masukkan jumlah yang valid.")
            elif pilihan == '3':
                print("Terima kasih telah menggunakan ATM. Sampai jumpa!")
                break
            else:
                print("Pilihan tidak valid. Silakan coba lagi.")

# Inisialisasi ATM dan mulai program
atm = ATM()
atm.mulai()
```

## Output program
![Screenshot 2024-11-10 115444](https://github.com/user-attachments/assets/2ae3dea3-ed83-4f6e-aed4-82a6df8a0f3b)

## Penjelasan program
1. Class ATM:
- __init__: Menginisialisasi saldo awal (Rp1.000.000).
- tampilkan_saldo: Menampilkan saldo saat ini.
- tarik_tunai: Memeriksa apakah saldo mencukupi dan jika jumlah valid, mengurangi saldo dengan jumlah penarikan.
- mulai: Menjalankan antarmuka utama ATM dengan tiga opsi:
- Cek Saldo: Memanggil tampilkan_saldo.
- Tarik Tunai: Meminta input jumlah dan memanggil tarik_tunai.
- Keluar: Mengakhiri program.
2. Penggunaan Program:
- Inisialisasi objek ATM dan panggil mulai untuk memulai simulasi ATM.
