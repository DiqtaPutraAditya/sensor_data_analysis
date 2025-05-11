# 🌡️📈 Simulasi Pengambilan dan Analisis Data Sensor dengan Python

Mini project ini bertujuan untuk **mensimulasikan proses pengambilan data dari sensor suhu dan cahaya**, kemudian **menyimpannya**, **menganalisisnya**, dan akhirnya **menyimpan hasil data tersebut ke dalam file CSV** agar bisa digunakan kembali.

Proyek ini sangat cocok untuk pemula yang sedang belajar Python, khususnya tentang:

* Penggunaan `list`, `loop`, dan `dictionary`
* Manipulasi data dengan `pandas`
* Penggunaan `numpy` untuk membuat data acak (simulasi sensor)
* Penyimpanan data ke dalam file `.csv`

---

## 📚 Apa yang Dilakukan Program Ini?

Program ini akan:

1. **Mensimulasikan** pengambilan data suhu dan cahaya sebanyak 10 kali dengan interval waktu 1 detik.
2. Menampilkan data tersebut ke **terminal** (layar).
3. Menyimpan seluruh data ke dalam **DataFrame** (struktur data mirip tabel) menggunakan `pandas`.
4. Menghitung dan menampilkan **rata-rata dan nilai maksimum** untuk suhu dan cahaya.
5. Menyimpan data ke file `data_sensor.csv`.

---

## 🧠 Penjelasan Kode

### 🔹 1. Library yang Digunakan

* **`pandas`**: digunakan untuk membuat dan mengelola **DataFrame**, yaitu struktur data seperti tabel Excel.
* **`numpy`**: digunakan untuk membuat angka acak dalam rentang tertentu — dalam hal ini, sebagai **simulasi sensor**.
* **`datetime`**: mengambil waktu saat ini untuk dicatat bersama data.
* **`time.sleep()`**: memberikan jeda 1 detik agar simulasi terasa seperti data sensor nyata yang datang berkala.

---

### 🔹 2. Proses Simulasi

```python
for i in range(10):
    suhu = round(np.random.uniform(25, 35), 2)
    cahaya = round(np.random.uniform(200, 800), 2)
```

* `np.random.uniform(a, b)`: menghasilkan angka desimal acak antara `a` dan `b`.
* `round(..., 2)`: membulatkan hasil ke dua angka di belakang koma.
* Simulasi dilakukan sebanyak **10 kali**, setiap detik satu data.

---

### 🔹 3. Penyimpanan Data

```python
data.append({
    "Waktu": waktu,
    "Suhu (°C)": suhu,
    "Cahaya (lux)": cahaya
})
```

* Setiap data dimasukkan ke dalam list `data`, berupa dictionary berisi 3 nilai: waktu, suhu, cahaya.

---

### 🔹 4. Analisis Data

```python
df["Suhu (°C)"].mean()
df["Suhu (°C)"].max()
```

* Data dimasukkan ke **DataFrame** agar mudah dianalisis.
* `mean()` menghitung rata-rata.
* `max()` mencari nilai tertinggi.
* Metode ini berasal dari library `pandas`.

---

### 🔹 5. Ekspor ke CSV

```python
df.to_csv("data_sensor.csv", index=False)
```

* Data diekspor ke file CSV agar bisa dibuka di Excel, Google Sheets, dll.
* `index=False` artinya kita tidak menyimpan nomor baris otomatis dari DataFrame.

---

## 📆 Contoh Output Terminal

```
[1] Waktu: 2025-05-12 22:00:00 | Suhu: 28.72°C | Cahaya: 456.12 lux
...
=== Analisis Data ===
Rata-rata Suhu: 29.48
Suhu Tertinggi: 33.10
Rata-rata Cahaya: 545.27
Cahaya Tertinggi: 799.99
```

---

## 📂 File Output

File `data_sensor.csv` berisi:

| Waktu               | Suhu (°C) | Cahaya (lux) |
| ------------------- | --------- | ------------ |
| 2025-05-12 22:00:00 | 28.72     | 456.12       |
| ...                 | ...       | ...          |

---

## 🛠️ Cara Menjalankan

1. Pastikan Python 3 sudah terinstall.
2. Install library jika belum:

   ```bash
   pip install pandas numpy
   ```
3. Jalankan program:

   ```bash
   python simulasi_sensor.py
   ```

---

## 📌 Tujuan Pembelajaran

Proyek ini membantu kamu memahami:

* Bagaimana cara kerja simulasi sensor
* Cara menyimpan data dalam struktur tabel (DataFrame)
* Cara melakukan analisis statistik dasar
* Konversi data Python menjadi file CSV

---

## 👨‍💻 Penulis

Nama: *\[Nama Kamu]*
Github: *\[Link akun GitHub]*

---

## ✅ Status

Proyek ini sudah selesai dan dapat dikembangkan lebih lanjut, misalnya dengan:

* Menambahkan visualisasi grafik (matplotlib)
* Menghubungkannya ke sensor fisik seperti DHT22 atau LDR menggunakan Arduino
