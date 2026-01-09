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

Primaya Hospital Group memerlukan integrasi dengan sistem AdMedika untuk memfasilitasi pasien menggunakan payor AdMedika dalam mendapatkan layanan Rawat Inap. Implementasi mencakup 5 touchpoint utama:

1. **Pendaftaran Rawat Inap** - Payor AdMedika dapat dipilih saat registrasi
2. **Pengecekan Benefit** - Cek benefit real-time
3. **Pemetaan Benefit** - Mapping benefit dengan database internal
4. **Proses Klaim** - Submission dokumen klaim
5. **Daily Monitoring** - Monitor penggunaan benefit harian

### Tujuan Sistem

- Memfasilitasi penggunaan payor AdMedika oleh pasien rawat inap
- Mengotomatisasi pengecekan benefit dan klaim
- Monitoring penggunaan benefit real-time

---

## Scope Overview

### Fitur Utama

1. **Integrasi Pendaftaran Pasien Admedika** - Payor AdMedika tersedia saat registrasi, validasi otomatis ke sistem AdMedika
2. **Pengecekan Benefit Rawat Inap** - Cek benefit real-time dengan breakdown per kategori
3. **Pemetaan Benefit ke Database Internal** - Mapping benefit AdMedika dengan master data RS
4. **Proses Klaim Rawat Inap** - Pengumpulan dan submission dokumen klaim
5. **Daily Monitoring Penggunaan Benefit** - Laporan harian penggunaan benefit dengan alert

### Tidak Termasuk dalam Scope

- Penentuan ekses billing (manual di kasir)
- Lock billing (hanya notifikasi)

---

## User Personas

### Persona 1: Admisi/Registrasi
- Peran: Staff Admisi Rawat Inap
- Goals: Registrasi pasien cepat dengan verifikasi payor otomatis
- Tech Level: Menengah

### Persona 2: Kasir/Billing
- Peran: Staff Kasir/Billing Rawat Inap
- Goals: Verifikasi benefit dan submit klaim dengan dokumentasi lengkap
- Tech Level: Menengah-Tinggi

### Persona 3: Case Mix/Medical Record
- Peran: Case Mix Manager
- Goals: Monitor benefit usage dan identifikasi audit risk
- Tech Level: Tinggi

---

## User Stories

### Story #1: Pasien Mendaftar Rawat Inap dengan Payor AdMedika

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Admisi/Registrasi |
| **Jobs to be Done** | Mendaftarkan pasien rawat inap dengan payor AdMedika dan menampilkan benefit information |
| **Referensi UI** | [Kosongkan dulu] |
| **User Flow** | [Kosongkan dulu] |

---

### Story #2: Proses Pengecekan Benefit Rawat Inap

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Kasir/Billing |
| **Jobs to be Done** | Melakukan pengecekan detail benefit rawat inap pasien AdMedika |
| **Referensi UI** | [Kosongkan dulu] |
| **User Flow** | [Kosongkan dulu] |

---

### Story #3: Pemetaan & Konfigurasi Benefit

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Case Mix / Billing Supervisor |
| **Jobs to be Done** | Melakukan mapping antara benefit AdMedika dengan master data internal RS |
| **Referensi UI** | [Kosongkan dulu] |
| **User Flow** | [Kosongkan dulu] |

---

### Story #4: Proses Klaim Rawat Inap

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Kasir/Billing |
| **Jobs to be Done** | Mengelola proses klaim rawat inap ke AdMedika dengan submission dokumen |
| **Referensi UI** | [Kosongkan dulu] |
| **User Flow** | [Kosongkan dulu] |

---

### Story #5: Daily Monitoring Penggunaan Benefit

#### Story Overview

| Field | Value |
|-------|-------|
| **User Persona** | Case Mix Manager / Supervisor |
| **Jobs to be Done** | Monitor penggunaan benefit pasien rawat inap harian |
| **Referensi UI** | [Kosongkan dulu] |
| **User Flow** | [Kosongkan dulu] |

---

## Image Mapping

| Story | Screenshot Range | Description | Personas |
|-------|------------------|-------------|----------|
| Story #1 | 001-002 | Registrasi Pasien Rawat Inap dengan Payor AdMedika | Admisi |
| Story #2 | 003-008 | Proses Pengecekan Benefit & Breakdown Detail | Kasir/Billing |
| Story #3 | 009-011 | Pemetaan & Konfigurasi Benefit AdMedika | Case Mix/Admin |
| Story #4 | 012 | Upload Dokumen Klaim | Kasir |
| Story #5 | 013-016 | Daily Monitoring Penggunaan Benefit Pasien | Case Mix Manager |

**Total Screenshots: 16 PNG files (001-016)**

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

#### Story #2: Proses Pengecekan Benefit Rawat Inap
**Screenshots: 003-008 (6 total)**

1. **Menu Cek Benefit Accessible** (Screenshot 003)
   - Menu "Cek Benefit Rawat Inap" tersedia di dashboard kasir/billing

2. **Display Benefit Breakdown** (Screenshot 004)
   - Tampilkan benefit dalam format tabel: Kategori, Hak Maksimal, Telah Digunakan, Sisa, %

3. **Mapping Benefit vs Tarif RS** (Screenshot 005)
   - Tampilkan kolom Tarif RS, Benefit Coverage %, Pasien Bayar

4. **Real-time Update Benefit Data** (Screenshot 006)
   - Data benefit selalu updated dengan current admission
   - Timestamp terakhir update ditampilkan

5. **Detail View per Kategori** (Screenshot 007)
   - Kasir dapat drill-down per kategori untuk melihat detail layanan
   - Breakdown tindakan dengan cost per item

6. **Print/Download Report** (Screenshot 008)
   - Kasir dapat print atau download benefit summary untuk discharge/klaim

---

#### Story #3: Pemetaan & Konfigurasi Benefit
**Screenshots: 009-011 (3 total)**

1. **Configuration Menu Available** (Screenshot 009)
   - Menu "Manage AdMedika Benefit Mapping" tersedia di admin section
   - Role-based access control (Case Mix Manager, Billing Supervisor)

2. **Create/Edit Mapping** (Screenshot 010)
   - Tambah mapping baru dengan form: AdMedika Benefit Category, RS Service Category, Coverage %, Co-payment
   - Edit mapping yang sudah ada, Delete mapping dengan audit trail

3. **Test & Validation Mapping** (Screenshot 011)
   - Admin dapat test mapping dengan patient case sample
   - Preview benefit calculation sebelum go-live

---

#### Story #4: Proses Klaim Rawat Inap
**Screenshots: 012 (1 total)**

1. **Document Collection & Upload** (Screenshot 012)
   - Sistem menampilkan checklist dokumen (Medical Record, Invoice, Receipt, Lab Report, dll)
   - Kasir dapat upload dokumen per item dengan file validation

---

#### Story #5: Daily Monitoring Penggunaan Benefit
**Screenshots: 013-016 (4 total)**

1. **Daily Monitoring Dashboard** (Screenshot 013)
   - List semua pasien rawat inap dengan payor AdMedika
   - Per pasien: Patient Name, Room, Total Limit, Used, Remaining, Risk Status

2. **Risk Indicators Color Coding** (Screenshot 014)
   - Green: Usage < 70%, Yellow: 70-90%, Red: >90%
   - Visual quick scan dengan color coding

3. **Alert System & Detail View** (Screenshot 015)
   - Auto-alert untuk pasien dengan usage > 85%
   - Drill-down detail per pasien: breakdown per kategori

4. **Report Generation & Export** (Screenshot 016)
   - Generate summary report (daily/weekly/monthly)
   - Export ke Excel untuk further analysis

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
    "coverage_pct": 80
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
  "documents": [...]
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
  "rejection_reason": "string (if rejected)"
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
- created_date: datetime
```

#### 2. admedika_benefit_mapping
```
- id (PK)
- benefit_category: 'kamar|obat|tindakan|lab|radiologi'
- rs_service_group: string
- coverage_percentage: decimal
- copay_amount: decimal
- effective_date: date
- end_date: date
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
- rejection_reason: text
```

#### 4. admedika_benefit_usage
```
- id (PK)
- admission_id (FK)
- benefit_category: string
- service_date: date
- service_description: string
- rs_amount: decimal
- benefit_coverage_pct: decimal
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

Dokumen ini dibuat dalam konteks Projek Hospital Information System (HIS) V2 Primaya Hospital Group. Semua informasi dalam dokumen ini disediakan "sebagaimana adanya" tanpa jaminan atau garansi. Pengguna dokumen ini menggunakan informasi tersebut atas risiko dan tanggung jawab tunggalnya.

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
| 1.0 | 09-01-2026 | Initial Draft - Admedika Rawat Inap PRD (Simplified) | Claude AI |

---

**END OF DOCUMENT**
