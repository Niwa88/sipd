# Dokumentasi Sistem Informasi Presensi Digital
<br>

## Deskripsi Alur Sistem (Naratif)

Sistem presensi ini berjalan dengan dua jenis aktor utama, yaitu **Admin** dan **User**, yang masing-masing memiliki peran berbeda namun saling berkaitan.

### **1. Peran & Alur Admin**


Admin memulai proses dengan melakukan **login** untuk mengakses seluruh fitur manajemen dalam sistem. Setelah berhasil masuk, Admin dapat melakukan berbagai pengelolaan, seperti:


* **Mengelola data user**

  * Membuat akun user baru
  * Menampilkan daftar user
  * Mencari data user
  * Mengubah atau menghapus data user

* **Mengelola kode presensi**

  * Membuat kode presensi
  * Membaca informasi kode presensi
  * Memperbarui kode presensi
  * Menghapus kode presensi

* **Memantau aktivitas user**

  * Melihat riwayat login setiap user

Fitur-fitur ini memungkinkan Admin memantau dan mengelola operasional sistem secara menyeluruh.


### **2. Peran & Alur User**

User memulai interaksi dengan sistem melalui halaman **login**. Setelah berhasil masuk, User dapat melakukan:

* **Presensi**

  * Memasukkan kode presensi yang sedang aktif
  * Data presensi otomatis tersimpan sebagai bagian dari riwayat pribadi

* **Melihat riwayat presensi**

  * Melihat daftar kehadiran pada tanggal-tanggal sebelumnya

* **Mengelola akun**

  * Memperbarui password
  * Mengganti foto profil


### **3. Kesimpulan Alur Sistem**

Secara keseluruhan, alur sistem menggambarkan hubungan yang jelas antara **Admin sebagai pengelola utama** dan **User sebagai pelaksana presensi**.
Setiap aktivitas — mulai dari manajemen user, pembuatan kode presensi, hingga presensi harian — tercatat dengan baik sehingga sistem menjadi:

* Terstruktur
* Transparan
* Mudah dipantau

---  
<br>

## USE CASE DESCRIPTION  

### 1. Use Case: Login Admin

**Aktor:** Admin  
**Deskripsi:** Admin masuk ke sistem menggunakan email dan password untuk mengakses fitur manajemen.  
**Precondition:** Admin sudah terdaftar.  
**Trigger:** Admin membuka halaman login.  

**Alur Utama:**  
1. Admin memasukkan email dan password.
2. Sistem memvalidasi akun.
3. Admin berhasil masuk ke dashboard.  
   **Postcondition:** Admin berada pada halaman utama sistem.  
   **Exception:** Email atau password salah → sistem menampilkan pesan error.

### 2. Use Case: Create User

**Aktor:** Admin  
**Deskripsi:** Admin membuat akun user baru.  
**Precondition:** Admin sudah login.  
**Trigger:** Admin memilih menu tambah user.  
**Alur Utama:**  
1. Admin mengisi data user (nama, email, no telepon, password).
2. Sistem memvalidasi form.
3. Sistem menyimpan data user.
4. Sistem menampilkan pesan berhasil.
  **Postcondition:** Data user baru tersimpan.  
  **Exception:** Nip duplicate → sistem menolak penyimpanan.  

### 3. Use Case: Read & Search User

**Aktor:** Admin  
**Deskripsi:** Admin melihat daftar user dan melakukan pencarian.  
**Precondition:** Admin sudah login.  
**Trigger:** Admin membuka halaman daftar user.  

**Alur Utama:**  
1. Sistem menampilkan seluruh user.
2. Admin memasukkan kata kunci.  
3. Sistem menampilkan hasil pencarian.  
   **Postcondition:** Data user tampil sesuai filter.
   **Exception:** Data tidak ditemukan → tampil pesan "tidak ada hasil".

### 4. Use Case: Update User

**Aktor:** Admin  
**Deskripsi:** Mengubah data user.  
**Precondition:** Admin sudah login.  
**Trigger:** Admin memilih user yang akan diedit.  
**Alur Utama:**
1. Sistem menampilkan form edit.
2. Admin mengubah data.
3. Sistem menyimpan dan memperbarui database.  
   **Postcondition:** Data user ter-update.  
   **Exception:** Validasi gagal → perubahan dibatalkan. 

### 5. Use Case: Delete User

**Aktor:** Admin  

**Deskripsi:** Admin menghapus akun user.  

**Precondition:** Admin sudah login.  

**Trigger:** Admin memilih hapus pada data user.  

**Alur Utama:**  
1. Admin mengonfirmasi penghapusan.
2. Sistem menghapus data dari database.  
   Postcondition: Data user terhapus.  
   Exception: Admin membatalkan penghapusan.

6. Use Case: Create Kode Presensi

Aktor: Admin
Deskripsi: Membuat kode presensi yang dipakai user untuk absen.
Precondition: Admin sudah login.
Trigger: Admin memilih menu kode presensi.
Alur Utama:

Admin memasukkan kode & informasi pendukung.

Sistem memvalidasi dan menyimpan.
Postcondition: Kode presensi aktif dan tersimpan.
Exception: Kode sudah digunakan sebelumnya.

7. Use Case: Read / Update / Delete Kode Presensi

Aktor: Admin
Deskripsi: Mengelola data kode presensi.
Precondition: Admin sudah login.
Trigger: Admin membuka halaman kode presensi.
Alur Utama:

Sistem menampilkan daftar kode presensi.

Admin dapat mengedit atau menghapus data.
Postcondition: Data presensi berubah sesuai tindakan Admin.
Exception: Kode tidak ditemukan atau konflik data.

8. Use Case: Read & Search Riwayat Login

Aktor: Admin
Deskripsi: Admin melihat riwayat login semua user.
Precondition: Admin sudah login.
Trigger: Admin membuka menu riwayat login.
Alur Utama:

Sistem menampilkan riwayat login.

Admin dapat memfilter berdasarkan user/tanggal.
Postcondition: Riwayat login tampil sesuai filter.
Exception: Data tidak ditemukan.

USE CASE UNTUK USER
9. Use Case: Login User

Aktor: User
Deskripsi: User masuk ke sistem untuk melakukan presensi.
Precondition: User memiliki akun.
Trigger: User membuka halaman login.
Alur Utama:

User memasukkan email & password.

Sistem memvalidasi dan mengarahkan ke dashboard.
Postcondition: User berhasil masuk.
Exception: Password salah / akun tidak ada.

10. Use Case: Melakukan Presensi

Aktor: User
Deskripsi: User melakukan presensi menggunakan kode yang disediakan Admin.
Precondition: User login dan kode presensi aktif.
Trigger: User membuka menu presensi.
Alur Utama:

User memasukkan kode presensi.

Sistem memeriksa kevalidan kode.

Sistem mencatat presensi ke database.
Postcondition: Presensi tersimpan.
Exception: Kode tidak valid / sudah kadaluarsa.

11. Use Case: Melihat Riwayat Presensi

Aktor: User
Deskripsi: User menampilkan daftar presensi yang pernah dilakukan.
Precondition: User login.
Trigger: User membuka menu riwayat presensi.
Alur Utama:

Sistem menampilkan riwayat presensi berdasarkan user.
Postcondition: Riwayat presensi tampil.
Exception: Tidak ada data.

12. Use Case: Update Password

Aktor: User
Deskripsi: User mengubah password akun.
Precondition: User login.
Trigger: User membuka menu pengaturan akun.
Alur Utama:

User mengisi password lama dan password baru.

Sistem memvalidasi password lama.

Sistem menyimpan password baru.
Postcondition: Password berhasil diperbarui.
Exception: Password lama salah.

13. Use Case: Update Foto Profile

Aktor: User
Deskripsi: User mengganti foto profil.
Precondition: User login.
Trigger: User membuka menu profil.
Alur Utama:

User mengunggah foto baru.

Sistem memvalidasi format & ukuran gambar.

Sistem menyimpan foto baru dan mengganti foto sebelumnya.
Postcondition: Foto profil diperbarui.
Exception: Format/file tidak valid.
