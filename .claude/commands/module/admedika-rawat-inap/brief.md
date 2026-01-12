# Brief Template - PRD Generation

**Template untuk membuat brief file sebelum generate PRD**
**Setiap field sudah include CONTOH dari REHAB_MEDIK**

---

## Format: module/[MODULE_NAME]/brief.md

Copy template ini dan isi semua 10 sections:

```markdown
# Brief - [MODULE_NAME]

## 1. Project Context

**Nama Project:**
[Bridging AdMedika Rawat Inap - Hospital Information System (HIS) V@]
=> Contoh: Rehab Medik - Hospital Information System (HIS) V2

**Klien/Organisasi:**
[Nama klien/rumah sakit/organisasi]
=> Contoh: Primaya Hospital Group  #Masih Sama

**Tujuan Sistem:**
[Jelaskan tujuan utama module ini dalam 2-3 kalimat]
=> Contoh: Mengimplementasikan modul Rehab Medik dalam sistem HIS V2 untuk memfasilitasi proses konsultasi, dokumentasi, dan pelaksanaan fisioterapi pasien. Sistem ini memungkinkan dokter, fisioterapis, dan pasien untuk berkolaborasi dalam program rehabilitasi medis dengan dokumentasi elektronik yang terintegrasi.

Implementasi Bridging AdMedika dengan HISv2 untuk memfasilitasi pasien biar bisa menggunakan payor Admedika untuk mendapatkan layanan Rawat Inap. Disini bisa cek benefit2 rawat inap seperti hak kamar, obat, tindakan, dan lainnya. 


**Background/Latar Belakang:**
[Konteks mengapa system ini dibuat, masalah apa yang dipecahkan]
=> Contoh: Rumah Sakit Primaya memerlukan sistem informasi terpadu untuk mengelola pelayanan rehabilitasi medis. Saat ini, proses konsultasi dokter, perencanaan program terapi, dan dokumentasi pelaksanaan fisioterapi masih tersebar di beberapa sistem atau bahkan manual. Sistem HIS V2 Rehab Medik akan mengintegrasikan seluruh proses tersebut dalam satu platform yang efisien, dengan fitur signature digital untuk persetujuan tindakan medis.

Saat ini ada kebutuhan dari Primaya untuk integrate ke Admedika, sudah terjadi di Rawat Jalan, tinggal lanjutin ke Rawat Inap. Adapun ada 3 pintu touchpoint dimana2 aja bisa menggunakan (terutama cek benefit):
1. Pendaftaran Rawat Inap
2. Transfer Rawat Inap
3. Migrasi Pasien


**Timeline:**
[Kapan project ini direncanakan dimulai dan selesai]
=> Contoh: Document Preparation: 1 hari (03-12-2025) | Development: TBD | QC: TBD | UAT: TBD
ya buat aja 10 hari kerja

---

## 2. Scope Overview

**Fitur Utama:**
- [Fitur 1: Integrasi Pendaftaran Pasien Admedika: nah ini payor admedika bisa dipake oleh pasien di pendaftaran]
- [Fitur 2: Cek benefit: konteks rawat inap ya]
- [Fitur 3: mapping benefits: ngejahitin apa2 aja benefit yang bisa diklaim di rawat inap ]
- [Fitur 4: Proses Claim: upload dokumen, lihat berapa yang bisa diklaim layanan apa bae]
- [Fitur 5: Daily Monitoring: Lihat Kejadian daily monitoring pasien, nanti ada contohnya]

=> Contoh:
- Konsultasi Awal Dokter: Dokter membuat form pemeriksaan rawat jalan dengan form tambahan khusus Rehab Medik (Anjuran, Evaluasi, Suspek Penyakit Akibat Kerja)
- Catatan Terintegrasi Fisioterapis: Fisioterapis membuat catatan SOAP dan mendapatkan signature digital dari Pasien
- Manajemen Kehadiran Program: Sistem tracking untuk kehadiran dan ketidakhadiran pasien dalam program fisioterapi
- Penyelesaian Sesi Terapi: Fisioterapis menutup sesi terapi dengan pencatatan hasil dan progres pasien
- Evaluasi Dokter: Dokter me-review seluruh dokumentasi pelaksanaan fisioterapi dan membuat evaluasi

**Tidak termasuk dalam scope:**
- [Hal yang OUT OF SCOPE 1: Penentuan ekses billing, karena masih dilakukan manual di kasir oleh admimsi ini perlu effort human kalo ada ekses (lebih bayar)]
- [Hal yang OUT OF SCOPE 2: Proses lock billing, ini juga perlu diantisipasi oleh kasir, kalo udah diproses claim ini gab oleh ditambah2kan lagi, nanti bisa dikasi notif ini gab oleh dibuka (unlock billing) dan tambahin layanan lagi]

=> Contoh:
- Manajemen tarif/billing untuk layanan fisioterapi
- Integrasi dengan peralatan fisioterapi (TENS, Ultrasound, Laser)
- Report analytics dan business intelligence untuk Rehab Medik
- Mobile app untuk patient engagement

**Integrasi dengan sistem lain:**
- [Sistem A: dengan sistem Admedika]
// pelajari aja dari screenshots yang aku buat ya
- [Sistem B: apa data yang ditukar]

=> Contoh:
- EMR System: Pull data pasien, diagnosis, riwayat medis
- Master Data: Retrieve data dokter, fisioterapis, program terapi standard
- Appointment System: Integrasi dengan jadwal layanan fisioterapi
- Document Management: Penyimpanan dan retrieval dokumen digital yang ditandatangani

---

## 3. User Personas

### Persona 1: [Admisi] ==> persona 2 nya [kasir] // sesuaikan aja, terus casemix (generate aja goals2nya sesuai user persna)


## 4. User Stories Overview

// generate dari screenshots adjust2 aja storynya yak seperti ini. Yang pasti dimulai proses step seperti ini:
1. Pendaftaran
2. Cek benefit
3. Daily monitoring
4. Proses klaim

**Total Stories:** [Jumlah - minimal 3, maksimal 5]
=> Contoh: 5

Daftar stories yang akan di-generate:

1. **Story 1: [Judul Story]**
   - Persona: [Yang digunakan]
   - Deskripsi: [Singkat apa yang dilakukan]

2. **Story 2: [Judul Story]**
   - Persona: [Yang digunakan]
   - Deskripsi: [Singkat apa yang dilakukan]

3. **Story 3: [Judul Story]**
   - Persona: [Yang digunakan]
   - Deskripsi: [Singkat apa yang dilakukan]

=> Contoh:
1. **Story 1: Pasien Konsul ke Dokter Rehab Medik Pertama Kali**
   - Persona: Dokter
   - Deskripsi: Dokter membuat form pemeriksaan rawat jalan dengan form tambahan khusus Rehab Medik (Anjuran, Evaluasi, Suspek Penyakit Akibat Kerja)

2. **Story 2: Pasien Melaksanakan Fisioterapi**
   - Persona: Fisioterapis, Pasien
   - Deskripsi: Fisioterapis membuat catatan SOAP, kemudian mendapatkan signature digital dari Fisioterapis dan Pasien menggunakan Wacom atau QR Code

3. **Story 3: Pasien Tidak Hadir Fisioterapi**
   - Persona: Fisioterapis
   - Deskripsi: Sistem mencatat ketidakhadiran pasien dalam program fisioterapi dan notifikasi ke dokter

4. **Story 4: Fisioterapis Akhiri Sesi Terapi**
   - Persona: Fisioterapis
   - Deskripsi: Fisioterapis menutup sesi terapi dengan pencatatan hasil, progress, dan rekomendasi lanjutan

5. **Story 5: Dokter Mengevaluasi Pelaksanaan Fisioterapi**
   - Persona: Dokter
   - Deskripsi: Dokter me-review seluruh dokumentasi pelaksanaan fisioterapi, membuat evaluasi, dan menentukan lanjutan treatment


## 5. Functional Requirmeents
Ini juga generate dari Screenshots, jelaskan dari screenshots itu ngapain aja

**Functional Requirements:**
1. [Requirement 1 dari screenshots image 001: Deskripsi detail]
2. [Requirement 2 dari screenshots image 002: Deskripsi detail]
3. [Requirement 3 dari screenshots image 003: Deskripsi detail]
dan seterusnya

=> Contoh:
1. Form Pemeriksaan RJ Khusus Rehab Medik: Sistem harus menampilkan 3 form tambahan (Anjuran, Evaluasi, Suspek Penyakit Akibat Kerja) ketika pasien diklasifikasikan sebagai Rehab Medik
2. Catatan SOAP Terintegrasi: Fisioterapis dapat membuat/edit catatan SOAP dan sistem menyimpan dengan timestamp dan user identity
3. Signature Digital: Sistem mendukung 2 metode signature (Wacom pen pad, QR Code scan) dengan validation dan encryption
4. Tracking Kehadiran: Sistem mencatat kehadiran/ketidakhadiran pasien per sesi dengan notifikasi ke dokter jika tidak hadir
5. Auto-Generate Dokumen: Sistem menggenerate Lembar Formulir Rawat Jalan dan dokumen Layanan Kedokteran Fisik & Rehabilitasi dalam format PDF


## Note instructions!
Pastikan buatkan user flownya per story yang kamu lihat dari screenshots