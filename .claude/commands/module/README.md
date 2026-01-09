# Module Registry

## Module Context File Format

Each module must have a `[module-name].md` file in this folder with the following structure:
```markdown
# [Module Name]

## Document Info
| Field | Value |
|-------|-------|
| Document Number | [XXX/MODULE-CODE/PRD/PHG/MM/YYYY] |
| Document Title | [Full Title] |
| Project Manager | [Name] |
| Document Editor | [Name] |
| Version | [X.X] |
| Status | [Draft/Review/Approved] |

## Overview
[Brief description of the module and its purpose in HIS V2]

## User Personas
| Persona | Description | System Role |
|---------|-------------|-------------|
| [Name] | [Description] | [Login Role] |

## User Stories
| # | Story Title | Persona | Priority |
|---|-------------|---------|----------|
| 1 | [Title] | [Persona] | [High/Medium/Low] |
| 2 | [Title] | [Persona] | [High/Medium/Low] |

## Key Features
- [Feature 1]
- [Feature 2]

## Technical Notes
- [Note 1]
- [Note 2]

## Figma References
- Main Design: `[FIGMA_LINK]`
- Components: `[FIGMA_LINK]`
```

---

## Registered Modules

| Module Name | Document Number | Stories | Status | Last Updated |
|-------------|-----------------|---------|--------|--------------|
| rehab-medik | 668/REHAB-MEDIK/PRD/PHG/XII/2025 | 5 | Draft | 03-12-2025 |

---

## How to Add New Module

1. Create file `module/[module-name].md` with format above
2. Create folders:
   - `screenshots/[module-name]/`
   - `flowcharts/[module-name]/`
   - `stories/[module-name]/`
3. Update the table above
4. Run `/generate-story [module-name] [story-number]` for each story
5. Run `/compile [module-name]` to generate final PRD