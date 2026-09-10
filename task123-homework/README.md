# Praktikum Modul 1 - Kevin Akbar / 251511014 

## Ringkasan halaman
Halaman ini menampilkan komponen kartu harga paket lokakarya (Mandiri, Terbimbing,
Intensif) yang responsif. Halaman dikembangkan menggunakan struktur HTML semantik dan
murni dengan CSS tanpa framework(seperti tailwind or bootstrap kinda thing)

## Tiga keputusan teknis
1.Pendekatan Mobile-First: Menerapkan tata letak satu kolom (`flex-direction: column`)
sebagai bawaan untuk layar kecil, lalu menggunakan media query di titik 768px untuk
mengubahnya menjadi baris.
2.Custom Properties (Token): Menyimpan nilai warna, jarak, dan radius di dalam `:root`
agar desain konsisten dan mudah diperbarui di satu tempat.
3.Pemisahan Modifier: Menggunakan `.price-card` sebagai kelas utama yang bisa dipakai
ulang, dan `.price-card--featured` khusus untuk menambahkan gaya spesifik kartu agar
kode reusable.

## Masalah, diagnosis, dan perbaikan
Masalah: Posisi tombol di bagian bawah kartu tidak sejajar karena jumlah poin fasilitas
(`<li>`) pada masing-masing paket berbeda
Diagnosis: Elemen di dalam kartu menggunakan flexbox vertikal, tetapi tidak ada elemen
yang diinstruksikan untuk mengisi sisa ruang kosong
Perbaikan: Menambahkan properti `flex-grow: 1` pada elemen `<ul>` agar daftar fasilitas otomatis merenggang ke bawah dan mendesak semua tombol sejajar di dasar kartu

## Hasil pengujian empat viewport
320px: Tidak overflow
375px: Tidak overflow
768px: Breakpoint aktif, layout beralih menjadi dua kartu secara berdampingan dan 1
kartu dibawahnya
1024px: layout beralih menjadi 3 kartu secara berdampingan

## Refleksi belajar
Proyek ini memperkuat pemahaman saya tentang keandalan *box model* dan efisiensi
Flexbox. Saya belajar bahwa menulis CSS modular menggunakan class reusable(didalem
root) dan modifier jauh lebih bersih dibandingkan menggunakan inline style atau aturan
yang spesifikasinya terlalu tinggi

## Log AI atau sumber bantuan 
