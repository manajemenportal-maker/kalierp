KALIERP ADMIN V3 - TAMBAH KUOTA USER CUSTOMER LAMA

FILE:
- index.html = landing page
- app.html = aplikasi ERP
- admin-license.html = panel admin membuat license dan upgrade kuota user
- firestore.rules = rules Firebase terbaru
- license-sample.json = contoh license

CARA MENAMBAH KUOTA USER CUSTOMER LAMA:
1. Upload admin-license.html atau buka lokal.
2. Login admin.
3. Buka tab "Tambah Kuota Existing".
4. Cari customer dengan Tenant ID atau License Code lama.
5. Isi "Kuota User Baru / Total User Setelah Upgrade".
   Contoh: dari 3 user jadi 7 user, isi 7.
6. Isi tanggal valid sampai baru.
7. Klik "Simpan Upgrade Kuota".

RUMUS:
Starter  = Rp 23.000 x total user aktif paket
Business = Rp 75.000 x total user aktif paket

CONTOH:
Business lama 3 user = 3 x 75.000 = 225.000/bulan
Upgrade jadi 7 user = 7 x 75.000 = 525.000/bulan
Tambahan bayar per bulan = 4 x 75.000 = 300.000/bulan

PENTING:
Pasang firestore.rules baru dari paket ini, karena admin panel v3 butuh akses admin untuk membaca dan mengupdate tenants.


UPDATE V5 - ADMIN NORMAL LOGIN FIXED:
- admin-license.html hanya memakai login normal Email/Password.
- Tidak ada Google Login.
- Ada tombol Reset Password untuk email admin.
- Error login dibuat lebih jelas.

CARA MEMASTIKAN LOGIN NORMAL BERHASIL:
1. Firebase Console > Authentication > Sign-in method
   Aktifkan Email/Password.

2. Firebase Console > Authentication > Users
   Pastikan ada user:
   kalimayasuryaalam@gmail.com

3. Kalau belum ada:
   Klik Add user
   Email: kalimayasuryaalam@gmail.com
   Password: buat password baru minimal 6 karakter

4. Kalau user sudah ada tapi login tetap salah:
   Klik Reset Password dari admin-license.html
   atau dari Firebase Authentication > Users > pilih user > Reset password.

PENTING:
Password Gmail tidak otomatis sama dengan password Firebase Email/Password.
