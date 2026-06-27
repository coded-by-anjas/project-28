# Brief — Website Hadiah (lokal, pakai foto sendiri)

Website satu halaman buat dikasih ke pacar. Tiap ketuk munculin satu foto + ucapan,
ditutup foto berdua + pesan penutup. Di **belakang** ada foto-foto aset kamu yang
melayang pelan kayak kolase kenangan.

---

## 1. Struktur folder

Taruh semuanya dalam satu folder, contoh `hadiah/`:

```
hadiah/
├─ hadiah.html        ← file utama (tinggal dobel-klik buat dibuka)
└─ assets/            ← semua foto kamu masuk sini
   ├─ bg1.jpg         ← foto-foto buat melayang di belakang
   ├─ bg2.jpg
   ├─ bg3.jpg
   ├─ ...
   ├─ foto1.jpg       ← foto buat tiap momen (yang di tengah)
   ├─ foto2.jpg
   ├─ ...
   └─ berdua.jpg      ← foto kalian berdua (layar terakhir)
```

Nama file bebas — yang penting nanti dicocokin di pengaturan (langkah 3).

---

## 2. Ukuran & jumlah foto (rekomendasi)

| Bagian             | Rasio bagus | Jumlah ideal | Catatan                                               |
| ------------------ | ----------- | ------------ | ----------------------------------------------------- |
| Foto melayang (bg) | bebas       | 5–10         | makin banyak makin variatif; dipotong otomatis ke 4:5 |
| Foto momen         | tegak 4:5   | 4–6          | wajah/objek di tengah biar aman kena crop             |
| Foto berdua        | tegak 4:5   | 1            | jadi klimaks di akhir                                 |

- Idealnya tiap foto **di bawah ~1 MB** biar enteng dibuka, apalagi di HP.
- Format `.jpg` atau `.png` dua-duanya bisa.

---

## 3. Cara ganti isi

Buka `hadiah.html` pakai editor teks (VS Code / Notepad / TextEdit),
scroll ke bawah cari **`const CONFIG`**. Itu satu-satunya yang perlu diubah.

- `namaDia` — panggilan buat dia
- `dariKamu` — tanda tanganmu di layar akhir
- `bgFotos` — daftar foto yang melayang di belakang. Tambah/hapus baris sesukamu:
  ```
  bgFotos: [
    "assets/bg1.jpg",
    "assets/bg2.jpg",
    ...
  ],
  ```
- `momen` — tiap baris `{ foto: "...", ucapan: "..." }` = satu layar.
  Isi `foto` dengan path (mis. `"assets/foto1.jpg"`) dan `ucapan` dengan kata-katamu.
  Mau nambah/ngurang momen tinggal tambah/hapus barisnya.
- `penutup` — foto berdua + pesan terakhir.

> Foto yang dikosongin (`""`) bakal muncul sebagai kotak placeholder, jadi nggak error.
> Kalau `bgFotos` dikosongin semua, latar belakang otomatis balik ke cahaya bokeh.

---

## 4. Cara buka / test

Cukup **dobel-klik `hadiah.html`** — kebuka di browser. Foto dari folder `assets/`
otomatis kebaca karena ada di folder yang sama.

Catatan kecil: font tulisannya diambil dari internet (Google Fonts), jadi pas
pertama buka sebaiknya ada koneksi. Kalau offline, tetap jalan tapi fontnya
ganti ke font bawaan sistem.

---

## 5. Yang bikin nggak norak (biar konsisten kalau mau diutak-atik)

- Foto belakang sengaja **transparan + agak blur + gerak lambat** — biar jadi
  suasana, bukan rebutan perhatian sama teks depan.
- Nggak ada hati berhamburan / warna nyala. Aksen cuma emas tipis.
- Animasi otomatis dimatiin kalau HP-nya nyetel "kurangi gerak".

Kalau mau, palet warna (`:root` di bagian `<style>`) bisa diganti —
`--gold`, `--cream`, dan `--bg-0/1/2` itu kunci warnanya.
