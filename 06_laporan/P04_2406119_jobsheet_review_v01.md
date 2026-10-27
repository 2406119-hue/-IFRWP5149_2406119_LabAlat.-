## Situasi A — Mahasiswa Mengakses Kalender Akademik Tanpa Asosiasi Langsung

Berdasarkan diagram, situasi ini dinyatakan valid karena mahasiswa tetap dapat menjalankan SIA-UC07 meskipun tidak memiliki garis asosiasi langsung dengan use case tersebut.

Hal ini didasarkan pada hubungan *generalization* antara Mahasiswa dan Civitas Akademika, dengan segitiga kosong mengarah ke Civitas Akademika. Asosiasi Civitas Akademika dengan SIA-UC07 memungkinkan mahasiswa mewarisi kemampuan interaksi aktor umum tersebut. Sesuai aturan UML 2.5.1 dari OMG, aktor khusus dapat menjalankan interaksi yang tersedia bagi aktor umum. Oleh karena itu, asosiasi tidak perlu digambarkan ulang dari Mahasiswa maupun Dosen.

## Situasi B — Dosen yang Bukan Pengampu Mencoba Menginput Nilai

Berdasarkan deskripsi SIA-UC08, sistem harus menolak permintaan dosen yang bukan pengampu mata kuliah terpilih. Pada langkah kedua alur utama, sistem melakukan pemeriksaan terhadap status dosen sebagai pengampu. Jika persyaratan tersebut tidak terpenuhi, alur alternatif A1 dijalankan.

Sistem kemudian menampilkan pesan bahwa penginputan nilai hanya dapat dilakukan oleh dosen pengampu. Formulir input tidak ditampilkan dan tidak ada nilai yang disimpan ke dalam sistem.

Dasarnya adalah prasyarat SIA-UC08, kebutuhan SIA-R08 yang membatasi penginputan nilai pada mata kuliah yang diampu dosen, serta aturan batas dalam dokumen kebutuhan. Asosiasi Dosen dengan SIA-UC08 menunjukkan bahwa dosen dapat mengakses fungsi tersebut, sedangkan pembatasan mata kuliah yang boleh diproses ditentukan dalam alur use case.

## Situasi C — Admin Akademik Menghapus Data Mahasiswa yang Masih Memiliki Data Akademik Aktif

Sesuai aturan tugas, sistem harus menolak penghapusan data mahasiswa yang masih memiliki data akademik aktif. Alur alternatif SIA-UC13 dijalankan dengan menampilkan alasan penolakan kepada admin akademik. Data mahasiswa tetap tersimpan dan tidak mengalami perubahan.

Ketentuan ini mengacu pada perilaku SIA-UC13 yang membatasi penghapusan hanya untuk mahasiswa tanpa data akademik aktif, serta aturan batas dalam dokumen kebutuhan. Admin Akademik tetap memiliki hak untuk menjalankan SIA-UC13 melalui asosiasi dengan use case umum SIA-UC10. Namun, hak akses tersebut tidak berarti semua tindakan penghapusan dapat dilakukan, karena keberhasilannya tetap bergantung pada kondisi data mahasiswa.