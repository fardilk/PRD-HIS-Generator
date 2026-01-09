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
[Nama lengkap module/project]
=> Contoh: Rehab Medik - Hospital Information System (HIS) V2

**Klien/Organisasi:**
[Nama klien/rumah sakit/organisasi]
=> Contoh: Primaya Hospital Group

**Tujuan Sistem:**
[Jelaskan tujuan utama module ini dalam 2-3 kalimat]
=> Contoh: Mengimplementasikan modul Rehab Medik dalam sistem HIS V2 untuk memfasilitasi proses konsultasi, dokumentasi, dan pelaksanaan fisioterapi pasien. Sistem ini memungkinkan dokter, fisioterapis, dan pasien untuk berkolaborasi dalam program rehabilitasi medis dengan dokumentasi elektronik yang terintegrasi.

**Background/Latar Belakang:**
[Konteks mengapa system ini dibuat, masalah apa yang dipecahkan]
=> Contoh: Rumah Sakit Primaya memerlukan sistem informasi terpadu untuk mengelola pelayanan rehabilitasi medis. Saat ini, proses konsultasi dokter, perencanaan program terapi, dan dokumentasi pelaksanaan fisioterapi masih tersebar di beberapa sistem atau bahkan manual. Sistem HIS V2 Rehab Medik akan mengintegrasikan seluruh proses tersebut dalam satu platform yang efisien, dengan fitur signature digital untuk persetujuan tindakan medis.

**Timeline:**
[Kapan project ini direncanakan dimulai dan selesai]
=> Contoh: Document Preparation: 1 hari (03-12-2025) | Development: TBD | QC: TBD | UAT: TBD

---

## 2. Scope Overview

**Fitur Utama:**
- [Fitur 1: Deskripsi singkat]
- [Fitur 2: Deskripsi singkat]
- [Fitur N: Deskripsi singkat]

=> Contoh:
- Konsultasi Awal Dokter: Dokter membuat form pemeriksaan rawat jalan dengan form tambahan khusus Rehab Medik (Anjuran, Evaluasi, Suspek Penyakit Akibat Kerja)
- Catatan Terintegrasi Fisioterapis: Fisioterapis membuat catatan SOAP dan mendapatkan signature digital dari Pasien
- Manajemen Kehadiran Program: Sistem tracking untuk kehadiran dan ketidakhadiran pasien dalam program fisioterapi
- Penyelesaian Sesi Terapi: Fisioterapis menutup sesi terapi dengan pencatatan hasil dan progres pasien
- Evaluasi Dokter: Dokter me-review seluruh dokumentasi pelaksanaan fisioterapi dan membuat evaluasi

**Tidak termasuk dalam scope:**
- [Hal yang OUT OF SCOPE 1]
- [Hal yang OUT OF SCOPE 2]

=> Contoh:
- Manajemen tarif/billing untuk layanan fisioterapi
- Integrasi dengan peralatan fisioterapi (TENS, Ultrasound, Laser)
- Report analytics dan business intelligence untuk Rehab Medik
- Mobile app untuk patient engagement

**Integrasi dengan sistem lain:**
- [Sistem A: apa data yang ditukar]
- [Sistem B: apa data yang ditukar]

=> Contoh:
- EMR System: Pull data pasien, diagnosis, riwayat medis
- Master Data: Retrieve data dokter, fisioterapis, program terapi standard
- Appointment System: Integrasi dengan jadwal layanan fisioterapi
- Document Management: Penyimpanan dan retrieval dokumen digital yang ditandatangani

---

## 3. User Personas

### Persona 1: [Nama Role]

**Demografi:**
- Umur: [range]
- Lokasi: [Ruangan/department]
- Pengalaman dengan teknologi: [Beginner/Intermediate/Advanced]

**Karakteristik:**
[Deskripsi singkat tentang tipe user ini]

**Primary Goals:**
- [Goal 1]
- [Goal 2]

**Pain Points:**
- [Pain point 1]
- [Pain point 2]

**Behavior Pattern:**
[Bagaimana user ini biasanya bekerja]

=> Contoh:
### Persona 1: Dokter Spesialis Rehabilitasi Medik

**Demografi:**
- Umur: 40-60 tahun
- Lokasi: Poliklinik/Rawat Inap Rehab Medik
- Pengalaman dengan teknologi: Intermediate

**Karakteristik:**
Dokter berpengalaman yang bertanggung jawab untuk diagnosis, perencanaan program terapi, dan evaluasi hasil pelaksanaan fisioterapi pasien.

**Primary Goals:**
- Membuat form konsultasi awal dan perencanaan program terapi dengan cepat
- Review dan evaluasi hasil pelaksanaan program fisioterapi

**Pain Points:**
- Form terlalu panjang dan rumit, menyita waktu
- Sulit melihat history dan progress pelaksanaan terapi pasien

**Behavior Pattern:**
Dokter menghabiskan 10-15 menit per pasien untuk konsultasi. Membutuhkan interface yang clean dan navigasi mudah untuk input data dan review.

---

### Persona 2: [Nama Role]
[Isi dengan format sama seperti Persona 1 di atas]

=> Contoh:
### Persona 2: Fisioterapis

**Demografi:**
- Umur: 25-45 tahun
- Lokasi: Ruangan/Klinik Fisioterapi
- Pengalaman dengan teknologi: Beginner-Intermediate

**Karakteristik:**
Tenaga medis profesional yang melaksanakan program fisioterapi sesuai perencanaan dokter.

**Primary Goals:**
- Dokumentasi lengkap setiap sesi terapi (SOAP notes)
- Dapatkan signature pasien untuk setiap sesi terapi

**Pain Points:**
- Pencatatan manual yang memakan waktu
- Sulit mendapatkan signature pasien dengan aman dan legal

**Behavior Pattern:**
Fisioterapis menangani 8-12 pasien per hari. Membutuhkan interface yang intuitive dan cepat untuk input data, tanpa perlu training panjang.

---

### Persona 3: [Nama Role]
[Isi dengan format sama seperti Persona 1 di atas]

=> Contoh:
### Persona 3: Pasien

**Demografi:**
- Umur: 18-75 tahun
- Lokasi: Klinik/Rumah Sakit
- Pengalaman dengan teknologi: Beginner

**Karakteristik:**
Pasien yang menjalani program fisioterapi sebagai bagian dari treatment medis mereka.

**Primary Goals:**
- Memahami program terapi yang direncanakan dokter
- Memberikan persetujuan untuk pelaksanaan terapi

**Pain Points:**
- Sulit memahami dokumen medis yang kompleks
- Khawatir dengan legalitas signature digital

**Behavior Pattern:**
Pasien menghabiskan 20-60 menit per sesi terapi. Membutuhkan komunikasi yang jelas tentang apa yang akan dilakukan.

---

## 4. User Stories Overview

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

---

## 5. Image Mapping

**Referensi UI Screenshots:**

| Story | Screenshot Range | Deskripsi | Personas |
|-------|------------------|-----------|----------|
| Story 1: [Judul] | [Range: e.g. 001-005] | [Apa yang ditunjukkan images] | [Persona yang involved] |
| Story 2: [Judul] | [Range: e.g. 006-010] | [Apa yang ditunjukkan images] | [Persona yang involved] |

=> Contoh:
| Story 1 | 001-005.png | Menu EMR Dokter, Button +Pemeriksaan RJ, Form isian RJ dengan Anjuran/Evaluasi/Suspek, Daftar Pemeriksaan | Dokter |
| Story 2 | 006-015.png | Catatan Terintegrasi pasien, Button +SOAP, Form SOAP S-O-A-P, Tanda Tangan Fisioterapis (Wacom/QR), Tanda Tangan Pasien, Generated Document | Fisioterapis, Pasien |
| Story 3 | 016-018.png | Menu Absen Program, Form/List Absen Pasien, Notifikasi ketidakhadiran | Fisioterapis |
| Story 4 | 019-022.png | Form Penutupan Sesi Terapi, Hasil & Progress, Rekomendasi Lanjutan, Summary Sesi | Fisioterapis |
| Story 5 | 023-025.png | Review History Pelaksanaan, Form Evaluasi Dokter, Final Assessment & Rekomendasi | Dokter |

**Total Screenshots:** [Jumlah] PNG files (sequential naming: 001.png - NNN.png)
=> Contoh: 25 PNG files (001.png - 025.png)

---

## 6. Key Requirements

**Functional Requirements:**
1. [Requirement 1: Deskripsi detail]
2. [Requirement 2: Deskripsi detail]
3. [Requirement 3: Deskripsi detail]

=> Contoh:
1. Form Pemeriksaan RJ Khusus Rehab Medik: Sistem harus menampilkan 3 form tambahan (Anjuran, Evaluasi, Suspek Penyakit Akibat Kerja) ketika pasien diklasifikasikan sebagai Rehab Medik
2. Catatan SOAP Terintegrasi: Fisioterapis dapat membuat/edit catatan SOAP dan sistem menyimpan dengan timestamp dan user identity
3. Signature Digital: Sistem mendukung 2 metode signature (Wacom pen pad, QR Code scan) dengan validation dan encryption
4. Tracking Kehadiran: Sistem mencatat kehadiran/ketidakhadiran pasien per sesi dengan notifikasi ke dokter jika tidak hadir
5. Auto-Generate Dokumen: Sistem menggenerate Lembar Formulir Rawat Jalan dan dokumen Layanan Kedokteran Fisik & Rehabilitasi dalam format PDF

**Non-Functional Requirements:**
- Performance: [Spec jika ada]
- Security: [Spec jika ada]
- Usability: [Spec jika ada]

=> Contoh:
- Performance: Load time < 3 detik per page, response time API < 1 detik
- Security: SSL/TLS encryption, password policy standar, audit trail lengkap, compliance dengan regulasi data medis
- Usability: UI/UX user-friendly untuk skill IT beragam, support bahasa Indonesia
- Availability: System uptime 99.5%, backup otomatis harian

**Business Rules:**
1. [Rule 1: Bagaimana sistem harus behave]
2. [Rule 2: Business logic yang harus diterapkan]

=> Contoh:
1. Form Anjuran, Evaluasi, dan Suspek hanya muncul jika pasien diklasifikasikan Rehab Medik
2. Catatan SOAP harus diisi lengkap sebelum dapat di-submit
3. Signature Pasien harus diperoleh sebelum sesi terapi dianggap complete
4. Dokter dapat melakukan review hanya setelah minimal 1 sesi fisioterapi tercatat
5. Ketidakhadiran pasien lebih dari 3 kali akan trigger notifikasi urgent ke dokter

---

## 7. Document Metadata

**Project/Module Name:**
[Nama resmi module]
=> Contoh: Rehab Medik - Hospital Information System (HIS) V2

**Module Code:**
[Kode singkat, e.g., RM]
=> Contoh: RM

**Version:**
[Versi, default 1.0]
=> Contoh: 1.0

**Created Date:**
[Tanggal brief dibuat]
=> Contoh: 03-12-2025

**Created By:**
[Nama orang yang membuat brief]
=> Contoh: Fardil Khalidi

**Document Status:**
[Draft / In Review / Approved]
=> Contoh: Draft

**Target Approval Date:**
[Tanggal diharapkan approve]
=> Contoh: 07-12-2025

**Client Contact:**
- Name: [Nama contact person]
- Email: [Email]
- Phone: [Phone]

=> Contoh:
- Name: Roky Sarasi
- Email: roky.sarasi@primayahospital.com
- Phone: +62-21-XXXX-XXXX

**Development Team Lead:**
- Name: [Nama team lead]
- Email: [Email]

=> Contoh:
- Name: Adrianto
- Email: adrianto@sistemintegrasi.com

---

## 8. Special Notes & Considerations

**Technical Considerations:**
- [Teknologi yang digunakan]
- [Constraints teknis]

=> Contoh:
- Technology Stack: Web-based system, responsive design untuk desktop dan tablet
- Signature Technology: Integration dengan Wacom SDK untuk tablet, QR Code library untuk mobile
- Database: PostgreSQL dengan encryption untuk sensitive data
- Document Generation: Template engine (Jinja2 atau similar) untuk generate PDF

**Design Considerations:**
- [Bahasa UI]
- [Theme/Color scheme]
- [Accessibility requirements]

=> Contoh:
- Bahasa UI: Bahasa Indonesia dengan bantuan Bahasa Inggris
- Theme: Healthcare theme dengan color scheme biru (trust, professional)
- Accessibility: WCAG compliance, support screen reader, keyboard navigation
- Responsive: Work di desktop (1920x1080), tablet (iPad), minimal mobile support

**Regulatory/Compliance:**
- [Regulasi yang harus diikuti]
- [Data privacy considerations]

=> Contoh:
- Regulasi Medis: Compliance dengan peraturan Kementerian Kesehatan Indonesia tentang rekam medis elektronik
- Data Privacy: GDPR-like approach untuk data pasien sensitif, encrypt PII
- Audit: Semua transaction tercatat di audit log untuk compliance
- Signature Legal: Digital signature memiliki legal standing sesuai Undang-Undang ITE Indonesia

**Assumptions:**
- [Asumsi tentang data availability]
- [Asumsi tentang user skills]

=> Contoh:
- Pasien sudah terdaftar di sistem sebelum masuk ke flow Rehab Medik
- Dokter dan Fisioterapis sudah trained dengan sistem HIS dasar
- Infrastructure dan network bandwidth sudah memadai untuk signature digital
- Wacom devices atau QR code readers sudah tersedia di lokasi layanan fisioterapi

**Risks & Mitigation:**
- Risk 1: [Deskripsi] → Mitigation: [Cara handle]
- Risk 2: [Deskripsi] → Mitigation: [Cara handle]

=> Contoh:
- Risk 1: User kesulitan menggunakan signature digital → Mitigation: Comprehensive training, multiple signature methods, clear on-screen instructions
- Risk 2: Signature digital tidak diterima oleh legal → Mitigation: Coordinate dengan legal team sebelum implementation, ensure compliance
- Risk 3: Data loss atau signature corruption → Mitigation: Redundant backup, encryption, regular testing & validation
- Risk 4: Performance issue saat multiple users access signature → Mitigation: Load testing, query optimization, distributed system architecture

---

## 9. Expected Output

**PRD Document Structure:**
- Cover page dengan approval section
- Document properties & metadata
- Executive summary
- [N] User personas (detailed)
- [N] User stories (13 sections each)
- Integration & system requirements
- Glossary & terminology
- Appendix with references
- Sign-off & approval section
- Changelog & version history

=> Contoh: Untuk 5 stories dengan 3 personas = ~3500-5000 lines markdown = ~150-200 pages PDF

**Output Format:**
- Markdown file: `exports/[MODULE_NAME]-PRD.md`
- PDF file: `expectations/PRD-[MODULE_NAME].pdf`

=> Contoh:
- `exports/REHAB_MEDIK-PRD.md`
- `expectations/PRD-REHAB_MEDIK.pdf`

**Quality Standards:**
- All user stories complete dengan 13 sections
- All acceptance criteria well-defined & testable
- All screenshots referenced dengan clear instructions
- All forms & data fields documented
- No placeholder text [INSERT_XXX] remaining
- Language consistency (Bahasa Indonesia)

---

## 10. Generation Instructions

**Step 1 - Setup:**
- [✓] Brief file dibuat (file ini)
- [ ] Screenshots uploaded ke `screenshots/[MODULE_NAME]/`
- [ ] Folder structure created

**Step 2 - Generate Stories (AI Agent):**
```
generate-story untuk [MODULE_NAME]:
- Generate semua stories (1-N)
- Analyze screenshots untuk extract requirements
- Output: stories/[MODULE_NAME]/story-001.md ... story-N.md
- Each story harus lengkap 13 sections
```

**Step 3 - Review Quality (AI Agent):**
```
review untuk [MODULE_NAME]:
- Check all stories generated
- Check no placeholder text
- Generate review report
```

**Step 4 - Compile PRD (AI Agent):**
```
compile PRD untuk [MODULE_NAME]:
- Merge template + brief + all stories
- Output: exports/[MODULE_NAME]-PRD.md
```

**Step 5 - Export to PDF (Manual/Tool):**
```
pandoc atau markdown converter:
- Input: exports/[MODULE_NAME]-PRD.md
- Output: expectations/PRD-[MODULE_NAME].pdf
```

**Special Instructions untuk AI:**
- [Instruksi khusus untuk AI/system]
- [Preferences untuk tone/style]

=> Contoh:
- Tone: Professional, formal, medical documentation style
- Language: 100% Bahasa Indonesia
- Detail Level: High detail untuk requirements dan acceptance criteria
- Consistency: Use consistent terminology dari brief

---

## ✅ Checklist Sebelum Submit

- [ ] Semua 10 sections diisi lengkap
- [ ] Module name clear dan unik
- [ ] Minimal 3 user personas didefinisikan
- [ ] Minimal 3-5 user stories terdaftar
- [ ] Image mapping sesuai dengan screenshots
- [ ] Key requirements jelas dan measurable
- [ ] Metadata lengkap dengan contact info
- [ ] Expected output jelas
- [ ] Generation instructions spesifik

**Status Brief:** ☐ Ready untuk generate / ☐ Perlu perbaikan

---

## 💡 Tips

1. **Copy-Paste Section:** Copy setiap section dari template ini ke file brief.md kamu
2. **Replace Contoh:** Replace [placeholder] dengan data kamu, atau copy dari section "=> Contoh" jika sesuai
3. **Screenshots:** Pastikan sequential naming (001.png, 002.png, dst) dan sesuai dengan image mapping
4. **Personas:** Buat realistic, berbeda background & goals
5. **Stories:** Setiap story minimal 3-5 screenshots untuk detail
6. **Requirements:** Pastikan measurable dan testable
7. **Metadata:** Jelas siapa stakeholders & timeline

---

**Ready? Buat file baru: `module/[MODULE_NAME]/brief.md` dan mulai isi!** 🚀
```
