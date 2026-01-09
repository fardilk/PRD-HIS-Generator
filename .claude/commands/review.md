# Review Command

Review generated PRD stories for quality assurance.

## Usage
```
/review [module-name]
/review [module-name] [story-number]
```

## Checklist

### Structure
- [ ] Story header has complete metadata table
- [ ] Context paragraph is clear and concise
- [ ] Acceptance criteria are properly bulleted
- [ ] Flow notation is valid
- [ ] Steps are numbered sequentially

### Content
- [ ] User persona matches module definition
- [ ] JTBD is clearly stated
- [ ] All acceptance criteria are testable
- [ ] Flow covers all decision branches
- [ ] Screenshot instructions are detailed

### Completeness
- [ ] No missing steps in user journey
- [ ] All UI interactions are documented
- [ ] Edge cases are covered in acceptance criteria
- [ ] Error states are mentioned where applicable

### Consistency
- [ ] UI element names are consistent (bold)
- [ ] Terminology matches other stories
- [ ] Signifier format is correct

## Output
Report to console with:
- Pass/Fail status per checklist item
- Specific issues found
- Suggested fixes