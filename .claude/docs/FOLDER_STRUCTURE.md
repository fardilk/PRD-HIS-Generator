# PRD Folder Structure - Complete Hierarchy

**Generated:** 2026-01-10
**Status:** ✅ Complete

---

## 📁 Full Directory Tree

```
PRD/
│
├── 📄 AGENTS.md                              ← All available agents & commands
├── 📄 CLAUDE.md                              ← Original project instructions
├── 📄 CLAUDE_NEW.md                          ← NEW: Modular project instructions ⭐
├── 📄 README.md                              ← System overview
├── 📄 EXPECTATIONS.md                        ← System specifications
├── 📄 SYSTEM_SUMMARY.md                      ← Complete system documentation
├── 📄 NEW_STRUCTURE_SUMMARY.md               ← What changed in v2.0
├── 📄 FOLDER_STRUCTURE.md                    ← This file
│
├── 📁 .claude/
│   └── 📁 commands/
│       ├── 📄 generate-story.md              ← Agent: Generate story from images
│       ├── 📄 review.md                      ← Agent: Quality review
│       └── 📁 module/
│           ├── 📄 create.md                  ← Agent: Create module (planned)
│           └── 📄 list.md                    ← Agent: List all modules
│
├── 📁 module/                                ← Module registry & briefs
│   ├── 📄 README.md                          ← Master registry of all projects
│   │
│   ├── 📁 REHAB_MEDIK/                       ← Example: COMPLETE ✅
│   │   ├── 📄 brief.md                       ← 10-section module brief
│   │   ├── 📄 metadata.json                  ← Module metadata
│   │   └── 📄 todos.md                       ← Progress tracking
│   │
│   ├── 📁 MOBILE_BANKING/                    ← Example: IN PROGRESS 🟡
│   │   ├── 📄 brief.md                       ← To be created
│   │   ├── 📄 metadata.json                  ← To be created
│   │   └── 📄 todos.md                       ← To be created
│   │
│   ├── 📁 E_COMMERCE/                        ← Example: PLANNED 🔵
│   │   ├── 📄 brief.md                       ← To be created
│   │   ├── 📄 metadata.json                  ← To be created
│   │   └── 📄 todos.md                       ← To be created
│   │
│   └── 📁 LAB_MANAGEMENT/                    ← Example: PLANNED 🔵
│       ├── 📄 brief.md                       ← To be created
│       ├── 📄 metadata.json                  ← To be created
│       └── 📄 todos.md                       ← To be created
│
├── 📁 stories/                               ← Generated user stories
│   ├── 📄 todos.md                           ← Master progress tracker (all modules)
│   │
│   ├── 📁 REHAB_MEDIK/
│   │   ├── 📄 story-001.md                   ← Pasien Konsul (Ready to generate)
│   │   ├── 📄 story-002.md                   ← Pelaksanaan Fisioterapi
│   │   ├── 📄 story-003.md                   ← Tidak Hadir
│   │   ├── 📄 story-004.md                   ← Akhiri Sesi
│   │   └── 📄 story-005.md                   ← Evaluasi Dokter
│   │
│   ├── 📁 MOBILE_BANKING/                    ← Empty (generate stories here)
│   │   └── 📄 story-[N].md                   ← To be generated
│   │
│   ├── 📁 E_COMMERCE/                        ← Empty (generate stories here)
│   │   └── 📄 story-[N].md                   ← To be generated
│   │
│   └── 📁 LAB_MANAGEMENT/                    ← Empty (generate stories here)
│       └── 📄 story-[N].md                   ← To be generated
│
├── 📁 screenshots/                           ← UI mockups (organized by module)
│   ├── 📁 REHAB_MEDIK/
│   │   ├── 🖼️ 001.png                        ← Story 1, Step 1
│   │   ├── 🖼️ 002.png                        ← Story 1, Step 2
│   │   ├── 🖼️ 003.png                        ← Story 1, Step 3
│   │   ├── 🖼️ 004.png                        ← Story 1, Flowchart
│   │   └── 🖼️ ...025.png                     ← Up to 25 images
│   │
│   ├── 📁 MOBILE_BANKING/                    ← Add screenshots here
│   │   ├── 🖼️ 001.png
│   │   └── 🖼️ ...NNN.png
│   │
│   ├── 📁 E_COMMERCE/                        ← Add screenshots here
│   │   └── 🖼️ images...
│   │
│   └── 📁 LAB_MANAGEMENT/                    ← Add screenshots here
│       └── 🖼️ images...
│
├── 📁 flowcharts/                            ← Flowchart diagrams (organized by module)
│   ├── 📁 REHAB_MEDIK/
│   │   ├── 📊 flow-story-1.png               ← Story 1 process flow
│   │   ├── 📊 flow-story-2.png               ← Story 2 process flow
│   │   └── 📊 ...
│   │
│   ├── 📁 MOBILE_BANKING/                    ← Add flowcharts here
│   │   └── 📊 flow-[story].png
│   │
│   ├── 📁 E_COMMERCE/                        ← Add flowcharts here
│   │   └── 📊 flow-[story].png
│   │
│   └── 📁 LAB_MANAGEMENT/                    ← Add flowcharts here
│       └── 📊 flow-[story].png
│
├── 📁 exports/                               ← Final PRD documents (output)
│   ├── 📄 REHAB_MEDIK-PRD.md                 ← Final compiled PRD (Ready to generate)
│   ├── 📄 REHAB_MEDIK-review.md              ← Quality review report
│   ├── 📄 MOBILE_BANKING-PRD.md              ← To be generated
│   ├── 📄 MOBILE_BANKING-review.md           ← To be generated
│   ├── 📄 E_COMMERCE-PRD.md                  ← To be generated
│   ├── 📄 E_COMMERCE-review.md               ← To be generated
│   ├── 📄 LAB_MANAGEMENT-PRD.md              ← To be generated
│   └── 📄 LAB_MANAGEMENT-review.md           ← To be generated
│
├── 📁 command/ (legacy - keep for reference)
│   ├── 📄 GENERATE_PRD_FROM_IMAGES.md
│   ├── 📄 WORKFLOW_SUMMARY.md
│   ├── 📄 README.md
│   ├── 📁 brief/
│   │   ├── 📄 _TEMPLATE_brief.md
│   │   └── 📄 REHAB_MEDIK_PRIMAYA.md
│   └── 📁 images/
│       └── 📁 REHAB_MEDIK_PRIMAYA/
│           └── (25 images referenced)
│
├── 📁 STORIES/ (legacy - keep for reference)
│   └── 📄 _TEMPLATE.md
│
├── 📁 FORMS/ (legacy - keep for reference)
│   └── 📄 _TEMPLATE.md
│
└── 📁 HISv2/ (original export folder)
    └── (exported files)
```

---

## 📊 Legend

| Symbol | Meaning |
|--------|---------|
| 📄 | Markdown file (.md) |
| 📁 | Folder/Directory |
| 🖼️ | Image file (.png, .jpg) |
| 📊 | Diagram/Flowchart file |
| ✅ | Complete/Done |
| 🟡 | In Progress |
| 🔵 | Planned/Pending |
| ⭐ | New/Important |

---

## 🎯 Key Folders Explained

### `.claude/commands/`
**Purpose:** Agent instruction files
**Contains:** Command definitions & processing logic
**Access:** Referenced by agents

### `module/`
**Purpose:** Module configuration & metadata
**Contains:** Per-module briefs, status, progress tracking
**Per Module:**
- `brief.md` - 10-section project brief
- `metadata.json` - Project metadata
- `todos.md` - Progress tracking

### `stories/`
**Purpose:** Generated user story documents
**Contains:** Completed stories with all 13 sections
**Organization:** By module name
**Master File:** `todos.md` (all modules progress)

### `screenshots/`
**Purpose:** UI mockups organized by project
**Contains:** Sequential images (001.png, 002.png...)
**Organization:** By module name
**Usage:** Source for story generation

### `flowcharts/`
**Purpose:** Process flow diagrams
**Contains:** Flow diagrams per story
**Organization:** By module name
**Usage:** Visual reference for story documentation

### `exports/`
**Purpose:** Final PRD documents ready for stakeholders
**Contains:** Compiled PRDs & review reports
**Organization:** By module name
**Files:**
- `[MODULE]-PRD.md` - Final compiled PRD
- `[MODULE]-review.md` - Quality assurance report

---

## 📝 File Organization Pattern

### Each Module Follows This Pattern:

```
module/[MODULE_NAME]/
├── brief.md              (10 sections - required to start)
├── metadata.json         (Auto-generated/updated)
└── todos.md             (Progress tracking)

screenshots/[MODULE_NAME]/
├── 001.png
├── 002.png
└── ...NNN.png           (Sequential naming required)

stories/[MODULE_NAME]/
├── story-001.md         (Generated from agent command)
├── story-002.md
└── story-[N].md

exports/
├── [MODULE_NAME]-PRD.md (Final compiled document)
└── [MODULE_NAME]-review.md (Quality report)
```

---

## ✅ Current Status

### Folders Created: ✅
- [x] `.claude/commands/` - Agent commands folder
- [x] `module/` - Module registry folder
- [x] `stories/` - Stories folder with master todos.md
- [x] `screenshots/` - Screenshots folder (empty, ready for images)
- [x] `flowcharts/` - Flowcharts folder (empty, ready for diagrams)
- [x] `exports/` - Final PRD output folder (empty, ready for output)

### Modules Setup: ✅
- [x] `module/REHAB_MEDIK/` - Complete module structure
- [x] `module/MOBILE_BANKING/` - Empty folder ready
- [x] `module/E_COMMERCE/` - Empty folder ready
- [x] `module/LAB_MANAGEMENT/` - Empty folder ready

### Stories Folders: ✅
- [x] `stories/REHAB_MEDIK/` - Ready for generated stories
- [x] `stories/MOBILE_BANKING/` - Ready for generated stories
- [x] `stories/E_COMMERCE/` - Ready for generated stories
- [x] `stories/LAB_MANAGEMENT/` - Ready for generated stories

### Command Agents: ✅
- [x] `.claude/commands/generate-story.md` - Story generation agent
- [x] `.claude/commands/review.md` - Review agent
- [x] `.claude/commands/module/list.md` - List modules agent

---

## 🚀 How to Use Structure

### To Start New Module:
```
1. Create folder: module/[YOUR_MODULE]/
2. Add brief.md: module/[YOUR_MODULE]/brief.md (10 sections)
3. Add metadata.json: module/[YOUR_MODULE]/metadata.json
4. Add screenshots: screenshots/[YOUR_MODULE]/*.png
5. Add flowcharts: flowcharts/[YOUR_MODULE]/*.png
6. Generate stories: generate-story untuk [YOUR_MODULE]
7. Output saved: stories/[YOUR_MODULE]/story-[N].md
```

### To Review Module:
```
1. After generating all stories
2. Run: review untuk [YOUR_MODULE]
3. Output: exports/[YOUR_MODULE]-review.md
4. Fix any issues
5. Ready to compile
```

### To Export PRD:
```
1. After passing review
2. Run: compile PRD untuk [YOUR_MODULE]
3. Output: exports/[YOUR_MODULE]-PRD.md
4. Ready for stakeholder distribution
```

---

## 📂 Storage Capacity

**Current Structure:**
- Total folders: 20+
- Total files: 50+
- Templates: 5+
- Example modules: 4

**Scalable to:**
- 50+ modules
- 200+ stories
- 1000+ images
- Unlimited PRDs

---

## 🔄 File References

### Most Important Files:
1. `CLAUDE_NEW.md` - ⭐ START HERE for instructions
2. `AGENTS.md` - Available commands
3. `module/README.md` - Module registry
4. `.claude/commands/generate-story.md` - Story generation help

### Reference Files:
5. `.claude/commands/review.md` - Review process
6. `.claude/commands/module/list.md` - Module listing
7. `stories/todos.md` - Master progress tracker

### Legacy Files (keep for reference):
8. `README.md` - Original system overview
9. `EXPECTATIONS.md` - System specifications
10. `command/` folder - Original image-to-PRD system

---

## ✨ You Now Have:

✅ **Complete folder structure** organized by module
✅ **Ready-to-use agent system** with command files
✅ **4 example modules** with proper structure
✅ **Progress tracking** at master & module level
✅ **Clear separation** of content types
✅ **Scalable system** ready for growth
✅ **Professional organization** enterprise-ready

---

## 🚀 Quick Reference

| Need | Location |
|------|----------|
| Project instructions | `CLAUDE_NEW.md` |
| All agents | `AGENTS.md` |
| Module registry | `module/README.md` |
| Generate story | `.claude/commands/generate-story.md` |
| Review PRD | `.claude/commands/review.md` |
| All stories progress | `stories/todos.md` |
| Add screenshots | `screenshots/[MODULE]/` |
| Add flowcharts | `flowcharts/[MODULE]/` |
| Export PRD | `exports/[MODULE]-PRD.md` |

---

**Status:** ✅ **FOLDER STRUCTURE COMPLETE**

All folders created and ready for use!

Next: Start generating PRD content using the agent commands.

