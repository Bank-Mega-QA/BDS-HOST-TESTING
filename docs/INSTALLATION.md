# 🚀 Instalasi & Konfigurasi — BDS Host Testing

Dokumen ini menjelaskan langkah-langkah untuk mengatur lingkungan pengembangan (*environment*) agar dapat menjalankan **BDS Host Testing Automated Test Suite**.

---

## 📋 Prasyarat (Prerequisites)

Sebelum melakukan instalasi, pastikan sistem operasi dan tools berikut sudah siap:

| Tool | Versi | Deskripsi | Download |
| :--- | :--- | :--- | :--- |
| **Katalon Studio** | Latest | IDE utama untuk menjalankan automation test | [GitHub Releases](https://github.com/katalon-studio/katalon-studio/releases) |
| **Google Chrome** | Latest | Browser utama untuk web testing | [Download Chrome](https://www.google.com/chrome/) |
| **Git** | Latest | Untuk clone repository | [Download Git](https://git-scm.com/downloads) |

---

## 📥 Panduan Instalasi Langkah-demi-Langkah

### 1. Install Katalon Studio

1. Buka halaman rilis resmi:
   👉 [https://github.com/katalon-studio/katalon-studio/releases](https://github.com/katalon-studio/katalon-studio/releases)

2. Download versi **terbaru** sesuai OS kamu:
   - **Windows** → `Katalon_Studio_Windows_64-XX.X.X.zip`
   - **macOS (Apple Silicon)** → `Katalon.Studio.Arm64.dmg`

3. **Windows:** Extract file `.zip`, lalu jalankan `katalon.exe`
   **macOS:** Buka file `.dmg`, drag Katalon ke folder Applications

4. Buka Katalon Studio, lalu **login** atau **buat akun** jika belum punya

> 💡 Katalon Studio memerlukan koneksi internet untuk aktivasi lisensi pertama kali.

---

### 2. Install Google Chrome

Pastikan **Google Chrome** sudah terinstall dan dalam versi terbaru.

👉 [Download Google Chrome](https://www.google.com/chrome/)

> ⚠️ ChromeDriver dikelola otomatis oleh Katalon Studio — tidak perlu install manual.

---

### 3. Clone Repository

Pilih salah satu cara berikut:

#### Menggunakan Git CLI

```bash
git clone https://github.com/Bank-Mega-QA/BDS-HOST-TESTING.git
cd BDS-HOST-TESTING
```

#### Menggunakan GitHub Desktop

1. Buka **GitHub Desktop**
2. Klik **File → Clone Repository**
3. Pilih tab **URL**, masukkan:
   ```
   https://github.com/Bank-Mega-QA/BDS-HOST-TESTING
   ```
4. Pilih folder tujuan, lalu klik **Clone**

---

### 4. Buka Project di Katalon Studio

1. Buka **Katalon Studio**
2. Klik **Open Project**
3. Arahkan ke folder hasil clone `BDS-HOST-TESTING/`
4. Klik **OK** — project akan otomatis ter-load

---

### 5. Konfigurasi Browser

1. Di Katalon Studio, buka **Project → Settings → Execution**
2. Pada bagian **Default Execution**, pilih **Chrome**
3. Klik **Apply and Close**

---

### 6. Konfigurasi Desired Capabilities

> 📝 *Bagian ini akan diisi oleh tim QA — coming soon.*

---

## ⚙️ Konfigurasi Global Variable

<details>
<summary><strong>⚙️ Konfigurasi Global Variable (via Katalon UI)</strong></summary>

Setelah project ter-load, buka **Profiles → default** di Katalon Studio dan sesuaikan nilai variabel berikut:

| GlobalVariable | Wajib? | Deskripsi | Contoh Value |
| :--- | :---: | :--- | :--- |
| *(coming soon)* | — | — | — |

> 📝 *Konfigurasi ini akan diisi oleh tim QA.*

</details>

<details>
<summary><strong>⚙️ Konfigurasi Global Variable (via Code Editor)</strong></summary>

Global Variable juga dapat dikonfigurasi langsung melalui file profile.

### 📂 Lokasi File

```
Profiles/default.glbl
```

### 📝 Langkah Edit Manual

1. Buka project menggunakan VS Code, IntelliJ, atau code editor lainnya
2. Buka file `Profiles/default.glbl`
3. Sesuaikan nilai variabel yang diperlukan
4. Save file

### 🔄 Setelah Edit

1. Buka kembali Katalon Studio
2. Klik kanan project → **Refresh**, atau tekan:
   ```
   Windows : Ctrl + Shift + R
   Mac     : Cmd  + Shift + R
   ```
3. Masuk ke **Profiles → default** dan pastikan semua variabel sudah muncul

### ⚠️ Catatan Penting

- Jangan mengubah struktur XML
- Jangan menghapus `<defaultProfile>true</defaultProfile>`
- Gunakan data *dummy* untuk repository — jangan push kredensial asli ke Git

</details>

---

## ✅ Verifikasi Instalasi

Jalankan salah satu Test Case sederhana untuk memastikan environment sudah berjalan:

1. Buka folder **Test Cases/** di panel kiri
2. Klik kanan salah satu Test Case → **Run → Chrome**
3. Jika browser terbuka dan test berjalan → ✅ instalasi berhasil!

---

## 🆘 Troubleshooting

| Masalah | Solusi |
| :--- | :--- |
| Katalon tidak bisa login | Pastikan koneksi internet aktif |
| Chrome tidak terdeteksi | Update Chrome ke versi terbaru |
| Project tidak ter-load | Pastikan folder clone lengkap dan tidak korup |
| ChromeDriver error | Restart Katalon Studio dan coba lagi |
| Global Variable kosong | Cek file `Profiles/default.glbl` dan refresh project |

---

Butuh bantuan lebih lanjut? 👉 [Submit an Issue](https://github.com/Bank-Mega-QA/BDS-HOST-TESTING/issues)

[⬅️ Kembali ke Halaman Utama](https://github.com/Bank-Mega-QA/BDS-HOST-TESTING/blob/main/README.md)

---

*Internal use only. All content is confidential.*
