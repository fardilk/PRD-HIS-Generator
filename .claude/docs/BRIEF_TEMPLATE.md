# Brief Template - PRD Generation

**Panduan untuk membuat brief file sebelum generate PRD**

---

## Format: module/[MODULE_NAME]/brief.md

Salin template ini dan isi semua 10 sections:

```markdown
# Brief - [MODULE_NAME]

## 1. Project Context

**Nama Project:**
[Nama lengkap module/project]

**Klien/Organisasi:**
[Nama klien/rumah sakit/organisasi]

**Tujuan Sistem:**
[Jelaskan tujuan utama module ini dalam 2-3 kalimat]

**Background/Latar Belakang:**
[Konteks mengapa system ini dibuat, masalah apa yang dipecahkan]

**Timeline:**
[Kapan project ini direncanakan dimulai dan selesai]

---

## 2. Scope Overview

**Fitur Utama:**
- [Fitur 1: Deskripsi singkat]
- [Fitur 2: Deskripsi singkat]
- [Fitur 3: Deskripsi singkat]

**Tidak termasuk dalam scope:**
- [Hal yang OUT OF SCOPE]
- [Hal yang akan di-handle di fase lain]

**Integrasi dengan sistem lain:**
- [Sistem A: apa data yang ditukar]
- [Sistem B: apa data yang ditukar]

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

---

### Persona 2: [Nama Role]
[Isi dengan format sama seperti Persona 1]

---

### Persona 3: [Nama Role]
[Isi dengan format sama seperti Persona 1]

---

## 4. User Stories Overview

**Total Stories:** [Jumlah]

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

4. **Story 4: [Judul Story]**
   - Persona: [Yang digunakan]
   - Deskripsi: [Singkat apa yang dilakukan]

5. **Story 5: [Judul Story]**
   - Persona: [Yang digunakan]
   - Deskripsi: [Singkat apa yang dilakukan]

---

## 5. Image Mapping

**Referensi UI Screenshots:**

| Story | Screenshot Range | Deskripsi | Personas |
|-------|------------------|-----------|----------|
| Story 1: [Judul] | 001-005.png | [Apa yang ditunjukkan images] | [Persona yang involved] |
| Story 2: [Judul] | 006-010.png | [Apa yang ditunjukkan images] | [Persona yang involved] |
| Story 3: [Judul] | 011-015.png | [Apa yang ditunjukkan images] | [Persona yang involved] |
| Story 4: [Judul] | 016-020.png | [Apa yang ditunjukkan images] | [Persona yang involved] |
| Story 5: [Judul] | 021-025.png | [Apa yang ditunjukkan images] | [Persona yang involved] |

**Total Screenshots:** [Jumlah] PNG files (sequential naming: 001.png - NNN.png)

---

## 6. Key Requirements

**Functional Requirements:**
1. [Requirement 1: Deskripsi detail]
2. [Requirement 2: Deskripsi detail]
3. [Requirement 3: Deskripsi detail]
4. [Requirement 4: Deskripsi detail]
5. [Requirement 5: Deskripsi detail]

**Non-Functional Requirements:**
- Performance: [Spec jika ada]
- Security: [Spec jika ada]
- Usability: [Spec jika ada]
- Availability: [Spec jika ada]

**Business Rules:**
1. [Rule 1: Bagaimana sistem harus behave]
2. [Rule 2: Business logic yang harus diterapkan]
3. [Rule 3: Validasi atau constraint]

---

## 7. Document Metadata

**Project/Module Name:**
[Nama resmi module]

**Module Code:**
[Kode singkat, e.g., RM untuk Rehab Medik]

**Version:**
1.0

**Created Date:**
[Tanggal brief dibuat]

**Created By:**
[Nama orang yang membuat brief]

**Document Status:**
Draft / In Review / Approved

**Target Approval Date:**
[Tanggal diharapkan approve]

**Client Contact:**
- Name: [Nama contact person]
- Email: [Email]
- Phone: [Phone]

**Development Team Lead:**
- Name: [Nama team lead]
- Email: [Email]

---

## 8. Special Notes & Considerations

**Technical Considerations:**
- [Teknologi yang digunakan]
- [Constraints teknis]
- [Dependencies external systems]

**Design Considerations:**
- [Bahasa UI: Indonesian/English]
- [Theme/Color scheme (jika ada)]
- [Accessibility requirements (jika ada)]

**Regulatory/Compliance:**
- [Regulasi yang harus diikuti]
- [Data privacy considerations]
- [Industry standards]

**Assumptions:**
- [Asumsi tentang data availability]
- [Asumsi tentang user skills]
- [Asumsi tentang infrastructure]

**Risks & Mitigation:**
- Risk 1: [Deskripsi] → Mitigation: [Cara handle]
- Risk 2: [Deskripsi] → Mitigation: [Cara handle]

---

## 9. Expected Output

**PRD Document Structure:**
- Cover page with approval section
- Document properties & metadata
- Executive summary
- [N] User personas (detailed)
- [N] User stories (13 sections each)
- Integration & system requirements
- Glossary & terminology
- Appendix with references
- Sign-off & approval section
- Changelog & version history

**Output Format:**
- Markdown file: `exports/[MODULE_NAME]-PRD.md`
- PDF file: `expectations/PRD-[MODULE_NAME].pdf`
- Approximate length: 2000-5000 lines markdown

**Quality Standards:**
- All user stories complete with screenshots
- All acceptance criteria well-defined
- All forms & data fields documented
- All flows documented with step-by-step instructions
- All glossary terms defined
- No placeholder text [INSERT_XXX] remaining

---

## 10. Generation Instructions

**Step 1 - Setup (Sudah Done):**
- [✓] Brief file dibuat
- [ ] Screenshots uploaded ke `screenshots/[MODULE_NAME]/`
- [ ] All required info filled in brief

**Step 2 - Generate Stories:**
```
generate-story untuk [MODULE_NAME]:
- Story number: 1-5
- Use brief data untuk context
- Analyze screenshots untuk extract requirements
```

**Step 3 - Review Quality:**
```
review untuk [MODULE_NAME]:
- Check all sections complete
- Check no placeholder text
- Generate review report
```

**Step 4 - Compile PRD:**
```
compile PRD untuk [MODULE_NAME]:
- Merge template + stories
- Format untuk PDF
- Output to exports/
```

**Step 5 - Export PDF:**
```
pandoc atau markdown converter:
- Input: exports/[MODULE_NAME]-PRD.md
- Output: expectations/PRD-[MODULE_NAME].pdf
```

**Special Instructions:**
- [Instruksi khusus untuk AI/system]
- [Preferences untuk tone/style]
- [Specific format requirements]

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

**Status Brief:** Ready untuk generate / Perlu perbaikan

---

## 💡 Tips

1. **Personas:** Buat realistic, berbeda background & goals
2. **Stories:** Setiap story minimal 3-5 screenshots untuk detail
3. **Requirements:** Pastikan measurable dan testable
4. **Image Mapping:** Sequential naming PENTING untuk AI analyze
5. **Metadata:** Jelas siapa stakeholders & timeline
6. **Notes:** Jangan lupa technical constraints & business rules

---

**Contoh real:** Lihat `module/REHAB_MEDIK/brief.md`

Siap? Copy template ini dan isi sesuai module kamu! 🚀
```

---

## Cara Pakai

1. **Copy template di atas**
2. **Buat file:** `module/[NAMA_MODULE]/brief.md`
3. **Isi semua 10 sections**
4. **Upload screenshots:** `screenshots/[NAMA_MODULE]/001.png` dst
5. **Kasih tahu nama module** → aku generate PRD

Contoh struktur:
```
module/REHAB_MEDIK/
├── brief.md              ← Isi dari template ini
└── metadata.json

screenshots/REHAB_MEDIK/
├── 001.png
├── 002.png
└── ...025.png
```

Siap isi brief? 🚀
