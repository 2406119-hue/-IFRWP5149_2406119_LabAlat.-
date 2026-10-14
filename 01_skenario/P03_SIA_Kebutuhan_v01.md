Skenario tugas: 
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap 
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, 
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, 
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen 
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih 
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS 
dan memberikan catatan keputusan. 

|   ID	        | Tugas / Kebutuhan Sistem                                                 |
|------------------------------------------------------------------------------------------|
|   SIA-R01	    | Mahasiswa dapat melihat jadwal kuliah                                    |
|   SIA-R02 	| Admin akademik dapat mengelola jadwal kuliah                             |
|   SIA-R03 	| Mahasiswa dapat mengajukan KRS                                           |
|   SIA-R04 	| Sistem memvalidasi KRS sebagai bagian pengajuan                          |
|   SIA-R05 	| Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan|
|   SIA-R06 	| Dosen wali dapat memproses persetujuan atau penolakan KRS                |


Kode dimulai dari R03 agar kebutuhan jadwal SIA-R01 dan SIA-R02 dari 
Pertemuan 2 tetap mempunyai identitas berbeda. 
Batas dan asumsi: 
• Pengguna telah terautentikasi. 
• Data mata kuliah, prasyarat, dan jadwal tersedia. 
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan. 
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan. 
• KRS tersimpan belum berarti disetujui. 
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar 
tugas. 


|Aktor	        |Tujuan terhadap sistem                                                                     |
|-----------------------------------------------------------------------------------------------------------|
|Mahasiswa	    |Melihat jadwal kuliah, memilih mata kuliah, mengajukan KRS, dan mengunduh bukti pengajuan. |
|Admin Akademik	|Mengelola jadwal kuliah.                                                                   |
|Dosen Wali  	|Memproses pengajuan KRS, menyetujui atau menolak KRS, dan memberikan catatan keputusan.    |


ID	        Nama use case	        Peran dalam model

SIA-R01	    Lihat jadwal kuliah	    Fungsi utama mahasiswa
SIA-R02	    Kelola jadwal kuliah	Fungsi utama admin akademik
SIA-R03	    Ajukan KRS	            Fungsi utama mahasiswa
SIA-R04	    Validasi KRS	        Perilaku yang disertakan pada R03
SIA-R05	    Unduh bukti pengajuan	Tambahan bersyarat pada R03
SIA-R06	    Proses keputusan KRS	-


lima keputusan pemodelan:

1. SIA-R03 <<include>> SIA-R04
Alasan: Setiap pengajuan KRS wajib menjalankan validasi untuk memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal.

2. SIA-R05 <<extend>> SIA-R03
Extension point: Bukti pengajuan tersedia.
Kondisi: Mahasiswa memilih mengunduh bukti pengajuan.
Alasan: Pengajuan KRS tetap berhasil meskipun mahasiswa tidak mengunduh bukti pengajuan.

3. SIA-R03 <<include>> SIA-R06
Alasan: Setiap pengajuan KRS harus memeriksa kelengkapan data pengajuan sebelum pengajuan dinyatakan valid.

4. SIA-R07 <<extend>> SIA-R03
Extension point: Pengajuan KRS berhasil disimpan.
Kondisi:Validasi KRS berhasil dan mahasiswa memilih mengunduh bukti pengajuan pada konfirmasi penyimpanan.
Alasan: Pengunduhan bukti merupakan proses opsional dan tidak menjadi syarat keberhasilan pengajuan.

5. SIA-R08 <<include>> SIA-R06
Alasan: Proses keputusan dosen wali mencakup pencatatan hasil persetujuan atau penolakan KRS beserta catatan keputusan.