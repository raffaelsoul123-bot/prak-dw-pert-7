# Praktikum Desain Web – Pertemuan 6
## HTML Form Dasar: Input & Pengiriman Data

Repositori ini berisi dua tugas praktikum: **Tugas Individu** dan **Studi Kasus**.

- **Nama:** Mukhamad Akbar Raffael Ridho
- **NIM:** 4525210085
- **Kelas:** Desain Web A

---

## Struktur Folder

```
.
├── README.md
├── tugas-individu/
│   ├── index.html
│   └── style.css
└── studi-kasus/
    ├── index.html
    └── style.css
```

## Cara Menjalankan

1. Unduh atau clone folder proyek ini.
2. Buka `tugas-individu/index.html` atau `studi-kasus/index.html` di browser (klik dua kali atau gunakan Live Server di VS Code).
3. Isi form lalu tekan tombol kirim. Karena belum ada backend, data hanya ditampilkan di bawah form (tanpa password).

---

## 1. Tugas Individu – Form Pendaftaran Kursus

Form pendaftaran kursus dengan minimal lima tipe input dan tiga jenis button, dan setiap kontrol punya label yang terhubung.

| Field | `type` | `id` / `name` |
|---|---|---|
| Nama lengkap | `text` | `nama` |
| Email | `email` | `email` |
| Kata sandi | `password` | `password` |
| Usia | `number` | `usia` |
| Tanggal mulai kursus | `date` | `tanggal-mulai` / `tanggal_mulai` |
| Nomor telepon | `tel` | `telepon` |

**Jenis button**

| Button | Fungsi |
|---|---|
| `type="submit"` (Daftar) | Mengirim form |
| `type="reset"` (Kosongkan form) | Mengembalikan semua isian ke kondisi awal |
| `type="button"` (Lihat, Bantuan) | Tidak mengirim form; hanya menjalankan JavaScript (menampilkan password dan petunjuk) |

## 2. Studi Kasus – Prototipe Form Penerimaan Mahasiswa Baru

Prototipe form untuk panitia penerimaan mahasiswa baru yang nantinya dapat diintegrasikan dengan backend.

| Data | `type` | `id` | `name` |
|---|---|---|---|
| Nama | `text` | `nama` | `nama` |
| Email | `email` | `email` | `email` |
| Password | `password` | `password` | `password` |
| Nilai | `number` (0–100) | `nilai` | `nilai` |
| Tanggal lahir | `date` | `tanggal-lahir` | `tanggal_lahir` |

Setiap field memiliki `<label for>` yang sama dengan `id` inputnya.

---

## Konsep yang Diterapkan

- **`<form>`** membungkus semua kontrol input dan mendefinisikan tujuan pengiriman.
- **`action="#"`** adalah placeholder; nanti diganti URL backend.
- **`method="post"`** dipilih karena data pendaftaran dan password sebaiknya tidak tampil di URL. Method tidak otomatis membuat data aman; tetap perlu HTTPS dan validasi di server.
- **`name`** wajib ada karena menjadi key saat data dikirim.
- **`<label for>` = `id`** memperluas area klik dan membantu pembaca layar.
- **Reset** pada studi kasus meminta konfirmasi dulu agar isian tidak terhapus tidak sengaja.

---

## Ringkasan (150–250 kata)

Pada praktikum ini saya membuat dua form HTML: form pendaftaran kursus (tugas individu) dan prototipe form penerimaan mahasiswa baru (studi kasus). Perubahan utamanya adalah menyusun struktur form yang benar: elemen `<form>` dengan `action` dan `method`, setiap kontrol memiliki `id`, `name`, dan `<label for>` yang terhubung, serta tipe input yang sesuai dengan datanya, yaitu `text`, `email`, `password`, `number`, `date`, dan `tel`. Pada tugas individu saya juga memakai tiga jenis button: submit, reset, dan button biasa.

Masalah yang saya temui adalah form belum bisa diproses karena belum ada backend, sehingga klik tombol kirim akan memuat ulang halaman dan data hilang. Saya juga sadar bahwa tombol reset berisiko menghapus isian secara tidak sengaja, dan `method="post"` tidak otomatis membuat data aman.

Solusinya, pengiriman ditahan dengan `preventDefault()` dan data valid ditampilkan di halaman tanpa password sebagai simulasi. Untuk reset, saya menambahkan dialog konfirmasi pada studi kasus. Atribut validasi seperti `required`, `minlength`, `min`, dan `max` ditambahkan sebagai bantuan pengguna, dengan catatan validasi sebenarnya tetap harus dilakukan di server. Dengan struktur ini, form siap diintegrasikan dengan backend cukup dengan mengganti nilai `action`.

---


