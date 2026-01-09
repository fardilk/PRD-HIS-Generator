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

Primaya Hospital Group memerlukan integrasi dengan sistem AdMedika untuk memfasilitasi pasien menggunakan payor AdMedika dalam mendapatkan layanan Rawat Inap.

### Tujuan Sistem

- Memfasilitasi penggunaan payor AdMedika oleh pasien rawat inap
- Mengotomatisasi pengecekan benefit dan klaim
- Monitoring penggunaan benefit real-time

---

## Scope Overview

### Fitur Utama

1. **Dashboard Pasien AdMedika** - Entry point untuk proses AdMedika
2. **Proses Klaim Rawat Inap** - Pengecekan benefit, mapping, kalkulasi, dan submission dokumen
3. **Daily Monitoring Penggunaan Benefit** - Monitor benefit usage harian dengan alert

---

## User Personas

### Persona 1: Admisi/Registrasi
- Peran: Staff Admisi Rawat Inap
- Goals: Registrasi pasien dengan payor AdMedika
- Tech Level: Menengah

### Persona 2: Kasir/Billing
- Peran: Staff Kasir/Billing Rawat Inap
- Goals: Verifikasi benefit dan submit klaim
- Tech Level: Menengah-Tinggi

### Persona 3: Case Mix/Medical Record
- Peran: Case Mix Manager
- Goals: Monitor benefit usage harian
- Tech Level: Tinggi

---

## User Stories

### Story #1: Dashboard Pasien AdMedika

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Admisi/Kasir/Case Mix |
| **Jobs to be Done** | Akses dashboard terpusat untuk semua proses AdMedika (Klaim, Monitoring) |
| **Referensi UI** | [Kosongkan dulu] |
| **User Flow** | [Kosongkan dulu] |

---

### Story #2: Proses Klaim Rawat Inap

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Kasir/Billing |
| **Jobs to be Done** | Kelola proses klaim dengan pengecekan benefit, mapping, kalkulasi, dan upload dokumen |
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

| Story | Screenshot Range | Description | Personas |
|-------|------------------|-------------|----------|
| Story #1 | 001 | Menuju Dashboard Pasien AdMedika | All |
| Story #2 | 002-008 | Proses Klaim: Dashboard, Map Benefit, Detail, Kalkulasi, Total, Status, Upload Dokumen | Kasir/Billing |
| Story #3 | 009-012 | Daily Monitoring: Dashboard, Add Data, Form Isian, Data Terkirim | Case Mix Manager |

**Total Screenshots: 12 PNG files (001-012)**

---

## Key Requirements

### Functional Requirements (Grouped by Story)

#### Story #1: Dashboard Pasien AdMedika
**Screenshots: 001 (1 total)**

1. **Dashboard Entry Point** (Screenshot 001)
   - Menampilkan dashboard terpusat akses ke proses AdMedika
   - Quick links ke Proses Klaim dan Daily Monitoring
   - Summary informasi pasien AdMedika yang aktif

---

#### Story #2: Proses Klaim Rawat Inap
**Screenshots: 002-008 (7 total)**

1. **Klaim Dashboard** (Screenshot 002)
   - Menu "Proses Klaim" dengan list pasien yang siap diklaim
   - Status overview setiap pasien

2. **Map Benefit Interface** (Screenshot 003)
   - Menampilkan mapping benefit AdMedika dengan layanan RS
   - Interface untuk review benefit allocation

3. **Benefit Detail View** (Screenshot 004)
   - Detail breakdown benefit per kategori (kamar, obat, tindakan)
   - Coverage percentage dan co-payment info

4. **Kalkulasi Total Benefit** (Screenshot 005)
   - System melakukan kalkulasi otomatis benefit yang akan diklaim
   - Preview benefit amount vs total tagihan

5. **Total Terkalkulasi Display** (Screenshot 006)
   - Menampilkan final total yang akan diklaim
   - Breakdown: Total RS, Benefit Coverage, Pasien Bayar

6. **Status Klaim** (Screenshot 007)
   - Menampilkan status klaim setelah submission
   - Timeline dan update info dari AdMedika

7. **Upload Dokumen Klaim** (Screenshot 008)
   - Form upload untuk dokumen klaim (Medical Record, Invoice, Receipt, Lab Report)
   - Checklist dokumen required dan file validation

---

#### Story #3: Daily Monitoring Penggunaan Benefit
**Screenshots: 009-012 (4 total)**

1. **Monitoring Dashboard** (Screenshot 009)
   - Display list semua pasien rawat inap dengan payor AdMedika
   - Benefit usage summary per pasien (Used %, Risk Status)

2. **Add Data Monitoring** (Screenshot 010)
   - Interface untuk menambah/update data monitoring
   - Input service yang baru diberikan dan benefit usage

3. **Form Isian Monitoring** (Screenshot 011)
   - Form detail untuk input monitoring data
   - Field: Kategori, Amount, Date, Service Description

4. **Data Terkirim Confirmation** (Screenshot 012)
   - Confirmation bahwa monitoring data sudah tersimpan
   - Summary data yang ter-record di sistem

---

## Non-Functional Requirements

- **Performance**: API calls < 3 detik, Dashboard load < 5 detik
- **Security**: SSL/TLS encryption, audit trail lengkap, role-based access control
- **Availability**: System uptime 99.5%, automated backup harian
- **Data Integrity**: Consistent benefit calculation across all modules

---

## Business Rules

1. **Payor Selection Rule**
   - Payor AdMedika hanya dapat dipilih jika status kepesertaan valid
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
   - Klaim hanya bisa di-submit setelah pasien di-discharge
   - Klaim harus dilengkapi dokumen support
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
  "effective_date": "YYYY-MM-DD"
}
```

#### 2. Benefit Detail API
```
Endpoint: GET /api/v1/admedika/benefit/{peserta_id}
Response:
{
  "kamar": {
    "limit_amount": 3000000,
    "coverage_pct": 100
  },
  "obat": {
    "limit_amount": 2000000,
    "coverage_pct": 80
  }
}
```

#### 3. Claim Submission API
```
Endpoint: POST /api/v1/admedika/claim/submit
Request:
{
  "no_peserta": "string",
  "claim_amount": 7500000,
  "documents": [...]
}

Response:
{
  "claim_ref_number": "CLM-2026-001234",
  "status": "submitted"
}
```

#### 4. Claim Status API
```
Endpoint: GET /api/v1/admedika/claim/{claim_ref_number}/status
Response:
{
  "claim_ref": "CLM-2026-001234",
  "status": "submitted|on_review|approved|rejected|paid",
  "approved_amount": 7500000
}
```

---

## Database Schema Extensions

#### 1. admedika_payor_mapping
```
- id (PK)
- payor_code: 'ADMEDIKA'
- peserta_number: string
- rs_patient_id (FK)
- admission_id (FK)
- status: active|inactive
- verified_date: datetime
```

#### 2. admedika_benefit_mapping
```
- id (PK)
- benefit_category: 'kamar|obat|tindakan'
- rs_service_group: string
- coverage_percentage: decimal
- copay_amount: decimal
- effective_date: date
```

#### 3. admedika_claim
```
- id (PK)
- claim_ref_number: string (unique)
- admission_id (FK)
- claim_amount: decimal
- approved_amount: decimal
- status: submitted|on_review|approved|rejected|paid
- submitted_date: datetime
```

#### 4. admedika_benefit_usage
```
- id (PK)
- admission_id (FK)
- benefit_category: string
- service_date: date
- rs_amount: decimal
- benefit_amount: decimal
- copay_amount: decimal
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
| 1.0 | 09-01-2026 | Initial Draft - Admedika Rawat Inap PRD | Claude AI |

---

**END OF DOCUMENT**
