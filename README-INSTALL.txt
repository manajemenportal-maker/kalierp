KALIERP PROTECTED PER USER FINAL

FILE:
- index.html = landing page jualan
- app.html = aplikasi ERP
- firestore.rules = pasang di Firebase Firestore Rules
- license-sample.json = contoh data license code

HARGA:
- Starter = Rp 23.000 / user / bulan
- Business = Rp 75.000 / user / bulan
- Lifetime = Rp 1.500.000 sekali bayar

PROTEKSI:
- Owner tidak bisa daftar bebas.
- Owner wajib punya License Code dari collection Firestore: licenses
- License status harus Available.
- Setelah dipakai, license menjadi Used.
- Tenant menyimpan subscription: plan, status, userLimit, pricePerUser, monthlyAmount, validUntil.
- Staff tidak bisa daftar kalau kuota user penuh.
- Jika status bukan Active atau validUntil habis, aplikasi terkunci dan diarahkan upgrade via WhatsApp.

CARA BUAT LICENSE MANUAL DI FIREBASE:
Firestore Database > Data > Start collection
Collection ID: licenses
Document ID: KALI-BUSINESS-001

Fields contoh:
plan: Business
status: Available
pricePerUser: 75000
userLimit: 5
billingCycle: monthly
validUntil: 2026-06-18

Untuk Starter:
pricePerUser: 23000
userLimit: sesuai jumlah user yang dibeli

Untuk Lifetime:
plan: Lifetime
status: Available
pricePerUser: 0
oneTimePrice: 1500000
billingCycle: lifetime
validUntil: 2099-12-31

UPLOAD:
Upload index.html dan app.html ke domain.
Copy isi firestore.rules ke Firebase Console > Firestore Database > Rules > Publish.
