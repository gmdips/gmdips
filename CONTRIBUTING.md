<div align="center">

![Welcome](https://img.shields.io/badge/Welcome-Contributor-brightgreen?style=for-the-badge)

**Panduan berkontribusi untuk website GDIPS**

[🇮🇩 Bahasa Indonesia](#bahasa-indonesia) · [🇬🇧 English](#english)

</div>

---

## Bahasa Indonesia

### 📋 Daftar Isi

- [Mulai Cepat](#mulai-cepat)
- [Jenis Kontribusi](#jenis-kontribusi)
- [Setup Lokal](#setup-lokal)
- [Struktur File](#struktur-file)
- [Standar Kode](#standar-kode)
- [Membuat Pull Request](#membuat-pull-request)
- [Melaporkan Bug](#melaporkan-bug)
- [Mengusulkan Fitur](#mengusulkan-fitur)
- [Tips untuk Pemula](#tips-untuk-pemula)

---

### ⚡ Mulai Cepat

```
1. Fork repo ini
2. Edit file (bisa langsung di GitHub, tanpa clone!)
3. Commit dengan pesan yang jelas
4. Buat Pull Request
5. Selesai! ✨
```

> **Tidak perlu install apapun.** Bisa langsung edit di browser via GitHub.

---

### 🛠 Jenis Kontribusi

#### 🐛 Fix Bug (Paling Mudah!)
- Typo di text manapun
- Link yang rusak (404)
- Gambar yang tidak muncul
- Layout yang berantakan
- Warna/spacing yang salah

#### 🎨 Perbaikan Visual
- Perbaiki responsif di mobile
- Perbaiki kontras warna
- Tambah/ubah animasi
- Perbaiki font sizing
- Tambah hover effects

#### ♿ Aksesibilitas
- Tambah `alt` text pada gambar
- Tambah `aria-label` pada tombol
- Pastikan navigasi bisa pakai keyboard
- Perbaiki kontras warna (WCAG)
- Tambah `role` attributes

#### 🌐 Terjemahan
- Terjemahkan teks English → Indonesia
- Pastikan terjemahan natural (bukan harfiah)
- Konsisten dengan istilah yang sudah ada

#### 📝 Konten
- Tulis blog post
- Tulis dokumentasi
- Perbaiki deskripsi
- Tambah FAQ

#### 📄 Halaman Baru
- Buat halaman About
- Buat halaman Contributors
- Buat halaman FAQ
- Buat halaman changelog

#### 🔍 SEO
- Perbaiki meta descriptions
- Tambah structured data
- Perbaiki heading hierarchy (h1, h2, h3...)
- Tambah sitemap entries

#### ⚡ Performa
- Optimasi ukuran gambar
- Minimalkan CSS/JS yang tidak dipakai
- Gunakan lazy loading untuk gambar
- Compress assets

---

### 🖥 Setup Lokal

#### Option 1: Tanpa Clone (Termudah)

```
1. Buka https://github.com/gmdips/site
2. Navigasi ke file yang mau diedit
3. Klik icon ✏️ (pencil) di atas kanan
4. Edit, tulis commit message, klik "Commit changes"
5. GitHub otomatis buat fork + branch + PR
```

#### Option 2: Clone & Edit Lokal

```bash
# 1. Fork repo (klik tombol Fork di GitHub)

# 2. Clone
git clone https://github.com/KAMU/site.git
cd site

# 3. Buat branch
git checkout -b fix/typo-homepage

# 4. Edit file di text editor
# Rekomendasi: VS Code

# 5. Preview (pilih salah satu)
#    - Double-click index.html → buka di browser
#    - VS Code: install "Live Server" → klik kanan → Open with Live Server
#    - python3 -m http.server 8080

# 6. Commit & push
git add .
git commit -m "fix: perbaiki typo di homepage"
git push origin fix/typo-homepage

# 7. Buat PR di GitHub
```

#### Option 3: GitHub Codespaces (Online IDE)

```
1. Buka https://github.com/gmdips/site
2. Klik tombol "Code" (hijau)
3. Pilih "Codespaces" tab
4. Klik "Create codespace"
5. Edit file di browser
6. Preview di tab terminal (port forward 8080)
7. Commit & PR langsung dari sana
```

---

### 📁 Struktur File

```
site/
├── index.html              # ← Homepage (mulai dari sini)
├── download.html           # ← Halaman download
├── about.html              # ← Halaman about
├── contributors.html       # ← Halaman kontributor
├── 404.html                # ← Halaman not found
│
├── public/
│   └── assets/
│       ├── img/            # ← Semua gambar di sini
│       │   ├── logo.png
│       │   ├── favicon.ico
│       │   └── og-image.png
│       ├── css/
│       │   ├── style.css   # ← Style utama
│       │   └── animations.css
│       └── js/
│           ├── main.js     # ← Script utama
│           └── utils.js
│
├── blog/
│   ├── index.html
│   └── posts/              # ← Blog post di sini
│
└── docs/
    ├── index.html
    └── guides/             # ← Guide di sini
```

> **Aturan penting:** Semua asset (gambar, CSS, JS) wajib di folder `public/assets/`

---

### 📏 Standar Kode

#### HTML

```html
<!-- ✅ Benar -->
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Deskripsi halaman">
    <title>Judul Halaman - GDIPS</title>
    
    <!-- CSS -->
    <link rel="stylesheet" href="public/assets/css/style.css">
</head>
<body>
    <header>
        <nav aria-label="Navigasi utama">
            <a href="index.html" aria-label="GDIPS Home">
                <img src="public/assets/img/logo.png" alt="GDIPS Logo" width="40">
            </a>
        </nav>
    </header>

    <main>
        <h1>Judul Utama</h1>
        <p>Paragraf deskripsi.</p>
        
        <!-- Gunakan semantic HTML -->
        <section aria-labelledby="heading-id">
            <h2 id="heading-id">Subjudul</h2>
        </section>
    </main>

    <footer>
        <p>&copy; 2024 GDIPS</p>
    </footer>

    <!-- JS di akhir body -->
    <script src="public/assets/js/main.js"></script>
</body>
</html>

<!-- ❌ Salah -->
<html>
<head>
    <title>gdips</title>
</head>
<body>
    <div class="header">
        <div class="nav"><a href="#">home</a></div>
    </div>
    <div class="content">
        <div class="title">Judul</div>
    </div>
</body>
</html>
```

**Aturan HTML:**
- Selalu `<!DOCTYPE html>` di baris pertama
- `<html lang="id">` untuk Bahasa Indonesia
- Semantic tags: `header`, `nav`, `main`, `section`, `article`, `footer`
- Heading hierarchy: satu `<h1>`, lalu `<h2>`, `<h3>` (tidak loncat)
- Semua gambar WAJIB punya `alt` text
- Semua link WAJIB deskriptif (bukan "klik di sini")
- CSS di `<head>`, JS sebelum `</body>`
- Indentasi: 4 spasi

#### CSS

```css
/* ✅ Benar - terorganisir */
/* ===== COMPONENTS ===== */

/* Buttons */
.btn {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.75rem 1.5rem;
    border-radius: 0.5rem;
    font-weight: 600;
    transition: all 0.2s ease;
}

.btn-primary {
    background-color: var(--color-primary);
    color: #ffffff;
}

.btn-primary:hover {
    background-color: var(--color-primary-hover);
    transform: translateY(-1px);
}

/* Responsive */
@media (max-width: 768px) {
    .btn {
        width: 100%;
        justify-content: center;
    }
}

/* ❌ Salah - semrawut */
.btn{display:inline-flex;padding:10px 20px;}
.btn:hover{background:blue;}
@media(max-width:768px){.btn{width:100%;}}
```

**Aturan CSS:**
- Gunakan CSS variables untuk warna & spacing
- Kelompokkan per component/section dengan komentar
- Mobile-first: tulis style mobile dulu, baru `@media (min-width:)` untuk desktop
-命名: `kebab-case` (`.btn-primary`, `.nav-link`)
- Jangan pakai `!important` (kecuali override library)
- Indentasi: 4 spasi

#### JavaScript

```javascript
// ✅ Benar - bersih & aman
'use strict';

/**
 * Toggle mobile navigation menu
 */
function toggleMobileNav() {
    const nav = document.querySelector('[data-nav]');
    const isOpen = nav.classList.toggle('nav--open');
    
    // Update aria attribute for accessibility
    nav.setAttribute('aria-hidden', !isOpen);
    
    // Prevent body scroll when menu is open
    document.body.classList.toggle('no-scroll', isOpen);
}

// Event listener
document.querySelector('[data-nav-toggle]')
    .addEventListener('click', toggleMobileNav);

// ❌ Salah
function toggle(){ 
    document.getElementById("nav").style.display="block";
}
```

**Aturan JS:**
- `'use strict'` di awal file
- Gunakan `const` > `let` > `var` (hindari `var`)
- Pilih element dengan `data-` attributes: `[data-nav]` bukan `#nav`
- Fungsi diberi komentar JSDoc
- Tidak ada inline JS di HTML (`onclick=""` ❌)
- Handle edge cases (null checks)

---

### 📝 Standar Commit

```
<type>: <deskripsi>

Types:
  fix       → Perbaikan bug
  feat      → Fitur baru
  style     → Perubahan visual (CSS, spacing)
  content   → Perubahan konten (text, blog)
  seo       → Perubahan SEO (meta, tags)
  a11y      → Perbaikan aksesibilitas
  i18n      → Perubahan terjemahan
  perf      → Perbaikan performa
  refactor  → Refactor kode
  docs      → Perubahan dokumentasi
  chore     → Maintenance, config, dll
```

**Contoh:**
```
fix: perbaiki typo di judul homepage
feat: tambah halaman about
style: perbaiki spacing tombol di mobile
content: tulis blog post tentang update v2.1.3
seo: tambah meta description di semua halaman
a11y: tambah alt text pada semua gambar
i18n: terjemahkan footer ke Bahasa Indonesia
perf: kompres gambar logo (200KB → 50KB)
fix(download): perbaiki link download yang rusak
style(nav): tambah hover effect pada menu
```

---

### 🔀 Membuat Pull Request

#### Checklist

```
✅ Fork & buat branch terpisah
✅ Nama branch deskriptif (fix/xxx, feat/xxx)
✅ Commit message mengikuti format
✅ Preview di local sebelum push
✅ Tidak ada broken link
✅ Tidak ada console error
✅ Responsive di mobile & desktop
✅ PR description diisi
```

#### Nama Branch

```
fix/typo-homepage
fix/broken-download-link
feat/add-about-page
style/mobile-nav-spacing
content/blog-post-v213
seo/meta-descriptions
a11y/alt-text-images
i18n/translate-footer
perf/compress-logo
```

#### Template PR

```markdown
## 📝 Perubahan
Jelaskan apa yang berubah.

## 📸 Screenshot
Before → After (taruh screenshot di sini)

## ✅ Checklist
- [ ] Sudah di-preview lokal
- [ ] Responsive di mobile
- [ ] Tidak ada console error
- [ ] Tidak ada broken link

## 🔗 Terkait Issue
Closes #nomor
```

---

### 🐛 Melaporkan Bug

#### Template

```markdown
## 🐛 Bug
Jelaskan masalahnya.

## 📍 Lokasi
Halaman: `index.html`
Elemen: Tombol download di hero section
Browser: Chrome Android
URL: https://gmdips.pages.dev/#hero

## ✅ Yang Diharapkan
...

## ❌ Yang Terjadi
...

## 📸 Screenshot
```

---

### 💡 Mengusulkan Fitur

#### Template

```markdown
## 💡 Usulan
Jelaskan fitur/halaman yang diinginkan.

## 🎯 Tujuan
Kenapa ini dibutuhkan?

## 📐 Contoh
Screenshot/mockup/deskripsi visual.

## 🔗 Referensi
Website lain yang punya fitur serupa:
- https://example.com
```

---

### 💡 Tips untuk Pemula

#### PR Pertamamu? Ikuti ini:

1. **Mulai dari issue berlabel `good first issue`**
2. **Pilih yang paling sederhana** — typo fix adalah PR pertama yang sempurna
3. **Jangan takut salah** — maintainer akan bantu koreksi di review
4. **Tanya di Discord** kalau bingung: [discord.gg/YyeZ2Sxjgf](https://discord.gg/YyeZ2Sxjgf)
5. **Baca PR orang lain** untuk belajar cara mereka kontribusi

#### Workflow yang Direkomendasikan

```
Pilih issue → Comment "saya kerjakan" → Fork → Branch → Edit → 
Preview → Commit → Push → PR → Review → Merge → 🎉
```

#### Tools yang Membantu

| Tool | Untuk | Link |
|------|-------|------|
| VS Code | Text editor | code.visualstudio.com |
| Live Server | Preview lokal | VS Code extension |
| W3C Validator | Cek HTML | validator.w3.org |
| CSS Validator | Cek CSS | jigsaw.w3.org/css-validator |
| Lighthouse | Cek performa/SEO/a11y | Chrome DevTools |
| PageSpeed Insights | Cek kecepatan | pagespeed.web.dev |
| Can I Use | Cek browser support | caniuse.com |

---

## English

### 📋 Table of Contents

- [Quick Start](#quick-start)
- [Types of Contributions](#types-of-contributions)
- [Local Setup](#local-setup)
- [Code Standards](#code-standards)
- [Pull Request Process](#pull-request-process)
- [Tips for Beginners](#tips-for-beginners)

---

### ⚡ Quick Start

```
1. Fork this repo
2. Edit a file (directly on GitHub — no install needed!)
3. Commit with a clear message
4. Open a Pull Request
5. Done! ✨
```

> **No installation required.** You can edit directly in your browser via GitHub.

---

### 🛠 Types of Contributions

#### 🐛 Bug Fixes (Easiest!)
- Typos in any text
- Broken links (404)
- Missing images
- Broken layouts
- Wrong colors/spacing

#### 🎨 Visual Improvements
- Fix mobile responsiveness
- Fix color contrast
- Add/change animations
- Fix font sizing
- Add hover effects

#### ♿ Accessibility
- Add `alt` text to images
- Add `aria-label` to buttons
- Ensure keyboard navigation works
- Fix color contrast (WCAG)
- Add `role` attributes

#### 🌐 Translation
- Translate English → Indonesian text
- Keep translations natural (not literal)
- Stay consistent with existing terms

#### 📝 Content
- Write blog posts
- Write documentation
- Improve descriptions
- Add FAQ entries

#### 📄 New Pages
- About page
- Contributors page
- FAQ page
- Changelog page

#### 🔍 SEO
- Fix meta descriptions
- Add structured data
- Fix heading hierarchy (h1, h2, h3...)
- Add sitemap entries

#### ⚡ Performance
- Optimize image sizes
- Remove unused CSS/JS
- Add lazy loading for images
- Compress assets

---

### 🖥 Local Setup

#### Option 1: No Clone (Easiest)

```
1. Open https://github.com/gmdips/site
2. Navigate to the file you want to edit
3. Click the ✏️ (pencil) icon top-right
4. Edit, write commit message, click "Commit changes"
5. GitHub automatically creates fork + branch + PR
```

#### Option 2: Clone & Edit Locally

```bash
# 1. Fork the repo (click Fork button on GitHub)

# 2. Clone
git clone https://github.com/YOU/site.git
cd site

# 3. Create branch
git checkout -b fix/typo-homepage

# 4. Edit files in your text editor
# Recommended: VS Code

# 5. Preview (pick one)
#    - Double-click index.html → opens in browser
#    - VS Code: install "Live Server" → right-click → Open with Live Server
#    - python3 -m http.server 8080

# 6. Commit & push
git add .
git commit -m "fix: typo on homepage"
git push origin fix/typo-homepage

# 7. Open PR on GitHub
```

---

### 📏 Code Standards

#### HTML Rules
- Always `<!DOCTYPE html>` on first line
- `<html lang="id">` for Indonesian content
- Use semantic tags: `header`, `nav`, `main`, `section`, `article`, `footer`
- One `<h1>` per page, then `<h2>`, `<h3>` (no skipping)
- All images MUST have `alt` text
- All links MUST be descriptive (not "click here")
- CSS in `<head>`, JS before `</body>`
- 4 spaces indentation

#### CSS Rules
- Use CSS variables for colors & spacing
- Group by component/section with comments
- Mobile-first approach
- `kebab-case` naming (`.btn-primary`)
- No `!important` (unless overriding library)
- 4 spaces indentation

#### JavaScript Rules
- `'use strict'` at file start
- Use `const` > `let` > `var` (avoid `var`)
- Select with `data-` attributes: `[data-nav]` not `#nav`
- JSDoc comments on functions
- No inline JS in HTML (`onclick=""` ❌)
- Handle edge cases (null checks)

---

### 📝 Commit Standards

```
<type>: <description>

Types:
  fix       → Bug fix
  feat      → New feature
  style     → Visual change (CSS, spacing)
  content   → Content change (text, blog)
  seo       → SEO change (meta, tags)
  a11y      → Accessibility fix
  i18n      → Translation change
  perf      → Performance fix
  refactor  → Code refactor
  docs      → Documentation change
  chore     → Maintenance, config, etc.
```

---

### 🔀 Pull Request Process

#### Checklist
```
✅ Forked & created separate branch
✅ Branch name is descriptive (fix/xxx, feat/xxx)
✅ Commit message follows format
✅ Previewed locally before push
✅ No broken links
✅ No console errors
✅ Responsive on mobile & desktop
✅ PR description filled in
```

---

### 💡 Tips for Beginners

1. **Start with `good first issue` labeled issues**
2. **Pick the simplest** — a typo fix is the perfect first PR
3. **Don't be afraid of mistakes** — maintainers will help in review
4. **Ask on Discord** if confused: [discord.gg/YyeZ2Sxjgf](https://discord.gg/YyeZ2Sxjgf)
5. **Read other PRs** to learn how others contribute

#### Helpful Tools

| Tool | Purpose | Link |
|------|---------|------|
| VS Code | Text editor | code.visualstudio.com |
| Live Server | Local preview | VS Code extension |
| W3C Validator | Check HTML | validator.w3.org |
| Lighthouse | Check perf/SEO/a11y | Chrome DevTools |
| PageSpeed Insights | Check speed | pagespeed.web.dev |

---

<div align="center">

## 💬 Questions?

[![Discord](https://img.shields.io/badge/Discord-Ask_Here-5865F2?style=for-the-badge&logo=discord)](https://discord.gg/YyeZ2Sxjgf)

---

> *"Tidak ada kontribusi yang terlalu kecil. Satu typo fix sudah membantu."*

**Selamat berkontribusi! 🎉**

![Divider](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

</div>
