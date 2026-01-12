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
| Document Status | Completed (Reworked v2.0) |
| Version | 2.0 |
| Created Date | 09 Jan 2026 |
| Last Updated | 12 Jan 2026 |

---

## Executive Summary

Dokumen Persyaratan Produk (PRD) ini memberikan gambaran rinci tentang implementasi **Bridging AdMedika untuk layanan Rawat Inap** dalam sistem HIS V2 Primaya Hospital Group.

### Latar Belakang

Primaya Hospital Group memerlukan integrasi dengan sistem AdMedika untuk memfasilitasi pasien menggunakan payor AdMedika dalam mendapatkan layanan Rawat Inap. Integrasi AdMedika sudah tersedia untuk layanan Rawat Jalan, sekarang dilanjutkan ke layanan Rawat Inap dengan 3 touchpoint utama:
1. Pendaftaran Rawat Inap
2. Transfer Rawat Inap
3. Migrasi Pasien

### Tujuan Sistem

- Memfasilitasi penggunaan payor AdMedika oleh pasien rawat inap
- Mengotomatisasi pengecekan benefit rawat inap (hak kamar, obat, tindakan)
- Mengelola proses klaim dengan dokumentasi lengkap
- Monitoring penggunaan benefit real-time

---

## Scope Overview

### Fitur Utama

1. **Integrasi Pendaftaran Pasien Admedika** - Payor AdMedika tersedia saat registrasi rawat inap
2. **Pengecekan Benefit Rawat Inap** - Cek benefit real-time dengan breakdown per kategori
3. **Pemetaan Benefit ke Database Internal** - Mapping benefit AdMedika dengan master data RS
4. **Proses Klaim Rawat Inap** - Pengumpulan dan submission dokumen klaim
5. **Daily Monitoring Penggunaan Benefit** - Monitor benefit usage harian dengan alert

### Tidak Termasuk dalam Scope

- Penentuan ekses billing (manual di kasir oleh administrasi)
- Lock billing (hanya notifikasi unlock jika ada penambahan layanan)

---

## User Personas

### Persona 1: Admisi/Registrasi
- Peran: Staff Admisi Rawat Inap
- Goals: Registrasi pasien dengan payor AdMedika yang cepat dan akurat
- Tech Level: Menengah

### Persona 2: Kasir/Billing
- Peran: Staff Kasir/Billing Rawat Inap
- Goals: Verifikasi benefit, proses klaim, dan manage dokumentasi
- Tech Level: Menengah-Tinggi

### Persona 3: Case Mix Manager
- Peran: Case Mix/Medical Record Manager
- Goals: Monitor benefit usage harian dan identifikasi audit risk
- Tech Level: Tinggi

---

## User Stories

### Story #1: Pendaftaran Pasien Rawat Inap dengan Payor AdMedika

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Admisi/Registrasi |
| **Jobs to be Done** | Melakukan pendaftaran pasien rawat inap dengan pemilihan payor AdMedika, verifikasi benefit, dan konfirmasi data registrasi |
| **Referensi UI** | Screenshots 001-008 |

#### Deskripsi

Staff Admisi Rawat Inap melakukan pendaftaran pasien baru atau transfer pasien yang akan menggunakan payor AdMedika. Sistem akan memandu melalui proses verifikasi benefit AdMedika secara real-time dan menampilkan hak coverage untuk kamar, obat, dan tindakan medis.

#### User Acceptance Criteria

1. Staff dapat membuka form pendaftaran rawat inap dengan standard fields (nama, NIK, DOB, alamat, dll)
2. Setelah data dasar terisi, form Cek Benefit muncul otomatis dengan option untuk memilih payor
3. Dropdown payor menampilkan pilihan termasuk AdMedika dengan filter berdasarkan status kepesertaan active
4. Saat memilih AdMedika, sistem melakukan verifikasi real-time ke API AdMedika dengan mengirim no_peserta dan tanggal lahir
5. Benefit details ditampilkan dalam breakdown kategori (Kamar, Obat, Tindakan) dengan coverage percentage dan co-payment info
6. Jika verifikasi gagal, sistem menampilkan error message dan memberikan opsi untuk retry atau pilih payor lain
7. User dapat upload dokumen pendukung (KTP, Kartu Peserta, Medical Record) sebelum finalisasi
8. Setelah semua data valid, sistem menampilkan dashboard AdMedika dan konfirmasi bahwa registrasi berhasil disimpan

#### User Flow

```
[Start: Form Pendaftaran]
  → [Input Data Pasien]
  → [Cek Benefit - Pilih Payor]
  → {AdMedika Selected?}
    → [Yes] → [Verifikasi ke API AdMedika]
    → [No] → [Regular Payor Flow]

  [Verifikasi Berhasil?]
    → [Yes] → [Tampilkan Benefit Details]
      → [Upload Dokumen (Optional)]
      → [Confirm & Save]
      → [Dashboard AdMedika]
      → [End: Success]
    → [No] → [Error Message]
      → [Retry/Select Other]
      → [Return to Payor Selection]
```

#### Forms & Data Fields

**Form Pendaftaran Rawat Inap (Screenshot 001)**
- Nama Pasien (required, text)
- Nomor Identitas/NIK (required, numeric)
- Tanggal Lahir (required, date picker)
- Jenis Kelamin (required, radio: Laki-laki/Perempuan)
- Alamat (required, textarea)
- Nomor Telepon (required, phone)
- Asuransi/Payor (required, dropdown)

**Form Cek Benefit (Screenshot 002-003)**
- Nomor Peserta AdMedika (required, text - conditional if AdMedika selected)
- Payor Selection Dropdown dengan filter status ACTIVE
- Search & Select AdMedika option

**Benefit Display (Screenshot 004)**
- Benefit Category: Kamar
  - Hak Kamar: Class selection dengan limit
  - Coverage: X% dari tarif RS
  - Co-payment: Rp [amount]
- Benefit Category: Obat
  - List covered drugs dengan reference pricing
  - Coverage: X% dari tarif
  - Co-payment: Rp [amount]
- Benefit Category: Tindakan
  - List covered procedures dengan co-payment schedule
  - Coverage: X% dari tarif RS
  - Co-payment: Rp [amount]

**Error Handling (Screenshot 005)**
- Error Message Display dengan detail reason
- Retry Button untuk verifikasi ulang
- Cancel/Select Other Payor option

**Document Upload (Screenshot 006)**
- File upload field dengan supported formats (PDF, JPG, PNG)
- Document checklist:
  - [ ] KTP/Identitas
  - [ ] Kartu Peserta AdMedika
  - [ ] Medical Record (jika ada)
- Upload status indicator

#### Screenshots Referenced

| Step | Screenshot | Deskripsi |
|------|-----------|-----------|
| 1 | 001-form-pendaftaran-rawat-inap.png | Form pendaftaran standar dengan field dasar pasien |
| 2 | 002-form-cek-benefit.png | Form cek benefit dan pilih payor |
| 3 | 003-form-cek-benefit-pilih-admedika.png | Dropdown payor dengan opsi AdMedika |
| 4 | 004-tampilan-benefit-admedika.png | Detail breakdown benefit per kategori |
| 5 | 005-jika-gagal.png | Error message jika verifikasi gagal |
| 6 | 006-ketika-upload-dokumen-diklik.png | Modal/form upload dokumen pendukung |
| 7 | 007-menuju-ke-dashboard-pasien-AdMedika.png | Navigasi ke dashboard AdMedika |
| 8 | 008-pendaftaran-pasien-dengan-admedika-bisa-terisi-ke-form.png | Konfirmasi registrasi dengan data terisi lengkap |

#### System Integration

**API Calls:**
- `POST /api/v1/admedika/peserta/verify` - Verifikasi peserta
- `GET /api/v1/admedika/benefit/{peserta_id}` - Ambil detail benefit
- `POST /his/admisi/registrasi-rawat-inap` - Simpan registrasi

**Database Operations:**
- Insert ke `admedika_payor_mapping` dengan status REGISTERED
- Insert ke `admissions` dengan payor reference
- Insert ke `documents` untuk uploaded files

#### Non-Functional Requirements

- **Performance**: Verifikasi ke AdMedika harus selesai dalam < 3 detik, UI responsif pada 3G
- **Security**: Data pasien encrypted at rest, audit trail untuk setiap verifikasi
- **Validation**: No Special characters dalam no_peserta, Format DOB validated
- **Error Handling**: Graceful degradation jika API AdMedika timeout, cache benefit data 24 jam
- **Accessibility**: Form accessible via keyboard navigation, screen reader compatible

#### Known Issues & Limitations

- Jika AdMedika API down, user tidak dapat register dengan payor AdMedika (fallback ke payor lain)
- Benefit data cache untuk 24 jam, perubahan benefit real-time dari AdMedika tidak immediately reflected
- Upload dokumen optional, tidak blocking untuk finalisasi registrasi

#### Dependencies

- AdMedika API availability dan response time SLA
- Master data of Payor dan Benefit maintained in HIS
- Document storage system untuk file upload
- Integration gateway untuk secure API communication

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
| **Jobs to be Done** | Mengelola proses klaim rawat inap dengan pengecekan benefit, mapping layanan, kalkulasi billing, dan submission dokumen klaim ke AdMedika |
| **Referensi UI** | Screenshots 009-015 |

#### Deskripsi

Staff Kasir/Billing mengelola seluruh proses klaim untuk pasien AdMedika dari saat pasien discharge hingga submission klaim ke AdMedika. Proses meliputi validasi benefit yang digunakan, mapping layanan RS ke benefit coverage, kalkulasi biaya yang akan diklaim vs co-payment pasien, dan pengumpulan dokumen pendukung sebelum submission.

#### User Acceptance Criteria

1. Kasir dapat mengakses dashboard klaim dengan list pasien rawat inap yang siap di-klaim (status discharge)
2. Dashboard menampilkan ringkasan data pasien, admission period, dan payor (AdMedika)
3. User dapat membuka form proses klaim yang menampilkan semua layanan yang diberikan selama admission
4. Sistem automatic mapping layanan RS ke benefit categories dengan sugesti coverage berdasarkan benefit profile
5. User dapat override mapping jika diperlukan dengan audit trail
6. Sistem melakukan kalkulasi real-time: total RS charge, benefit coverage amount, co-payment, excess billing
7. Preview kalkulasi ditampilkan sebelum finalisasi untuk approval user
8. User dapat trigger proses discharge pasien dan finalisasi klaim
9. Setelah discharge, status berubah menjadi "Sudah Diklaim" dan action menjadi "Lihat Klaim" untuk tracking
10. User dapat upload dokumen support klaim dengan checklist dan upload status tracking

#### User Flow

```
[Start: Klaim Dashboard]
  → [Select Pasien - Discharge Status]
  → [Open Proses Klaim Form]
  → [Load All Services dari Admission]

[Mapping Phase]
  → [Display Services + Auto-mapping to Benefit]
  → {User Review & Override?}
    → [Yes] → [Update Mapping + Audit Trail]
    → [No] → [Continue with Auto-mapping]

[Detail Mapping Review]
  → [Show Coverage Percentage & Co-payment per Service]
  → [User Confirm Mapping]

[Calculation Phase]
  → [Calculate Total RS Charge]
  → [Calculate Benefit Coverage Amount]
  → [Calculate Co-payment]
  → [Calculate Excess/Tagihan Pasien]

[Proses Discharge]
  → [Click Proses Discharge Button]
  → [Finalize Klaim]
  → [Kalkulasi Total]
  → [Status → Sudah Diklaim]

[Document Upload]
  → [Upload Supporting Documents]
  → [Checklist: MR, Invoice, Receipt, Lab, dll]

[Submission]
  → [Ready for Klaim Submit]
  → [Track Status: Submitted → Review → Approved/Rejected]
  → [End: Success]
```

#### Forms & Data Fields

**Klaim Dashboard (Screenshot 009)**
- List Pasien dengan filter:
  - Status: Discharged, Ready for Claim
  - Date range filter
  - Search by patient name/number
- Summary columns:
  - Patient Name
  - Admission Date
  - Discharge Date
  - Duration (days)
  - Payor (AdMedika)
  - Status (Ready/Submitted/Approved)
  - Total Charge (Rp)

**Proses Klaim - Fill Data & Map Benefit (Screenshot 009-010)**
- Section A: Pasien & Admission Info (read-only)
  - Nama Pasien
  - Nomor AdMedika Peserta
  - Admission Date - Discharge Date
  - Ruang/Kamar yang digunakan

- Section B: Services & Mapping
  - Table dengan columns:
    - Service Code
    - Service Name
    - Service Category
    - Date of Service
    - Qty
    - Unit Price (RS)
    - Total Charge
    - Benefit Category (dropdown with auto-suggest)
    - Coverage %
    - Benefit Amount
    - Co-payment
    - Notes

**Proses Klaim Overview (Screenshot 011)**
- Summary of klaim process:
  - Services yang sudah di-map
  - Progress indicator
  - Status validation (semua fields filled?)
  - Ready for discharge button

**Proses Discharge (Screenshot 012)**
- Confirmation dialog:
  - "Anda akan memfinalisasi klaim untuk pasien [Name]"
  - Total Charge: Rp [amount]
  - Benefit Coverage: Rp [amount]
  - Co-payment: Rp [amount]
  - Excess/Tagihan Pasien: Rp [amount]
  - [Confirm Discharge] [Cancel]

**Kalkulasi Total (Screenshot 013)**
- Detailed calculation breakdown:
  - Table format:
    - Total RS Charge: Rp [A]
    - Benefit Coverage Rate: X%
    - Benefit Amount: Rp [B] = [A] × X%
    - Co-payment (Fixed): Rp [C]
    - Total Klaim to AdMedika: Rp [B]
    - Pasien Tagihan: Rp [A] - [B] = Rp [D]
  - Visual: Bar chart showing breakdown

**Status Klaim - Sudah Diklaim (Screenshot 014)**
- Status indicator: ✓ CLAIMED
- Klaim details:
  - Klaim Reference Number: CLM-2026-XXXXX
  - Submission Date
  - Status History with timestamps
  - Action button: "Lihat Klaim" → view tracking

**Upload Dokumen Klaim (Screenshot 015)**
- Document Upload Section dengan checklist:
  - [ ] Medical Record / Ringkasan Klinis (PDF)
  - [ ] Invoice / Rincian Biaya (PDF)
  - [ ] Receipt / Bukti Pembayaran (PDF)
  - [ ] Lab Results / Hasil Lab (PDF)
  - [ ] Imaging / Hasil Imaging (PDF)
  - [ ] Medication Receipt / Bukti Obat (if applicable)
  - [ ] Other Supporting Documents (PDF/Image)

- Upload controls:
  - Drag & drop area atau Browse button
  - File validation: Max 10MB per file, PDF/JPG/PNG
  - Upload progress indicator
  - Delete option per document
  - Submit button

#### Screenshots Referenced

| Step | Screenshot | Deskripsi |
|------|-----------|-----------|
| 1 | 009-proses-klaim-fill-data-map-benefit.png | Dashboard klaim dan form fill data dengan auto-mapping benefit |
| 2 | 010-map-benefit.png | Detail mapping benefit AdMedika dengan coverage percentage per kategori |
| 3 | 011-proses-klaim.png | Overview proses klaim dengan summary layanan yang sudah di-map |
| 4 | 012-kalau-udah-klik-button-proses-disccharge-pasien.png | Konfirmasi proses discharge dan finalisasi klaim |
| 5 | 013-mengkalkulasi-total.png | Breakdown kalkulasi total RS charge, benefit coverage, co-payment, dan excess |
| 6 | 014-sudah-diklaim-maka-actionnya-jadi-lihat-klaim.png | Status klaim berubah menjadi "Sudah Diklaim" dengan aksi "Lihat Klaim" untuk tracking |
| 7 | 015-story-berikutnya-upload-dokumen.png | Form upload dokumen support klaim dengan checklist kelengkapan dokumen |

#### System Integration

**API Calls:**
- `GET /his/admission/{admission_id}/services` - Get all services during admission
- `GET /api/v1/admedika/benefit/{peserta_id}` - Get benefit coverage rules
- `POST /api/v1/admedika/claim/mapping-suggest` - Get auto-mapping suggestion
- `POST /api/v1/admedika/claim/calculate` - Calculate coverage & billing
- `POST /api/v1/admedika/claim/submit` - Submit klaim ke AdMedika
- `GET /api/v1/admedika/claim/{claim_ref_number}/status` - Track klaim status

**Database Operations:**
- Insert/Update `admedika_claim` dengan detail klaim
- Insert into `admedika_benefit_usage` untuk setiap service yang di-claim
- Insert/Update `admedika_claim_document` untuk uploaded files
- Create audit trail di `admedika_audit_log`

#### Non-Functional Requirements

- **Performance**: Klaim calculation harus selesai dalam < 2 detik, auto-mapping suggest dalam < 3 detik
- **Security**: Audit trail lengkap untuk setiap perubahan mapping, encrypted file storage
- **Data Validation**: No duplicate services, valid date ranges, service quantity > 0
- **Error Handling**: Graceful handling jika benefit data stale, retry mechanism untuk API failures
- **Reporting**: Generate klaim report dengan breakdowns per payor, per date range

#### Known Issues & Limitations

- Auto-mapping based on historical data, may need manual review untuk non-standard services
- File upload max 10MB per file untuk performa
- Klaim hanya bisa submitted setelah pasien di-discharge (final status)
- Co-payment amount fixed, tidak ada negotiation di billing module

#### Dependencies

- Service master data dalam HIS
- Benefit mapping rules dari AdMedika
- Document storage system dengan sufficient quota
- API gateway stable connection dengan AdMedika

#### Sign-off

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Kasir/Billing Manager | | | |
| Finance Manager | | | |
| Medical Director | | | |

---

### Story #3: Daily Monitoring Penggunaan Benefit

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Case Mix Manager |
| **Jobs to be Done** | Monitor penggunaan benefit pasien rawat inap harian, identify risk cases, dan generate alerts untuk intervention |
| **Referensi UI** | Screenshots 016-019 |

#### Deskripsi

Case Mix Manager melakukan monitoring harian terhadap penggunaan benefit pasien rawat inap AdMedika untuk mengidentifikasi case dengan risk tinggi (benefit usage > 85%) dan memastikan compliance dengan coverage limits. Manager dapat input data monitoring, track real-time usage, dan generate weekly reports untuk management.

#### User Acceptance Criteria

1. Dashboard monitoring menampilkan list semua pasien rawat inap active dengan payor AdMedika
2. Setiap pasien menampilkan: nama, kamar, admission date, benefit utilization percentage, dan risk indicator (warna)
3. Risk calculation berdasarkan: (Benefit Used / Benefit Available) × 100%
4. Alert otomatis trigger ketika usage mencapai > 85% dengan notification ke Case Mix Manager
5. User dapat klik patient record untuk detail breakdown benefit usage per kategori
6. User dapat input additional service/charges selama monitoring periode untuk update real-time calculation
7. Input form tersedia untuk Kategori Layanan, Amount, Tanggal Service, dan Deskripsi
8. Setiap input di-record dalam audit trail dan immediately reflected dalam calculation
9. Monitoring data automatic saved dengan timestamp dan user yang input
10. Weekly report dapat di-generate dengan summary risk cases, intervention actions, dan forecast

#### User Flow

```
[Start: Monitoring Dashboard]
  → [Display All Active Patients dengan AdMedika]
  → [Show Risk Indicator per Patient]

{Risk Detection}
  → {Usage > 85%?}
    → [Yes] → [Trigger Alert] → [Notify Case Mix Manager]
    → [No] → [Continue Monitoring]

[Detail Patient View]
  → [Click Patient]
  → [Show Benefit Breakdown]
    - Total Available per Category
    - Used Amount per Category
    - Remaining Amount per Category
    - Usage % per Category

[Add Monitoring Data]
  → [Click Add Data Button]
  → [Open Input Form]
  → [Select Category/Layanan]
  → [Input Amount & Date]
  → [Input Description/Notes]
  → [Submit]
  → [Record in Audit Trail]
  → [Recalculate Usage %]
  → [Update Dashboard]

[Confirmation]
  → [Show Data Saved Message]
  → [Display Updated Calculation]

[Weekly Reporting]
  → [Generate Report]
  → [Show Risk Cases Summary]
  → [Show Interventions Done]
  → [Show Forecast]
  → [Export/Send Report]
  → [End: Success]
```

#### Forms & Data Fields

**Daily Monitoring Dashboard (Screenshot 016)**
- Header info:
  - Date range filter
  - Payor filter (AdMedika selected)
  - Status filter: Active admissions only
  - Refresh button

- Patient List Table dengan columns:
  - [ ] Checkbox (for multi-select)
  - No. (sequential)
  - Patient Name
  - Medical Record Number
  - Kamar/Room
  - Admission Date
  - Days Admitted
  - Benefit Category (expandable)
  - Benefit Available (Rp)
  - Benefit Used (Rp)
  - Benefit Remaining (Rp)
  - Usage % (Visual: Progress bar dengan color coding)
    - 0-50%: Green
    - 51-84%: Yellow (Caution)
    - 85-100%: Orange (Alert)
    - >100%: Red (Excess)
  - Risk Icon: ⚠️ if >85%
  - Action: View Detail / Add Data

**Daily Monitoring - Add Data (Screenshot 017)**
- Quick Add button dengan modal/dialog untuk input:
  - Select Patient (dropdown atau pre-selected)
  - Category/Layanan (dropdown):
    - Kamar (Room)
    - Obat (Medication)
    - Tindakan (Procedure)
    - Pemeriksaan (Lab/Imaging)
    - Other
  - Amount (numeric, Rp)
  - Date of Service (date picker, default today)
  - Notes/Description (textarea, optional)
  - [Submit] [Cancel]

**Daily Monitoring - Form Input Data (Screenshot 018)**
- Expanded form dengan additional fields:
  - Patient Info (read-only):
    - Name
    - Room
    - Admission Date
    - Physician
  - Service Details:
    - Service Code (dropdown)
    - Service Description (auto-fill dari code)
    - Service Category (auto-fill dari code)
    - Service Date (date picker)
    - Qty (numeric)
    - Unit Price (Rp, read-only dari service master)
    - Total Amount (Rp, auto-calculated)
  - Benefit Mapping:
    - Map to Benefit Category (auto-suggest based on service code)
    - Coverage % (read-only dari benefit rules)
    - Estimated Benefit Amount (Rp, auto-calculated)
    - Co-payment (Rp, auto-calculated)
  - Notes (textarea)
  - [Save] [Cancel]

**Daily Monitoring - Data Terkirim (Screenshot 019)**
- Confirmation screen:
  - ✓ Data Berhasil Disimpan
  - Summary info yang baru di-input:
    - Service: [name]
    - Category: [category]
    - Amount: Rp [amount]
    - Date: [date]
  - Updated Patient Status:
    - Previous Benefit Used: Rp X
    - New Benefit Used: Rp X + [new]
    - Updated Usage %: Y%
    - Status: [Green/Yellow/Orange/Red]
  - [Back to Dashboard] [Add More Data] [View Patient Detail]

#### Screenshots Referenced

| Step | Screenshot | Deskripsi |
|------|-----------|-----------|
| 1 | 016-story-berikutnya-daily-monitoring.png | Dashboard daily monitoring dengan list pasien, benefit utilization %, dan risk indicator |
| 2 | 017-daily-monitoring-add-data.png | Quick add interface untuk input data monitoring tambahan |
| 3 | 018-daily-monitoring-isi-data-form.png | Form detail untuk input monitoring dengan auto-calculation benefit coverage |
| 4 | 019-daily-monitoring-terkirim.png | Confirmation screen dengan summary data yang baru di-input dan updated status |

#### System Integration

**API Calls:**
- `GET /his/admissions/active?payor=ADMEDIKA` - Get active admissions
- `GET /his/admission/{id}/benefit-usage` - Get current benefit usage
- `GET /his/admission/{id}/services` - Get all services to date
- `POST /his/monitoring/add-usage` - Record new usage/service
- `GET /api/v1/admedika/benefit/{peserta_id}` - Get current benefit limits
- `POST /his/monitoring/alert?patient_id=X&usage=%=Y` - Trigger alert

**Database Operations:**
- Insert into `admedika_benefit_usage` untuk monitoring entry
- Update `admedika_daily_monitoring` dengan timestamp & user
- Create entry di `admedika_audit_log` untuk tracking
- Generate report dari `admedika_daily_monitoring` table

#### Non-Functional Requirements

- **Performance**: Dashboard load dengan list 100+ patients dalam < 5 detik, add data dalam < 2 detik
- **Real-time**: Usage % updated immediately setelah data input, alert sent within 1 minute
- **Data Accuracy**: Benefit calculation consistent dengan benefit master data
- **Reporting**: Weekly report generation background job (scheduled midnight Sunday)
- **Retention**: Daily monitoring data retained untuk 2 years untuk audit trail

#### Known Issues & Limitations

- Alert notification bergantung pada email/SMS system availability
- Real-time calculation based on cached benefit data (refreshed every 24 hours)
- Cannot modify past monitoring entries (write-once principle untuk audit compliance)
- Weekly report generation may take 5-10 minutes untuk large dataset (>1000 patients)

#### Dependencies

- Active admission data maintained current
- Service master data updated dengan latest pricing
- Benefit rules dari AdMedika di-cache dan refreshed daily
- Email/SMS notification system untuk alert delivery
- Background job scheduler untuk report generation

#### Sign-off

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Case Mix Manager | | | |
| Medical Director | | | |
| IT Manager | | | |

---

## Image Mapping

| Story | Screenshot Range | Count | Description |
|-------|------------------|-------|-------------|
| Story #1 | 001-008 | 8 | Pendaftaran: Form, Cek Benefit, Pilih AdMedika, Tampilan Benefit, Error Handling, Upload Dokumen, Dashboard, Form Terisi |
| Story #2 | 009-015 | 7 | Klaim: Fill Data/Map Benefit, Map Benefit Detail, Proses, Discharge, Kalkulasi, Status, Upload Dokumen |
| Story #3 | 016-019 | 4 | Daily Monitoring: Dashboard, Add Data, Form Input, Confirmation |

**Total Screenshots: 19 PNG files (001-019)**

---

## Key Requirements

### Functional Requirements by Story

#### Story #1: Pendaftaran Pasien Rawat Inap dengan Payor AdMedika
**Screenshots: 001-008 (8 total)**

**Requirement 1.1: Form Pendaftaran Rawat Inap (001)**
- System harus menampilkan form pendaftaran standar dengan field: Nama, NIK, DOB, Gender, Address, Phone
- Form field harus pre-populated jika data pasien sudah terdaftar di sistem
- Form harus support pasien baru atau transfer/re-admission
- Validation: Required fields, valid format untuk NIK dan Phone
- UI harus responsive dan accessible

**Requirement 1.2: Form Cek Benefit & Payor Selection (002-003)**
- Setelah input data dasar, form Cek Benefit harus ditampilkan otomatis
- Dropdown payor harus menampilkan semua active payor dengan AdMedika sebagai salah satu option
- Filter payor berdasarkan status kepesertaan ACTIVE di AdMedika
- User selection harus trigger API verification ke AdMedika
- Numor Peserta AdMedika harus required field jika AdMedika dipilih
- System harus support search/autocomplete untuk kemudahan pemilihan

**Requirement 1.3: Real-time Benefit Verification (004)**
- Saat AdMedika dipilih, system melakukan POST ke `/api/v1/admedika/peserta/verify` dengan no_peserta & DOB
- Verification harus selesai dalam < 3 detik (SLA)
- Response harus include: status (active/inactive/not_found), nama_peserta, paket detail
- Benefit details harus ditampilkan dalam 3 kategori:
  - **Kamar**: Hak class, coverage %, co-payment amount
  - **Obat**: Covered drug list dengan reference pricing, coverage %, copay
  - **Tindakan**: Covered procedures dengan co-payment schedule
- Data harus clear & easy to understand dengan visual indicators

**Requirement 1.4: Error Handling & Retry Mechanism (005)**
- Jika verification gagal (timeout, invalid peserta, inactive status), system harus:
  - Display clear error message dengan reason
  - Provide [Retry] button untuk verifikasi ulang
  - Provide [Select Other Payor] untuk switch payor
  - Option untuk continue dengan payor lain tanpa AdMedika
- Error logs harus dicatat untuk audit & troubleshooting

**Requirement 1.5: Document Upload (006)**
- Optional document upload untuk supporting documents
- Supported formats: PDF, JPG, PNG
- File size limit: 10MB per file
- Checklist harus include: KTP/ID, Kartu Peserta, Medical Record
- Upload progress indicator harus visible
- File validation harus happen on client side & server side

**Requirement 1.6: Confirmation & Dashboard Navigation (007-008)**
- Setelah semua data valid, system harus menampilkan confirmation screen
- Summary data yang telah terisi harus ditampilkan untuk review
- [Confirm] button harus trigger final save & create admission record
- System harus automatic navigate ke Dashboard AdMedika
- Confirmation page harus show: Registration Status: SUCCESS, Admission ID, Expected Discharge, Next Actions

---

#### Story #2: Proses Klaim Rawat Inap
**Screenshots: 009-015 (7 total)**

**Requirement 2.1: Klaim Dashboard & Patient Selection (009)**
- System harus display list pasien rawat inap yang sudah discharge dan ready untuk klaim
- Filter harus include: Status (Ready/Submitted/Approved), Date Range, Search by name/ID
- Untuk setiap pasien, display: Name, Admission Date, Discharge Date, Duration, Payor, Total Charge, Status
- Dashboard harus support multi-select untuk batch processing
- Sorting harus support: Latest, Oldest, High Amount, Low Amount
- Performance: Load dashboard dengan 100+ patients dalam < 5 detik

**Requirement 2.2: Proses Klaim - Service Listing & Auto-Mapping (009-010)**
- Saat user membuka detail klaim, system harus load ALL services yang diberikan selama admission
- Setiap service harus include: Service Code, Name, Category, Date, Qty, Unit Price, Total Amount
- System harus automatic suggest benefit category mapping untuk setiap service
- Auto-mapping harus based on: Service code → Benefit category rules di benefit master
- User harus bisa override mapping dengan audit trail recording
- Change log harus include: Service, Original Mapping, New Mapping, Changed By, Timestamp

**Requirement 2.3: Benefit Mapping Detail & Coverage Calculation (010)**
- Map Benefit Detail harus menampilkan:
  - Service List (dengan mapping status)
  - Benefit Categories (Kamar, Obat, Tindakan, dll)
  - Coverage % per kategori
  - Co-payment Amount per service
  - Estimated Benefit Amount per service
- System harus calculate real-time based on benefit profile
- Visual representation harus clear dengan color coding untuk status

**Requirement 2.4: Proses Discharge & Finalization (011-012)**
- Confirmation dialog sebelum finalize harus display:
  - Patient name, admission dates
  - Total RS Charge: [amount]
  - Total Benefit Coverage: [amount]
  - Total Co-payment: [amount]
  - Patient Tagihan (Excess): [amount]
  - Final Approval checkbox & [Confirm] button
- User harus bisa cancel operasi
- System harus update admission status dari ACTIVE → DISCHARGED → BILLED

**Requirement 2.5: Calculation & Breakdown Display (013)**
- Calculation engine harus perform:
  - Sum all services: Total RS Charge = Rp [A]
  - Apply benefit rate: Benefit Amount = [A] × Coverage% = Rp [B]
  - Calculate co-payment: Based on benefit rules = Rp [C]
  - Calculate patient billing: Patient Tagihan = [A] - [B] = Rp [D]
- Calculation harus display dalam detail breakdown format
- Visual representation (bar chart) harus show proportion
- All calculations harus be reversible & auditable

**Requirement 2.6: Klaim Status & Action Updates (014)**
- Status harus change dari "Ready" → "Diklaim" after finalization
- System harus generate Klaim Reference Number: CLM-YYYY-XXXXX format
- Action button harus change dari [Proses Klaim] → [Lihat Klaim]
- [Lihat Klaim] harus link ke claim tracking page dengan status history
- Status history harus show: Submitted, Under Review, Approved/Rejected, Paid with timestamps

**Requirement 2.7: Document Upload & Checklist Compliance (015)**
- Upload form harus display checklist:
  - [ ] Medical Record / Ringkasan Klinis
  - [ ] Invoice / Rincian Biaya
  - [ ] Receipt / Bukti Pembayaran
  - [ ] Lab Results (if applicable)
  - [ ] Imaging Results (if applicable)
  - [ ] Medication Receipt (if applicable)
  - [ ] Other Supporting Documents
- Drag-and-drop upload interface
- File validation: Max 10MB per file, PDF/JPG/PNG only
- Delete & re-upload capability
- Upload status tracking dengan progress bar
- Submission hanya bisa dilakukan jika semua required documents uploaded

---

#### Story #3: Daily Monitoring Penggunaan Benefit
**Screenshots: 016-019 (4 total)**

**Requirement 3.1: Monitoring Dashboard & Patient List (016)**
- Dashboard harus display ALL active admission patients dengan payor AdMedika
- Patient list harus include columns:
  - Patient Name, MR Number, Room, Admission Date, Days Admitted
  - Benefit Available (Rp) - Total benefit limit untuk admission
  - Benefit Used (Rp) - Actual benefit yang sudah digunakan
  - Benefit Remaining (Rp) - Remaining benefit limit
  - Usage % - Visual progress bar dengan color coding:
    - 0-50%: Green (Normal)
    - 51-84%: Yellow (Caution)
    - 85-100%: Orange (Alert)
    - >100%: Red (Excess)
  - Risk Icon: ⚠️ if >85%, 🚨 if >100%
- Filter harus include: Date range, Payor, Status, Risk Level
- Search functionality untuk patient name/MR number
- Performance: Load 100+ patients dalam < 5 detik
- Auto-refresh setiap 5 menit untuk real-time data

**Requirement 3.2: Risk Detection & Alert Triggering**
- System harus automatic calculate usage % setiap kali ada service entry
- Alert harus trigger otomatis ketika Usage % > 85%
- Alert notification harus include: Patient Name, Current Usage %, Recommended Action
- Notification delivery: Email + SMS + In-app notification
- Alert timestamp harus recorded dalam audit log
- Case Mix Manager harus dapat acknowledge alert dengan notes

**Requirement 3.3: Add Monitoring Data - Quick Entry (017)**
- Quick Add button harus open modal/dialog dengan fields:
  - Select Patient (dropdown dengan search)
  - Category/Layanan (dropdown: Kamar, Obat, Tindakan, Pemeriksaan, Other)
  - Amount (numeric input, Rp)
  - Date of Service (date picker, default today)
  - Notes (textarea, optional)
  - [Submit] [Cancel]
- Submission harus trigger real-time calculation & dashboard update
- Entry harus immediately visible dalam patient's benefit usage

**Requirement 3.4: Detailed Monitoring Data Entry (018)**
- Expanded form untuk detailed entry:
  - Patient Info section (read-only): Name, Room, Admission Date, Physician
  - Service Details section:
    - Service Code (dropdown dari service master)
    - Service Description (auto-fill dari code)
    - Service Category (auto-fill)
    - Service Date (date picker)
    - Quantity (numeric)
    - Unit Price (read-only dari master)
    - Total Amount (auto-calculated)
  - Benefit Mapping section:
    - Map to Benefit Category (auto-suggest)
    - Coverage % (read-only dari benefit rules)
    - Estimated Benefit Amount (auto-calculated)
    - Co-payment (auto-calculated)
  - Notes section (textarea)
- All calculations harus automatic & real-time
- [Save] button harus trigger entry recording

**Requirement 3.5: Data Confirmation & Dashboard Update (019)**
- Confirmation screen harus display:
  - ✓ Data Berhasil Disimpan with timestamp
  - Summary data yang baru di-input
  - Updated Patient Status dengan new Usage %
  - Previous vs New Benefit Used comparison
  - Color indicator untuk updated status
- Options: [Back to Dashboard] [Add More Data] [View Patient Detail]
- Dashboard harus auto-refresh dengan new data

**Requirement 3.6: Weekly Reporting & Forecasting**
- System harus auto-generate weekly report (Sundays midnight)
- Report harus include:
  - Summary risk cases (Usage > 85%)
  - Intervention actions documented
  - Forecast untuk next week berdasarkan current trajectory
  - Recommendations untuk cost containment
- Report delivery: Email to Case Mix Manager & relevant directors
- Report harus accessible di dashboard untuk historical review

---

## Non-Functional Requirements

- **Performance**: API calls < 3 detik, Dashboard load < 5 detik
- **Security**: SSL/TLS encryption, audit trail lengkap, role-based access control
- **Availability**: System uptime 99.5%, automated backup harian
- **Data Integrity**: Consistent benefit calculation across all modules

---

## Business Rules

1. **Payor Selection Rule**
   - Payor AdMedika hanya dapat dipilih jika status kepesertaan valid (verified ke AdMedika)
   - Satu pasien satu admission hanya boleh satu payor
   - Perubahan payor hanya pre-discharge

2. **Benefit Coverage Rules**
   - Hak kamar sesuai paket kepesertaan
   - Obat covered sesuai formularium AdMedika
   - Tindakan medis ada co-payment sesuai schedule

3. **Benefit Calculation Rules**
   - Benefit dihitung berdasarkan tarif RS dan coverage percentage
   - Co-payment dari selisih tarif RS dengan benefit coverage
   - Excess menjadi tagihan pasien jika exceed limit

4. **Claim Processing Rules**
   - Klaim hanya bisa di-submit setelah pasien di-discharge (final)
   - Klaim harus dilengkapi dokumen support sesuai checklist
   - Audit trail lengkap untuk setiap klaim action

5. **Daily Monitoring Rules**
   - Data monitoring updated real-time untuk active admission
   - Alert trigger otomatis jika usage > 85%
   - Weekly report ke management

---

## Technical Integration

### API Integration dengan AdMedika

#### 1. Peserta Verification API
```
Endpoint: POST /api/v1/admedika/peserta/verify
Request: { "no_peserta": "string", "tgl_lahir": "YYYY-MM-DD" }
Response: { "status": "active|inactive|not_found", "nama_peserta": "string", "paket": "string" }
```

#### 2. Benefit Detail API
```
Endpoint: GET /api/v1/admedika/benefit/{peserta_id}
Response: { "kamar": {...}, "obat": {...}, "tindakan": {...} }
```

#### 3. Claim Submission API
```
Endpoint: POST /api/v1/admedika/claim/submit
Response: { "claim_ref_number": "CLM-2026-001234", "status": "submitted" }
```

#### 4. Claim Status API
```
Endpoint: GET /api/v1/admedika/claim/{claim_ref_number}/status
Response: { "status": "submitted|on_review|approved|rejected|paid", "approved_amount": 7500000 }
```

---

## Database Schema Extensions

#### 1. admedika_payor_mapping
```
- id (PK), payor_code, peserta_number, rs_patient_id (FK), admission_id (FK), status, verified_date
```

#### 2. admedika_benefit_mapping
```
- id (PK), benefit_category, rs_service_group, coverage_percentage, copay_amount, effective_date
```

#### 3. admedika_claim
```
- id (PK), claim_ref_number, admission_id (FK), claim_amount, approved_amount, status, submitted_date
```

#### 4. admedika_benefit_usage
```
- id (PK), admission_id (FK), benefit_category, service_date, rs_amount, benefit_amount, copay_amount
```

---

## Success Metrics

1. **Registration Success Rate**: ≥95% registrasi dengan payor AdMedika berhasil verified
2. **Benefit Verification Accuracy**: ≥99% akurasi benefit data dari AdMedika
3. **Claim Processing Time**: Average 2-3 hari dari discharge sampai klaim submitted
4. **Claim Approval Rate**: ≥90% klaim approved on first submission
5. **Monitoring Alerting**: 100% case dengan usage >85% ter-alert

---

## Disclaimer

Dokumen ini dibuat dalam konteks Projek Hospital Information System (HIS) V2 Primaya Hospital Group. Semua informasi disediakan "sebagaimana adanya" tanpa jaminan. Pengguna menggunakan informasi ini atas risiko dan tanggung jawab tunggalnya.

---

## Sign-Off

**Document Prepared By:**
[Name, Position, Date]

**Reviewed By:**
[Manager Name, Title, Date]

**Approved By:**
[Director Name, Title, Date]

---

## Version History

| Versi | Tanggal | Deskripsi | Revised By |
|-------|---------|-----------|-----------|
| 2.0 | 12-01-2026 | **REWORK** - Expanded User Stories with detailed requirements, updated screenshot sequence, comprehensive functional requirements per story, all 3 stories complete with acceptance criteria, forms, flows, integrations | Claude AI |
| 1.0 | 09-01-2026 | Initial Draft - Admedika Rawat Inap PRD (19 Screenshots) | Claude AI |

---

**END OF DOCUMENT**
