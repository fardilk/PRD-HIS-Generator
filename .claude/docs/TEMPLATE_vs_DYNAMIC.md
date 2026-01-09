# Template vs Dynamic Content - Detailed Breakdown

**Panduan untuk memahami bagian mana yang Template dan mana yang Dynamic**
**Versi:** 1.0
**Date:** 2026-01-10

---

## 📋 Struktur PRD Keseluruhan

Setiap PRD terdiri dari 11 bagian utama:

```
PRD Document
├── Part 1: Cover & Metadata (70% TEMPLATE, 30% DYNAMIC)
├── Part 2: Document Properties (50% TEMPLATE, 50% DYNAMIC)
├── Part 3: Intro & Context (20% TEMPLATE, 80% DYNAMIC)
├── Part 4: User Personas (10% TEMPLATE, 90% DYNAMIC)
├── Part 5: User Stories (10% TEMPLATE, 90% DYNAMIC) ← TERBESAR
├── Part 6: Integration Specs (30% TEMPLATE, 70% DYNAMIC)
├── Part 7: Glossary (40% TEMPLATE, 60% DYNAMIC)
├── Part 8: Appendix (90% TEMPLATE, 10% DYNAMIC)
├── Part 9: Sign-off (100% TEMPLATE, 0% DYNAMIC)
└── Part 10: Changelog (50% TEMPLATE, 50% DYNAMIC)
```

---

## 🎯 PART 1: Cover & Metadata (70% TEMPLATE)

### TEMPLATE Section
```markdown
# Surat Persetujuan Desain UI/UX
## [DYNAMIC: Module Name]

**[DYNAMIC: Document Code]**

Yang bertanda-tangan dibawah ini, menyatakan bahwa telah sepakat
dengan desain, sebagaimana merupakan lampiran tak terpisahkan
dari Surat Persetujuan Tahap Desain UI/UX ini.

| | |
|---|---|
| Diajukan tanggal | [TEMPLATE: Format] [DYNAMIC: Date Today] |
| Disetujui tanggal | _________________ |

| Yang Mengajukan | Mengetahui |
|-----------------|------------|
| **[DYNAMIC: Name]** | **[DYNAMIC: Client Rep]** |
| [DYNAMIC: Role] | [DYNAMIC: Role] |
| [DYNAMIC: Company] | [DYNAMIC: Company] |
```

**Penjelasan:**
- Struktur & format = TEMPLATE (sama untuk semua)
- Nama, tanggal, role = DYNAMIC (beda untuk setiap PRD)

---

## 📊 PART 2: Document Properties (50% TEMPLATE)

### TEMPLATE Structure + DYNAMIC Values

```markdown
## A. Document Property

| Field | Value |
|-------|-------|
| Document Number | TEMPLATE: `[CLIENT]/[MODULE]/PRD/[YEAR]` |
|  | DYNAMIC: `668/REHAB-MEDIK/PRD/2026` |
| Document Title | TEMPLATE: "PRD [Module]" |
|  | DYNAMIC: "PRD Rehab Medik Primaya Hospital" |
| Document Editor | DYNAMIC: `[User/Team Name]` |
| Editorial Team | DYNAMIC: `[Team Member List]` |
| Author | DYNAMIC: `[Author Names]` |
| Dissemination Level | TEMPLATE: `Private / Confidential` |
|  | DYNAMIC: `Private` |
| Keyword List | DYNAMIC: `UI/UX Design, PRD, [Module-specific]` |
| Status | DYNAMIC: `Draft / Ready / Approved` |
| Version | TEMPLATE: Starts at `1.0` |
|  | DYNAMIC: `1.0` atau `1.1` jika ada revisi |
```

**Tabel ini:**
- Row structure = TEMPLATE
- Values diisi = DYNAMIC dari brief.md

---

## 📖 PART 3: Intro & Context (20% TEMPLATE)

### TEMPLATE Paragraph
```markdown
## Intro

Selamat datang di Dokumen Persyaratan Produk (PRD) komprehensif
untuk **[DYNAMIC: Module Name]**. Dokumen ini bertujuan untuk
memberikan gambaran rinci tentang fitur, fungsi, dan spesifikasi
terkait [DYNAMIC: what this module does].
```

### DYNAMIC Content
```markdown
Dokumen [DYNAMIC: Module Name] pada aplikasi [DYNAMIC: System]
ini terdapat [DYNAMIC: N] user story yang akan dibahas yaitu:

- Story #1: [DYNAMIC: Story title]
- Story #2: [DYNAMIC: Story title]
- Story #N: [DYNAMIC: Story title]

Adapun user persona yang akan diterangkan disini adalah:

1. **[DYNAMIC: Persona 1]**: [DYNAMIC: Description]
2. **[DYNAMIC: Persona 2]**: [DYNAMIC: Description]
3. **[DYNAMIC: Persona 3]**: [DYNAMIC: Description]
```

**Penjelasan:**
- Intro paragraph = TEMPLATE (format standard)
- Module name, story list, personas = DYNAMIC (dari brief.md)

---

## 👥 PART 4: User Personas (10% TEMPLATE)

### TEMPLATE Structure
```markdown
## User Personas

### Persona 1: [DYNAMIC: Name]

| Field | Value |
|-------|-------|
| Role | [DYNAMIC: Role description] |
| Primary Goal | [DYNAMIC: Main objective] |
| Pain Points | [DYNAMIC: Problems faced] |
| Experience Level | [DYNAMIC: Beginner/Intermediate/Advanced] |
```

**Penjelasan:**
- Table structure dengan fields = TEMPLATE
- Semua values (role, goal, pain points) = DYNAMIC dari brief.md

---

## 📖 PART 5: User Stories (10% TEMPLATE, 90% DYNAMIC) ⭐

### INI BAGIAN TERBESAR DAN PALING PENTING!

Setiap story punya **13 sections** dengan pattern:

#### TEMPLATE: Section Header & Format

```markdown
## Story #[N]: [DYNAMIC: Title]

| Field | Value |
|-------|-------|
| User Persona | [DYNAMIC] |
| Jobs to be Done | [DYNAMIC] |
| Referensi UI | [DYNAMIC] |
| Flow Reference | [DYNAMIC] |
```

#### DYNAMIC: Content Setiap Section

```markdown
### 1. Persona
**Aktor:** [DYNAMIC: Dari brief → Siapa yang melakukan story ini]
**Role:** [DYNAMIC: Dari brief → Apa role mereka]
**Goal:** [DYNAMIC: Dari brief → Apa yang ingin dicapai]

### 2. Jobs to be Done
[DYNAMIC: Dari screenshot analysis → Apa yang user lakukan]

### 3. Referensi UI
- Figma: [DYNAMIC: Link dari brief]
- Screens: [DYNAMIC: Screenshot reference]

### 4. User Acceptance Criteria
- [DYNAMIC: Extracted dari image 001]
- [DYNAMIC: Extracted dari image 002]
- [DYNAMIC: Extracted dari image 003]
- [DYNAMIC: Extracted dari image 004]
- [DYNAMIC: Extracted dari image 005]

### 5. User Flow

**Step 1: [DYNAMIC: Dari image 001]**
- User: [DYNAMIC: Action dari image]
- System: [DYNAMIC: Response yang terlihat di image]
- Screenshot: 001.png

**Step 2: [DYNAMIC: Dari image 002]**
- User: [DYNAMIC: Action]
- System: [DYNAMIC: Response]
- Screenshot: 002.png

...dst

### 6. Forms & Data Fields
| Field | Type | Required | Notes |
|-------|------|----------|-------|
| [DYNAMIC: Field 1] | [DYNAMIC: Type dari UI] | [DYNAMIC: Yes/No] | [DYNAMIC] |
| [DYNAMIC: Field 2] | [DYNAMIC: Type dari UI] | [DYNAMIC: Yes/No] | [DYNAMIC] |

### 7. Screenshots
[DYNAMIC: Description dari setiap screenshot]

### 8-13. [Sections lainnya]
[DYNAMIC: Semua content dari story-[N].md]
```

**Penjelasan:**
- Section number, title, table format = TEMPLATE
- Semua content isi sections = DYNAMIC dari story-[N].md

---

## 🔌 PART 6: Integration Specs (30% TEMPLATE)

### TEMPLATE Section Headers
```markdown
## Integration & System Requirements

### Data Sources
### Data Outputs
### API Endpoints
### System Dependencies
```

### DYNAMIC Content
```markdown
### Data Sources

**Source 1:** [DYNAMIC: System name]
- Data: [DYNAMIC: What data]
- Location: [DYNAMIC: Where stored]
- Access: [DYNAMIC: How to access]

### Data Outputs

**Output 1:** [DYNAMIC: System name]
- Data: [DYNAMIC: What data sent]
- Method: [DYNAMIC: How sent]
- Frequency: [DYNAMIC: When sent]

### API Endpoints

**Endpoint 1:** [DYNAMIC: API URL]
- Method: [DYNAMIC: GET/POST/PUT]
- Purpose: [DYNAMIC: What it does]
- Parameters: [DYNAMIC: Required params]
- Response: [DYNAMIC: What returns]
```

**Penjelasan:**
- Section headers & structure = TEMPLATE
- Semua content tentang API, data flow = DYNAMIC dari brief.md

---

## 📚 PART 7: Glossary (40% TEMPLATE)

### TEMPLATE Section
```markdown
## Glossary & Terminology

Bagian ini menjelaskan istilah-istilah khusus yang digunakan
dalam dokumen ini untuk memastikan pemahaman yang sama.

### Istilah Bahasa Indonesia
```

### DYNAMIC Content
```markdown
| Term | Definition |
|------|-----------|
| [DYNAMIC: Term 1] | [DYNAMIC: Definition] |
| [DYNAMIC: Term 2] | [DYNAMIC: Definition] |
| [DYNAMIC: Term 3] | [DYNAMIC: Definition] |

### Istilah Teknis (English)
| Term | Definition |
|------|-----------|
| [DYNAMIC: Technical term 1] | [DYNAMIC: Definition] |
| [DYNAMIC: Technical term 2] | [DYNAMIC: Definition] |
```

**Penjelasan:**
- Section intro & structure = TEMPLATE
- Semua terms & definitions = DYNAMIC dari brief.md

---

## 📎 PART 8: Appendix (90% TEMPLATE)

### TEMPLATE Content
```markdown
## Appendix

### References
- [DYNAMIC: External links]

### Related Documents
- HIS V2 System Documentation
- Design Guidelines
- Technical Specifications

### Legenda Signifier
📊 FLOWCHART REQUIRED - Area perlu flowchart
🖼️ SCREENSHOT REQUIRED - Area perlu screenshot
[INSERT_XXX] - Placeholder perlu diisi

### Revision Log
[DYNAMIC: Version history]
```

**Penjelasan:**
- Section headers & standard content = TEMPLATE
- Links & version info = DYNAMIC

---

## ✍️ PART 9: Sign-Off (100% TEMPLATE)

### TEMPLATE Section (Identical untuk semua PRD)

```markdown
## Sign-Off & Approval

| Role | Name | Approval | Date | Notes |
|------|------|----------|------|-------|
| Product Owner | _________________ | _____ | _____ | _____ |
| Design Lead | _________________ | _____ | _____ | _____ |
| Tech Lead | _________________ | _____ | _____ | _____ |
| Client Rep | _________________ | _____ | _____ | _____ |

**Status:** ✅ APPROVED / 🔄 IN REVIEW / ❌ NEEDS REVISION

---

## Legal Statement

Dokumen ini merupakan properti [DYNAMIC: Company Name] dan
[DYNAMIC: Client Name]. Penggunaan atau reproduksi tanpa
izin tertulis dilarang.
```

**Penjelasan:**
- Seluruh section = TEMPLATE (sama persis untuk semua PRD)
- Yang beda: Names/company bisa DYNAMIC tapi form-nya sama

---

## 📊 PART 10: Changelog (50% TEMPLATE)

### TEMPLATE Structure
```markdown
## Document History

| Version | Date | Description | Revised By | Status |
|---------|------|-------------|-----------|--------|
| 1.0 | [DYNAMIC: Date] | [DYNAMIC: Description] | [DYNAMIC: Name] | Draft |
| 1.1 | [DYNAMIC: Date] | [DYNAMIC: Description] | [DYNAMIC: Name] | In Review |
```

**Penjelasan:**
- Table structure = TEMPLATE
- Dates, descriptions, names = DYNAMIC

---

## 🎨 Visual Breakdown

```
TEMPLATE (Statis) = Same structure for all PRDs
┌─────────────────────────────────────┐
│ Section Header                      │
│ Field names                         │
│ Table columns                       │
│ Disclaimers                         │
│ Standard format                     │
└─────────────────────────────────────┘

        ↓

DYNAMIC (Beda untuk setiap module)
┌─────────────────────────────────────┐
│ Module-specific content             │
│ Values dari brief.md                │
│ Screenshots references              │
│ Requirements extracted              │
│ Module context & flow               │
└─────────────────────────────────────┘

        ↓

RESULT = Professional PRD
```

---

## 💾 File Generation Flow

### 1. Input Files

**brief.md** (created by user)
```
- Module name
- 10 sections dengan content
- Image mapping
```

**stories/[MODULE]/story-[1..N].md** (generated by AI)
```
- 13 sections per story
- All content extracted dari screenshots
```

### 2. Template Files (Built-in)

**TEMPLATE_PRD.md** (sistem)
```
- Document structure
- Section headers
- Standard tables
- Disclaimers
- Sign-off form
```

### 3. Compilation Process

```python
FINAL_PRD =
    TEMPLATE_HEADER +
    DYNAMIC_METADATA +
    TEMPLATE_INTRO +
    DYNAMIC_PERSONAS +
    DYNAMIC_STORIES +
    TEMPLATE_INTEGRATION +
    DYNAMIC_GLOSSARY +
    TEMPLATE_APPENDIX +
    TEMPLATE_SIGNOFF +
    DYNAMIC_CHANGELOG
```

### 4. Output

**PRD-[MODULE_NAME].md**
```
2000-5000 lines
Complete document
Ready for PDF conversion
```

---

## 📄 Contoh: Template Section yang Sama

### PART 9: Sign-Off

**Untuk REHAB_MEDIK:**
```markdown
## Sign-Off & Approval

| Role | Name | Approval | Date |
|------|------|----------|------|
| Product Owner | _________________ | _____ | _____ |
| Design Lead | _________________ | _____ | _____ |
| Tech Lead | _________________ | _____ | _____ |
```

**Untuk MOBILE_BANKING:**
```markdown
## Sign-Off & Approval

| Role | Name | Approval | Date |
|------|------|----------|------|
| Product Owner | _________________ | _____ | _____ |
| Design Lead | _________________ | _____ | _____ |
| Tech Lead | _________________ | _____ | _____ |
```

**PERSIS SAMA!** ← Ini adalah TEMPLATE

---

## 🎯 Key Takeaways

### Template adalah:
✅ Structure & format
✅ Section headers
✅ Table layouts
✅ Standard text
✅ Legal disclaimers
✅ Sign-off forms

### Dynamic adalah:
✅ Module-specific names
✅ Content dari screenshots
✅ Business requirements
✅ User stories detail
✅ Integration specs
✅ Company/person names

### Hasil:
✅ Consistent format (dari template)
✅ Unique content (dari dynamic)
✅ Professional PRD document
✅ Ready untuk PDF export

---

## 📋 Quick Reference

| Section | Template % | Dynamic % | Source |
|---------|-----------|----------|--------|
| Cover | 70% | 30% | brief.md |
| Properties | 50% | 50% | brief.md |
| Intro | 20% | 80% | brief.md |
| Personas | 10% | 90% | brief.md |
| Stories | 10% | 90% | story-[N].md |
| Integration | 30% | 70% | brief.md |
| Glossary | 40% | 60% | brief.md |
| Appendix | 90% | 10% | System |
| Sign-off | 100% | 0% | System |
| Changelog | 50% | 50% | System |

---

**Kesimpulan:** Template + Dynamic = Professional, consistent, yet unique PRD untuk setiap module!

