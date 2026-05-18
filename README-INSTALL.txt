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


UPDATE FAST LOGIN:
- Saat tombol Login/Aktivasi/Daftar Staff diklik, layar loading langsung muncul.
- Tombol berubah status agar user merasa aplikasi langsung merespon.
- Dashboard dibuka lebih cepat karena penyimpanan cloud lanjutan berjalan di background.
- Delay cek members dipangkas agar tidak terasa lama.


UPDATE V6 - MEMBERS AUTO FIX:
Jika akun Owner lama sudah punya dokumen tenants/{uid}, tetapi belum punya members/{uid}, app.html akan otomatis membuat:
members/{uid}
  tenantId: uid
  role: Owner
  status: Aktif

Jika akun belum punya tenant/perusahaan, app akan memberi pesan jelas:
- Customer baru harus Aktivasi Pembeli pakai License Code.
- Admin license harus masuk lewat admin-license.html, bukan app.html.
