# Brief Example - REHAB_MEDIK

**Contoh pengisian brief yang lengkap dari Rehab Medik Primaya Hospital**

---

## 1. Project Context

**Nama Project:**
Rehab Medik - Hospital Information System (HIS) V2

**Klien/Organisasi:**
Primaya Hospital Group

**Tujuan Sistem:**
Mengimplementasikan modul Rehab Medik dalam sistem HIS V2 untuk memfasilitasi proses konsultasi, dokumentasi, dan pelaksanaan fisioterapi pasien. Sistem ini memungkinkan dokter, fisioterapis, dan pasien untuk berkolaborasi dalam program rehabilitasi medis dengan dokumentasi elektronik yang terintegrasi.

**Background/Latar Belakang:**
Rumah Sakit Primaya memerlukan sistem informasi terpadu untuk mengelola pelayanan rehabilitasi medis. Saat ini, proses konsultasi dokter, perencanaan program terapi, dan dokumentasi pelaksanaan fisioterapi masih tersebar di beberapa sistem atau bahkan manual. Sistem HIS V2 Rehab Medik akan mengintegrasikan seluruh proses tersebut dalam satu platform yang efisien, dengan fitur signature digital untuk persetujuan tindakan medis.

**Timeline:**
- Document Preparation: 1 hari (03-12-2025)
- Development: [Dalam diskusi]
- Quality Control: [Dalam diskusi]
- User Acceptance Testing: [Dalam diskusi]

---

## 2. Scope Overview

**Fitur Utama:**
- **Konsultasi Awal Dokter**: Dokter dapat membuat form pemeriksaan rawat jalan khusus untuk pasien Rehab Medik dengan form tambahan (Anjuran, Evaluasi, Suspek Penyakit Akibat Kerja)
- **Catatan Terintegrasi Fisioterapis**: Fisioterapis dapat membuat catatan SOAP (Subjective, Objective, Assessment, Plan) dan mendokumentasikan pelaksanaan terapi
- **Manajemen Kehadiran Program**: Sistem tracking untuk kehadiran dan ketidakhadiran pasien dalam program fisioterapi
- **Penyelesaian Sesi Terapi**: Fisioterapis dapat menutup sesi terapi dengan pencatatan hasil dan progres pasien
- **Evaluasi Dokter**: Dokter dapat mengevaluasi pelaksanaan program fisioterapi dan membuat kesimpulan klinis
- **Signature Digital**: Pasien dan Fisioterapis dapat melakukan signature digital menggunakan Wacom atau QR Code
- **Generate Dokumen**: Sistem auto-generate Lembar Formulir Rawat Jalan dan dokumen Layanan Kedokteran Fisik dan Rehabilitasi

**Tidak termasuk dalam scope:**
- Manajemen tarif/billing untuk layanan fisioterapi
- Integrasi dengan peralatan fisioterapi (TENS, Ultrasound, Laser)
- Report analytics dan business intelligence untuk Rehab Medik
- Mobile app untuk patient engagement

**Integrasi dengan sistem lain:**
- **EMR System**: Pull data pasien, diagnosis, dan riwayat medis
- **Master Data**: Retrieve data dokter, fisioterapis, program terapi standard
- **Appointment System**: Integrasi dengan jadwal layanan fisioterapi
- **Document Management**: Penyimpanan dan retrieval dokumen digital yang ditandatangani

---

## 3. User Personas

### Persona 1: Dokter Spesialis Rehabilitasi Medik

**Demografi:**
- Umur: 40-60 tahun
- Lokasi: Poliklinik/Rawat Inap Rehab Medik
- Pengalaman dengan teknologi: Intermediate (sudah familiar dengan EMR dasar)

**Karakteristik:**
Dokter berpengalaman yang bertanggung jawab untuk diagnosis, perencanaan program terapi, dan evaluasi hasil pelaksanaan fisioterapi pasien. Mereka perlu dengan cepat membuat form konsultasi yang terstruktur dan review progress pasien.

**Primary Goals:**
- Membuat form konsultasi awal dan perencanaan program terapi dengan cepat
- Review dan evaluasi hasil pelaksanaan program fisioterapi
- Membuat keputusan klinis berdasarkan progress pasien

**Pain Points:**
- Form terlalu panjang dan rumit, menyita banyak waktu
- Sulit melihat history dan progress pelaksanaan terapi pasien
- Data tidak terintegrasi dari berbagai sistem

**Behavior Pattern:**
Dokter menghabiskan sekitar 10-15 menit per pasien untuk konsultasi dan form filling. Mereka membutuhkan interface yang clean dan navigasi yang mudah untuk input data dan review.

---

### Persona 2: Fisioterapis

**Demografi:**
- Umur: 25-45 tahun
- Lokasi: Ruangan/Klinik Fisioterapi
- Pengalaman dengan teknologi: Beginner-Intermediate (kurang familiar dengan sistem kompleks)

**Karakteristik:**
Tenaga medis profesional yang melaksanakan program fisioterapi sesuai perencanaan dokter. Mereka perlu mendokumentasikan setiap sesi terapi dengan detail dan memastikan persetujuan pasien.

**Primary Goals:**
- Dokumentasi lengkap setiap sesi terapi (SOAP notes)
- Tracking kehadiran dan ketidakhadiran pasien
- Dapatkan signature pasien untuk setiap sesi terapi

**Pain Points:**
- Pencatatan manual yang memakan waktu
- Sulit mendapatkan signature pasien dengan aman dan legal
- Tidak ada visibility terhadap rencana program dari dokter

**Behavior Pattern:**
Fisioterapis menangani 8-12 pasien per hari. Mereka perlu interface yang intuitive dan cepat untuk input data, tanpa perlu training panjang.

---

### Persona 3: Pasien

**Demografi:**
- Umur: 18-75 tahun
- Lokasi: Klinik/Rumah Sakit
- Pengalaman dengan teknologi: Beginner (kurang familiar dengan teknologi digital)

**Karakteristik:**
Pasien yang menjalani program fisioterapi sebagai bagian dari treatment medis mereka. Mereka perlu memahami rencana terapi dan memberikan persetujuan untuk setiap sesi.

**Primary Goals:**
- Memahami program terapi yang direncanakan dokter
- Memberikan persetujuan/tanda setuju untuk pelaksanaan terapi
- Tracking progress terapi mereka

**Pain Points:**
- Sulit memahami dokumen medis yang kompleks
- Khawatir dengan legalitas signature digital
- Tidak tahu progress atau hasil dari program mereka

**Behavior Pattern:**
Pasien menghabiskan 20-60 menit per sesi terapi. Mereka membutuhkan komunikasi yang jelas tentang apa yang akan dilakukan dan perlu merasa aman dalam memberikan persetujuan digital.

---

## 4. User Stories Overview

**Total Stories:** 5

Daftar stories yang akan di-generate:

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
| Story 1 | 001-005.png | Menu EMR Dokter, Button +Pemeriksaan RJ, Form isian RJ dengan Anjuran/Evaluasi/Suspek, Daftar Pemeriksaan | Dokter |
| Story 2 | 006-015.png | Catatan Terintegrasi pasien, Button +SOAP, Form SOAP S-O-A-P, Tanda Tangan Fisioterapis (Wacom/QR), Tanda Tangan Pasien, Generated Document | Fisioterapis, Pasien |
| Story 3 | 016-018.png | Menu Absen Program, Form/List Absen Pasien, Notifikasi ketidakhadiran | Fisioterapis |
| Story 4 | 019-022.png | Form Penutupan Sesi Terapi, Hasil & Progress, Rekomendasi Lanjutan, Summary Sesi | Fisioterapis |
| Story 5 | 023-025.png | Review History Pelaksanaan, Form Evaluasi Dokter, Final Assessment & Rekomendasi | Dokter |

**Total Screenshots:** 25 PNG files (sequential naming: 001.png - 025.png)

---

## 6. Key Requirements

**Functional Requirements:**
1. **Form Pemeriksaan RJ Khusus Rehab Medik**: Sistem harus menampilkan 3 form tambahan (Anjuran, Evaluasi, Suspek Penyakit Akibat Kerja) ketika pasien diklasifikasikan sebagai Rehab Medik
2. **Catatan SOAP Terintegrasi**: Fisioterapis dapat membuat/edit catatan SOAP dan sistem menyimpan dengan timestamp dan user identity
3. **Signature Digital**: Sistem mendukung 2 metode signature (Wacom pen pad, QR Code scan) dengan validation dan encryption
4. **Tracking Kehadiran**: Sistem mencatat kehadiran/ketidakhadiran pasien per sesi dengan notifikasi ke dokter jika tidak hadir
5. **Auto-Generate Dokumen**: Sistem menggenerate Lembar Formulir Rawat Jalan dan dokumen Layanan Kedokteran Fisik & Rehabilitasi dalam format PDF yang siap print
6. **History & Audit Trail**: Semua perubahan data, signature, dan action harus tercatat dengan timestamp dan user identity
7. **Permission Management**: Hak akses berbeda untuk Dokter, Fisioterapis, dan Pasien

**Non-Functional Requirements:**
- **Performance**: Load time < 3 detik untuk setiap page, response time API < 1 detik
- **Security**: SSL/TLS encryption, password policy sesuai standar, audit trail lengkap, compliance dengan regulasi data medis
- **Usability**: UI/UX harus user-friendly untuk user dengan skill IT yang beragam, support bahasa Indonesia
- **Availability**: System uptime 99.5%, backup otomatis data setiap hari

**Business Rules:**
1. Form Anjuran, Evaluasi, dan Suspek hanya muncul jika pasien diklasifikasikan Rehab Medik
2. Catatan SOAP harus diisi lengkap sebelum dapat di-submit
3. Signature Pasien harus diperoleh sebelum sesi terapi dianggap complete
4. Dokter dapat melakukan review dan evaluasi hanya setelah minimal 1 sesi fisioterapi tercatat
5. Ketidakhadiran pasien lebih dari 3 kali akan trigger notifikasi urgent ke dokter
6. Generated dokumen tidak dapat diedit, hanya dapat dilihat dan diprint

---

## 7. Document Metadata

**Project/Module Name:**
Rehab Medik - Hospital Information System (HIS) V2

**Module Code:**
RM (Rehab Medik)

**Version:**
1.0

**Created Date:**
03-12-2025

**Created By:**
Fardil Khalidi

**Document Status:**
Draft

**Target Approval Date:**
07-12-2025

**Client Contact:**
- Name: Roky Sarasi
- Email: roky.sarasi@primayahospital.com
- Phone: +62-21-XXXX-XXXX

**Development Team Lead:**
- Name: Adrianto
- Email: adrianto@sistemintegrasi.com
- Title: Ka Div IT Operasional

---

## 8. Special Notes & Considerations

**Technical Considerations:**
- **Technology Stack**: Web-based system, responsive design untuk desktop dan tablet
- **Signature Technology**: Integration dengan Wacom SDK untuk tablet, QR Code library untuk mobile verification
- **Database**: PostgreSQL dengan encryption untuk sensitive data
- **API Integration**: RESTful API untuk komunikasi dengan EMR master data
- **Document Generation**: Menggunakan template engine (Jinja2 atau similar) untuk generate PDF

**Design Considerations:**
- **Bahasa UI**: Bahasa Indonesia dengan sidebar bantuan dalam Bahasa Inggris
- **Theme**: Medical/Healthcare theme dengan color scheme biru (trust, professional)
- **Accessibility**: WCAG compliance, support screen reader, keyboard navigation
- **Responsive**: Work di desktop (1920x1080), tablet (iPad), minimal responsif untuk mobile

**Regulatory/Compliance:**
- **Regulasi Medis**: Compliance dengan peraturan Kementerian Kesehatan Indonesia tentang rekam medis elektronik
- **Data Privacy**: GDPR-like approach untuk data pasien sensitif, encrypt PII
- **Audit**: Semua transaction harus tercatat di audit log untuk compliance & investigasi
- **Signature Legal**: Digital signature harus memiliki legal standing sesuai Undang-Undang ITE Indonesia

**Assumptions:**
- Pasien sudah terdaftar di sistem sebelum masuk ke flow Rehab Medik
- Dokter dan Fisioterapis sudah trained dengan sistem HIS dasar
- Infrastructure dan network bandwidth sudah memadai untuk handle signature digital
- Wacom devices atau QR code readers sudah tersedia di lokasi layanan fisioterapi

**Risks & Mitigation:**
- **Risk 1**: User (terutama Fisioterapis yang skill IT rendah) kesulitan menggunakan signature digital → Mitigation: Provide comprehensive training, support multiple signature methods, clear on-screen instructions
- **Risk 2**: Signature digital tidak diterima oleh internal audit/legal → Mitigation: Coordinate dengan legal team sebelum implementation, ensure compliance dengan regulasi
- **Risk 3**: Data loss atau signature corruption → Mitigation: Implement redundant backup, encryption, regular testing & validation
- **Risk 4**: Performance issue saat multiple users access signature simultaneously → Mitigation: Load testing, optimize query, consider distributed system architecture

---

## 9. Expected Output

**PRD Document Structure:**
- Cover page with approval section (Surat Persetujuan Desain)
- Document properties & metadata (Document Number, Title, Version, Author)
- Executive summary & Table of Contents
- 3 User personas (Dokter, Fisioterapis, Pasien) - detailed
- 5 User stories (13 sections each dengan breakdown per story):
  - Persona & Job to be Done
  - Acceptance Criteria
  - User Flow (with flowchart)
  - Forms & Data Fields
  - Screenshots references
  - Technical considerations
  - Business rules
  - Integration points
  - FAQ & edge cases
  - Glossary
- Integration & System Requirements
- Glossary & Terminology
- Appendix with references, related documents, revision log
- Sign-off & Approval section
- Changelog & Version history

**Output Format:**
- Markdown file: `exports/REHAB_MEDIK-PRD.md`
- PDF file: `expectations/PRD-REHAB_MEDIK.pdf`
- Approximate length: 3500-5000 lines markdown (150-200 pages PDF)

**Quality Standards:**
- All 5 user stories complete dengan all 13 sections
- All acceptance criteria well-defined dan testable
- All 25 screenshots referenced dengan clear instructions
- All forms & data fields documented dengan data types & validation
- All flowcharts visual representation dari user flows
- All business rules dan edge cases covered
- No placeholder text [INSERT_XXX] remaining (semua diganti dengan content actual)
- Language consistency (Bahasa Indonesia throughout)

---

## 10. Generation Instructions

**Step 1 - Setup (Manual, Sebelum AI Generate):**
- [✓] Brief file dibuat (file ini)
- [ ] Screenshots uploaded ke `screenshots/REHAB_MEDIK/` (001.png - 025.png)
- [✓] All required info filled in brief
- [ ] Folder structure created: `module/REHAB_MEDIK/`, `stories/REHAB_MEDIK/`

**Step 2 - Generate Stories (AI Agent):**
```
generate-story untuk REHAB_MEDIK:
- Generate untuk story 1-5
- Analyze screenshots untuk extract requirements detail
- Output: stories/REHAB_MEDIK/story-001.md ... story-005.md
- Each story harus 13 sections lengkap
- Reference images dalam story sesuai mapping di brief
```

**Step 3 - Review Quality (AI Agent):**
```
review untuk REHAB_MEDIK:
- Check: All 5 stories generated
- Check: No [INSERT_XXX] placeholder text
- Check: All screenshots referenced
- Check: All acceptance criteria clear
- Generate: exports/REHAB_MEDIK-review.md
- Output: Pass ✅ atau perlu fix ⚠️
```

**Step 4 - Compile PRD (AI Agent):**
```
compile PRD untuk REHAB_MEDIK:
- Merge template + brief metadata + all 5 stories
- Format untuk PDF-ready markdown
- Output: exports/REHAB_MEDIK-PRD.md
- Check: No missing sections, consistent formatting
```

**Step 5 - Export to PDF (Manual atau Tool):**
```
pandoc atau markdown converter:
- Input: exports/REHAB_MEDIK-PRD.md
- Output: expectations/PRD-REHAB_MEDIK.pdf
- Options: Include TOC, A4 page size, default margins
```

**Special Instructions untuk AI:**
- **Tone**: Professional, formal, medical documentation style
- **Language**: 100% Bahasa Indonesia, no English terms jika bisa diterjemahkan
- **Detail Level**: High detail untuk requirements dan acceptance criteria
- **User Flow**: Include visual ASCII flowchart + written step-by-step
- **Screenshots**: Setiap screenshot harus dideskripsikan detailed dengan instruksi capture
- **Consistency**: Use consistent terminology dari brief (e.g., "Pemeriksaan RJ", "Catatan Terintegrasi", "Signature Digital")

---

## ✅ Checklist Sebelum Submit

- [✓] Semua 10 sections diisi lengkap
- [✓] Module name clear (REHAB_MEDIK) dan unik
- [✓] 3 user personas didefinisikan dengan detail
- [✓] 5 user stories terdaftar dengan mapping images
- [✓] Image mapping jelas dengan total 25 screenshots
- [✓] Key requirements terukur dan testable
- [✓] Metadata lengkap dengan contact info
- [✓] Expected output clear dan realistic
- [✓] Generation instructions spesifik untuk AI

**Status Brief:** ✅ **READY untuk generate PRD**

---

## 💡 Catatan

Contoh ini didasarkan pada data aktual dari Rehab Medik Primaya Hospital Group. Brief yang lengkap memastikan bahwa:
1. AI dapat menggenerate PRD yang relevant dengan requirement aktual
2. Quality review menjadi lebih objektif dan terstruktur
3. Approval process lebih cepat karena semua stakeholder sudah aligned
4. Development team punya dokumentasi yang jelas untuk implementation

---

**Contoh ini siap untuk di-generate → PRD lengkap dalam 2 jam!** 🚀

Untuk project baru, copy template di `BRIEF_TEMPLATE.md` dan isi sesuai project kamu.
