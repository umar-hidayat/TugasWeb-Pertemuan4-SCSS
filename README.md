# Tugas Rutin 4: Konversi CSS ke SCSS (7-1 Pattern)

Repository ini berisi hasil *refactoring* stylesheets dari Tugas Rutin 2 (Landing Page & Portofolio Personal) menggunakan **SCSS** berbasis arsitektur **7-1 Pattern**, dikompilasi ke CSS menggunakan Dart SASS.

---

## 📁 Arsitektur Project (7-1 Pattern)

```text
TugasWeb-Pertemuan4-SCSS/
├── src/
│   └── scss/
│       ├── abstracts/      # Variables, mixins, dan index penghubung
│       │   ├── _variables.scss
│       │   ├── _mixins.scss
│       │   └── _index.scss
│       ├── base/           # CSS Reset, typography, dan root variables
│       │   ├── _reset.scss
│       │   ├── _typography.scss
│       │   └── _index.scss
│       ├── components/     # Modul UI spesifik (form, card/image)
│       │   ├── _form.scss
│       │   ├── _card.scss
│       │   └── _index.scss
│       ├── layout/         # Header, grid layout main/aside, footer
│       │   ├── _header.scss
│       │   ├── _grid.scss
│       │   ├── _footer.scss
│       │   └── _index.scss
│       ├── utilities/      # Class utility generator (@each loop)
│       │   ├── _loop.scss
│       │   └── _index.scss
│       └── main.scss       # Main entry point SCSS
├── index.html              # Dokumentasi portofolio HTML5
├── style.css               # File CSS hasil kompilasi SASS
├── style.css.map           # Source map kompilasi SASS
├── Foto_Setup.webp         # Aset gambar lokal portofolio
└── package.json            # Konfigurasi dependency & scripts

```

---

## 🛠️ Implementasi Syarat Ketentuan SCSS

1. **Variables (`_variables.scss`)**: Mengorganisasi color palette untuk *Light Mode* dan *Dark Mode*, nilai radius, dan unit spacing.
2. **Mixins (`_mixins.scss`)**:
* `flex-center`: Menangani tata letak Flexbox secara dinamis.
* `card-style`: Menyederhanakan penulisan atribut container card.
* `respond-to`: Mengatur breakpoint media query secara konsisten.


3. **Control Flow Loop (`_loop.scss`)**: Memakai `@each` untuk melakukan *generate* utility class margin bottom (`.mb-sm`, `.mb-md`, `.mb-lg`).
4. **Modern System Import**: Menggunakan aturan `@use` dan `@forward` untuk isolasi skop variabel/mixin (menghindari penggunaan `@import` yang *deprecated*).
5. **Nesting Rules**: Maksimal 3 tingkat kedalaman nesting untuk menjaga *specificity* tetap rendah dan menghindari CSS hasil kompilasi yang bloated.

---

## 🚀 Cara Menjalankan Project

1. **Install Dependency**:
```bash
npm install

```


2. **Kompilasi SCSS ke CSS**:
```bash
npx sass src/scss/main.scss style.css

```


3. **Watch Mode (Opsional untuk Development)**:
```bash
npx sass --watch src/scss/main.scss:style.css

```

