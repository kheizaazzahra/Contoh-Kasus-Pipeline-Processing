# Contoh-Kasus-Pipeline-Processing

## **Contoh Kasus Pipeline Processing: Proses Upload dan Konversi Video di Platform Streaming**

### **Deskripsi Kasus:**
Ketika pengguna mengunggah video ke platform seperti YouTube, video tersebut tidak langsung bisa ditonton. Ada proses berlapis yang dilakukan sistem secara bertahap.

### **Tahapan Pipeline:**

1. **Tahap 1: Upload & Validasi File**
   - Mengecek format file, ukuran, dan integritas data.

2. **Tahap 2: Transcoding Video**
   - Mengonversi video ke berbagai resolusi (480p, 720p, 1080p) agar bisa ditonton di berbagai perangkat.

3. **Tahap 3: Ekstraksi Metadata**
   - Mengambil info seperti durasi, resolusi, codec, thumbnail otomatis, dsb.

4. **Tahap 4: Penyimpanan & Distribusi**
   - Menyimpan video ke server CDN dan menyiapkannya untuk ditonton (streaming-ready).

5. **Tahap 5: Publikasi**
   - Menampilkan video ke profil pengguna dan membuatnya bisa dicari atau diakses publik.

### **Contoh Aliran Pipeline:**
- Video A diunggah duluan → mulai masuk Tahap 1.  
- Saat Video A masuk Tahap 2, Video B mulai masuk Tahap 1.  
- Saat Video A masuk Tahap 3, Video B masuk Tahap 2, Video C mulai masuk Tahap 1.  
- Dan seterusnya…

Hasilnya: Semua video diproses paralel di tahap yang berbeda → waktu tunggu total jadi lebih pendek.

### **Manfaat Pipeline:**
- Tidak ada bottleneck walau banyak video masuk.
- Pemrosesan bisa dioptimalkan untuk tiap tahap (misal, transcode bisa dijalankan di server GPU).
- Lebih mudah diskalakan karena tiap tahap bisa dipisah jadi service sendiri (microservice).
