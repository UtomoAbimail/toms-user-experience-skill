# Tom's User Experience

Skill Claude Code untuk **menguji aplikasi atau situs seperti pengguna sungguhan**. Claude berperan sebagai penguji, bukan developer: memakai aplikasi lewat browser bawaan, mencatat bagian yang membingungkan, lalu memberi laporan temuan.

## Deskripsi

Penguji pengguna sungguhan untuk aplikasi atau situs milik sendiri. Claude memilih persona yang realistis, lalu memakai aplikasi lewat browser bawaan layaknya pengguna yang baru pertama kali datang, tanpa membaca kode sumber dulu. Sambil jalan ia menceritakan apa yang dipikirkan dan mencatat bagian yang tersendat, membingungkan, bug, serta alur yang putus. Hasilnya laporan temuan yang diurutkan menurut tingkat keparahan, lengkap dengan tangkapan layar dan usulan perbaikan yang konkret.

Dipakai saat Anda bilang "uji sebagai pengguna", "coba aplikasinya", "test my app", "user test", "UX test", "usability test", "act as a user", atau ingin tahu bagaimana orang sungguhan mengalami sebuah halaman, alur, atau fitur.

### Deskripsi lengkap (asli, dari `SKILL.md`)

Teks ini yang dipakai Claude untuk memutuskan kapan skill ini dipanggil:

> Act as a real user tester for the user's own app or website. Picks a realistic persona, drives the app in the built-in browser like a first-time user (no reading source code first), thinks aloud, records friction, confusion, bugs and broken flows, then reports severity-ranked findings with screenshots and concrete fixes. Use when the user says "test my app", "user test", "uji sebagai pengguna", "coba aplikasinya", "UX test", "usability test", "act as a user", "toms-user-experience", or wants to know how a real person experiences a page, flow or feature.

## Cara memakai

Ketik di Claude Code:

```
/toms-user-experience
```

Bisa ditambah target, misalnya:

```
/toms-user-experience daftar → buat template → buat laporan
/toms-user-experience halaman harga, versi HP
```

Skill ini juga bisa terpanggil otomatis bila Anda menulis "uji sebagai pengguna", "coba aplikasinya", "usability test", dan sejenisnya.

## Apa yang dilakukan

1. **Persiapan.** Menentukan target, menjalankan server lokal (127.0.0.1), memilih persona (bawaan: pengguna awam yang baru pertama kali datang), dan menulis 3–6 tugas beserta ukuran berhasilnya.
2. **Pengujian.** Hanya mengklik apa yang terlihat, tanpa membaca kode tampilan dulu. Setiap langkah dicatat: harapan → tindakan → hasil → perasaan (😊 😐 😣 ❌). Juga mencoba kesalahan umum (form kosong, kata sandi salah, tombol kembali, muat ulang) dan sekali di ukuran HP.
3. **Laporan** (dalam bahasa Anda):
   - Ringkasan dan nilai per tugas (✅ / ⚠️ / ❌)
   - Temuan, diurutkan dari yang paling parah (Kritis, Tinggi, Sedang, Rendah) dengan tangkapan layar dan usulan perbaikan
   - Yang sudah bagus
   - Catatan teknis (error di konsol, permintaan yang gagal)
   - Tiga perbaikan yang paling layak didahulukan

Kode baru diubah setelah Anda setuju. Sesudahnya tugas yang terdampak diuji ulang dengan persona yang sama.

## Batasan keamanan

- Hanya memakai akun dan data uji, tidak pernah kata sandi atau data pembayaran asli.
- Pembayaran hanya dalam mode uji di localhost.
- Tidak mengirim email atau pesan sungguhan, tidak menghapus data asli.
- Tidak menguji situs produksi dengan data asli kecuali Anda minta.

## Berkas

- `SKILL.md`: instruksi lengkap yang dibaca Claude
- `README.md`: penjelasan ini
