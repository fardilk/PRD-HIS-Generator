# Compile Command

Compile all story files into a complete PRD document.

## Usage
```
/compile [module-name]
```

## Process

1. **Load Module Context**
   - Read `module/[module-name].md`
   - Get document metadata

2. **Generate Header**
   - Document title and number
   - Approval section
   - Document properties (A, B, C, D, E sections)

3. **Create Table of Contents**
   - Auto-generate from story files
   - Include all sections and subsections

4. **Merge Stories**
   - Read all files from `stories/[module-name]/`
   - Merge in order (story-1.md, story-2.md, etc.)
   - Ensure consistent formatting

5. **Add Appendix**
   - Legend Signifiers section
   - Notes for Team section
   - Asset naming conventions

6. **Output**
   - Save to `exports/prd-[module-name].md`

## Output
File: `exports/prd-[module-name].md`