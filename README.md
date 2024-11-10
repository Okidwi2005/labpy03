# latihan 1
# Deskripsi program
User disuruh untuk:
1. input n yang lebih kecil dari 0.5
2. nilai n diisi pada saat runtime
3. loop for dan while
4. import random ()

# Kode program
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

# Output program
