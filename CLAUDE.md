# PRD Generator - Hospital Information System V2

## Project Overview
Workspace for generating Product Requirement Documentation (PRD) for HIS V2 modules in Markdown format.

## Directory Structure
```
PRD/
├── AGENTS.md          # Agent behaviors & roles
├── CLAUDE.md          # This file - project instructions
├── exports/           # Final PRD documents (.md)
├── module/            # Module definitions & context
│   └── README.md      # Module registry
├── screenshots/       # UI screenshots organized by module
├── flowcharts/        # Flow diagrams organized by module
└── stories/           # Generated story documents
    └── todos.md       # Task queue
```

## Document Structure Standards

### PRD Header Template
```markdown
# [Document Title]
## [Module Name] - Primaya Hospital Group
**[Document Number]**

---

| Field | Value |
|-------|-------|
| Nama Dokumen | [Full Document Name] |
| Penanggung Jawab Proyek | [Project Manager] |
| Nama Proyek | Hospital Information System (HIS) V2 |
| Nama Institusi | Rumah Sakit Primaya Hospital Group |
```

### Story Template
```markdown
## Story #[N]: [Story Title]

| Field | Value |
|-------|-------|
| User Persona | [Persona] |
| Jobs to be Done | [JTBD Description] |
| Referensi UI | `[INSERT_FIGMA_LINK]` |
| Flow Reference | [Flow Name] |

[Context paragraph]

### User Acceptance Criteria
- [Criteria 1]
- [Criteria 2]
...

### User Flow
> **📊 FLOWCHART REQUIRED**
> 
> ```
> [Step 1] → [Step 2] → [Step 3] → [END]
> ```

---

### Step [N]: [Step Title]

[Step description]

> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Description]`
> 
> **Instruksi screenshot**: [Detailed instructions]
```

### Signifiers (Placeholders)

#### Flowchart Placeholder
```markdown
> **📊 FLOWCHART REQUIRED**
> 
> Buat flowchart dengan alur berikut menggunakan tools seperti Draw.io, Lucidchart, atau Figma:
> 
> ```
> [Start] → [Step 1] → [Step 2] → {Decision?}
>   → [Yes] → [Action A] → [END]
>   → [No] → [Action B] → [END]
> ```
```

#### Screenshot Placeholder
```markdown
> **🖼️ SCREENSHOT REQUIRED**
> 
> `[INSERT_SCREENSHOT: Brief description]`
> 
> **Instruksi screenshot**: Detailed description of elements that must be visible in the screenshot.
```

#### Figma Link Placeholder
```markdown
| Referensi UI | `[INSERT_FIGMA_LINK]` |
```

### Tables

#### Metadata Table
```markdown
| Field | Value |
|-------|-------|
| User Persona | [Value] |
| Jobs to be Done | [Value] |
```

#### Timeline Table
```markdown
| No. | Pekerjaan | Modul | Estimasi |
|-----|-----------|-------|----------|
| 1. | [Task] | [Module] | [Days] |
```

#### Document History Table
```markdown
| Versi | Tanggal | Deskripsi | Direvisi Oleh |
|-------|---------|-----------|---------------|
| 1.0 | [Date] | [Description] | [Author] |
```

## Workflow

1. **Context Setup**: Create module context in `module/[module-name].md`
2. **Define Stories**: List all user stories with personas and JTBD
3. **Generate**: Run `/generate-story [module-name] [story-number]`
4. **Add Assets**: Place screenshots in `screenshots/[module-name]/`
5. **Add Flowcharts**: Place flowcharts in `flowcharts/[module-name]/`
6. **Review**: Run `/review [module-name]`
7. **Compile**: Run `/compile [module-name]` to merge all stories into final PRD

## Naming Conventions

### Files
- Module context: `module/[module-name].md` (kebab-case)
- Story files: `stories/[module-name]/story-[n].md`
- Final PRD: `exports/prd-[module-name].md`

### Assets
- Screenshots: `ss_story[n]_step[n]_[description].png`
- Flowcharts: `flow_story[n]_[description].png`

### Document Numbers
Format: `[NUMBER]/[MODULE-CODE]/PRD/PHG/[MONTH-ROMAN]/[YEAR]`
Example: `668/REHAB-MEDIK/PRD/PHG/XII/2025`

## User Personas Reference
Common personas used in HIS V2:
- **Pasien**: Patient receiving medical services
- **Dokter**: Doctor/physician performing diagnosis and evaluation
- **Perawat**: Nurse handling patient care documentation
- **Fisioterapis**: Physiotherapist (logs in as Perawat role)
- **Admin**: Administrative staff

## Language
- Primary: Bahasa Indonesia
- Technical terms: Keep in English where appropriate (SOAP, QR Code, etc.)