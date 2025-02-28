# **Target Ramadan**

Sebuah aplikasi web sederhana untuk tracking target kegiatan di bulan Ramadan, seperti puasa dan sholat. Dibangun dengan **Vue.js 3**, **Tailwind CSS**, dan **Daisy UI**.

---

## **Fitur**

1. **Tracking Puasa**:

   - Daftar 30 hari puasa Ramadan.
   - User bisa mencentang hari yang sudah berpuasa.
   - Progress otomatis terupdate (contoh: 1/30).
   - Data disimpan di `localStorage` agar tidak hilang saat refresh.

2. **Tracking Sholat**:

   - Daftar 5 waktu sholat (Subuh, Dhuhur, Ashar, Maghrib, Isya) untuk setiap hari selama 30 hari.
   - Fitur collapse untuk menyembunyikan/menampilkan daftar sholat per hari.
   - Progress otomatis terupdate (contoh: 5/150).
   - Data disimpan di `localStorage` agar tidak hilang saat refresh.

3. **Tampilan Responsif**:
   - Desain menggunakan **Tailwind CSS** dan **Daisy UI** untuk tampilan yang rapi dan responsif.

---

## **Tech Stack**

- **Frontend Framework**: Vue.js 3
- **Styling**: Tailwind CSS + Daisy UI
- **Build Tool**: Vite
- **State Management**: LocalStorage
- **Routing**: Vue Router (jika diperlukan)

---

### **Tools for help**: Deepseek

---

## **Instalasi**

1. **Clone Repo**:

   ```bash
   git clone https://github.com/username/target-ramadan.git
   cd target-ramadan
   ```

2. **Instal Dependencies**:

   ```bash
   npm install
   ```

3. **Jalankan Aplikasi**:

   ```bash
   npm run dev
   ```

   Aplikasi akan berjalan di `http://localhost:5173`.

4. **Build untuk Produksi**:

   ```bash
   npm run build
   ```

5. **Preview Build**:
   ```bash
   npm run preview
   ```

---

## **Dependencies**

### **Dependencies Utama**

- `vue`: Framework utama untuk membangun aplikasi.
- `tailwindcss`: Utility-first CSS framework untuk styling.
- `@tailwindcss/vite`: Plugin Vite untuk Tailwind CSS.

### **Dev Dependencies**

- `vite`: Build tool modern.
- `@vitejs/plugin-vue`: Plugin Vite untuk Vue.js.
- `daisyui`: Komponen UI yang dibangun di atas Tailwind CSS.
- `vite-plugin-vue-devtools`: Plugin untuk Vue DevTools.

---

## **Cara Berkontribusi**

1. Fork repositori ini.
2. Buat branch baru (`git checkout -b fitur-baru`).
3. Commit perubahan Anda (`git commit -m 'Tambahkan fitur baru'`).
4. Push ke branch (`git push origin fitur-baru`).
5. Buat Pull Request.

---

## **Lisensi**

Proyek ini dilisensikan di bawah [MIT License](LICENSE).

---

## **Catatan**

- Aplikasi ini dibuat untuk membantu tracking kegiatan Ramadan secara sederhana.
- Jika ada bug atau saran, silakan buka [issue](https://github.com/sasakiRoo/target-ramadan/issues).
