# MikroTik Walled Garden Bypass List

Agar halaman login dapat memuat resource eksternal (CSS, Fonts, Icons) dengan lancar, gunakan konfigurasi Walled Garden berikut. **Penggunaan wildcard (`*`) sangat disarankan** karena CDN sering menggunakan subdomain yang dinamis.

## Command Line (Terminal)
Copy paste script berikut ke terminal MikroTik Anda (New Terminal):

```routeros
/ip hotspot walled-garden
add dst-host=*cdn.tailwindcss.com comment="Tailwind CSS"
add dst-host=*fonts.googleapis.com comment="Google Fonts CSS"
add dst-host=*fonts.gstatic.com comment="Google Fonts/Icons Assets"
```

> [!NOTE]
> Jika sebelumnya sudah menambahkan tanpa bintang (*), sebaiknya hapus dulu atau tambahkan yang baru ini.

## Manual Setup (WinBox)
1. Buka Menu **IP** -> **Hotspot**
2. Klik tab **Walled Garden**
3. Klik tombol **+** (Add)
4. Isi kolom **Dst. Host** dengan domain berikut (tambahkan bintang di depan):
   - `*cdn.tailwindcss.com`
   - `*fonts.googleapis.com`
   - `*fonts.gstatic.com`
   - `*cdnjs.cloudflare.com`
5. Klik **OK**.
