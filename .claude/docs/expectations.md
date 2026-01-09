# Surat Persetujuan Desain UI/UX
## Rehab Medik - Primaya Hospital Group
**668/REHAB-MEDIK/PRD/PHG/XII/2025**

---

| Field | Value |
|-------|-------|
| Nama Dokumen | PRD & Surat Persetujuan Desain UI/UX Rehab Medik - Primaya Hospital Group |
| Penanggung Jawab Proyek | Adri Anto |
| Nama Proyek | Hospital Information System (HIS) V2 |
| Nama Institusi | Rumah Sakit Primaya Hospital Group |

Yang bertanda-tangan dibawah ini, menyatakan bahwa telah sepakat dengan desain, sebagaimana merupakan lampiran tak terpisahkan dari Surat Persetujuan Tahap Desain UI/UX ini.

| | |
|---|---|
| Diajukan tanggal | 3 Dec 2025 |
| Disetujui tanggal | _____________ |

| Yang Mengajukan | Mengetahui |
|-----------------|------------|
| **Adrianto** | **Roky Sarasi** |
| Ka Div IT Operasional | Corporate IT |
| PT. Sistem Integrasi Medika | Primaya Hospital Group |

---

## A. Document Property

| Field | Value |
|-------|-------|
| Document Number | 668/REHAB-MEDIK/PRD/PHG/XII/2025 |
| Document Title | PRD Rehab Medik Primaya Hospital |
| Document Editor | Fardil Khalidi |
| Editorial Team | Fardil Khalidi, Muhamad Arabi Rizki Angkotasan |
| Author | Fardil Khalidi, Muhamad Arabi Rizki Angkotasan |
| Target Dissemination Level | Private |
| Keyword List | UI/UX Design, PRD |
| Document Status | Draft |
| Approval of this Report | Submitted for Review |
| Version | 1.0 |

## B. Production Property

| Field | Value |
|-------|-------|
| Reviewers | Adri Anto |

## C. Document History

| Versi | Tanggal | Deskripsi | Direvisi Oleh |
|-------|---------|-----------|---------------|
| 1.0 | 03-12-2025 | Initial Draft for Rehab Medik Primaya Hospital Group Elektronik Hospital Information System (HIS) V2 | Fardil Khalidi |

## D. Timeline

| No. | Pekerjaan | Modul | Estimasi |
|-----|-----------|-------|----------|
| 1. | Document Preparation | Rehab Medik Primaya Hospital Group | 1 hari |
| 2. | Development | Rehab Medik Primaya Hospital Group | … |
| 3. | Quality Control | Rehab Medik Primaya Hospital Group | … |
| 4. | User Acceptance Testing | Rehab Medik Primaya Hospital Group | … |

## E. Disclaimer

Dokumen ini dibuat dalam konteks Projek Hospital Information System (HIS) V2. Semua informasi dalam dokumen ini disediakan "sebagaimana adanya" dan tidak ada jaminan atau garansi yang diberikan bahwa informasi tersebut cocok untuk tujuan tertentu. Pengguna dokumen ini menggunakan informasi tersebut atas risiko dan tanggung jawab tunggalnya.

---

## Table of Contents

- [A. Document Property](#a-document-property)
- [B. Production Property](#b-production-property)
- [C. Document History](#c-document-history)
- [D. Timeline](#d-timeline)
- [E. Disclaimer](#e-disclaimer)
- [Intro](#intro)
- [User Story](#user-story)
  - [Story #1: Pasien Konsul ke Dokter Rehab Medik Pertama Kali](#story-1-pasien-konsul-ke-dokter-rehab-medik-pertama-kali)
  - [Story #2: Pasien Melaksanakan Fisioterapi](#story-2-pasien-melaksanakan-fisioterapi)
  - [Story #3: Pasien Tidak Hadir Fisioterapi](#story-3-pasien-tidak-hadir-fisioterapi)
  - [Story #4: Fisioterapis Akhiri Sesi Terapi](#story-4-fisioterapis-akhiri-sesi-terapi)
  - [Story #5: Dokter Mengevaluasi Pelaksaan Fisioterapi](#story-5-dokter-mengevaluasi-pelaksaan-fisioterapi)

---

# Intro

Selamat datang di Dokumen Persyaratan Produk (PRD) komprehensif untuk **Rehab Medik Primaya Hospital Group - Hospital Information System (HIS) V2**. Dokumen ini bertujuan untuk memberikan gambaran rinci tentang fitur, fungsi, dan spesifikasi terkait Form Edukasi Elektronik dalam aplikasi Hospital Information System (HIS) V2.

Dokumen Rehab Medik pada aplikasi Hospital Information System (HIS) V2 ini terdapat 5 user story yang akan dibahas yaitu:

- Story #1: Pasien Konsul ke Dokter Rehab Medik Pertama Kali
- Story #2: Pasien Melaksanakan Fisioterapi
- Story #3: Pasien Tidak Hadir Fisioterapi
- Story #4: Fisioterapis Akhiri Sesi terapi
- Story #5: Dokter Mengevaluasi Pelaksaan Fisioterapi

Adapun user persona yang akan diterangkan disini adalah:

1. **Pasien**: Pengguna layanan fisioterapi yang menjalani konsultasi dan terapi.
2. **Fisioterapis**: Tenaga medis yang memberikan dan mencatat tindakan terapi pasien.
3. **Dokter**: Performer medis yang mendiagnosis dan mengevaluasi terapi pasien.

---

# User Story

Berikut adalah list user story yang akan di-*accommodate* pada product requirement documentation (PRD) ini.

---

## Story #1: Pasien Konsul ke Dokter Rehab Medik Pertama Kali

| Field | Value |
|-------|-------|
| User Persona | Dokter |
| Jobs to be Done | Dokter bisa membuat pemeriksaan RJ untuk rehab medik |
| Referensi UI | `[INSERT_FIGMA_LINK]` |
| Flow Reference | Alur Pasien Konsul ke Dokter Rehab Medik Pertama Kali |

Pada tahap ini Dokter perlu login terlebih dahulu, kemudian menuju ke EMR Dokter, lalu mengisi pengkajian rawat jalan. Pastikan pasien sudah terdaftar sebagai pasien Rehab Medik.

### User Acceptance Criteria

- Untuk pasien yang diklasifikasikan sebagai **Rehab Medik**, sistem akan menampilkan tiga form tambahan, yaitu:
  - **Form Anjuran**: dapat diklik untuk mengaktifkan kolom isian.
  - **Form Evaluasi**: muncul secara otomatis setelah pasien diklasifikasikan.
  - **Form Suspect Penyakit Akibat Kerja**: tersedia dalam bentuk pilihan radio button (Ya/Tidak).
- Semua form yang ditampilkan dapat diisi oleh pengguna sesuai kebutuhan.
- Setelah pengisian selesai, tersedia tombol **Simpan** untuk menyimpan seluruh data yang telah dimasukkan.
- Jika penyimpanan berhasil, sistem akan menampilkan notifikasi sukses dan mengarahkan pengguna ke halaman **Daftar Pemeriksaan**.

### User Flow

> **📊 FLOWCHART REQUIRED**
> 
> Buat flowchart dengan alur berikut menggunakan tools seperti Draw.io, Lucidchart, atau Figma:
> 
> ```
> [Start] → [Login sebagai Dokter] → [Buka Modul EMR Dokter] → [Buka Modul EMR: Pemeriksaan RJ] → [Klik: Pemeriksaan RJ] → [Isi form Pemeriksaan RJ] → [Klik: Simpan] → [Form pemeriksaan RJ pasien terbentuk] → [End]
> ```
> 
> **Catatan**: Ada tambahan anjuran Program Terapi jika pasien Rehab Medik

---

Berikut proses user menambah master edukasi beserta tampilan UI:

### Step 1: Klik Pemeriksaan Rawat Jalan

Login sebagai dokter. Menuju ke menu EMR. Buka Modul EMR, klik pada modul EMR: **Pemeriksaan Rawat Jalan**

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Tampilan menu EMR Dokter dengan highlight pada modul "Pemeriksaan Rawat Jalan"]`
> 
> **Instruksi screenshot**: Capture halaman Modul e-MR yang menampilkan grid menu termasuk: Pengkajian Dewasa Geriatri RJ, Catatan Sedasi/Catatan Anestesi, Pemeriksaan Rawat Jalan, dll.

---

### Step 2: Klik button + Pemeriksaan RJ

Selanjutnya tampil halaman pemeriksaan RJ, klik button **+Pemeriksaan RJ**

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Halaman Pemeriksaan Saat Ini dengan button "+ Pemeriksaan RJ"]`
> 
> **Instruksi screenshot**: Capture halaman yang menampilkan tab "Pemeriksaan Saat Ini" dan "Histori RJ Sebelumnya" dengan button "+ Pemeriksaan RJ" yang terlihat.

---

### Step 3: Mengisi Form khusus untuk pasien rehab medik

Kemudian tampil form isian rawat jalan. Di sini dibuat jika pasien terklasifikasi sebagai pasien Rehab Medik, maka form **Anjuran**, **Evaluasi**, dan **Suspek Penyakit Akibat Kerja** akan tampil.

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Form Edit Pemeriksaan Rawat Jalan dengan field Anjuran, Evaluasi, dan Suspek Penyakit Akibat Kerja]`
> 
> **Instruksi screenshot**: Capture form yang menampilkan:
> - Header dengan No. Rekam Medis, Nama, Penjamin
> - Field Anjuran dengan checkbox
> - Field Evaluasi dengan text area
> - Field Suspek Penyakit Akibat Kerja dengan radio button (Tidak/Ya)

---

### Step 4: Daftar Pemeriksaan Rawat Jalan RJ terbentuk

Field khusus isian untuk pasien rehab medis dapat tampil di isian pemeriksaan RJ Dokter, yang mencakup: **Anjuran**, **Evaluasi**, dan **Suspek Penyakit Akibat Kerja**

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Halaman Daftar Pemeriksaan RJ dengan data lengkap termasuk Anjuran, Evaluasi, dan Suspek Penyakit Akibat Kerja]`
> 
> **Instruksi screenshot**: Capture halaman yang menampilkan daftar pemeriksaan dengan detail lengkap pasien rehab medik.

---

## Story #2: Pasien Melaksanakan Fisioterapi

| Field | Value |
|-------|-------|
| User Persona | Pasien dan Fisioterapis |
| Jobs to be Done | **Pasien**: bisa terdaftar ke sesi rehab medik, bisa melakukan tanda tangan digital/QR code<br>**Fisioterapi**: bisa mendaftarkan pasien ke sisi rehab medik, bisa melakukan tanda tangan digital/QR code |
| Referensi UI | `[INSERT_FIGMA_LINK]` |
| Flow Reference | Alur Menambah Asesmen Edukasi Pasien |

Pada tahap ini Fisioterapis mengisikan Catatan Terintegrasi pasien. Jika pasien adalah pasien fisioterapis, ada persetujuan untuk melakukan tindakan fisioterapi. Pasien dan fisioterapi difasilitasi mekanisme untuk melakukan tanda tangan digital.

### User Acceptance Criteria

- Jika pada menu Pemeriksaan Rawat Jalan terdapat checklist pada bagian Anjuran, maka sistem akan menampilkan tiga tombol khusus: **Rincian Program**, **Absen Program**, dan **Rencana Program**.
- Fisioterapis dapat membuat catatan SOAP (Subjective, Objective, Assessment, Plan) sebagai bagian dari dokumentasi pelayanan rehabilitasi.
- Setelah SOAP dan catatan disimpan, sistem akan menampilkan area untuk tanda tangan Fisioterapis dan Pasien.
- Fisioterapis dapat mengisi tanda tangan menggunakan perangkat **Wacom** atau melalui **QR Code**.
- Pasien juga dapat memberikan tanda tangan menggunakan **Wacom** atau **QR Code**.
- Setelah kedua pihak selesai melakukan tanda tangan, sistem dapat mengenerate **Lembar Formulir Rawat Jalan** serta **Layanan Kedokteran Fisik dan Rehabilitasi**.
- Jika proses tanda tangan telah selesai, maka di dalam Catatan Terintegrasi akan muncul penanda bahwa Rencana Program telah ditandatangani oleh kedua pihak.

### User Flow

> **📊 FLOWCHART REQUIRED**
> 
> Buat flowchart dengan alur berikut menggunakan tools seperti Draw.io, Lucidchart, atau Figma:
> 
> ```
> [Start] → [Login sebagai Fisioterapis] → [Buka Modul EMR Perawat] → [Buka Catatan Terintegrasi] → {Pasien rehab medik?}
>   → [Tidak] → [Tampil catatan terintegrasi pasien umum] → Ke flow: Pemeriksaan Pasien Umum
>   → [Ya] → [Tampil catatan terintegrasi pasien Rehab Medik] → [Klik: +SOAP] → [Isi SOAP] → [Klik: Simpan] → [Tampil catatan terintegrasi pasien Rehab Medik] → [Klik: Tanda Tangan Fisioterapis] → [Tampil: pop up tanda tangan] → {Wacom/QR Code?}
>     → [WACOM] → [Lakukan tanda tangan di Wacom] → [Submit]
>     → [QR CODE] → [Klik: QR Code] → [Tampil: Pop UP QR Code] → [Scan QR Code] → [lakukan tanda tangan di Device] → [Submit]
> → [Klik: Simpan] → [Tanda tangan disimpan di sistem (fisioterapis sudah tanda tangan)] → [Klik: Tanda Tangan Pasien] → [Tampil: pop up tanda tangan] → {Wacom/QR Code?}
>     → [WACOM] → [Lakukan tanda tangan di Wacom] → [Submit]
>     → [QR CODE] → [Klik: QR Code] → [Tampil: Pop UP QR Code] → [Scan QR Code] → [lakukan tanda tangan di Device] → [Submit]
> → [Klik: Simpan] → [Tanda tangan disimpan di popup] → [Tanda tangan disimpan di sistem (pasien sudah tanda tangan)] → [LEMBAR FORMULIR RAWAT JALAN - LAYANAN KEDOKTERAN FISIK DAN REHABILITASI tersimpan (sudah ditandatangani)] → [END]
> ```

---

Berikut proses user menambah asesmen edukasi pasien beserta tampilan UI:

### Step 1: Tampilan EMR Dokter - Catatan Terintegrasi

Fisioterapis login sebagai Perawat, kemudian menuju ke menu EMR Rawat Jalan, lalu klik modul **Catatan Terintegrasi**

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Menu EMR dengan highlight pada modul "Catatan Terintegrasi"]`
> 
> **Instruksi screenshot**: Capture halaman Modul e-MR yang menampilkan grid menu dengan highlight pada "Catatan Terintegrasi".

---

### Step 2: Tampilan Catatan Terintegrasi

- Ketika pasien dipilih pada menu Pemeriksaan Rawat Jalan Rehab Medik, dan terdapat checklist aktif pada bagian Program Terapi, maka sistem akan menampilkan tiga tombol tambahan pada tampilan Fisioterapis, yaitu:
  - **Rincian Program**
  - **Absen Program**
  - **Rencana Program**
- Tombol-tombol tersebut hanya akan muncul jika checklist Program Terapi pada Pemeriksaan RJ telah diaktifkan.
- Jika checklist tidak dicentang, maka tombol tersebut tidak ditampilkan.

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Halaman Catatan Terintegrasi dengan tombol Rincian Program, Absen Program, dan Rencana Program]`
> 
> **Instruksi screenshot**: Capture halaman Catatan Terintegrasi yang menampilkan:
> - Header dengan data pasien (No.Reg, No.Rek.Med, Nama Pasien, dll)
> - Button "+ Catatan SOAP", "Rincian Program", "Absen Program"
> - Label "Rencana Program" dengan value (contoh: TENS, US, MWD, Traksi, Laser Ringan)

---

### Step 3: Tampilan Detail Pasien (Form Asesmen Kebutuhan Edukasi Pasien)

Ketika user mencentang opsi Rencana Program, maka sistem akan menampilkan form SOAP yang terdiri dari:
- **S** (Subjective)
- **O** (Objective)
- **A** (Assessment)
- **P** (Plan)

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Form SOAP dengan field S, O, A, P beserta sidebar informasi pasien]`
> 
> **Instruksi screenshot**: Capture form yang menampilkan:
> - Sidebar kiri: Nama Dept/Ruang, Readback checkbox, Risiko Jatuh, Risiko Nyeri, Program, Keterangan, Oleh
> - Area kanan: Text editor dengan format SOAP (S:, O:, A:, P:)
> - Button "Ambil Template", "Simpan", "Batal"

---

### Step 4: Tampilan catatan terintegrasi setelah diisi Fisioterapis

Setelah form SOAP diisi dan disimpan oleh Fisioterapis, sistem akan otomatis menampilkan halaman Catatan Terintegrasi. Pada halaman Catatan Terintegrasi, data SOAP yang telah disimpan akan ditampilkan secara lengkap dan tidak dapat diubah. Di bawah catatan SOAP, sistem akan menampilkan area untuk **Tanda Tangan Fisioterapis** dan **Tanda Tangan Pasien**. Area tanda tangan ini hanya muncul setelah data SOAP berhasil disimpan.

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Tabel Catatan Terintegrasi dengan data SOAP dan button Tanda Tangan Fisioterapis & Tanda Tangan Pasien]`
> 
> **Instruksi screenshot**: Capture tabel yang menampilkan:
> - Kolom: No, Waktu/Oleh, Departemen, Catatan Perkembangan (SOAP), Verif Dokter, Batal
> - Data SOAP yang sudah terisi
> - Button "Tanda Tangan Fisioterapis" dan "Tanda Tangan Pasien" di bawah catatan

---

### Step 5: Tampilan Tanda Tangan Integrasi Wacom

- Setelah klik tanda tangan fisioterapis, sistem menampilkan tombol **"Tanda Tangan Fisioterapis"**.
- Ketika Fisioterapis menekan tombol tersebut, sistem akan menampilkan **pop-up untuk input tanda tangan**.
- Di dalam pop-up, Fisioterapis dapat melakukan tanda tangan menggunakan perangkat **Wacom**. Dan setelah tanda tangan selesai, Fisioterapis dapat menekan tombol **Simpan** pada pop-up.

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Pop-up Tanda Tangan dengan area signature pad dan button Tampilkan QR Code, Kembali, Simpan]`
> 
> **Instruksi screenshot**: Capture pop-up modal yang menampilkan:
> - Title: "Tanda Tangan"
> - Subtitle: "Pelaksanaan Terapi [tanggal]"
> - Label: "Tanda Tangan Fisioterapis"
> - Area signature (bisa kosong atau dengan contoh tanda tangan)
> - Button: "Tampilkan QR Code", "Kembali", "Simpan"

---

### Step 6: Tanda tangan QR Code (alternatif dari Wacom)

- Pada halaman Catatan Terintegrasi, selain opsi tanda tangan dengan Wacom, tersedia tombol **"Tampilkan QR Code"** di area tanda tangan Fisioterapis.
- Ketika Fisioterapis menekan tombol **Tampilkan QR Code**, sistem akan menampilkan **pop-up berisi QR Code**.
- QR Code yang ditampilkan dapat discan menggunakan perangkat pribadi Fisioterapis (misalnya: smartphone atau tablet).
- Setelah discan, Fisioterapis diarahkan ke halaman khusus untuk melakukan tanda tangan digital melalui perangkatnya.
- Setelah tanda tangan selesai dan dikirim, sistem akan menyimpan hasil tanda tangan tersebut dan menampilkannya di halaman Catatan Terintegrasi, menggantikan placeholder tanda tangan sebelumnya.

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Pop-up dengan QR Code untuk scan tanda tangan digital]`
> 
> **Instruksi screenshot**: Capture pop-up modal yang menampilkan:
> - Title: "Tanda Tangan"
> - Subtitle: "Pelaksanaan Terapi [tanggal]"
> - QR Code yang dapat discan
> - Button: "Kembali"

---

### Step 7: Pasien tanda tangan

Selanjutnya pasien melakukan tanda tangan. Klik pada **Tanda Tangan Pasien**

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Tampilan Catatan Terintegrasi dengan highlight pada button "Tanda Tangan Pasien"]`
> 
> **Instruksi screenshot**: Capture tabel catatan terintegrasi dengan button "Tanda Tangan Pasien" yang di-highlight atau dalam keadaan dapat diklik.

---

### Step 8: Tanda Tangan (di Wacom)

- Setelah klik tanda tangan Pasien, sistem menampilkan tombol **"Tanda Tangan Pasien"**.
- Ketika Pasien menekan tombol tersebut, sistem akan menampilkan **pop-up untuk input tanda tangan**.
- Di dalam pop-up, Pasien dapat melakukan tanda tangan menggunakan perangkat **Wacom**. Dan setelah tanda tangan selesai, pasien/fisioterapis dapat menekan tombol **Simpan** pada pop-up.

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Pop-up Tanda Tangan Pasien dengan contoh tanda tangan yang sudah terisi]`
> 
> **Instruksi screenshot**: Capture pop-up modal tanda tangan pasien dengan:
> - Title: "Tanda Tangan"
> - Label: "Tanda Tangan Pasien"
> - Area signature dengan contoh tanda tangan
> - Button: "Tampilkan QR Code", "Kembali", "Simpan"

---

### Step 9: Tanda tangan QR Code (alternatif dari Wacom)

- Pada halaman Catatan Terintegrasi, selain opsi tanda tangan dengan Wacom, tersedia tombol **"Tampilkan QR Code"** di area tanda tangan Pasien.
- Ketika Pasien menekan tombol **Tampilkan QR Code**, sistem akan menampilkan **pop-up berisi QR Code**.
- QR Code yang ditampilkan dapat discan menggunakan perangkat pribadi Pasien (misalnya: smartphone atau tablet).
- Setelah discan, Pasien diarahkan ke halaman khusus untuk melakukan tanda tangan digital melalui perangkatnya.
- Setelah tanda tangan selesai dan dikirim, sistem akan menyimpan hasil tanda tangan tersebut dan menampilkannya di halaman Catatan Terintegrasi, menggantikan placeholder tanda tangan sebelumnya.

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Pop-up dengan QR Code untuk tanda tangan Pasien]`
> 
> **Instruksi screenshot**: Capture pop-up modal QR Code untuk pasien dengan layout serupa step 6.

---

### Step 10: Tampilan Lembar Formulir Rawat Jalan Rehab Medik

Setelah Fisioterapis dan Pasien selesai menandatangani dokumen, tampil lembar formulir rawat jalan, dengan tanda tangan **Fisioterapis** dan **Pasien**

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Lembar Formulir Rawat Jalan - Layanan Kedokteran Fisik dan Rehabilitasi lengkap dengan tanda tangan]`
> 
> **Instruksi screenshot**: Capture dokumen PDF/form yang menampilkan:
> - Header: Logo Primaya Hospital, Data Pasien (Nama Lengkap, Tanggal Lahir, No. Rekam Medis)
> - Title: "LEMBAR FORMULIR RAWAT JALAN - LAYANAN KEDOKTERAN FISIK DAN REHABILITASI"
> - Section I: Diisi oleh Dokter SpKFR (Tanggal Pelayanan, Anamnesis, Diagnosis, dll)
> - Section II: Detail Program (Tanggal Terapi, Program, Keterangan, Terapis)
> - Area tanda tangan: Tanda Tangan Pasien, Dokter Pemeriksa, Tanda Tangan Terapis

---

## Story #3: Pasien Tidak Hadir Fisioterapi

| Field | Value |
|-------|-------|
| User Persona | Fisioterapis |
| Jobs to be Done | Fisioterapis: mencatat pasien yang tidak hadir (absen) |
| Referensi UI | `[INSERT_FIGMA_LINK]` |
| Flow Reference | Flow: Pasien tidak hadir fisioterapi |

Pada tahap ini, Fisioterapis mencatat jika pasien berhalangan hadir atau absen. Informasi ketidakhadiran tersebut akan tercatat dalam **Catatan Terintegrasi** sebagai riwayat pasien tidak datang (absen).

### User Acceptance Criteria

- Fisioterapis login sebagai Perawat, lalu mengakses menu EMR Rawat Jalan dan membuka modul Catatan Terintegrasi.
- Jika pasien termasuk kategori Rehab Medik, sistem menampilkan tombol **Absen Program** di halaman Catatan Terintegrasi.
- Ketika tombol **Absen Program** diklik, sistem memunculkan pop-up Absen Program.
- Di dalam pop-up, Fisioterapis dapat mengisi alasan atau detail ketidakhadiran pasien.
- Kolom **Tanggal Absen** tersedia dan wajib diisi, dengan pemilihan tanggal melalui date picker yang muncul saat kolom diklik.
- Setelah semua isian lengkap, Fisioterapis dapat menekan tombol **Simpan** untuk menyimpan data absen.
- Jika penyimpanan berhasil, sistem menampilkan flag "Absen pada tanggal: [tanggal]" di halaman Catatan Terintegrasi.
- Sistem juga menyediakan opsi hapus (delete) untuk menghapus data absen yang telah disimpan.

### User Flow

> **📊 FLOWCHART REQUIRED**
> 
> Buat flowchart dengan alur berikut menggunakan tools seperti Draw.io, Lucidchart, atau Figma:
> 
> ```
> [Start] → [Login sebagai Perawat] → [Buka Modul EMR Rawat Jalan] → [Klik Modul EMR: Catatan Terintegrasi] → [Tampil catatan terintegrasi pasien Rehab Medik] → [Klik button: Absen Program] → [Isi tanggal absen program] → [Klik: Simpan] → [Riwayat absen tersimpan] → [END]
> ```

---

### Step 1: Tampilan Detail Pasien (Form Asesmen Kebutuhan Edukasi Pasien)

Fisioterapis login sebagai Perawat, kemudian menuju ke menu EMR Rawat Jalan, lalu klik modul **Catatan Terintegrasi**

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Menu EMR dengan highlight pada modul "Catatan Terintegrasi"]`
> 
> **Instruksi screenshot**: Capture halaman Modul e-MR yang menampilkan grid menu dengan highlight pada "Catatan Terintegrasi" (sama seperti Story #2 Step 1).

---

### Step 2: Tampilan Catatan Integrasi

- Setelah Fisioterapis menekan tombol **Catatan Terintegrasi**, sistem akan menampilkan halaman **Catatan Terintegrasi**.
- Jika pasien termasuk dalam kategori **Rehab Medik**, maka tombol **Absen Program** akan muncul di halaman tersebut.
- Ketika tombol **Absen Program** diklik, sistem akan menampilkan **pop-up Absen Program**.

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Halaman Catatan Terintegrasi dengan highlight pada button "Absen Program"]`
> 
> **Instruksi screenshot**: Capture halaman Catatan Terintegrasi dengan button "Absen Program" yang di-highlight.

---

### Step 3: Tampilan Form Absen Program

Di dalam pop-up tersebut, Fisioterapis dapat mengisi informasi terkait alasan atau detail ketidakhadiran pasien pada sesi terapi.

Setelah form Absen Program diisi dan disimpan, informasi tersebut akan tersimpan dan tampil sebagai bagian dari **riwayat absen pasien** dalam Catatan Terintegrasi.

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Pop-up Absen Program dengan field Tanggal Absen dan Riwayat Absen kosong]`
> 
> **Instruksi screenshot**: Capture pop-up modal yang menampilkan:
> - Title: "Absen Program"
> - Field: "Tanggal Absen" dengan input date
> - Button: "Simpan"
> - Section: "Riwayat Absen" dengan text "Belum ada riwayat absen"
> - Button: "Tutup"

---

### Step 4: Tampilan Form Absen Program (Fisioterapis isi tanggal absen)

Di dalam pop-up Absen Program, terdapat kolom **Tanggal Absen** yang wajib diisi oleh Fisioterapis.

Ketika kolom Tanggal Absen diklik, sistem akan menampilkan **date picker** (kalender pop-up) untuk memilih tanggal.

Fisioterapis dapat memilih tanggal absen langsung dari date picker tanpa perlu mengetik manual, kemudian klik **simpan**

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Pop-up Absen Program dengan tanggal yang sudah terisi]`
> 
> **Instruksi screenshot**: Capture pop-up modal dengan:
> - Field "Tanggal Absen" terisi (contoh: 07-03-2025)
> - Button "Simpan" dalam keadaan aktif

---

### Step 5: Tampilan Form Absen Program (Absen Pasien terisi)

Jika data berhasil disimpan, maka sistem akan menampilkan **flag atau penanda** tanggal absen tersebut pada halaman Catatan Terintegrasi, misalnya:

*"Absen pada tanggal: 02 April 2025"*

Sistem juga menyediakan **opsi hapus (delete)** untuk menghapus data absen yang sudah terisi, apabila diperlukan.

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Pop-up Absen Program dengan Riwayat Absen yang sudah terisi dan icon delete]`
> 
> **Instruksi screenshot**: Capture pop-up modal dengan:
> - Section "Riwayat Absen" menampilkan list tanggal absen (contoh: "1. 07-03-2025")
> - Icon delete (trash) di samping setiap entry
> - Button "Tutup"

---

## Story #4: Fisioterapis Akhiri Sesi Terapi

| Field | Value |
|-------|-------|
| User Persona | Fisioterapis |
| Jobs to be Done | Fisioterapis: mengakhiri sesi terapi |
| Referensi UI | `[INSERT_FIGMA_LINK]` |
| Flow Reference | Flow: Pasien tidak hadir fisioterapi |

Pada tahap ini, Fisioterapis membuka Catatan Terintegrasi, memilih Rencana Program, lalu mengakhiri sesi setelah seluruh terapi tercatat. Setelah tanda tangan pasien dan Fisioterapis, sistem mengenerate dokumen yang tersimpan di Daftar Pemeriksaan RJ.

### User Acceptance Criteria

- Fisioterapis membuka modul Catatan Terintegrasi untuk pasien yang sedang menjalani program terapi.
- Fisioterapis menekan tombol **"Rencana Program"** yang tersedia pada halaman tersebut.
- Setelah tombol diklik, sistem menampilkan daftar Rencana Program Terapi, yang mencakup informasi berikut:
  - Nama Program Terapi
  - Tanggal Terapi
  - Status Kehadiran (Hadir / Tidak Hadir) untuk setiap sesi
- Di bagian akhir daftar, sistem akan menampilkan tombol **"Akhiri Program"**.
- Tombol **"Akhiri Program"** hanya muncul jika seluruh sesi terapi dalam rencana tersebut sudah terisi status kehadirannya.
- Ketika tombol **"Akhiri Program"** ditekan, sistem akan menampilkan pop-up tanda tangan untuk proses verifikasi akhir.
- Di dalam pop-up tersebut, tersedia dua bagian tanda tangan:
  - Tanda Tangan Fisioterapis
  - Tanda Tangan Pasien
- Masing-masing pihak dapat melakukan tanda tangan menggunakan dua metode:
  - Langsung pada perangkat Wacom
  - Melalui QR Code yang ditampilkan di layar, lalu discan untuk mengisi tanda tangan lewat device masing-masing
- Setelah kedua tanda tangan berhasil dilakukan dan disimpan, sistem akan otomatis menghasilkan (generate) dokumen **Lembar Formulir Rawat Jalan – Layanan Kedokteran Fisik dan Rehabilitasi** yang telah ditandatangani kedua pihak.
- Dokumen hasil tanda tangan dapat diakses melalui menu **Daftar Pemeriksaan RJ**, pada bagian **Hasil Scan Dokumen**.
- Dokumen tersebut merupakan **Lembar Formulir Rawat Jalan – Layanan Kedokteran Fisik dan Rehabilitasi** yang telah ditandatangani oleh Fisioterapis dan Pasien.
- Status bahwa program telah diakhiri akan tercatat secara otomatis dan menjadi bagian dari **riwayat terapi pasien** dalam sistem.

### User Flow

> **📊 FLOWCHART REQUIRED**
> 
> Buat flowchart dengan alur berikut menggunakan tools seperti Draw.io, Lucidchart, atau Figma:
> 
> ```
> [Start] → [Login sebagai Perawat] → [Buka Modul EMR Rawat Jalan] → [Klik Modul EMR: Catatan Terintegrasi] → [Tampil catatan terintegrasi pasien Rehab Medik] → [Klik button: Rincian Program] → [Tampil Rincian Program terapi] → [Klik: Akhiri Program] → [Tanda tangan (pasien & fisioterapis)] → [Lembar medis rawat jalan tergenerate] → [END]
> ```

---

Berikut proses user menambah master edukasi beserta tampilan UI:

### Step 1: Klik Rincian Program

Pada Catatan terinterigasi klik **Rincian Program**.

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Halaman Catatan Terintegrasi dengan highlight pada button "Rincian Program"]`
> 
> **Instruksi screenshot**: Capture halaman Catatan Terintegrasi dengan button "Rincian Program" yang di-highlight.

---

### Step 2: Tampil Rincian Program Terapi

Disini:
1. Menampilkan rincian program terapi pasien, termasuk anamnesis dan rencana terapi.
2. Setiap kunjungan terapi akan tercatat lengkap dengan tanggal, jenis program, dan status kehadiran.
3. Digunakan untuk memantau progres terapi serta mengunduh laporan atau mengakhiri program.
4. Bisa download PDF dari rincian programnya
5. Klik **Akhiri Program** akan memunculkan tanda tangan pasien (konfirmasi akhiri program)

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Modal Rincian Program Terapi dengan tabel sesi terapi dan button Akhiri Program]`
> 
> **Instruksi screenshot**: Capture modal yang menampilkan:
> - Header: Data Pasien (Nama, Jenis Kelamin, Tanggal Lahir, No. Rekam Medis)
> - Section: Data diagnosa dan terapi (Tanggal Pelayanan, Anamnesis, Diagnosis, dll)
> - Tabel: No, Nama Program, Tanggal Terapi, Status Kehadiran, Keterangan
> - Button: "Download PDF", "Tutup", "Akhiri Program"

---

### Step 3: Tanda tangan Pasien

Tampil popup tanda tangan pasien. Mula-mula tanda tangannya kosong. Jika sudah ditandatangani, tampilan tanda tangan pasien terisi di kotak. Di sini ada 2 opsi:
1. Klik **tampilkan QR Code** maka akan tampil pop up QR Code
2. Atau langsung sign di area
3. Jika sudah klik **simpan** untuk menyimpan tanda tangan

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Pop-up Tanda Tangan untuk konfirmasi Akhiri Program dengan contoh tanda tangan]`
> 
> **Instruksi screenshot**: Capture pop-up modal tanda tangan dengan:
> - Title: "Tanda Tangan"
> - Subtitle: "Pelaksanaan Terapi [tanggal range]"
> - Label: "Tanda Tangan Pasien"
> - Area signature dengan contoh tanda tangan
> - Button: "Tampilkan QR Code", "Kembali", "Simpan"

---

### Step 4: Jika memilih opsi Scan QR, tampil pop up berikut

Selanjutnya pasien Scan QR

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Pop-up QR Code untuk tanda tangan Akhiri Program]`
> 
> **Instruksi screenshot**: Capture pop-up modal dengan QR Code yang dapat discan.

---

### Step 5: Jika memilih opsi Scan QR, tampil pop up berikut

Selanjutnya pasien tanda tangani dan klik **simpan**

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Lembar Formulir Rawat Jalan lengkap dengan tabel program terapi dan semua tanda tangan]`
> 
> **Instruksi screenshot**: Capture dokumen PDF/form yang menampilkan:
> - Header: Logo Primaya Hospital, Data Pasien
> - Title: "LEMBAR FORMULIR RAWAT JALAN - LAYANAN KEDOKTERAN FISIK DAN REHABILITASI"
> - Section I: Diisi oleh Dokter SpKFR
> - Tabel: No, Program, Tanggal, Tanda Tangan (Pasien, Dokter, Terapis), Keterangan
> - Area tanda tangan: Tanda Tangan Pasien, Dokter Pemeriksa
> - Button: "Kembali", "Simpan"

---

### Step 6: Selanjutnya tampil di Catatan SOAP

Di sini Perawat bisa cek tanda tangan Fisioterapis dan tanda Tangan Pasien

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Tabel Catatan SOAP dengan indikator tanda tangan sudah lengkap (centang hijau)]`
> 
> **Instruksi screenshot**: Capture tabel catatan SOAP yang menampilkan:
> - Data SOAP lengkap
> - Indikator "✓ Tanda Tangan Fisioterapis" dan "✓ Tanda Tangan Pasien" (dengan centang hijau)

---

### Step 7: Jika sesi telah berakhir maka tampil

Di sini Perawat bisa cek tanda tangan Fisioterapis dan tanda Tangan Pasien

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Halaman Hasil Scan Dokumen dengan preview PDF Lembar Formulir Rawat Jalan]`
> 
> **Instruksi screenshot**: Capture halaman yang menampilkan:
> - Tab menu: Modul e-MR, List Pemeriksaan, Laboratorium, dll dengan "Hasil Scan Dokumen" aktif
> - Tree view: LABORATORIUM LUAR, RADIOLOGI LUAR, LAIN-LAIN
> - Preview PDF: Lembar Formulir Rawat Jalan dengan semua data dan tanda tangan

---

## Story #5: Dokter Mengevaluasi Pelaksaan Fisioterapi

| Field | Value |
|-------|-------|
| User Persona | Dokter |
| Jobs to be Done | Dokter mengevaluasi pelaksaan fisioterapi pasien |
| Referensi UI | `[INSERT_FIGMA_LINK]` |
| Flow Reference | Flow: Pasien tidak hadir fisioterapi |

### Acceptance Criteria

- Dokter dapat login ke sistem menggunakan akun yang valid.
- Dokter dapat mengakses modul EMR Rawat Jalan, lalu memilih menu **Pemeriksaan Rawat Jalan**.
- Sistem menampilkan histori pemeriksaan rawat jalan pasien, termasuk tab **Histori RJ Sebelumnya**.
- Dokter dapat memilih sesi sebelumnya dan menekan tombol **Pemeriksaan RJ**.
- Sistem menampilkan form edit Pemeriksaan Rawat Jalan untuk sesi yang dipilih.
- Dokter dapat menuju ke bagian Evaluasi dan menekan tombol **Perincian Program**.
- Sistem menampilkan **Lembar Formulir Rawat Jalan** yang dapat digunakan dokter untuk mengevaluasi rincian program terapi pasien.

### User Flow

> **📊 FLOWCHART REQUIRED**
> 
> Buat flowchart dengan alur berikut menggunakan tools seperti Draw.io, Lucidchart, atau Figma:
> 
> ```
> [Start] → [Login sebagai Dokter] → [Buka Modul EMR Dokter] → [Klik modul: history pemeriksaan rawat jalan] → [Tampil: halaman history pemeriksaan RJ pasien] → [Buka tab: History Pemeriksaan sebelumnya] → [Klik: +Pemeriksaan RJ] → [Ke sesi "EVALUASI" klik: Rincian Program] → [Tampil: Rincian program pemeriksaan pasien] → [END]
> ```

---

### Step 1: Dokter evaluasi melalui form Pemeriksaan Rawat Jalan

Di sini Dokter melakukan evaluasi isian pemeriksaan rawat jalan Rehab Medis

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Form Edit Pemeriksaan Rawat Jalan lengkap dengan semua field terisi]`
> 
> **Instruksi screenshot**: Capture form yang menampilkan:
> - Header: Data Pasien (No. Rekam Medis, Nama, Penjamin, Jenis Kelamin, Tgl Lahir)
> - Section Perawat: Tinggi Badan, Berat Badan, Skrining Nyeri, Skrining Jatuh, Tekanan Darah, Nadi, Suhu, dll
> - Field: Alat Bantu, Prothesa, Cacat Tubuh, ADL, Riwayat Jatuh, Riwayat Kejang, dll
> - Field: Status Psikologis, Keluhan Pasien (Diisi Perawat)

---

### Step 2: Tampilan Lembar Formulir Rawat Jalan (Kondisi sudah selesai Terapi)

Tampilan cetakan PDF

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: PDF Lembar Formulir Rawat Jalan - Layanan Kedokteran Fisik dan Rehabilitasi (kondisi selesai)]`
> 
> **Instruksi screenshot**: Capture dokumen PDF final yang menampilkan:
> - Header: Logo Primaya Hospital, Data Pasien
> - Section I: Diisi oleh Dokter SpKFR (semua field terisi lengkap)
> - Tabel Program: Semua sesi terapi dengan tanda tangan lengkap
> - Footer: Tanda Tangan Pasien, Dokter Pemeriksa
> - Reference: "RSAB-PKU/RM/007.14/LFRJLKFDR/2024/Rev.06 - Halaman 1 dari 1"

---

# Appendix: Legend Signifiers

## Signifier untuk Konten Third-Party

Dokumen ini menggunakan signifier berikut untuk menandai konten yang perlu dibuat menggunakan tools eksternal:

### 📊 FLOWCHART REQUIRED
Digunakan untuk menandai area yang memerlukan pembuatan flowchart/diagram alur menggunakan tools seperti:
- Draw.io
- Lucidchart
- Figma
- Miro
- Microsoft Visio

**Format:**
```markdown
> **📊 FLOWCHART REQUIRED**
> 
> Buat flowchart dengan alur berikut menggunakan tools seperti Draw.io, Lucidchart, atau Figma:
> 
> ```
> [Step 1] → [Step 2] → [Step 3] → [END]
> ```
```

### 🖼️ SCREENSHOT REQUIRED
Digunakan untuk menandai area yang memerlukan screenshot UI dari aplikasi.

**Format:**
```markdown
> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Deskripsi singkat screenshot]`
> 
> **Instruksi screenshot**: Deskripsi detail elemen yang harus ada dalam screenshot.
```

### `[INSERT_FIGMA_LINK]`
Placeholder untuk link referensi UI di Figma atau design tools lainnya.

### `[INSERT_SCREENSHOT: description]`
Placeholder inline untuk screenshot dengan deskripsi.

---

# Catatan untuk Tim

1. **Flowchart**: Semua flowchart yang ditandai dengan "📊 FLOWCHART REQUIRED" harus dibuat sesuai dengan alur yang dideskripsikan dalam blok kode.

2. **Screenshot**: Semua screenshot yang ditandai dengan "🖼️ SCREENSHOT REQUIRED" harus diambil dari aplikasi staging/development sesuai instruksi yang diberikan.

3. **Link Figma**: Ganti semua `[INSERT_FIGMA_LINK]` dengan link aktif ke design Figma yang relevan.

4. **Konsistensi**: Pastikan semua visual asset menggunakan resolusi dan format yang konsisten (recommended: PNG, 1920x1080 atau sesuai kebutuhan).

5. **Naming Convention**: Gunakan naming convention yang konsisten untuk file asset:
   - Flowchart: `flow_[story-number]_[description].png`
   - Screenshot: `ss_[story-number]_[step-number]_[description].png`