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
| **Jobs to be Done** | Melakukan pendaftaran pasien rawat inap dengan pemilihan payor AdMedika dan menampilkan benefit information |
| **Referensi UI** | [Kosongkan dulu] |
| **User Flow** | [Kosongkan dulu] |

---

### Story #2: Proses Klaim Rawat Inap

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Kasir/Billing |
| **Jobs to be Done** | Mengelola proses klaim rawat inap dengan pengecekan benefit, mapping, kalkulasi, dan submission dokumen |
| **Referensi UI** | [Kosongkan dulu] |
| **User Flow** | [Kosongkan dulu] |

---

### Story #3: Daily Monitoring Penggunaan Benefit

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Case Mix Manager |
| **Jobs to be Done** | Monitor penggunaan benefit pasien rawat inap harian dengan alert dan reporting |
| **Referensi UI** | [Kosongkan dulu] |
| **User Flow** | [Kosongkan dulu] |

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

### Functional Requirements (Grouped by Story)

#### Story #1: Pendaftaran Pasien Rawat Inap dengan Payor AdMedika
**Screenshots: 001-008 (8 total)**

1. **Form Pendaftaran Rawat Inap** (Screenshot 001)
   - Menampilkan form pendaftaran pasien rawat inap standar
   - Siap untuk penambahan field payor

2. **Form Cek Benefit** (Screenshot 002)
   - Menu atau form untuk cek benefit pasien
   - Persiapan sebelum memilih payor AdMedika

3. **Form Cek Benefit - Pilih AdMedika** (Screenshot 003)
   - Dropdown payor menampilkan opsi AdMedika
   - User dapat memilih AdMedika dari list payor

4. **Tampilan Benefit AdMedika** (Screenshot 004)
   - Setelah memilih AdMedika, sistem menampilkan benefit details
   - Breakdown per kategori (kamar, obat, tindakan)

5. **Error Handling - Jika Gagal** (Screenshot 005)
   - Jika verifikasi ke AdMedika gagal, tampilkan error message
   - Opsi untuk retry atau pilih payor lain

6. **Upload Dokumen - Ketika diklik** (Screenshot 006)
   - Form atau modal untuk upload dokumen pendukung
   - File validation dan checklist dokumen

7. **Menuju ke Dashboard Pasien AdMedika** (Screenshot 007)
   - Flow navigasi dari pendaftaran ke dashboard AdMedika
   - Dashboard entry point untuk proses lanjutan

8. **Pendaftaran Pasien dengan AdMedika - Form Terisi** (Screenshot 008)
   - Konfirmasi bahwa data pendaftaran sudah tersimpan dengan payor AdMedika
   - Summary informasi pendaftaran

---

#### Story #2: Proses Klaim Rawat Inap
**Screenshots: 009-015 (7 total)**

1. **Proses Klaim - Fill Data & Map Benefit** (Screenshot 009)
   - Dashboard untuk memulai proses klaim
   - Interface input data dan mapping benefit

2. **Map Benefit Detail** (Screenshot 010)
   - Menampilkan detail mapping benefit AdMedika dengan layanan RS
   - Coverage percentage, co-payment info per kategori

3. **Proses Klaim - Overview** (Screenshot 011)
   - Summary proses klaim yang sedang berjalan
   - Status dan informasi klaim

4. **Klik Button Proses Discharge Pasien** (Screenshot 012)
   - Trigger untuk memulai finalisasi klaim saat discharge
   - Mempersiapkan data untuk submission

5. **Mengkalkulasi Total** (Screenshot 013)
   - System melakukan kalkulasi benefit yang akan diklaim
   - Preview total benefit vs tarif RS vs copay pasien

6. **Status Klaim - Sudah Diklaim** (Screenshot 014)
   - Menampilkan status setelah klaim berhasil di-submit
   - Action berubah menjadi "Lihat Klaim" untuk tracking

7. **Upload Dokumen Klaim** (Screenshot 015)
   - Form upload untuk dokumen support klaim
   - Checklist: Medical Record, Invoice, Receipt, Lab Report, dll

---

#### Story #3: Daily Monitoring Penggunaan Benefit
**Screenshots: 016-019 (4 total)**

1. **Daily Monitoring - Dashboard** (Screenshot 016)
   - Display list pasien rawat inap dengan payor AdMedika
   - Summary benefit usage per pasien dengan risk indicator

2. **Daily Monitoring - Add Data** (Screenshot 017)
   - Interface untuk menambah/update monitoring data
   - Input service baru yang diberikan

3. **Daily Monitoring - Form Input Data** (Screenshot 018)
   - Form detail untuk input monitoring
   - Field: Kategori Layanan, Amount, Tanggal, Deskripsi

4. **Daily Monitoring - Data Terkirim** (Screenshot 019)
   - Confirmation bahwa data monitoring sudah tersimpan
   - Summary data yang ter-record

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
| 1.0 | 09-01-2026 | Initial Draft - Admedika Rawat Inap PRD (19 Screenshots) | Claude AI |

---

**END OF DOCUMENT**
