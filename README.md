
# Boot Mod SDCard

Repository ini berisi workflow GitHub Actions untuk memodifikasi dan menyesuaikan firmware OpenWRT agar dapat digunakan pada kartu SD bootable. Workflow ini mendukung berbagai konfigurasi perangkat dan menghasilkan file firmware dalam format `.img.gz` atau `.img.xz`.

---

## Fitur
- Mengunduh file firmware dari berbagai sumber (Google Drive, MediaFire, Mega.nz, tautan langsung).
- Mengekstrak, memodifikasi, dan mengompres file firmware.
- Menambahkan bootloader Amlogic untuk perangkat yang kompatibel.
- Mengunggah file firmware hasil modifikasi sebagai release asset secara otomatis.

---

## Input Workflow
### 1. **type_dtb**
   - **Deskripsi**: Memilih jenis file device tree binary (DTB) untuk perangkat target.
   - **Pilihan**: `b860h`, `hg680p`
   - **Default**: `b860h`

### 2. **type_file**
   - **Deskripsi**: Memilih format kompresi untuk file firmware.
   - **Pilihan**: `img.gz`, `img.xz`
   - **Default**: `img.xz`

### 3. **img_url**
   - **Deskripsi**: URL file firmware yang akan diunduh.
   - **Wajib**: Ya

### 4. **name_file**
   - **Deskripsi**: Menentukan nama file firmware hasil modifikasi.
   - **Default**: `FW-MOD-SDCARD`

---

## Cara Penggunaan
### 1. Menjalankan Workflow
Workflow ini dapat dijalankan secara manual melalui antarmuka GitHub Actions.

### 2. Input
Berikan input berikut:
- `type_dtb` - Jenis perangkat target.
- `type_file` - Format kompresi yang diinginkan.
- `img_url` - URL file firmware untuk diunduh.
- `name_file` - Nama untuk file firmware hasil modifikasi.

---

## Contoh Workflow Dispatch
Anda dapat menjalankan workflow secara manual menggunakan API atau antarmuka GitHub:

```json
{
  "type_dtb": "b860h",
  "type_file": "img.xz",
  "img_url": "https://contoh.com/firmware.img.xz",
  "name_file": "CustomFirmware"
}
```

---

## Hasil
- File firmware hasil modifikasi akan diunggah sebagai release asset di repository Anda.
- File akan diberi nama berdasarkan input `name_file` dan format kompresi yang dipilih.

---

## Persiapan Lingkungan
Workflow ini akan menginstal beberapa alat yang diperlukan, seperti:
- `gdown` untuk unduhan dari Google Drive
- `mediafire-dl` untuk tautan MediaFire
- `megacmd` untuk tautan Mega.nz

---

## Perangkat yang Didukung
### Saat ini mendukung:
1. **b860h**
2. **hg680p**

---

## Kontribusi
Silakan fork repository ini, lakukan modifikasi, dan kirim pull request. Kontribusi sangat diterima!

---

## Credits
 * [Alam Singgasana](https://www.facebook.com/share/p/ZTPHECCPmVH2nSjZ/?mibextid=oFDknk)
 * [ULO Builder](https://github.com/armarchindo/ULO-Builder/blob/main/ulo)
 * [gdown](https://github.com/wkentaro/gdown)
 * [mediafire-dl](https://github.com/Juvenal-Yescas/mediafire-dl)
 * [megacmd](https://github.com/meganz/MEGAcmd)

---

## Lisensi
Proyek ini dilisensikan di bawah **Lisensi MIT**.
