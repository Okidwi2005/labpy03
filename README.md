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
