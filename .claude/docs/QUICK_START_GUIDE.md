# QUICK START GUIDE - Membuat PRD dalam 2 Jam

**TL;DR - Panduan Singkat & Praktis**
**Untuk yang tidak sabar membaca long docs!**

---

## 🎯 Tujuan Akhir

```
Input:  Brief file + Screenshots
        ↓
Output: D:\OFFICE\PRD\expectations\PRD-[MODULE_NAME].pdf
        (Professional PRD siap untuk stakeholders)
```

---

## 6 STEPS - TOTAL WAKTU: 2 JAM

### ⏱️ STEP 1: Setup (30 menit)

**Apa yang kamu buat:**
```
HISv2/module/REHAB_MEDIK/
├── brief.md           ← File ini isian 10 section
├── metadata.json      ← Auto-generated
└── todos.md           ← Progress tracker

HISv2/screenshots/REHAB_MEDIK/
├── 001.png           ← Upload screenshots
├── 002.png
└── ...025.png        ← Sequential naming required
```

**Checklist:**
- [ ] Create folder `module/[MODULE_NAME]/`
- [ ] Create `brief.md` - Fill 10 sections:
  1. Project Context
  2. Scope Overview
  3. User Personas (3-5)
  4. User Stories Overview
  5. Image Mapping (which image = which story)
  6. Key Requirements
  7. Document Metadata
  8. Special Notes
  9. Expected Output
  10. Generation Instructions
- [ ] Create `metadata.json` - Copy dari template
- [ ] Upload screenshots `001.png, 002.png...`

**Template:** `module/REHAB_MEDIK/brief.md` (lihat contoh)

---

### ⏱️ STEP 2: Generate Stories (30 menit)

**Command (jalankan untuk setiap story):**
```
generate-story untuk [MODULE_NAME]:
- Story number: [1-5]
- Story title: [Dari brief]
- Personas: [Dari brief]
```

**Apa yang terjadi:**
- Claude analyze screenshots
- Extract requirements
- Generate story dengan 13 sections lengkap

**Output:**
```
HISv2/stories/[MODULE_NAME]/
├── story-001.md
├── story-002.md
├── story-003.md
├── story-004.md
└── story-005.md
```

**Time:** ~5-7 menit per story

---

### ⏱️ STEP 3: Review Quality (10 menit)

**Command:**
```
review untuk [MODULE_NAME]:
- Check: all
- Generate report: yes
```

**Output:**
```
HISv2/exports/[MODULE_NAME]-review.md
```

**Hasil:** Pass ✅ atau perlu fix ⚠️

---

### ⏱️ STEP 4: Compile PRD (10 menit)

**Command:**
```
compile PRD untuk [MODULE_NAME]:
- Output format: md
- Include metadata: yes
```

**Output:**
```
HISv2/exports/[MODULE_NAME]-PRD.md
(2000-5000 lines, complete document)
```

---

### ⏱️ STEP 5: Export to PDF (5 menit)

**Use Pandoc atau tool pilihan:**
```bash
pandoc HISv2/exports/REHAB_MEDIK-PRD.md \
  -o expectations/PRD-REHAB_MEDIK.pdf
```

**OR gunakan VS Code:**
1. Open `HISv2/exports/[MODULE_NAME]-PRD.md`
2. Install extension: "Markdown PDF"
3. Right-click → "Export as PDF"
4. Save ke `expectations/` folder

**Output:**
```
D:\OFFICE\PRD\expectations\PRD-[MODULE_NAME].pdf
```

---

### ⏱️ STEP 6: Done! Archive & Share (5 menit)

**Final output:**
```
✅ D:\OFFICE\PRD\expectations\PRD-REHAB_MEDIK.pdf
```

**Sekarang:**
1. ✉️ Share dengan stakeholders
2. 📤 Upload ke repository
3. 💾 Archive untuk reference

---

## 📋 Template vs Dynamic - Singkat

### TEMPLATE (Sama untuk Semua)
- Document structure
- Section headers
- Table formats
- Sign-off form
- Legal disclaimers

### DYNAMIC (Berbeda per Module)
- Module name
- Requirements (dari screenshots)
- User stories content
- Business logic
- Integration specs

**Result:** Consistent format + Unique content

---

## 🗂️ File Locations

| File | Purpose | Location |
|------|---------|----------|
| Brief | Input - Project info | `module/[MODULE]/brief.md` |
| Screenshots | Input - UI mockups | `screenshots/[MODULE]/001-NNN.png` |
| Stories | Generated content | `stories/[MODULE]/story-[N].md` |
| PRD Markdown | Compiled document | `exports/[MODULE]-PRD.md` |
| PRD PDF | FINAL OUTPUT | `expectations/PRD-[MODULE].pdf` |

---

## 📊 Workflow Visual

```
1. Brief File               HISv2/module/REHAB_MEDIK/brief.md
   + Screenshots            HISv2/screenshots/REHAB_MEDIK/001-025.png
   ↓
2. Generate Stories         HISv2/stories/REHAB_MEDIK/story-001-005.md
   ↓
3. Review Quality           HISv2/exports/REHAB_MEDIK-review.md
   ↓
4. Compile PRD              HISv2/exports/REHAB_MEDIK-PRD.md
   ↓
5. Export to PDF            expectations/PRD-REHAB_MEDIK.pdf ⭐
   ↓
6. Ready untuk Stakeholders ✅
```

---

## 🎯 Contoh Nyata: REHAB_MEDIK

**Input dibuat user (45 min total):**
```
1. Brief file + 10 sections .......... 20 min
2. Upload 25 screenshots ............ 15 min
3. Create metadata & folders ........ 10 min
```

**Sistem generate (65 min total):**
```
1. Generate 5 stories (7 min each) .. 35 min
2. Review quality ................... 10 min
3. Compile PRD ...................... 5 min
4. Export to PDF .................... 3 min
5. Archive & organize ............... 5 min
6. Misc time buffer ................. 7 min
```

**Total: ~2 jam**

**Output:**
```
D:\OFFICE\PRD\expectations\PRD-REHAB_MEDIK.pdf
(Professional, 100+ pages, ready for approval)
```

---

## ✅ Checklist Before Export

```
☑️ Brief file complete (10 sections filled)
☑️ Screenshots uploaded (sequential naming)
☑️ All stories generated (5 complete stories)
☑️ Review passed (no critical issues)
☑️ PRD markdown compiled (exports/ folder)
☑️ PDF exported (expectations/ folder)
☑️ Quality verified (50+ pages, all sections)
☑️ Ready for stakeholders ✅
```

---

## 📚 Related Docs

**Untuk details lebih:**
- `CARA_KERJA_SISTEM.md` - Detailed explanation
- `TEMPLATE_vs_DYNAMIC.md` - Break down setiap section
- `WORKFLOW_LENGKAP.md` - Complete step-by-step
- `FOLDER_STRUCTURE.md` - File organization

**Untuk reference:**
- `module/REHAB_MEDIK/brief.md` - Example brief
- `stories/REHAB_MEDIK/story-001.md` - Example story
- `exports/REHAB_MEDIK-PRD.md` - Example compiled PRD

---

## 🚀 Mulai Sekarang!

### Kamu perlu:
1. Module name (e.g., REHAB_MEDIK)
2. Screenshots (sequential, PNG format)
3. 15 menit untuk fill brief

### Then:
```
generate-story untuk [MODULE]
compile PRD untuk [MODULE]
export to PDF
DONE! ✅
```

---

## 💡 Key Takeaways

1. **2 Jam Waktu Total** - Dari brief → Professional PDF
2. **Automated** - System generate 80% dari content
3. **Professional** - Production-ready output
4. **Scalable** - Bisa buat banyak modules
5. **Consistent** - Same format, unique content

---

**Ready?** Start dengan Step 1! 🎉

Pertanyaan? Baca detailed docs atau check examples dalam `HISv2/` folder.

