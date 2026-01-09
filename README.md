# PRD-HIS-Generator

Sistem otomatis untuk generate Professional Product Requirements Documents (PRD) untuk Hospital Information System (HIS) modules.

## Overview

Platform yang memudahkan pembuatan PRD yang profesional dan konsisten dengan:
- Template structure yang terstandar
- Automated content generation dari screenshots
- Multi-module support
- Output format: PDF production-ready

## Quick Start

1. **Setup module baru:**
   ```bash
   # Create brief file
   module/[MODULE_NAME]/brief.md

   # Upload screenshots
   screenshots/[MODULE_NAME]/001.png, 002.png, ...
   ```

2. **Generate PRD:**
   ```bash
   generate-story untuk [MODULE_NAME]
   compile PRD untuk [MODULE_NAME]
   export to PDF
   ```

3. **Output:**
   ```
   expectations/PRD-[MODULE_NAME].pdf
   ```

## Folder Structure

```
HISv2/
├── AGENTS.md              # Command reference
├── CLAUDE.md              # Project instructions
├── .claude/
│   ├── commands/          # Agent command files
│   └── docs/              # Documentation
├── module/                # PRD briefs
├── stories/               # Generated user stories
├── screenshots/           # UI/UX screenshots
├── flowcharts/            # Flowchart files
├── exports/               # Compiled PRD markdown
└── expectations/          # Final PDF output
```

## Documentation

Semua dokumentasi ada di `.claude/docs/`:
- `QUICK_START_GUIDE.md` - Get started in 5 minutes
- `TEMPLATE_vs_DYNAMIC.md` - Understanding template & dynamic content
- `FOLDER_STRUCTURE.md` - File organization details
- `INDEX_DOKUMENTASI.md` - Complete documentation map

## Agents & Commands

### Available Commands
- **generate-story** - Generate user stories dari screenshots
- **review** - Quality check untuk PRD
- **list** - Show all modules & status

Lihat `AGENTS.md` untuk details lengkap.

## Requirements

- Brief file (10 sections per module)
- Screenshots (PNG, sequential naming: 001.png, 002.png, etc.)
- Pandoc atau Markdown PDF converter untuk export ke PDF

## Output Format

Setiap PRD terdiri dari:
- 10 bagian utama (Cover, Properties, Intro, Personas, Stories, Integration, Glossary, Appendix, Sign-off, Changelog)
- ~2000-5000 lines markdown
- Siap untuk approval stakeholders

## Timeline

Total waktu per PRD: **~2 jam**
- Setup: 30 min
- Generate stories: 30 min
- Review & Compile: 60 min
- Export: 5-10 min

## Status

- ✅ System setup complete
- ✅ Folder structure created
- ✅ Documentation ready
- 🔄 Ready untuk first module

## Author

Created for HIS V2 PRD documentation automation.

---

**Mulai dengan:** Baca `QUICK_START_GUIDE.md` di `.claude/docs/`
