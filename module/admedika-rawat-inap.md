# PRD - Bridging AdMedika Rawat Inap

**Professional Product Requirements Document**
Hospital Information System (HIS) V2
Primaya Hospital Group

---

## Document Property

| Property | Value |
|----------|-------|
| Document Number | 001/ADMEDIKA-RI/PRD/PHG/I/2026 |
| Document Title | PRD Bridging AdMedika Rawat Inap - Primaya Hospital Group |
| Project Name | Hospital Information System (HIS) V2 |
| Institution | Rumah Sakit Primaya Hospital Group |
| Module Name | Bridging AdMedika Rawat Inap |
| Document Editor | Claude AI |
| Target Level | Private |
| Document Status | Completed (Reworked v3.0 - 4 Stories) |
| Version | 3.0 |
| Created Date | 09 Jan 2026 |
| Last Updated | 12 Jan 2026 |

---

## Executive Summary

Dokumen Persyaratan Produk (PRD) ini memberikan gambaran rinci tentang implementasi **Bridging AdMedika untuk layanan Rawat Inap** dalam sistem HIS V2 Primaya Hospital Group dengan 4 user stories yang saling terintegrasi dalam satu dashboard AdMedika.

### Latar Belakang

Primaya Hospital Group memerlukan integrasi dengan sistem AdMedika untuk memfasilitasi pasien menggunakan payor AdMedika dalam mendapatkan layanan Rawat Inap. Integrasi AdMedika sudah tersedia untuk layanan Rawat Jalan, sekarang dilanjutkan ke layanan Rawat Inap. Implementasi ini mencakup 3 touchpoint utama:
1. Pendaftaran Rawat Inap
2. Transfer Rawat Inap
3. Migrasi Pasien

Semua proses ini akan terintegrasi dalam dashboard AdMedika yang unified dengan fitur:
- Pendaftaran & pengecekan benefit instant
- Proses klaim dengan auto-mapping dan kalkulasi
- Upload dokumen support klaim
- Daily monitoring benefit usage dengan alert system

### Tujuan Sistem

- Memfasilitasi penggunaan payor AdMedika oleh pasien rawat inap melalui proses pendaftaran yang simplified dan instant benefit verification
- Mengotomatisasi pengecekan benefit rawat inap (hak kamar, obat, tindakan) secara real-time di touchpoint pendaftaran
- Mengelola proses klaim yang komprehensif dengan auto-mapping benefit, kalkulasi billing, dan upload dokumen lengkap dalam satu interface
- Monitoring penggunaan benefit harian dengan risk indicator dan alert system untuk mencegah overspending

---

## Scope Overview

### Fitur Utama

1. **Integrasi Pendaftaran Pasien AdMedika** - Payor AdMedika tersedia saat registrasi rawat inap dengan instant benefit verification
2. **Pengecekan Benefit Rawat Inap** - Cek benefit real-time dengan breakdown per kategori (Kamar, Obat, Tindakan)
3. **Dashboard AdMedika** - Dashboard unified yang menampilkan pasien AdMedika dengan tab Proses Klaim, Upload Dokumen, dan Daily Monitoring
4. **Proses Klaim Rawat Inap** - Proses klaim dengan benefit mapping drag-drop, kalkulasi, dan status tracking dalam satu interface
5. **Upload Dokumen Klaim** - Interface terpisah untuk upload dokumen support klaim dengan checklist dan validasi
6. **Daily Monitoring Penggunaan Benefit** - Monitor benefit usage harian dengan risk indicator dan alert system

### Tidak Termasuk dalam Scope

- Penentuan ekses billing (manual di kasir oleh administrasi)
- Lock billing (hanya notifikasi unlock jika ada penambahan layanan)
- Negosiasi co-payment dengan pasien
- Integrasi dengan peralatan medis atau payment gateway pihak ketiga

---

## User Personas

### Persona 1: Admisi/Registrasi
- **Peran:** Staff Admisi Rawat Inap
- **Goals:** Registrasi pasien dengan payor AdMedika yang cepat dan akurat, instant benefit verification
- **Tech Level:** Menengah

### Persona 2: Kasir/Billing
- **Peran:** Staff Kasir/Billing Rawat Inap
- **Goals:** Manage proses klaim, mapping benefit, upload dokumen, dan tracking status klaim
- **Tech Level:** Menengah-Tinggi

### Persona 3: Case Mix Manager
- **Peran:** Case Mix/Medical Record Manager
- **Goals:** Monitor benefit usage harian, identify risk cases, dan trigger intervention
- **Tech Level:** Tinggi

---

## User Stories

### Story #1: Pendaftaran Pasien Rawat Inap dengan Payor AdMedika

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Admisi/Registrasi |
| **Jobs to be Done** | Melakukan pendaftaran pasien rawat inap dengan pemilihan payor AdMedika, instant benefit verification, dan konfirmasi registrasi |
| **Referensi UI** | Screenshots folder: `001-pendaftaran-dan-cek-benefit` (8 screenshots) |

#### Deskripsi

Staff Admisi Rawat Inap melakukan pendaftaran pasien baru atau transfer pasien yang akan menggunakan payor AdMedika. Sistem akan memandu melalui proses verifikasi benefit AdMedika secara real-time dan menampilkan hak coverage untuk kamar, obat, dan tindakan medis. Setelah registrasi sukses, dashboard AdMedika akan ditampilkan dengan tab-tab untuk proses klaim, upload dokumen, dan daily monitoring.

#### User Acceptance Criteria

1. Staff dapat membuka form pendaftaran rawat inap dengan standard fields (nama, NIK, DOB, alamat, telepon)
2. Setelah data dasar terisi, form Cek Benefit ditampilkan dengan dropdown payor yang sudah ter-filter hanya payor aktif
3. Saat memilih AdMedika, field "Nomor Peserta AdMedika" menjadi required dan focused untuk input
4. Sistem melakukan verifikasi real-time ke API AdMedika dengan mengirim nomor peserta dan tanggal lahir
5. Benefit details ditampilkan dalam breakdown kategori (Kamar, Obat, Tindakan) dengan clear visual hierarchy
6. Jika verifikasi gagal, error message ditampilkan dengan opsi Retry atau pilih payor lain
7. Benefit information yang ditampilkan mencakup coverage %, co-payment amount, dan available limit per kategori
8. Setelah semua data valid, dashboard AdMedika ditampilkan dengan tab: Proses Klaim, Upload Dokumen, Daily Monitoring
9. Registrasi confirmation page menampilkan: Patient ID, Payor Status (AdMedika), Benefit Summary, dan Next Steps

#### User Flow

```
[Start: Pendaftaran Rawat Inap]
  ↓
[Input Data Pasien - Step 001]
  - Nama, NIK, DOB, Gender, Alamat, Telepon
  ↓
[Cek Benefit & Pilih Payor - Step 002-003]
  - Dropdown payor dengan filter ACTIVE
  - Select AdMedika → Nomor Peserta field required
  ↓
[Verifikasi ke AdMedika API]
  - Request: no_peserta, tgl_lahir
  - Response: status, nama_peserta, benefit details
  ↓
{Verifikasi Berhasil?}
  ↓ YES                              ↓ NO
[Tampilkan Benefit - Step 004]    [Error Message - Step 005]
  - Kamar breakdown                  - Reason
  - Obat breakdown                   - [Retry] [Select Other]
  - Tindakan breakdown               ↓ (return ke Step 002-003)
  ↓
[Confirm Registration - Step 008]
  - Summary data review
  - [Confirm & Save]
  ↓
[Dashboard AdMedika - Step 007]
  - Navigasi ke dashboard
  - Tab: Proses Klaim, Upload Dokumen, Daily Monitoring
  ↓
[End: Registration Success]
```

#### Screenshots dalam Story #1

| No | Screenshot | Deskripsi |
|---|-----------|-----------|
| 001 | form-pendaftaran-rawat-inap.png | **Form Pendaftaran Rawat Inap** menampilkan standard registration form dengan fields: Nama Pasien, NIK (numeric validation), Tanggal Lahir (date picker), Jenis Kelamin (radio: Laki-laki/Perempuan), Alamat (textarea), Nomor Telepon (phone format), dan Status Tipe Pasien (dropdown: Baru/Transfer/Migrasi). Semua fields required, dengan real-time validation dan clear visual indication untuk required fields (asterisk/bold label). Form pre-populate data jika pasien sudah terdaftar. Setelah lengkap, user klik **[Lanjutkan]** atau **[Cek Benefit]** untuk lanjut ke step berikutnya. |
| 002 | form-cek-benefit.png | **Form Cek Benefit (Initial View)** menampilkan summary data pasien yang sudah di-input (read-only: Nama, NIK, DOB) dan dropdown "Pilih Payor" berisi semua payor dengan STATUS ACTIVE di sistem, ter-filter alphabetically dengan search/autocomplete functionality. Default text: "-- Pilih Payor --". User dapat scroll list atau type nama payor untuk filter dan memilih AdMedika dari list. |
| 003 | form-cek-benefit-pilih-admedika.png | **Form Cek Benefit (Setelah Pilih AdMedika):** Saat user select "AdMedika" dari dropdown, field baru otomatis muncul "Nomor Peserta AdMedika" (required, focused), dengan placeholder "Contoh: 123456789", validation alphanumeric max 20 chars, dan help text "Masukkan nomor peserta AdMedika yang tertera di kartu". User input nomor peserta, lalu sistem trigger API verification otomatis atau via "Verifikasi" button. |
| 004 | tampilan-benefit-admedika.png | **Tampilan Benefit AdMedika (Verifikasi Berhasil):** Jika API verification success, display header confirmation (✓ "Peserta AdMedika Terverifikasi", nama peserta, paket, tanggal verifikasi) diikuti **3 Benefit Breakdown Sections** dengan card layout:<br/>**KAMAR:** Class selection (VIP/Kelas 1/2/3), Coverage X% dari tarif RS, Co-payment Rp[Y]/hari, Hak total [Z] hari, Green badge "Covered"<br/>**OBAT:** "Covered sesuai formularium AdMedika", Coverage X%, Co-payment Rp[Y]/item, Green badge "Covered"<br/>**TINDAKAN:** "Covered dengan co-payment per prosedur", Coverage X%, Co-payment Rp[Y]/tindakan, Green badge "Covered"<br/>Clear visual hierarchy dengan spacing. User dapat scroll. Button **[Lanjutkan]** atau **[Confirm Benefit]** enabled. |
| 005 | jika-gagal.png | **Error Message (Verifikasi GAGAL):** Prominent red Error Alert Box menampilkan ✗ "Verifikasi Gagal" dengan detailed error message sesuai API response (contoh: "Peserta tidak ditemukan", "Status tidak aktif", "Data tidak sesuai (DOB)", "Koneksi timeout"). **Recovery Options:** buttons untuk **[Retry Verifikasi]**, **[Pilih Payor Lain]** (kembali ke 002), atau **[Batal]** (clear & restart). Error di-log untuk audit trail. |
| 006 | ketika-upload-dokumen-diklik.png | **Upload Dokumen (Optional Step):** Modal dialog "Upload Dokumen Pendukung (Opsional)" dengan text "Anda dapat upload untuk mempercepat proses klaim". Drag-drop area dengan text "Drag file di sini atau klik untuk browse" + **[Browse]** button. **Checklist dokumen:** KTP/Identitas (PDF/JPG), Kartu Peserta AdMedika (PDF/JPG), Medical Record (PDF). Per dokumen: format & size info, progress indicator, [Remove] button. Bottom buttons: **[Skip]** (continue tanpa upload), **[Upload & Lanjutkan]**. Optional, non-blocking. |
| 007 | menuju-ke-dashboard-pasien-AdMedika.png | **Dashboard AdMedika Navigation:** Setelah registrasi sukses, sistem auto-navigate ke Dashboard AdMedika menampilkan: **Patient Summary Card** (Patient Name, MR Number auto-generated, Admission Date & Time, Room/Bed, **Payor Status Badge**: "✓ AdMedika (Verified)" green) + **Three Tabs:** "Proses Klaim" | "Upload Dokumen" | "Daily Monitoring" + **Benefit Summary Card** (read-only): Kamar: [X] hari / Rp[Y] limit | Coverage Z%, Obat: Covered formularium | Coverage Z%, Tindakan: Covered co-payment | Coverage Z%. Menunjukkan integrated dashboard struktur. |
| 008 | pendaftaran-pasien-dengan-admedika-bisa-terisi-ke-form.png | **Confirmation Page (Registrasi Complete):** Green success message box ✓ "Registrasi Berhasil" + subtitle "Data pasien telah tersimpan dalam sistem HIS dengan payor AdMedika". **Summary (read-only):** Nama Pasien, Nomor Rekam Medis (auto-generated), Nomor Peserta AdMedika, Status Payor (AdMedika - Verified), Tanggal Pendaftaran, Status Admisi (Active/Rawat Inap). **Next Steps:** Step 1: ✓ Pendaftaran selesai, Step 2: (Soon) Kasir proses klaim post-discharge, Step 3: (Soon) Upload dokumen. Bottom buttons: **[Kembali ke Dashboard]**, **[Lihat Dashboard AdMedika]**. Peace of mind confirmation. |

#### System Integration

**API Calls:**
- `POST /api/v1/admedika/peserta/verify` - Verify peserta AdMedika membership
- `GET /api/v1/admedika/benefit/{peserta_id}` - Get benefit detail
- `POST /his/admisi/registrasi-rawat-inap` - Save admission record

**Database Operations:**
- Insert `admissions` dengan payor_id (AdMedika)
- Insert `admedika_payor_mapping` dengan status REGISTERED
- Insert `admedika_benefit_snapshot` untuk snapshot benefit saat registrasi
- Create audit log entry

#### Non-Functional Requirements

- **Performance**: API call < 3 detik, form load < 2 detik, UI responsif pada network 3G
- **Security**: All patient data encrypted at rest, audit trail untuk setiap verifikasi attempt
- **Validation**: Input validation on client & server side, prevent SQL injection & XSS
- **Caching**: Cache benefit data untuk 24 jam untuk improve performance
- **Accessibility**: Form accessible via keyboard, screen reader compatible

#### Sign-off

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Admisi Manager | | | |
| IT Manager | | | |
| Medical Director | | | |

---

### Story #2: Proses Klaim Rawat Inap

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Kasir/Billing |
| **Jobs to be Done** | Mengelola proses klaim rawat inap dari dashboard AdMedika dengan benefit mapping, kalkulasi, dan finalisasi klaim |
| **Referensi UI** | Screenshots folder: `002-proses-klaim` (6 screenshots) |

#### Deskripsi

Staff Kasir/Billing mengakses dashboard AdMedika dan membuka tab "Proses Klaim". Di sini, mereka dapat melihat daftar pasien AdMedika yang siap untuk di-klaim, melakukan benefit mapping melalui drag-and-drop interface, melihat kalkulasi otomatis, dan melakukan discharge serta finalisasi klaim. Setiap step menampilkan visual yang jelas tentang service yang akan di-klaim dan berapa benefit yang akan diterima vs co-payment pasien.

#### User Acceptance Criteria

1. Kasir dapat membuka tab "Proses Klaim" di dashboard AdMedika dan melihat list pasien AdMedika yang ready untuk di-klaim
2. Dashboard menampilkan informasi pasien: Name, MR Number, Admission Period, Total Charge, Current Status
3. Saat membuka proses klaim untuk pasien, sistem menampilkan semua services yang diberikan selama admission
4. Sistem menampilkan interface mapping dengan drag-drop capability antara services dan benefit categories
5. Setiap service memiliki unit price dan total charge yang ter-kalkulasi dari admission data
6. Saat user melakukan mapping/drag-drop, sistem otomatis kalkulasi benefit amount berdasarkan benefit rules
7. Kalkulasi menampilkan breakdown: RS Charge, Benefit Amount, Co-payment, Patient Tagihan (excess)
8. User dapat trigger "Proses Discharge" button yang akan finalize klaim dan update status
9. Setelah discharge, status berubah menjadi "Sudah Diklaim" dan klaim reference number di-generate
10. Hasil kalkulasi menampilkan item yang approved vs unapproved untuk transparansi

#### User Flow

```
[Start: Dashboard AdMedika]
  ↓
[View Pasien List - Step 001]
  - List pasien AdMedika dengan status discharge/ready-for-claim
  - Columns: Name, MR, Admission, Total Charge, Status
  ↓
[Select Pasien untuk Proses Klaim]
  ↓
[Proses Klaim Interface - Step 002]
  - Left panel: Services list dengan price
  - Right panel: Benefit categories (Kamar, Obat, Tindakan, etc)
  - Middle: Drag-drop mapping area
  ↓
[Auto-mapping / Manual Mapping - Step 003]
  - System suggests mapping based on service type
  - User dapat drag-drop untuk adjust mapping
  - Real-time kalkulasi saat mapping updated
  ↓
[Benefit Mapping Detail - Step 003]
  - Show coverage % per benefit category
  - Show co-payment rules
  - Show estimated benefit amount
  ↓
[Review Calculation - Step 004]
  - Confirmation dialog untuk proses discharge
  - Display: Total RS Charge, Total Benefit, Total Co-payment, Patient Tagihan
  ↓
[Klik Proses Discharge]
  ↓
[Kalkulasi Total - Step 005]
  - System finalize calculation
  - Generate Klaim Reference Number: CLM-YYYY-XXXXX
  - Show breakdown: Approved vs Unapproved items
  ↓
[Status Updated to "Sudah Diklaim" - Step 006]
  - Display klaim reference number
  - Display status history: Submitted, Under Review, etc
  - Action button berubah dari "Proses Klaim" → "Lihat Klaim"
  ↓
[End: Klaim Process Completed]
```

#### Screenshots dalam Story #2

| No | Screenshot | Deskripsi |
|---|-----------|-----------|
| 001 | tampilan-dashboard-admedika.png | **Dashboard Pasien AdMedika** menampilkan daftar pasien AdMedika. **Filter Section:** No. Reg (text input), No. Rek Med (text input), Penjamin (dropdown), Departemen (dropdown), Cari button, Reset button. **Patient Table Columns:** No., No. Reg, No. Rek. Med., Nama Pasien, Penjamin, Departemen, Tanggal Kunjungan, Jenis Kunjungan, LoA, LoC, Action. **Per-row Action Buttons:** Proses Klaim button (untuk pasien belum diklaim), Lihat Klaim button (untuk pasien sudah diklaim), Batalkan button. **Pagination** menampilkan page indicator dan jumlah records total. |
| 002 | ketika-klik-proses-klaim-tampil-pop-up-proses-klaim.png | **Modal "Proses Klaim"** menampilkan data pasien dan interface mapping benefit. **Header Patient Info:** Nama Pasien, No. Reg, No. Rekam Medis, Penjamin, Departemen, Jenis Kunjungan. **Tab Buttons:** Discharge Pasien, Upload Dokumen, Daily Monitoring. **Section "Informasi Medis Pasien":** Diagnosis (text field), Nama Dokter (text field), Pasien Kecelakaan (radio buttons: Ya/Tidak), Dilakukan Operasi (radio buttons: Ya/Tidak), Catatan (textarea). **Section "Mapping Benefit"** dengan dua kolom: **Kolom kiri "Biaya RS"** menampilkan services/items grouped by category (Biaya Konsultasi Spesialis, Biaya Administratif, Biaya Obat/Alkes Apotik) dengan item details dan amounts, Total display. **Kolom kanan "Benefit Penjamin"** menampilkan benefit categories (01 - Biaya Admin & Dokter Umum, 07 - Biaya Dokter Spesialis, 42 - Medical Check Up, 41 - Biaya Obat, 82 q - Imunisasi) siap untuk mapping, Total display. **Bottom Buttons:** Tutup, Proses Discharge Pasien. |
| 003 | ini-bisa-drag-and-drop-benefit.png | **Modal "Proses Klaim"** menunjukkan proses drag-and-drop mapping in progress. Beberapa service items sudah ter-drag dari kolom kiri ke kategori benefit di kolom kanan. **Kolom kiri "Biaya RS":** menampilkan remaining services yang belum di-map, grouped by category, dengan item details dan amounts, Total display. **Kolom kanan "Benefit Penjamin":** menampilkan benefit categories dengan mapped services di bawahnya, "Total Diajukan" display per kategori. User dapat terus melakukan drag-drop untuk map services lainnya. |
| 004 | ketika-sudah-mapping-semua-klik-proses-discharge-pasien.png | **Modal "Proses Klaim"** dengan mapping sudah lengkap semua items ter-map. **Kolom kiri "Biaya RS":** empty (semua services sudah di-map), Total display = 0. **Kolom kanan "Benefit Penjamin":** menampilkan semua benefit categories dengan mapped services di bawahnya masing-masing, X remove buttons per item, "Total Diajukan" display per kategori, Grand total display. Ready untuk finalisasi dengan klik "Proses Discharge Pasien" button. |
| 005 | tampil-hasil-ada-yang-disetujui-ada-tidak-disetujui.png | **Modal "Proses Klaim"** menampilkan hasil mapping dengan tab "Discharge Pasien" active. **Header:** informasi pasien display. **Section "Informasi Medis Pasien":** diagnosis, dokter, operasi, catatan info. **Section "Mapping Benefit":** **Kolom kiri "Biaya RS":** menampilkan service categories, Total display. **Kolom kanan "Benefit Penjamin":** menampilkan benefit categories dengan mapped items di bawahnya, "Total Diajukan" display per kategori, Grand total display. **Bottom Buttons:** Tutup, Cetak LoC. Interface menunjukkan summary hasil mapping. |
| 006 | tampilan-data-ketika-sudah-diklaim-kalo-klik-lihat-detail-kembali-ke-image-05.png | **Dashboard Pasien AdMedika** kembali ke list view. Menampilkan table dengan daftar pasien. **Action Button Updates:** Pasien yang baru di-klaim menampilkan button "Lihat Klaim" menggantikan "Proses Klaim", menunjukkan status bahwa klaim sudah disubmit. Pasien yang belum diklaim masih menampilkan button "Proses Klaim". Pasien dengan status lainnya menampilkan button "Lihat Klaim" atau "Batalkan" sesuai status. **Pagination:** menampilkan page indicator dan jumlah records total. |

#### System Integration

**API Calls:**
- `GET /his/admission/{admission_id}/services` - Get all services
- `GET /api/v1/admedika/benefit/{peserta_id}` - Get benefit rules for mapping
- `POST /api/v1/admedika/claim/calculate` - Calculate benefit & co-payment
- `POST /api/v1/admedika/claim/submit` - Submit klaim to AdMedika
- `GET /api/v1/admedika/claim/{claim_id}/status` - Track klaim status

**Database Operations:**
- Insert into `admedika_claim` dengan klaim details
- Insert into `admedika_claim_detail` untuk each service mapping
- Insert into `admedika_claim_calculation` untuk calculation breakdown
- Create entries di `admedika_audit_log`

#### Non-Functional Requirements

- **Performance**: Load services < 2 detik, calculation < 1 detik, API submit < 3 detik
- **Security**: Audit trail untuk setiap mapping change, encrypted file storage
- **Validation**: All services must be mapped, prevent duplicate mapping
- **Error Handling**: Graceful handling jika benefit data changed, retry mechanism

#### Sign-off

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Kasir/Billing Manager | | | |
| Finance Manager | | | |
| Medical Director | | | |

---

### Story #3: Upload Dokumen Klaim

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Kasir/Billing |
| **Jobs to be Done** | Upload dokumen support klaim dari dashboard AdMedika dengan checklist validasi dan progress tracking |
| **Referensi UI** | Screenshots folder: `003-upload-dokumen` (2 screenshots) |

#### Deskripsi

Setelah proses klaim selesai dan status menjadi "Sudah Diklaim", staff Kasir/Billing dapat upload dokumen support klaim melalui tab "Upload Dokumen" di dashboard AdMedika. Interface ini menampilkan checklist dokumen yang diperlukan, area untuk upload, progress indicator, dan validasi file.

#### User Acceptance Criteria

1. Tab "Upload Dokumen" tersedia di dashboard AdMedika setelah proses klaim selesai
2. Interface menampilkan checklist dokumen yang diperlukan untuk klaim approval
3. Checklist mencakup: Medical Record, Invoice, Receipt, Lab Results, Imaging, Medication Receipt, Other
4. User dapat upload file dengan drag-drop atau browse button
5. System melakukan file validation: format (PDF/JPG/PNG), size (max 10MB), dan mandatory field check
6. Upload progress indicator menampilkan status upload per file
7. User dapat delete dan re-upload file jika diperlukan
8. Setelah semua mandatory documents uploaded, submission status berubah menjadi ready
9. System menampilkan confirmation bahwa semua dokumen berhasil diterima

#### User Flow

```
[Start: Dashboard AdMedika - Proses Klaim Tab]
  ↓
[Klik Tab "Upload Dokumen" - Step 001]
  - Dari proses klaim, link ke upload dokumen
  ↓
[Upload Dokumen Interface - Step 002]
  - Menampilkan checklist dokumen yang diperlukan
  - Drag-drop area atau [Browse] button
  - File validation info (format, size)
  ↓
[Upload Dokumen Support Klaim]
  - Medical Record / Ringkasan Klinis (Mandatory)
  - Invoice / Rincian Biaya (Mandatory)
  - Receipt / Bukti Pembayaran (Mandatory)
  - Lab Results / Hasil Lab (Conditional)
  - Imaging Results (Conditional)
  - Medication Receipt (Conditional)
  - Other Supporting Docs (Optional)
  ↓
[Upload Progress & Validation]
  - Show upload progress per file
  - Validate: Format, Size, Content
  - Show error if validation fails
  ↓
{All Mandatory Docs Uploaded?}
  ↓ YES
[Submission Ready - Step 002]
  - "✓ Semua dokumen berhasil diunggah"
  - Display list dokumen yang sudah uploaded
  - [Confirm Submission] button enabled
  ↓
[Submit Klaim dengan Dokumen]
  - Send to AdMedika dengan semua dokumen
  - Update klaim status to SUBMITTED_WITH_DOCS
  ↓
[Confirmation Message]
  - Klaim dengan dokumen sudah dikirim ke AdMedika
  - Estimated review time
  ↓
[End: Upload Complete]
```

#### Screenshots dalam Story #3

| No | Screenshot | Deskripsi |
|---|-----------|-----------|
| 001 | dari-proses-klaim-klik-upload-dokumen.png | **Navigation: Dashboard AdMedika Tabs** menampilkan tab navigation: **Tab "Proses Klaim"**, **Tab "Upload Dokumen"** ← User klik tab ini untuk access upload interface. Alternatif: dari proses klaim, user dapat klik button untuk direct link ke tab. Sistem navigate ke Tab "Upload Dokumen" dan load interface. |
| 002 | selanjutnya-tampil-tab-upload-dokumen-klik-button-upload.png | **Tab "Upload Dokumen" Interface dengan Checklist:** **Header Section:** Title, Subtitle, Klaim Reference Number (read-only). **Info Messages:** Keterangan tentang dokumen wajib, format file yang diterima, ukuran maksimal, dan instruksi. **Document Checklist - Grouped by Importance:** **MANDATORY Group:** Checkbox items untuk dokumen wajib (Medical Record/Ringkasan Klinis, Invoice/Rincian Biaya, Receipt/Bukti Pembayaran) dengan status indicator. **CONDITIONAL Group:** Checkbox items untuk dokumen conditional (Lab Results, Imaging Results, Medication Receipt). **OPTIONAL Group:** Checkbox items untuk dokumen optional (Other Supporting Documents). **Upload Interface per document:** Drag-drop area OR Browse button OR clickable upload area. **Status Indicators:** Not Uploaded (gray), Uploading (progress), Uploaded (green), Error (red). **Completion Status & Actions:** Progress display dengan jumlah dokumen yang sudah uploaded. **Action Buttons:** Submit Klaim button (state: disabled/enabled based on mandatory docs), Save as Draft button, Cancel button. Clear mandatory vs optional indication with submit button control logic. |

#### System Integration

**API Calls:**
- `POST /api/v1/admedika/claim/{claim_id}/upload-document` - Upload dokumen
- `DELETE /api/v1/admedika/claim/{claim_id}/document/{doc_id}` - Delete dokumen
- `GET /api/v1/admedika/claim/{claim_id}/documents` - Get uploaded documents
- `POST /api/v1/admedika/claim/{claim_id}/submit-with-documents` - Final submission

**Database Operations:**
- Insert into `admedika_claim_document` untuk setiap dokumen uploaded
- Update `admedika_claim` status to SUBMITTED_WITH_DOCUMENTS
- Create audit log untuk setiap upload/delete action

#### Non-Functional Requirements

- **Performance**: File upload < 30 detik untuk 10MB file, UI remain responsive
- **Security**: File stored encrypted, virus scan di server, access control
- **Validation**: File integrity check, prevent malicious file upload
- **Scalability**: Support concurrent uploads dari multiple users

#### Sign-off

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Kasir/Billing Manager | | | |
| IT Manager | | | |
| Medical Director | | | |

---

### Story #4: Daily Monitoring Penggunaan Benefit

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Case Mix Manager |
| **Jobs to be Done** | Monitor penggunaan benefit pasien AdMedika harian dari dashboard dengan input data, risk detection, dan alert triggering |
| **Referensi UI** | Screenshots folder: `004-daily-monitoring` (5 screenshots) |

#### Deskripsi

Case Mix Manager mengakses tab "Daily Monitoring" di dashboard AdMedika untuk monitor penggunaan benefit pasien rawat inap. Tab ini menampilkan list semua pasien AdMedika yang sedang dirawat dengan benefit utilization percentage, risk indicator, dan alert status. Manager dapat input additional services/charges untuk update real-time calculation dan melihat benefit remaining untuk setiap pasien. System otomatis trigger alert ketika usage mencapai >85%.

#### User Acceptance Criteria

1. Tab "Daily Monitoring" accessible dari dashboard AdMedika
2. Dashboard menampilkan list semua active patients dengan payor AdMedika
3. Setiap pasien menampilkan: Name, MR Number, Room, Admission Date, Benefit Available, Benefit Used, Benefit Remaining, Usage %
4. Usage % ditampilkan dengan visual progress bar dengan color coding: Green (<50%), Yellow (50-84%), Orange (85-99%), Red (>100%)
5. Risk indicator icon (⚠️) muncul ketika usage >85%
6. System otomatis trigger alert notification ketika usage mencapai >85% (email, SMS, in-app)
7. User dapat klik [Add Data] button untuk input additional services/charges
8. Input form menampilkan: Patient selection, Service category, Amount, Date, Notes
9. Setiap input otomatis update benefit usage calculation dan progress bar di dashboard
10. Confirmation message menampilkan updated benefit usage dan current status

#### User Flow

```
[Start: Dashboard AdMedika]
  ↓
[Klik Tab "Daily Monitoring" - Step 001]
  - Navigate to daily monitoring interface
  ↓
[View Daily Monitoring Dashboard - Step 002]
  - Display list all active patients dengan payor AdMedika
  - Columns: Name, MR, Room, Admission Date, Benefit Available, Benefit Used, Benefit Remaining, Usage %
  - Color coding: Green (<50%), Yellow (50-84%), Orange (85-99%), Red (>100%)
  - Risk icon: ⚠️ if >85%, 🚨 if >100%
  ↓
{Risk Detection}
  - System automatic scan setiap 5 menit
  - If Usage > 85%: Trigger Alert
    ↓
    [Alert Notification - Step 001]
    - Email + SMS + In-app notification
    - Content: Patient Name, Current Usage %, Recommended Action
    - [View Patient] button di notification
  ↓
[Add Monitoring Data - Step 003a]
  - User klik [Add Data] button
  - Modal opens dengan quick input form
  - Fields: Patient (dropdown), Category, Amount, Date, Notes
  ↓
[Detailed Form (if needed) - Step 003b]
  - Expanded form dengan additional fields
  - Auto-fill service details dari service master
  - Real-time benefit calculation
  ↓
[Input Data & Submit]
  - User input semua required fields
  - [Save] button submit data
  ↓
[Confirmation & Update - Step 004]
  - Success message: "✓ Data Berhasil Disimpan"
  - Display summary: Service, Amount, New Usage %
  - Previous Usage % → New Usage %
  - Benefit progress bar updated dengan new status
  ↓
[Dashboard Auto-refresh]
  - Table updated dengan new data
  - Progress bar color updated jika threshold crossed
  - Alert re-triggered jika applicable
  ↓
[End: Daily Monitoring Complete]
```

#### Screenshots dalam Story #4

| No | Screenshot | Deskripsi |
|---|-----------|-----------|
| 001 | dari-proses-klaim-ke-daily-monitoring.png | **Tab Navigation di Dashboard AdMedika** menampilkan tiga tab utama: "Proses Klaim", "Upload Dokumen", dan "Daily Monitoring". User dapat mengakses Daily Monitoring dengan mengklik tab ini atau melalui link di sidebar dashboard. Setelah klik, sistem akan navigate ke Daily Monitoring interface dan memuat data monitoring terbaru. |
| 002 | tampil-tab-daily-monitoring-terdapat-data-disana.png | **Tampilan Daily Monitoring Dashboard** menampilkan list lengkap semua pasien AdMedika yang sedang dirawat inap. Di bagian atas terdapat section untuk filter dan kontrol data, dengan date range picker untuk memilih periode monitoring, dropdown untuk filter berdasarkan tingkat risiko (Normal/Caution/Alert/Excess), dropdown status pasien (Active/About to Discharge), search box untuk mencari pasien berdasarkan nama atau nomor MR, tombol manual refresh, dan indikator status auto-refresh. Tabel utama menampilkan kolom-kolom penting meliputi nomor urut, nama pasien yang dapat diklik untuk detail, nomor rekam medis, kamar, tanggal masuk, jumlah hari dirawat, benefit yang tersedia, benefit yang sudah digunakan, benefit sisa, dan persentase penggunaan benefit dalam bentuk progress bar berwarna (hijau untuk <50%, kuning untuk 50-84%, oranye untuk 85-99%, merah untuk >100%). Setiap baris pasien juga menampilkan risk indicator icon dan tombol action untuk melihat detail atau menambah data monitoring. Pagination ditampilkan di bawah untuk navigasi antar halaman. |
| 003a | tampil-form-tambah-data-daily-monitoring.png | **Modal Form Input Cepat** "Tambah Data Monitoring - Input Cepat" terbuka ketika user mengklik tombol Add Data dari dashboard. Form ini dirancang untuk input data yang cepat dan sederhana dengan field-field: dropdown untuk memilih pasien (dengan fitur search/autocomplete), dropdown kategori service, field numeric untuk amount dalam format Rp, date picker untuk tanggal service, dan textarea opsional untuk catatan. Setiap field yang required akan memiliki validasi real-time dengan pesan error inline dan highlighting jika ada kesalahan. Tombol action di bawah mencakup Save untuk menyimpan data, Cancel untuk membatalkan, dan link "Expand Form" untuk membuka form lengkap jika perlu input lebih detail. |
| 003b | tampilan-form-tambah-daily-monitoring-complete.png | **Modal Form Input Lengkap** "Tambah Data Monitoring - Form Lengkap" menyediakan interface yang lebih komprehensif untuk input data monitoring dengan presisi tinggi. Form terbagi menjadi beberapa section: pertama adalah section informasi pasien (read-only) yang menampilkan nama pasien, nomor rekam medis, kamar, tanggal admission, dan dokter pengasuh. Section kedua untuk detail service mencakup kode service dengan dropdown berfitur search, deskripsi service (auto-fill, read-only), kategori service (auto-fill), tanggal service, quantity, dan unit price beserta total amount yang ter-kalkulasi otomatis. Section ketiga menampilkan perhitungan benefit secara real-time, memungkinkan user untuk memilih/mengedit kategori benefit terpetakan, menampilkan coverage percentage, estimasi benefit amount, dan co-payment amount yang semuanya ter-update secara real-time saat user mengubah data. Section terakhir adalah textarea optional untuk catatan tambahan. Semua perhitungan (service amount, coverage %, benefit amount, co-payment) ditampilkan dan diupdate secara langsung saat user melakukan perubahan. Tombol action mencakup Save untuk menyimpan, Cancel untuk membatalkan, dan link untuk collapse form kembali ke versi quick form. |
| 004 | daily-monitoring-berhasil-ditambahkan.png | **Layar Konfirmasi Success** menampilkan green success message card dengan tanda "✓ Data Berhasil Disimpan" beserta subtitle dan timestamp pencatatan. Di bawah pesan success, sistem menampilkan ringkasan data yang baru saja di-input meliputi service details (nama service, kategori, amount, quantity, tanggal) dan benefit calculation details (coverage %, benefit amount, co-payment). Untuk memberikan konteks dampak, screen menampilkan comparison sebelum dan sesudah: bagian "Sebelum" menunjukkan benefit used, benefit remaining, dan usage % pasien sebelum entry baru, sedangkan bagian "Sesudah" menampilkan nilai-nilai yang sudah diupdate dengan visual indicator menunjukkan perubahan yang terjadi. Jika input data ini menyebabkan usage mencapai threshold alert (>85%), sistem menampilkan notification alert yang memberitahu tentang kondisi ini dan info tentang pengiriman alert (email/SMS/in-app). Tombol action di bawah mencakup "Kembali ke Dashboard" yang akan me-refresh dashboard secara otomatis dengan data terbaru, "Tambah Data Lagi" untuk kembali membuka form dan menambah data lainnya, dan "Lihat Detail Pasien" untuk melihat semua informasi detail pasien tersebut. |

#### System Integration

**API Calls:**
- `GET /his/admissions/active?payor=ADMEDIKA` - Get all active AdMedika admissions
- `GET /his/admission/{id}/benefit-usage` - Get current benefit utilization
- `GET /his/admission/{id}/services` - Get all services charged to date
- `GET /api/v1/admedika/benefit/{peserta_id}` - Get current benefit limits & rules
- `POST /his/monitoring/add-usage` - Record new service/usage entry
- `POST /his/monitoring/alert` - Trigger alert when threshold crossed
- `GET /his/monitoring/weekly-report` - Generate weekly report

**Database Operations:**
- Insert into `admedika_benefit_usage` untuk setiap monitoring entry
- Update `admedika_daily_monitoring` dengan latest usage data
- Insert into `admedika_alert_log` saat alert triggered
- Create audit log entry untuk setiap action
- Generate report dari aggregated `admedika_daily_monitoring` data

#### Non-Functional Requirements

- **Performance**: Dashboard load dengan list 100+ patients dalam < 5 detik, add data dalam < 2 detik
- **Real-time**: Usage % updated immediately setelah data input, dashboard reflect within 10 seconds
- **Scalability**: Support concurrent monitoring dari multiple Case Mix Managers
- **Data Accuracy**: Benefit calculation consistent dengan benefit master & previous entries
- **Alerting**: Alert delivery within 1 minute of threshold crossing
- **Reporting**: Weekly report generation < 10 minutes untuk dataset dengan 1000+ patients

#### Known Issues & Limitations

- Alert notification delivery depends on email/SMS gateway availability
- Real-time calculation based on cached benefit data (refreshed every 6 hours)
- Cannot modify past monitoring entries (write-once principle untuk audit compliance)
- Weekly report generation may take 5-10 minutes untuk large dataset

#### Dependencies

- Active admission data maintained current dalam HIS
- Service master data updated dengan latest pricing & benefit mapping
- Benefit rules dari AdMedika di-cache dan refreshed every 6 hours
- Email/SMS notification system operational untuk alert delivery
- Background job scheduler operational untuk report generation

#### Sign-off

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Case Mix Manager | | | |
| Medical Director | | | |
| IT Manager | | | |

---

## Image Mapping Summary

| Story | Folder | Screenshot Count | Description |
|-------|--------|------------------|-------------|
| Story #1 | 001-pendaftaran-dan-cek-benefit | 8 | Pendaftaran & Cek Benefit dengan instant verification |
| Story #2 | 002-proses-klaim | 6 | Proses Klaim dengan drag-drop mapping & kalkulasi |
| Story #3 | 003-upload-dokumen | 2 | Upload dokumen support klaim dengan checklist |
| Story #4 | 004-daily-monitoring | 5 | Daily monitoring dengan risk detection & input data |
| **Total** | **4 folders** | **21 screenshots** | **Integrated AdMedika Dashboard** |

---

## Non-Functional Requirements (Global)

- **Performance**: All API calls < 3 detik, Dashboard load < 5 detik, UI responsif pada 3G network
- **Security**: SSL/TLS encryption, audit trail lengkap, role-based access control, data encryption at rest
- **Availability**: System uptime 99.5%, automated backup harian
- **Data Integrity**: Consistent benefit calculation across all modules, no data loss
- **Scalability**: Support 1000+ concurrent users, 10000+ patient records
- **Accessibility**: WCAG 2.1 AA standard, keyboard navigation, screen reader compatible

---

## Business Rules (Global)

1. **Payor Selection Rule**
   - Payor AdMedika hanya dapat dipilih jika status kepesertaan ACTIVE di AdMedika
   - Satu pasien satu admission hanya boleh satu payor
   - Perubahan payor hanya bisa pre-discharge

2. **Benefit Coverage Rules**
   - Hak kamar sesuai paket kepesertaan AdMedika
   - Obat covered sesuai formularium AdMedika
   - Tindakan medis ada co-payment sesuai schedule AdMedika

3. **Benefit Calculation Rules**
   - Benefit dihitung berdasarkan tarif RS dan coverage percentage dari AdMedika
   - Co-payment = Service Amount - Benefit Amount (atau fixed amount per rules)
   - Excess/Patient Tagihan = Total RS Charge - Total Benefit Coverage

4. **Claim Processing Rules**
   - Klaim hanya bisa di-submit setelah semua services ter-map dengan benefit category
   - Klaim harus include dokumen support sesuai checklist sebelum final submission
   - Audit trail lengkap untuk setiap klaim action

5. **Daily Monitoring Rules**
   - Data monitoring updated real-time saat ada service entry baru
   - Alert trigger otomatis jika usage > 85%
   - Weekly report auto-generated every Sunday midnight
   - Case Mix Manager harus acknowledge alert within 24 hours

---

## Success Metrics

1. **Registration Success Rate**: ≥95% registrasi dengan payor AdMedika berhasil verified
2. **Benefit Verification Accuracy**: ≥99% akurasi benefit data dari AdMedika
3. **Claim Processing Time**: Average 2-3 hari dari discharge sampai klaim submitted dengan dokumen lengkap
4. **Claim Approval Rate**: ≥90% klaim approved on first submission (dengan dokumen lengkap)
5. **Alert Accuracy**: 100% case dengan usage >85% ter-detect & alerted
6. **System Uptime**: 99.5% availability selama jam operasional

---

## Disclaimer

Dokumen ini dibuat dalam konteks Projek Hospital Information System (HIS) V2 Primaya Hospital Group. Semua informasi disediakan "sebagaimana adanya" tanpa jaminan. Pengguna menggunakan informasi ini atas risiko dan tanggung jawab tunggalnya.

---

## Sign-Off (Document)

**Document Prepared By:**
Claude AI | AI Assistant | 12 Jan 2026

**Reviewed By:**
[Manager Name, Title, Date]

**Approved By:**
[Director Name, Title, Date]

---

## Version History

| Versi | Tanggal | Deskripsi | Revised By |
|-------|---------|-----------|-----------|
| 3.0 | 12-01-2026 | **REWORK v3.0** - Complete restructure untuk 4 stories (Pendaftaran, Proses Klaim, Upload Dokumen, Daily Monitoring) dengan screenshot folders terpisah. Integrated dashboard AdMedika dengan semua functionality. Detailed functional requirements per story. | Claude AI |
| 2.0 | 12-01-2026 | REWORK v2.0 - Expanded 3 stories dengan detailed requirements, screenshots, flows, integrations | Claude AI |
| 1.0 | 09-01-2026 | Initial Draft - Admedika Rawat Inap PRD (19 Screenshots) | Claude AI |

---

**END OF DOCUMENT**

**Document Status:** ✅ **READY FOR REVIEW**

Last Updated: 12 January 2026
Next Review: Upon stakeholder feedback
