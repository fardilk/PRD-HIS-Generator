# Agent Definitions

## Primary Agent: PRD Writer

### Role
Generate comprehensive Product Requirement Documentation based on module context, user stories, and UI references.

### Behavior

1. **Analyze Module Context**
   - Read module definition from `module/[module-name].md`
   - Understand the feature scope and user personas
   - Identify all user stories to be documented

2. **Structure Each Story**
   - Create metadata table (User Persona, JTBD, References)
   - Write context paragraph explaining the story
   - Define User Acceptance Criteria (bullet points)
   - Create User Flow in flowchart notation
   - Break down into numbered steps with screenshot placeholders

3. **Generate Acceptance Criteria**
   - Each criteria must be testable
   - Use clear conditional language (if/when/then)
   - Cover happy path and edge cases
   - Include UI element references

4. **Create Flow Notation**
   - Use standard notation: `[Action]`, `{Decision?}`, `→`
   - Branch decisions with `→ [Yes]` and `→ [No]`
   - Always start with `[Start]` and end with `[END]`

5. **Document Steps**
   - Each step = one user action or system response
   - Include screenshot placeholder with detailed instructions
   - Reference UI elements by name (bold)

### Output Quality Checks
- [ ] All user personas are defined
- [ ] Each story has complete metadata table
- [ ] Acceptance criteria are testable
- [ ] Flow notation is valid and complete
- [ ] Every step has screenshot instructions
- [ ] Screenshot instructions are detailed enough for capture

---

## Secondary Agent: PRD Reviewer

### Role
Review generated PRD for completeness, consistency, and clarity.

### Checklist

#### Structure
- [ ] Document header is complete
- [ ] All stories follow template structure
- [ ] Tables are properly formatted
- [ ] Signifiers are correctly placed

#### Content
- [ ] User personas are consistent throughout
- [ ] Acceptance criteria are complete and testable
- [ ] Flow matches the steps described
- [ ] No missing steps or gaps in user journey
- [ ] Screenshot instructions are actionable

#### Consistency
- [ ] Terminology is consistent
- [ ] Button/menu names match across stories
- [ ] Numbering is sequential
- [ ] Cross-references are valid

---

## Tertiary Agent: PRD Compiler

### Role
Compile individual story files into a complete PRD document.

### Process
1. Generate document header with metadata
2. Create Table of Contents
3. Merge all story files in order
4. Add Appendix (Legend Signifiers, Notes for Team)
5. Output to `exports/prd-[module-name].md`