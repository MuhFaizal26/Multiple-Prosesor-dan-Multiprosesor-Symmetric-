# Multiple-Prosesor-dan-Multiprosesor-Symmetric-
![_Multiple Prosesor dan Multiprosesor Symmetric drawio](https://github.com/user-attachments/assets/3e05d42b-a777-43dd-93f2-1b80cd380b84)
# Arsitektur Multiprosesor

Dokumentasi ini menjelaskan dua model arsitektur multiprosesor berdasarkan diagram yang telah dibuat:

---

## 1. Multiprosesor Symmetric (SMP)

Pada bagian kiri gambar, diperlihatkan arsitektur **Multiprosesor Symmetric**.

- Semua prosesor terhubung melalui **BUS** besar yang juga menjadi jalur utama untuk mengakses **Main Memory** dan **I/O**.
- Setiap prosesor memiliki **Cache** sendiri untuk mempercepat akses data lokal.
- Cache masing-masing prosesor terhubung ke **Main Memory**.
- Akses terhadap memori dan I/O dilakukan **secara bersamaan** melalui bus yang sama, yang dapat menyebabkan **kemacetan (bottleneck)** jika banyak prosesor mengakses bersamaan.

### Ciri-ciri dari gambar:
- BUS utama berwarna merah besar menunjukkan jalur komunikasi tunggal.
- Tiga cache terhubung langsung ke Main Memory via BUS.
- Terdapat hubungan antara cache dan RAM (Memory), menunjukkan hirarki memori.
- Terdapat juga koneksi ke perangkat I/O.

### Kesimpulan:
SMP menawarkan kemudahan implementasi dan efisiensi pada jumlah prosesor yang tidak terlalu banyak, namun kinerjanya dapat terganggu jika trafik di BUS terlalu padat.

---

## 2. Arsitektur Multiprosesor Terdistribusi

Pada bagian kanan gambar, diperlihatkan arsitektur **Multiprosesor Terdistribusi**.

- Setiap CPU memiliki **Cache** lokal masing-masing.
- CPU berkomunikasi dengan **BUS** melalui Cache, bukan langsung ke BUS.
- BUS ini kemudian terhubung ke beberapa **controller**, yaitu:
  - **Controller Memory** (mengelola akses ke memori utama),
  - **Controller System** (mengatur pengelolaan data dan tugas antar CPU),
  - **I/O Controller** (mengatur interaksi dengan perangkat input/output).
- Arsitektur ini membagi tanggung jawab kontrol, sehingga **mengurangi bottleneck** yang sering terjadi pada model SMP.

### Ciri-ciri dari gambar:
- Terdapat empat CPU yang masing-masing terhubung ke Cache.
- Semua cache menuju ke BUS berwarna hitam.
- BUS menghubungkan ke tiga controller terpisah: Memory, System, dan I/O.

### Kesimpulan:
Arsitektur ini mendukung skalabilitas yang lebih baik dan mengoptimalkan performa pada sistem dengan jumlah CPU yang lebih besar, meskipun membutuhkan manajemen yang lebih kompleks.

---

# Perbandingan Singkat

| Fitur | Multiprosesor Symmetric (SMP) | Arsitektur Multiprosesor Terdistribusi |
| :--- | :--- | :--- |
| Koneksi CPU ke Memori | Melalui bus bersama | Melalui controller memory |
| Komunikasi | Langsung via bus | Terorganisir via controller |
| Skalabilitas | Terbatas | Tinggi |
| Bottleneck | Tinggi di bus | Dikurangi lewat distribusi kontrol |
| Kompleksitas Sistem | Lebih sederhana | Lebih kompleks |

---

# Catatan Tambahan
Gambar ini menggambarkan perbedaan utama dalam hal **akses memori**, **manajemen sumber daya**, dan **kinerja sistem** antara dua model arsitektur multiprosesor.  
Pemilihan arsitektur tergantung pada kebutuhan performa, skalabilitas, dan kompleksitas sistem yang diinginkan.



