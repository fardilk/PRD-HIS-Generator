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
| Document Editor | [Editor Name] |
| Target Level | Private |
| Document Status | Draft |
| Version | 1.0 |
| Created Date | 09 Jan 2026 |

---

## Executive Summary

Dokumen Persyaratan Produk (PRD) ini memberikan gambaran rinci tentang implementasi **Bridging AdMedika untuk layanan Rawat Inap** dalam sistem HIS V2 Primaya Hospital Group. Dokumen ini mendefinisikan fitur, fungsi, user personas, dan spesifikasi teknis untuk integrasi payor AdMedika dalam proses rawat inap pasien.

### Latar Belakang

Primaya Hospital Group memerlukan integrasi dengan sistem AdMedika untuk memfasilitasi pasien menggunakan payor AdMedika dalam mendapatkan layanan Rawat Inap. Saat ini, integrasi AdMedika sudah tersedia untuk layanan Rawat Jalan. Dengan PRD ini, implementasi akan dilanjutkan ke layanan Rawat Inap dengan 3 touchpoint utama:

1. **Pendaftaran Rawat Inap** - Payor AdMedika dapat dipilih saat registrasi pasien masuk rawat inap
2. **Transfer Rawat Inap** - Proses perpindahan layanan dengan benefit checking
3. **Migrasi Pasien** - Konversi data pasien dari sistem lama ke HIS V2 dengan verifikasi benefit

### Tujuan Sistem

Implementasi Bridging AdMedika Rawat Inap bertujuan untuk:
- Memfasilitasi penggunaan payor AdMedika oleh pasien rawat inap
- Mengotomatisasi proses pengecekan benefit rawat inap (hak kamar, obat, tindakan, dll)
- Memetakan benefit AdMedika dengan tarif dan layanan Rumah Sakit
- Mengelola proses klaim yang efisien dengan dokumentasi lengkap
- Monitoring harian penggunaan benefit pasien rawat inap

---

## Timeline

| No. | Pekerjaan | Modul | Estimasi |
|-----|-----------|-------|----------|
| 1 | Document Preparation | Admedika Rawat Inap | 1 hari |
| 2 | Development | Admedika Rawat Inap | TBD |
| 3 | Quality Control | Admedika Rawat Inap | TBD |
| 4 | User Acceptance Testing | Admedika Rawat Inap | TBD |

---

## Table of Contents

1. [Intro](#intro)
2. [Scope Overview](#scope-overview)
3. [User Personas](#user-personas)
4. [User Stories](#user-stories)
5. [Image Mapping](#image-mapping)
6. [Key Requirements](#key-requirements)
7. [Technical Integration](#technical-integration)
8. [Business Rules & Workflows](#business-rules--workflows)

---

## Intro

Selamat datang di Dokumen Persyaratan Produk (PRD) komprehensif untuk **Bridging AdMedika Rawat Inap** dalam sistem Hospital Information System (HIS) V2 milik Primaya Hospital Group.

Dokumen ini menjelaskan secara detail tentang fitur-fitur yang akan diimplementasikan untuk memungkinkan pasien rawat inap menggunakan payor AdMedika, melakukan pengecekan benefit, dan mengelola klaim secara terintegrasi dalam sistem.

### Scope Implementasi

Implementasi Bridging AdMedika Rawat Inap mencakup **5 user stories utama** yang akan dibahas:

1. **Story #1: Pasien Mendaftar Rawat Inap dengan Payor AdMedika**
   - Pendaftaran pasien rawat inap dengan pemilihan payor AdMedika
   - Verifikasi status kepesertaan AdMedika

2. **Story #2: Proses Pengecekan Benefit Rawat Inap**
   - Cek benefit hak kamar, obat, tindakan, dan layanan lain
   - Mapping benefit dengan tarif rumah sakit

3. **Story #3: Pemetaan & Konfigurasi Benefit**
   - Mapping benefit AdMedika dengan database internal RS
   - Penentuan coverage dan co-payment

4. **Story #4: Proses Klaim Rawat Inap**
   - Upload dokumen klaim
   - Tracking status dan pembayaran klaim

5. **Story #5: Daily Monitoring Penggunaan Benefit**
   - Monitoring penggunaan benefit per hari
   - Alert jika melebihi hak benefit

### User Personas

Dokumen ini mengakomodasi 3 user personas utama:

1. **Admisi/Registrasi** - Staff yang mengelola pendaftaran dan verifikasi pasien rawat inap
2. **Kasir/Billing** - Staff yang mengelola tagihan, benefit checking, dan proses klaim
3. **Case Mix/Medical Record** - Staff yang melakukan verifikasi medis dan monitoring

---

## Scope Overview

### Fitur Utama

1. **Integrasi Pendaftaran Pasien Admedika**
   - Payor AdMedika tersedia di menu pendaftaran rawat inap
   - Validasi otomatis status kepesertaan ke sistem AdMedika
   - Diskon/benefit ditampilkan saat registrasi

2. **Pengecekan Benefit Rawat Inap**
   - Cek benefit real-time untuk payor AdMedika
   - Menampilkan hak kamar, obat, tindakan, dan layanan pendukung
   - Detail coverage dan co-payment untuk setiap layanan

3. **Pemetaan Benefit ke Database Internal**
   - Mapping otomatis benefit AdMedika dengan master data RS
   - Konfigurasi harga dan coverage per jenis layanan
   - Update benefit mapping secara berkala

4. **Proses Klaim Rawat Inap**
   - Pengumpulan dokumen klaim otomatis
   - Submit klaim ke AdMedika
   - Tracking status dan hasil klaim

5. **Daily Monitoring Penggunaan Benefit**
   - Laporan harian penggunaan benefit pasien
   - Identifikasi pasien yang melebihi benefit limit
   - Alert dan notifikasi untuk case manager

### Tidak Termasuk dalam Scope

1. **Penentuan Ekses Billing** - Masih dilakukan manual di kasir oleh administrasi (memerlukan effort human jika ada ekses pembayaran)
2. **Lock Billing** - Perlu diantisipasi oleh kasir bahwa jika sudah diproses klaim, tidak boleh ditambahkan lagi layanan baru (dapat diberikan notifikasi untuk unlock billing jika diperlukan penambahan)

### Integrasi dengan Sistem Lain

| Sistem | Data yang Ditukar | Jenis Integrasi |
|--------|-------------------|-----------------|
| **Sistem AdMedika** | Status kepesertaan, benefit detail, claim submission | API synchronous/asynchronous |
| **EMR (Electronic Medical Record)** | Data pasien, diagnosis, riwayat medis | API sync |
| **Master Data System** | Mapping layanan, tarif, dokter, departemen | Database sync |
| **Appointment/Billing System** | Data tagihan, pembayaran, rekonsialisasi | Database sync |
| **Document Management** | Penyimpanan dokumen klaim digital | File storage |

---

## User Personas

### Persona 1: Admisi/Registrasi

**Profile:**
- Peran: Staff Admisi Rawat Inap
- Tanggung Jawab: Mendaftar pasien baru, memverifikasi payor, mencatat data asuransi
- Skill Level: Menengah - Familiar dengan sistem registrasi dasar
- Frekuensi Penggunaan: Setiap hari (high volume)

**Goals:**
- Registrasi pasien cepat dan akurat dengan verifikasi payor otomatis
- Menampilkan benefit information saat registrasi untuk transparansi pasien
- Mengurangi error dalam input data asuransi
- Mempercepat proses check-in pasien

**Pain Points:**
- Proses verifikasi asuransi manual yang lambat
- Data asuransi inkonsisten antar sistem
- Pasien kurang mendapat informasi benefit saat registrasi
- Banyak revisi data di kemudian hari

**Expectations:**
- Interface registrasi yang user-friendly
- Integrasi payor AdMedika yang real-time
- Notifikasi otomatis untuk benefit information
- History payor untuk pasien repeat

---

### Persona 2: Kasir/Billing

**Profile:**
- Peran: Staff Kasir/Billing Rawat Inap
- Tanggung Jawab: Manajemen tagihan, klaim, pembayaran, benefit verification
- Skill Level: Menengah-Tinggi - Memahami benefit dan billing kompleks
- Frekuensi Penggunaan: Setiap hari (high volume at discharge)

**Goals:**
- Memverifikasi benefit sebelum discharge
- Mengelola klaim submission dengan dokumentasi lengkap
- Tracking pembayaran klaim dari AdMedika
- Identifikasi biaya yang belum ter-cover (ekses)

**Pain Points:**
- Proses klaim manual yang memakan waktu
- Tidak ada visibility benefit yang ter-used vs remaining
- Klaim sering ditolak karena dokumen tidak lengkap
- Rekonsialisasi pembayaran rumit
- Ekses billing tidak jelas kapan dan berapa

**Expectations:**
- Dashboard benefit usage yang real-time
- Automated klaim packaging dan submission
- Clear audit trail untuk setiap transaksi
- Integration dengan sistem pembayaran

---

### Persona 3: Case Mix/Medical Record

**Profile:**
- Peran: Case Mix Manager atau Medical Record Staff
- Tanggung Jawab: Verifikasi medis, monitoring benefit, data accuracy
- Skill Level: Tinggi - Memahami medical coding, ICD-10, benefit rules
- Frekuensi Penggunaan: Daily monitoring, ad-hoc untuk special cases

**Goals:**
- Monitor penggunaan benefit per pasien setiap hari
- Identifikasi audit risk dan potential denials
- Ensure medical documentation completeness
- Optimize benefit usage sesuai medical necessity

**Pain Points:**
- Tidak ada daily monitoring tool untuk benefit usage
- Laporan benefit manual yang tidak real-time
- Sulit track mana pasien yang sudah exceed benefit
- Medical documentation sering tidak lengkap saat klaim
- Tidak ada alert system untuk potential issues

**Expectations:**
- Daily monitoring dashboard dengan alert
- Detailed benefit usage breakdown per service
- Integration dengan EMR untuk medical validation
- Customizable report untuk management

---

## User Stories

### Story #1: Pasien Mendaftar Rawat Inap dengan Payor AdMedika

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Admisi/Registrasi |
| **Jobs to be Done** | Mendaftarkan pasien rawat inap dengan payor AdMedika dan menampilkan benefit information |
| **Priority** | P0 - Critical |
| **Complexity** | Medium |

#### Description

Admisi melakukan registrasi pasien rawat inap baru. Pada proses registrasi, staff admisi memilih payor **AdMedika** dari dropdown list. Sistem melakukan verifikasi otomatis ke AdMedika untuk:
- Memvalidasi status kepesertaan pasien
- Mengambil data benefit sesuai paket kepesertaan
- Menampilkan informasi benefit kepada staff admisi dan pasien

#### Acceptance Criteria

1. **Dropdown Payor AdMedika Tersedia**
   - Menu registrasi menampilkan dropdown dengan opsi payor termasuk AdMedika
   - Payor AdMedika dapat dipilih dari list yang tersedia

2. **Validasi Kepesertaan Real-time**
   - Saat payor AdMedika dipilih, sistem otomatis call API AdMedika
   - Verifikasi nomor peserta dan status aktif/tidak aktif
   - Menampilkan konfirmasi status dengan timestamp verifikasi

3. **Tampilkan Benefit Information**
   - Sistem menampilkan detail benefit:
     - Hak kamar (kelas 1, 2, 3 atau sesuai paket)
     - Coverage obat (100%, 80%, sesuai formularium)
     - Coverage tindakan (percentage coverage)
     - Co-payment amount (jika ada)
   - Informasi ditampilkan dalam format yang mudah dibaca untuk pasien

4. **Save Payor Selection**
   - Data payor dan benefit info disimpan dengan registrasi pasien
   - Dapat direferensikan di proses selanjutnya (billing, klaim)

5. **Error Handling**
   - Jika API AdMedika timeout, tampilkan offline mode dengan manual input
   - Jika status tidak aktif, tampilkan warning dan ask for confirmation
   - Jika nomor peserta tidak valid, tampilkan error dan request nomor yang benar

#### User Flow

```
Start
  → Staff Admisi Buka Form Registrasi Rawat Inap
    → Input Data Pasien (Nama, No RM, dll)
      → Pilih Payor: Dropdown → Select "AdMedika"
        → Sistem: Call API AdMedika Validate Peserta
          → Waiting... (API Response)
            → If Valid & Active
              → Display: Benefit Information
              → Staff Admisi Review Benefit
              → Pasien Informed Consent
                → Save Registrasi
                → Show Confirmation
                  → End (Success)
            → If Invalid or Not Active
              → Display: Warning/Error Message
              → Ask For Alternative Action
              → Ask For Manual Override (with confirmation)
                → Proceed atau Re-input
                  → Refer to above flow
```

### Story #2: Cek Benefit Rawat Inap

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Kasir/Billing |
| **Jobs to be Done** | Melakukan pengecekan detail benefit rawat inap pasien AdMedika |
| **Priority** | P0 - Critical |
| **Complexity** | Medium |

#### Description

Kasir membuka menu "Cek Benefit" untuk melihat detail benefit rawat inap pasien yang menggunakan payor AdMedika. Sistem menampilkan:
- Breakdown benefit per kategori (kamar, obat, tindakan, dll)
- Hak maksimal vs penggunaan saat ini (remaining benefit)
- Co-payment dan coverage percentage
- Detail tarif RS vs benefit coverage

#### Acceptance Criteria

1. **Menu Cek Benefit Accessible**
   - Menu "Cek Benefit Rawat Inap" tersedia di dashboard kasir/billing
   - Dapat diakses dari patient profile atau registrasi

2. **Display Benefit Breakdown**
   - Tampilkan benefit dalam format tabel/card:
     - Kategori (Kamar, Obat-obatan, Tindakan Medis, Konsultasi, Lab, Radiologi, dll)
     - Hak Maksimal (dalam rupiah atau hari untuk kamar)
     - Telah Digunakan (cost dari layanan yang sudah diberikan)
     - Sisa Benefit (remaining)
     - Persentase Penggunaan (used%)
     - Co-payment per kategori

3. **Mapping Benefit vs Tarif RS**
   - Tampilkan kolom tambahan:
     - Tarif Rumah Sakit (standard price)
     - Benefit Coverage (berapa % yang ditanggung AdMedika)
     - Pasien Bayar (co-payment amount atau selisih)

4. **Real-time Update**
   - Data benefit selalu updated dengan current admission
   - Reflect penggunaan terbaru saat kasir buka halaman
   - Timestamp terakhir update ditampilkan

5. **Detail View**
   - Kasir dapat drill-down per kategori untuk melihat detail layanan
   - Misal: Click "Tindakan Medis" → lihat daftar tindakan yang sudah diberikan dengan cost breakdown

#### User Flow

```
Start
  → Kasir Buka Dashboard Billing
    → Click "Cek Benefit Rawat Inap"
      → System: Load Patient AdMedika Data
        → Display: Benefit Summary Tabel
          - Kategori Layanan | Hak Maksimal | Digunakan | Sisa | Persentase
          - Kamar            | 3,000,000   | 1,500,000 | 1,5M | 50%
          - Obat-obatan      | 2,000,000   | 800,000   | 1.2M | 40%
          - Tindakan         | 5,000,000   | 2,000,000 | 3M   | 40%
          - ...
        → Kasir: Review Benefit Usage
          → Click Detail Tindakan
            → Display: Daftar Tindakan (dengan date, description, cost, benefit cover)
          → Back to Summary
            → Click Print/Download Report (opsional)
            → End (Ready for Discharge/Klaim)
```

### Story #3: Pemetaan Benefit AdMedika ke Sistem

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Case Mix / Billing Supervisor |
| **Jobs to be Done** | Melakukan mapping antara benefit AdMedika dengan master data internal RS |
| **Priority** | P1 - Important |
| **Complexity** | High |

#### Description

Sistem administrator atau case mix manager melakukan setup/maintenance pemetaan (mapping) antara benefit rule AdMedika dengan database internal Rumah Sakit. Ini termasuk:
- Mapping kategori benefit AdMedika → kategori layanan RS (tarif group, departemen)
- Menentukan coverage percentage per kategori
- Menetapkan co-payment amount
- Update mapping saat ada perubahan benefit rule dari AdMedika

#### Acceptance Criteria

1. **Configuration Menu Available**
   - Menu "Manage AdMedika Benefit Mapping" tersedia di admin section
   - Role-based access (Case Mix Manager, Billing Supervisor)

2. **Mapping Data Structure**
   - Sistem menyimpan mapping dalam tabel dengan field:
     - AdMedika Benefit Category
     - RS Service Category / Tariff Group
     - Coverage Percentage (%)
     - Co-payment (rupiah atau %)
     - Max Limit per Category (jika ada)
     - Effective Date & End Date (untuk benefit yang berlaku berkala)

3. **Create/Edit/Delete Mapping**
   - Tambah mapping baru dengan form validation
   - Edit mapping yang sudah ada
   - Delete mapping (dengan audit trail)
   - Bulk import mapping dari CSV/Excel (opsional)

4. **Validation Rules**
   - Coverage % tidak boleh melebihi 100%
   - Co-payment validation (consistent antara rupiah vs %)
   - Check untuk duplicate mapping
   - Mandatory fields validation

5. **History & Audit Trail**
   - System mencatat siapa, kapan, apa yang diubah pada mapping
   - Dapat restore previous mapping jika diperlukan

6. **Testing & Validation**
   - Admin dapat test mapping dengan patient case sample
   - Preview bagaimana benefit akan di-calculate untuk pasien tertentu
   - Dry-run sebelum live deployment

#### User Flow

```
Start
  → Admin Buka Menu "Manage Benefit Mapping"
    → Display: Current Mapping List (Table)
      [AdMedika Category | RS Category | Coverage | Co-pay | Effective Date]

    → Option 1: View/Edit Existing
      → Click Row → Edit Form
        → Change Coverage/Co-pay
        → Save Changes
        → System: Log Audit Trail
        → End

    → Option 2: Create New
      → Click "Add New Mapping"
      → Form: Select AdMedika Category (dropdown from API)
             Select RS Service Category (dropdown from local DB)
             Enter Coverage %
             Enter Co-payment
             Set Effective Date Range
      → Click Save
      → System: Validate & Save
      → End

    → Option 3: Bulk Import
      → Click "Import from File"
      → Upload CSV
      → System: Validate Data
      → Preview Changes
      → Confirm & Apply
      → End

    → Option 4: Test Mapping
      → Click "Test Mapping"
      → Select Patient (sample case)
      → System: Calculate Benefit berdasarkan current mapping
      → Display: Preview Benefit Calculation
      → Validate dengan expected result
      → End
```

---

### Story #4: Proses Klaim Rawat Inap

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Kasir/Billing |
| **Jobs to be Done** | Mengelola proses klaim rawat inap ke AdMedika dengan submission dokumen |
| **Priority** | P0 - Critical |
| **Complexity** | High |

#### Description

Kasir mengelola proses klaim rawat inap dari admission hingga submission ke AdMedika. Proses mencakup:
- Finalisasi tagihan dan benefit calculation
- Mengumpulkan dokumen klaim (medical record, receipt, invoice, dll)
- Upload dokumen ke sistem
- Submit klaim ke AdMedika
- Tracking status dan pembayaran

#### Acceptance Criteria

1. **Klaim Initiation at Discharge**
   - Saat pasien akan di-discharge, kasir dapat start proses klaim
   - System akan compile semua service yang diberikan during admission
   - Benefit calculation otomatis berdasarkan mapping

2. **Document Collection**
   - Sistem menampilkan checklist dokumen yang diperlukan:
     - Medical Record Summary
     - Discharge Summary
     - Invoice / Tagihan Rumah Sakit
     - Receipt Pembayaran
     - Lab Report (jika ada)
     - Imaging Report (jika ada)
     - Doctor's Signature
     - Resep Obat
   - Kasir dapat upload dokumen per item
   - System validate file type dan size

3. **Klaim Summary Review**
   - Pre-submission review dengan breakdown:
     - Total Tagihan RS
     - Total Benefit Coverage
     - Co-payment Pasien
     - Amount Claimed to AdMedika
   - Kasir dapat verify sebelum submit

4. **Submit to AdMedika**
   - Click "Submit Klaim" button
   - System: Package dokumen dan data dalam format yang sesuai API AdMedika
   - System: Call API to submit klaim
   - Menampilkan confirmation dengan claim reference number

5. **Claim Tracking**
   - Dashboard untuk track status klaim
   - Status options: Submitted, On Review, Approved, Rejected, Paid
   - Show timeline dari submission hingga payment
   - Notifikasi otomatis untuk update status

6. **Rejection Handling**
   - Jika klaim ditolak, tampilkan detail reason dari AdMedika
   - Kasir dapat resubmit dengan revisi dokumen
   - Audit trail untuk setiap resubmission

#### User Flow

```
Start
  → Kasir: Pasien akan di-discharge
    → Click "Finalize & Claim"
    → System: Display Claim Preparation Form

      Step 1: Review Admission & Services
        - Display: Pasien Info, Service List, Total Cost
        - Kasir: Review & Confirm

      Step 2: Benefit Calculation
        - System: Auto-calculate benefit per service
        - Display: Breakdown (Service | Tarif | Coverage % | Amount)
        - Show: Total Claim to AdMedika

      Step 3: Collect Documents
        - Display: Document Checklist
        - Kasir: Upload per dokumen (Medical Record, Invoice, dll)
        - System: Validate file type/size

      Step 4: Review Claim Summary
        - Display: Final Klaim Summary
          * Total Tagihan: Rp 10,000,000
          * Benefit AdMedika: Rp 7,500,000
          * Pasien Bayar (co-pay): Rp 2,500,000
        - Kasir: Review & Approve

      Step 5: Submit Klaim
        - Click "Submit to AdMedika"
        - System: Submit via API
        - Display: Success Message + Claim Reference Number
        - Kasir: Print receipt

      → End

  Later:
  → Kasir: Check Claim Status
    → Menu: "Track Klaim"
    → Display: List Klaim dengan status
    → Click Klaim → Detail Status & Timeline
    → Jika Rejected → Click "Resubmit" → Revise & Resubmit
    → Jika Approved → Show Payment Details (amount, date, reference)
```

---

### Story #5: Daily Monitoring Penggunaan Benefit

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Case Mix Manager / Supervisor |
| **Jobs to be Done** | Monitor penggunaan benefit pasien rawat inap harian |
| **Priority** | P1 - Important |
| **Complexity** | Medium |

#### Description

Case Mix Manager melakukan monitoring harian terhadap penggunaan benefit pasien rawat inap. Sistem menyediakan dashboard yang menampilkan:
- Daftar pasien rawat inap dengan payor AdMedika
- Breakdown penggunaan benefit per pasien
- Alert untuk pasien yang mendekati limit benefit
- Summary report untuk management

#### Acceptance Criteria

1. **Daily Monitoring Dashboard**
   - Tampilkan list semua pasien rawat inap dengan payor AdMedika
   - Per pasien, tampilkan:
     - Patient Name, No. RM, Room
     - Admission Date, Length of Stay (LOS)
     - Total Benefit Limit
     - Used So Far (amount & percentage)
     - Remaining Benefit
     - Risk Status (Green/Yellow/Red based on usage)

2. **Risk Indicators**
   - Green: Usage < 70%
   - Yellow: Usage 70-90%
   - Red: Usage > 90% (at risk of exceed)
   - Display dengan color coding untuk visual quick scan

3. **Detail View per Pasien**
   - Click patient row → drill down detail
   - Show breakdown per kategori (kamar, obat, tindakan, dll)
   - Timeline benefit usage (day-by-day breakdown)
   - Medical validation status

4. **Alert System**
   - Auto-alert untuk pasien dengan usage > 85%
   - Notify case mix team (email/in-app notification)
   - Suggestion untuk early discharge atau benefit optimization

5. **Report & Export**
   - Generate summary report (daily/weekly/monthly)
   - Export ke Excel untuk further analysis
   - Prediksi LOS based on benefit usage trend

6. **Data Accuracy Validation**
   - Periodic reconciliation dengan AdMedika data
   - Flag discrepancies untuk investigation
   - Sync mechanism untuk updated benefit data

#### User Flow

```
Start
  → Case Mix Manager: Open Daily Monitoring Dashboard
    → Display: Benefit Usage Summary
      - Total Patients: 45 (AdMedika payor)
      - At Risk (>85%): 3 patients (Red flag)
      - Watch List (70-85%): 8 patients (Yellow)
      - Healthy (<70%): 34 patients (Green)

    → Table: Patient Benefit Status List
      [Name | Room | LOS | Total Limit | Used | % | Status]
      [Anto | A301 | 5 d | 10,000,000 | 8,5M | 85% | Yellow Alert]
      [Budi | A302 | 2 d | 10,000,000 | 3M   | 30% | Green]
      [Citra| B101 | 8 d | 7,500,000  | 7,2M | 96% | Red Alert!]
      ...

    → Manager: Click on Citra (Red Alert)
      → Drill-down Detail View:
        - Patient: Citra XXX (Room B101, LOS 8 days)
        - Admission Diagnosis: Complex case
        - Benefit Breakdown:
          * Kamar (Rp 3M limit): Rp 2.8M used (93%)
          * Obat (Rp 2.5M): Rp 2.4M (96%)
          * Tindakan (Rp 3M): Rp 2.8M (93%)
        - Timeline: Day-by-day cost
        - Recommendation: Consider discharge or benefit appeal

      → Manager: Take Action
        - Option 1: Add Note for Doctor (discharge planning)
        - Option 2: Request benefit adjustment from AdMedika
        - Option 3: Mark for Follow-up
        - Save & Continue

    → Manager: Generate Report
      → Click "Generate Daily Report"
      → System: Compile summary
        - Date, Total Patients, At Risk Count, Avg Usage %
      → Option to export to Excel
      → Print/Save Report

    → End
```

---

## Image Mapping

### Screenshots Documentation

| Story | Screenshot Range | Description | Personas |
|-------|------------------|-------------|----------|
| Story #1 | 001-002 | Navigasi ke Pendaftaran Rawat Inap & Form Registrasi dengan Payor AdMedika | Admisi |
| Story #2 | 002-007 | Proses Cek Benefit: Klaim Proses, Map Benefit, Kalkulasi Total, Status Klaim | Kasir/Billing |
| Story #3 | 003-005 | Detail Mapping Benefit AdMedika ke Sistem RS | Case Mix/Admin |
| Story #4 | 008 | Upload Dokumen Klaim | Kasir |
| Story #5 | 009-012 | Daily Monitoring Penggunaan Benefit Pasien | Case Mix Manager |

### Total Screenshots: 12 PNG files
- **001**: Menuju Dashboard Pasien AdMedika
- **002**: Proses Klaim - Dashboard
- **003**: Proses Klaim - Map Benefit
- **004**: Map Benefit - Detail
- **005**: Kalkulasi Total Benefit
- **006**: Total Terkalkulasi
- **007**: Status Klaim Setelah Diklaim
- **008**: Upload Dokumen Klaim
- **009**: Daily Monitoring - Dashboard
- **010**: Daily Monitoring - Add Data
- **011**: Daily Monitoring - Form Isian
- **012**: Daily Monitoring - Data Terkirim

---

## Key Requirements

### Functional Requirements (Grouped by Story)

#### Story #1: Pasien Mendaftar Rawat Inap dengan Payor AdMedika
**Screenshots: 001-002 (2 total)**

1. **Dropdown Payor AdMedika** (Screenshot 001)
   - Form registrasi menampilkan dropdown payor dengan opsi AdMedika
   - Payor AdMedika dapat dipilih dari list

2. **Validasi Peserta & Tampilkan Benefit** (Screenshot 002)
   - Validasi otomatis ke sistem AdMedika saat payor dipilih
   - Tampilkan benefit info (hak kamar, obat, tindakan) ke kasir dan pasien
   - Simpan payor selection dan benefit data dengan patient record

---

#### Story #2: Cek Benefit Rawat Inap
**Screenshots: 002-007 (6 total)**

1. **Menu Cek Benefit Accessible** (Screenshot 002)
   - Menu "Cek Benefit Rawat Inap" tersedia di dashboard kasir/billing

2. **Display Benefit Breakdown** (Screenshot 003)
   - Tampilkan benefit dalam format tabel: Kategori, Hak Maksimal, Telah Digunakan, Sisa, %

3. **Mapping Benefit vs Tarif RS** (Screenshot 004)
   - Tampilkan kolom Tarif RS, Benefit Coverage %, Pasien Bayar

4. **Real-time Update Benefit Data** (Screenshot 005)
   - Data benefit selalu updated dengan current admission
   - Timestamp terakhir update ditampilkan

5. **Detail View per Kategori** (Screenshot 006)
   - Kasir dapat drill-down per kategori untuk melihat detail layanan
   - Breakdown tindakan dengan cost per item

6. **Print/Download Report** (Screenshot 007)
   - Kasir dapat print atau download benefit summary untuk discharge/klaim

---

#### Story #3: Pemetaan Benefit AdMedika ke Sistem
**Screenshots: 003-005 (3 total)**

1. **Configuration Menu Available** (Screenshot 003)
   - Menu "Manage AdMedika Benefit Mapping" tersedia di admin section
   - Role-based access control (Case Mix Manager, Billing Supervisor)

2. **Create/Edit Mapping** (Screenshot 004)
   - Tambah mapping baru dengan form: AdMedika Benefit Category, RS Service Category, Coverage %, Co-payment
   - Edit mapping yang sudah ada, Delete mapping dengan audit trail

3. **Test & Validation Mapping** (Screenshot 005)
   - Admin dapat test mapping dengan patient case sample
   - Preview benefit calculation sebelum go-live
   - Dry-run validation sebelum deployment

---

#### Story #4: Proses Klaim Rawat Inap
**Screenshots: 008 (1 total)**

1. **Document Collection & Upload** (Screenshot 008)
   - Sistem menampilkan checklist dokumen (Medical Record, Invoice, Receipt, Lab Report, dll)
   - Kasir dapat upload dokumen per item dengan file validation

---

#### Story #5: Daily Monitoring Penggunaan Benefit
**Screenshots: 009-012 (4 total)**

1. **Daily Monitoring Dashboard** (Screenshot 009)
   - List semua pasien rawat inap dengan payor AdMedika
   - Per pasien: Patient Name, Room, Total Limit, Used, Remaining, Risk Status

2. **Risk Indicators Color Coding** (Screenshot 010)
   - Green: Usage < 70%, Yellow: 70-90%, Red: >90%
   - Visual quick scan dengan color coding

3. **Alert System & Detail View** (Screenshot 011)
   - Auto-alert untuk pasien dengan usage > 85%
   - Drill-down detail per pasien: breakdown per kategori, timeline day-by-day

4. **Report Generation & Export** (Screenshot 012)
   - Generate summary report (daily/weekly/monthly)
   - Export ke Excel untuk further analysis
   - Prediksi LOS based on benefit usage trend

### Non-Functional Requirements

- **Performance**: API calls < 3 detik, Dashboard load < 5 detik
- **Security**: SSL/TLS encryption, audit trail lengkap, role-based access control
- **Availability**: System uptime 99.5%, automated backup harian
- **Data Integrity**: Consistent benefit calculation across all modules
- **Integration**: API standards (REST/SOAP), error logging dan monitoring

### Business Rules

1. **Payor Selection Rule**
   - Payor AdMedika hanya dapat dipilih jika status kepesertaan valid (verified ke AdMedika)
   - Satu pasien satu admission hanya boleh menggunakan satu payor
   - Perubahan payor hanya bisa dilakukan pre-discharge (tidak bisa mid-admission)

2. **Benefit Coverage Rules**
   - Hak kamar sesuai paket kepesertaan (Kelas 1, 2, 3, General)
   - Obat covered sesuai formularium AdMedika (tidak semua obat 100% covered)
   - Tindakan medis ada co-payment sesuai schedule
   - Setiap kategori benefit punya limit maksimal per admission

3. **Benefit Calculation Rules**
   - Benefit dihitung berdasarkan tarif RS dan coverage percentage
   - Co-payment dihitung dari selisih tarif RS dengan benefit coverage
   - Jika pasien exceed benefit limit, excess menjadi tagihan pasien
   - Benefit recalculation dilakukan saat ada amendment (service change, discharge date)

4. **Claim Processing Rules**
   - Klaim hanya bisa di-submit setelah pasien di-discharge (final)
   - Klaim harus dilengkapi dokumen support sesuai checklist
   - Resubmission hanya boleh jika reject dengan valid reason
   - Audit trail lengkap untuk setiap klaim action

5. **Daily Monitoring Rules**
   - Monitoring data updated real-time untuk active admission
   - Alert trigger otomatis jika usage > 85%
   - Recommendation untuk early discharge jika benefit akan exceed
   - Weekly report ke management untuk oversight

---

## Technical Integration

### API Integration dengan AdMedika

#### 1. Peserta Verification API
```
Endpoint: POST /api/v1/admedika/peserta/verify
Request:
{
  "no_peserta": "string",
  "tgl_lahir": "YYYY-MM-DD"
}

Response:
{
  "status": "active|inactive|not_found",
  "nama_peserta": "string",
  "paket": "string",
  "effective_date": "YYYY-MM-DD",
  "end_date": "YYYY-MM-DD"
}
```

#### 2. Benefit Detail API
```
Endpoint: GET /api/v1/admedika/benefit/{peserta_id}
Response:
{
  "kamar": {
    "limit_amount": 3000000,
    "coverage_pct": 100,
    "max_nights": 30
  },
  "obat": {
    "limit_amount": 2000000,
    "coverage_pct": 80,
    "formularium": "URL"
  },
  "tindakan": {
    "limit_amount": 5000000,
    "coverage_pct": 75,
    "schedule": "URL"
  },
  ...
}
```

#### 3. Claim Submission API
```
Endpoint: POST /api/v1/admedika/claim/submit
Request:
{
  "no_peserta": "string",
  "claim_date": "YYYY-MM-DD",
  "admission_date": "YYYY-MM-DD",
  "discharge_date": "YYYY-MM-DD",
  "total_amount": 10000000,
  "claim_amount": 7500000,
  "documents": [
    {
      "type": "medical_record|invoice|receipt",
      "file_url": "string"
    }
  ]
}

Response:
{
  "claim_ref_number": "CLM-2026-001234",
  "status": "submitted",
  "submitted_date": "YYYY-MM-DD HH:mm:ss"
}
```

#### 4. Claim Status API
```
Endpoint: GET /api/v1/admedika/claim/{claim_ref_number}/status
Response:
{
  "claim_ref": "CLM-2026-001234",
  "status": "submitted|on_review|approved|rejected|paid",
  "last_update": "YYYY-MM-DD HH:mm:ss",
  "approved_amount": 7500000,
  "rejection_reason": "string (if rejected)",
  "payment_date": "YYYY-MM-DD",
  "payment_amount": 7500000
}
```

### Database Schema Extensions

#### 1. admedika_payor_mapping
```sql
- id (PK)
- payor_code: 'ADMEDIKA'
- peserta_number: string
- rs_patient_id (FK)
- admission_id (FK)
- status: active|inactive
- verified_date: datetime
- created_date: datetime
- created_by: user_id
```

#### 2. admedika_benefit_mapping
```sql
- id (PK)
- benefit_category: 'kamar|obat|tindakan|lab|radiologi'
- rs_service_group: string
- coverage_percentage: decimal
- copay_amount: decimal
- copay_percentage: decimal
- effective_date: date
- end_date: date
- created_by: user_id
- updated_by: user_id
```

#### 3. admedika_claim
```sql
- id (PK)
- claim_ref_number: string (unique)
- admission_id (FK)
- claim_amount: decimal
- approved_amount: decimal
- status: submitted|on_review|approved|rejected|paid
- submitted_date: datetime
- submitted_by: user_id
- rejection_reason: text
- created_date: datetime
- updated_date: datetime
```

#### 4. admedika_benefit_usage
```sql
- id (PK)
- admission_id (FK)
- benefit_category: string
- service_date: date
- service_description: string
- rs_amount: decimal
- benefit_coverage_pct: decimal
- benefit_amount: decimal
- copay_amount: decimal
- created_date: datetime
```

---

## Business Rules & Workflows

### Workflow 1: Registrasi dengan Payor AdMedika

```
START: Staff Admisi buka form registrasi RJ
  ↓
INPUT: Data pasien (nama, no RM, tgl lahir, alamat)
  ↓
SELECT: Payor dropdown → Pilih "AdMedika"
  ↓
SYSTEM: Trigger API Verify Peserta ke AdMedika
  ├─ IF Response = Valid & Active
  │  ├─ Display: Green Status "Peserta Valid"
  │  ├─ Fetch: Benefit Detail (Kamar, Obat, Tindakan, dll)
  │  ├─ Display: Benefit Info Card untuk transparansi pasien
  │  └─ Save: payor selection + benefit snapshot
  │
  ├─ IF Response = Not Active
  │  ├─ Display: Yellow Warning "Peserta Tidak Aktif"
  │  ├─ Ask: Apakah ingin lanjut dengan payor lain?
  │  └─ Options: Pilih payor lain OR Manual Override (dengan approval)
  │
  ├─ IF Response = Not Found
  │  ├─ Display: Red Error "Peserta Tidak Ditemukan"
  │  ├─ Ask: Apakah nomor peserta benar?
  │  └─ Option: Re-input nomor peserta
  │
  └─ IF API Timeout (Offline Mode)
     ├─ Display: Warning "Sistem AdMedika tidak responsif"
     ├─ Offer: Manual entry benefit info
     └─ Note: Akan di-verify ulang nanti
  ↓
CONFIRM: Registrasi selesai, pasien masuk ke rawat inap
  ↓
END
```

### Workflow 2: Cek Benefit & Klaim

```
START: Kasir buka menu Benefit & Claim Management
  ↓
SELECT: Pilih pasien dari list RJ AdMedika
  ↓
DISPLAY: Benefit Usage Summary
  ├─ Total Benefit Limit (per kategori)
  ├─ Services Used So Far (breakdown by category)
  ├─ Remaining Benefit (amount & percentage)
  └─ Co-payment Summary
  ↓
ACTION: Kasir mempersiapkan klaim
  ├─ Review service list & calculate benefit
  ├─ Collect required documents
  ├─ Fill klaim form dengan auto-calculation
  └─ Verify total claim amount
  ↓
SYSTEM: Generate Klaim Package
  ├─ Compile semua data & dokumen
  ├─ Create claim reference number
  └─ Prepare submission format sesuai API AdMedika
  ↓
SUBMIT: Click "Kirim Klaim ke AdMedika"
  ├─ System: Call API submitClaim
  ├─ IF Success
  │  ├─ Display: "Klaim berhasil dikirim"
  │  ├─ Show: Claim Reference Number
  │  ├─ Print: Receipt/confirmation
  │  └─ Save: claim status = "submitted"
  │
  └─ IF Failed
     ├─ Display: Error message
     ├─ Log: untuk investigation
     └─ Option: Retry atau contact support
  ↓
TRACKING: Kasir dapat track status klaim
  ├─ Status Update: Polling API setiap jam
  ├─ Status Options:
  │  ├─ Submitted
  │  ├─ On Review (by AdMedika)
  │  ├─ Approved → Show approved amount
  │  ├─ Rejected → Show reason, Option to resubmit
  │  └─ Paid → Show payment details
  │
  └─ Notification: Alert ketika ada status change
  ↓
END
```

### Workflow 3: Daily Monitoring Benefit Usage

```
START: Case Mix Manager buka Daily Monitoring Dashboard (pagi hari)
  ↓
SYSTEM: Compile Benefit Usage Data
  ├─ Query: Semua patient RJ AdMedika yang still active
  ├─ Calculate: Benefit usage untuk masing-masing
  ├─ Categorize: Green (<70%) | Yellow (70-85%) | Red (>85%)
  └─ Generate: Summary stats
  ↓
DISPLAY: Monitoring Dashboard
  ├─ Summary Card:
  │  ├─ Total Active Patients: 45
  │  ├─ At Risk (Red): 3 patients
  │  ├─ Watch List (Yellow): 8 patients
  │  └─ Healthy (Green): 34 patients
  │
  └─ Detailed Table:
     ├─ Patient info (Name, Room, LOS)
     ├─ Benefit Status (Used%, Color code)
     ├─ Trending (usage trajectory)
     └─ Last Updated timestamp
  ↓
ACTION: Manager Monitor & Follow-up
  ├─ Scan dashboard untuk alert (Red status)
  ├─ Click RED patient → Drill-down detail
  │  ├─ View: Benefit breakdown by category
  │  ├─ View: Day-by-day service cost trend
  │  ├─ Review: Medical necessity vs benefit rules
  │  └─ Take action:
  │     ├─ Option A: Add note untuk doctor (discharge planning)
  │     ├─ Option B: Request appeal ke AdMedika (jika valid reason)
  │     └─ Option C: Plan alternative treatment (cost optimization)
  │
  └─ Mark case untuk follow-up
  ↓
REPORT: Generate Daily Report (end of day)
  ├─ Compile: Summary stats, At-risk cases, Actions taken
  ├─ Export: To Excel untuk further analysis
  └─ Share: With management untuk oversight
  ↓
END
```

---

## System Diagram

### High-Level Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    HIS V2 Primaya                           │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌──────────────────────────────────────────────────────┐  │
│  │  UI Layer (Frontend)                                 │  │
│  │  - Registration Module                               │  │
│  │  - Billing & Klaim Module                            │  │
│  │  - Daily Monitoring Dashboard                        │  │
│  └──────────────────────────────────────────────────────┘  │
│                          ↓                                   │
│  ┌──────────────────────────────────────────────────────┐  │
│  │  Business Logic Layer (Backend)                      │  │
│  │  - Payor Validation Service                          │  │
│  │  - Benefit Calculation Engine                        │  │
│  │  - Claim Management Service                          │  │
│  │  - Monitoring & Alert Service                        │  │
│  └──────────────────────────────────────────────────────┘  │
│                          ↓                                   │
│  ┌──────────────────────────────────────────────────────┐  │
│  │  Data Layer                                          │  │
│  │  - Patient Data                                      │  │
│  │  - Payor Mapping Data                                │  │
│  │  - Benefit Mapping Config                            │  │
│  │  - Claim Records & History                           │  │
│  └──────────────────────────────────────────────────────┘  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
         ↓                              ↓
    ┌─────────────┐            ┌──────────────────┐
    │   AdMedika  │            │ Other Systems    │
    │   Platform  │            │ (EMR, Master,    │
    │   (External)│            │  Billing, etc)   │
    └─────────────┘            └──────────────────┘
```

---

## Success Metrics

1. **Registration Success Rate**
   - Target: ≥95% registrasi dengan payor AdMedika berhasil verified
   - Metric: (Success / Total Attempts) × 100%

2. **Benefit Verification Accuracy**
   - Target: ≥99% akurasi benefit data dari AdMedika
   - Metric: Manual verification audit results

3. **Claim Processing Time**
   - Target: Average 2-3 hari dari discharge sampai klaim submitted
   - Metric: Time tracking per claim

4. **Claim Approval Rate**
   - Target: ≥90% klaim approved on first submission
   - Metric: (Approved / Total Submitted) × 100%

5. **Monitoring Alerting**
   - Target: 100% case dengan usage >85% ter-alert
   - Metric: Alert coverage & timeliness

---

## Disclaimer

Dokumen ini dibuat dalam konteks Projek Hospital Information System (HIS) V2 Primaya Hospital Group. Semua informasi dalam dokumen ini disediakan "sebagaimana adanya" dan tidak ada jaminan atau garansi yang diberikan bahwa informasi tersebut cocok untuk tujuan tertentu. Pengguna dokumen ini menggunakan informasi tersebut atas risiko dan tanggung jawab tunggalnya.

---

## Sign-Off

**Document Prepared By:**
[Name, Position, Date]

**Reviewed By:**
[Manager Name, Title, Date]

**Approved By:**
[Director Name, Title, Date]

---

**Version History**

| Versi | Tanggal | Deskripsi | Revised By |
|-------|---------|-----------|-----------|
| 1.0 | 09-01-2026 | Initial Draft - Admedika Rawat Inap PRD | Claude AI |

---

**END OF DOCUMENT**
