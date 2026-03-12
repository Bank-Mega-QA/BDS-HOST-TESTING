# 🤝 Panduan Kontribusi (Contributing Guidelines)

Terima kasih atas minat Anda untuk berkontribusi pada project **BDS Host Testing**! Dokumen ini berisi standar dan aturan main agar kode kita tetap rapi, mudah dibaca, dan minim konflik.

---

## 🌿 Git Workflow

Kami menggunakan alur kerja standar Git. Mohon ikuti langkah-langkah berikut saat mengerjakan fitur atau perbaikan baru:

1. **Pull Terbaru:** Selalu mulai dengan menarik data terbaru dari branch `main`.
   ```bash
   git checkout main
   git pull origin main
   ```

2. **Buat Branch Baru:** Jangan coding langsung di `main`. Gunakan format nama branch:
   - New Branch: `branch/nama-kamu` (Contoh: `branch/kiora`)
   ```bash
   git checkout -b branch/kiora
   ```

3. **Commit:** Berikan pesan commit yang jelas.
   - ✅ `Feat: Add validation for Login module`
   - ✅ `Fix: Correct expected result on TC-021`
   - ❌ `Update script`

4. **Push & Pull Request:** Push branch Anda dan buat Pull Request (PR) di repository.

---

## 📝 Naming Convention (Standar Penamaan)

Konsistensi penamaan adalah kunci kerapian project ini.

### 1. Test Cases (TC)

Format: `[TIPE]-[LEVEL]-[MENU] - [DESKRIPSI]`

- **TIPE:** `P` (Positive), `N` (Negative)
- **LEVEL:** `TC` (Test Case), `TS` (Test Suite)
- **MENU:** Nama modul/menu yang dites (Kapital)

**Contoh:**
- ✅ `P-TC-LOGIN - Login dengan Kredensial Valid`
- ✅ `N-TC-LOGIN - Login dengan Password Salah`
- ✅ `P-TC-DASHBOARD - Validasi Data Transaksi`
- ❌ `Cek Login` (Terlalu umum)

### 2. Object Repository (OR)

Format: `[NO].[TIPE]-[NAMA]`

Gunakan penomoran untuk mengurutkan elemen berdasarkan letaknya dari atas ke bawah halaman.

- **TIPE:** `Button`, `Label`, `Input`, `Dropdown`, `Table`, `Link`

**Contoh:**
- `01. Input - Username`
- `02. Input - Password`
- `03. Button - Login`
- `04. Label - Error Message`

### 3. Variables

- **Local Variable:** camelCase → `nomorRekening`, `namaUser`
- **Global Variable:** PascalCase diawali `G_` → `G_TimeoutDuration`, `G_BaseURL`

---

## 🚫 Coding Standards (Do's and Don'ts)

### ✅ DO (Lakukan)

- **Gunakan Custom Keywords:** Gunakan Keywords yang sudah tersedia untuk logika yang berulang — jangan tulis ulang dari nol.
- **Gunakan Template:** Awali setiap script TC dengan template setup yang ada di [User Guide](USER_GUIDE.md).
- **Validasi:** Setiap aksi penting harus ada validasi (`WebUI.verifyElementVisible()` / `WebUI.verifyElementText()`).
- **Data Dinamis:** Gunakan Global Variable untuk data kredensial (`G_PasswordLogin`) — jangan di-*hardcode* di dalam script.
- **Gunakan WebUI Wait:** Gunakan `WebUI.waitForElementVisible()` untuk menunggu elemen sebelum berinteraksi.

### ❌ DON'T (Jangan Lakukan)

- **Hardcoded Sleep:** Hindari `Thread.sleep(5000)`. Gunakan `WebUI.waitForElementVisible()` atau `WebUI.waitForPageLoad()`.
- **Duplicate Objects:** Jangan membuat object baru di Repository jika sudah pernah dibuat sebelumnya. Cari dulu!
- **Sensitive Data:** Jangan pernah meng-commit password asli/production ke dalam Git.
- **Direct Edit di `main`:** Selalu gunakan branch terpisah untuk setiap perubahan.

---

## 🐛 Melaporkan Bug (Issue Reporting)

Jika Anda menemukan bug pada Framework (bukan bug aplikasinya), silakan buat Issue dengan format:

1. **Judul:** Deskriptif → *WebUI.verifyElementText gagal pada halaman Dashboard*
2. **Langkah Reproduksi:** Step-by-step kejadian
3. **Log Error:** Lampirkan log error dari Console Katalon
4. **Environment:** OS, Versi Katalon, Versi Chrome

👉 [Submit an Issue](https://github.com/Bank-Mega-QA/BDS-HOST-TESTING/issues)

---

[⬅️ Kembali ke Halaman Utama](https://github.com/Bank-Mega-QA/BDS-HOST-TESTING/blob/main/README.md)

---

*Internal use only. All content is confidential.*
