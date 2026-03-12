# 📖 Panduan Penggunaan & Penulisan Test Case

Dokumen ini berisi panduan teknis cara menulis script automation menggunakan framework **BDS Host Testing**.

---

## 🏗️ Standar Struktur Test Case (Template)

Setiap *Test Case* (TC) baru **wajib** diawali dengan blok kode inisialisasi berikut. Tujuannya agar konfigurasi timeout, manajemen browser, dan penamaan folder screenshot seragam.

### 📋 Template Script

<details>
<summary><b>✅ Klik untuk Template Transaksi POSITIF</b></summary>

```groovy
// --- IMPORT STANDARD KATALON ---
import static com.kms.katalon.core.testobject.ObjectRepository.findTestObject
import com.kms.katalon.core.model.FailureHandling
import com.kms.katalon.core.webui.keyword.WebUiBuiltInKeywords as WebUI
import com.kms.katalon.core.util.KeywordUtil
import internal.GlobalVariable
import java.util.concurrent.atomic.AtomicInteger

// --- IMPORT CUSTOM KEYWORDS ---
// coming soon

// --- 1. OPEN BROWSER & NAVIGATE ---
// Selalu gunakan WebUI.openBrowser() dan navigateToUrl() — jangan hardcode URL
WebUI.openBrowser('')
WebUI.navigateToUrl(GlobalVariable.G_BaseURL)
WebUI.maximizeWindow()

// --- 2. SETUP CONFIGURATION & VARIABLES ---
// coming soon

// --- 3. SETUP SCREENSHOT DIRECTORY ---
// Format: getScreenshotDirectory("Menu", "SubMenu", "TipeTC")
// coming soon
AtomicInteger screenshotCounter = new AtomicInteger(1)

// --- MULAI SCRIPT TESTING DI BAWAH SINI ---

```

</details>

<details>
<summary><b>❌ Klik untuk Template Transaksi NEGATIF</b></summary>

```groovy
// --- IMPORT STANDARD KATALON ---
import static com.kms.katalon.core.testobject.ObjectRepository.findTestObject
import com.kms.katalon.core.model.FailureHandling
import com.kms.katalon.core.webui.keyword.WebUiBuiltInKeywords as WebUI
import com.kms.katalon.core.util.KeywordUtil
import internal.GlobalVariable
import java.util.concurrent.atomic.AtomicInteger

// --- IMPORT CUSTOM KEYWORDS ---
// coming soon

// --- 1. OPEN BROWSER & NAVIGATE ---
WebUI.openBrowser('')
WebUI.navigateToUrl(GlobalVariable.G_BaseURL)
WebUI.maximizeWindow()

// --- 2. SETUP CONFIGURATION & VARIABLES ---
// coming soon

// --- 3. SETUP SCREENSHOT DIRECTORY ---
// coming soon
AtomicInteger screenshotCounter = new AtomicInteger(1)

// --- MULAI SCRIPT TESTING NEGATIF DI BAWAH SINI ---

```

</details>

---

## 🧠 Penjelasan Custom Keywords

Framework ini memiliki beberapa *Helper* untuk menangani elemen dinamis pada web. Gunakan *keyword* ini daripada merekam (*record*) langkah manual yang berulang.

> 📝 *Dokumentasi Custom Keywords akan diisi seiring perkembangan framework.*

### 1. Browser Management
> *Coming soon*

### 2. Login Helper
> *Coming soon*

### 3. Navigation Helper
> *Coming soon*

### 4. Screenshot Helper
> *Coming soon*

### 5. Verification Helper
> *Coming soon*

### 6. Error Handling Helper
> *Coming soon*

---

## 📂 Modul yang Diuji

> 📝 *Daftar modul BDS akan diisi seiring perkembangan project.*

| Modul | Deskripsi | Status |
| :--- | :--- | :--- |
| *(coming soon)* | — | — |

---

## 💡 Tips & Best Practice

1. **Hindari Hardcoded Delay:** Jangan menulis `WebUI.delay(5)` secara manual — gunakan `WebUI.waitForElementVisible()` atau `WebUI.waitForPageLoad()` agar lebih stabil.
2. **Naming Screenshot:** Gunakan counter (`screenshotCounter++`) agar urutan gambar sesuai alur cerita (`01.png`, `02.png`, dst).
3. **Gunakan Global Variable:** Simpan URL, kredensial, dan data konfigurasi di `GlobalVariable` — jangan di-*hardcode* langsung di script.
4. **Tutup Browser:** Akhiri setiap TC dengan `WebUI.closeBrowser()` agar tidak ada sisa sesi browser yang mengganggu eksekusi berikutnya.
5. **Reuse Keywords:** Jika ada langkah yang dipakai di lebih dari satu TC, pindahkan ke Custom Keyword — jangan copy-paste script.

---

[⬅️ Kembali ke Halaman Utama](https://github.com/Bank-Mega-QA/BDS-HOST-TESTING/blob/main/README.md)

---

*Internal use only. All content is confidential.*
