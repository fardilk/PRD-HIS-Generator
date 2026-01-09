# Generate Story Command

Generate a single user story document for a PRD module.

## Usage
```
/generate-story [module-name] [story-number]
```

## Examples
```
/generate-story rehab-medik 1
/generate-story rehab-medik all
```

## Process

1. **Load Context**
   - Read `module/[module-name].md`
   - Get story details from User Stories table
   - Check for existing screenshots in `screenshots/[module-name]/`

2. **Analyze Requirements**
   - Identify user persona and their goals
   - Map out the user journey
   - Define acceptance criteria

3. **Generate Story Document**
   - Create story header with metadata table
   - Write context paragraph
   - List acceptance criteria
   - Create flow notation
   - Break down into steps with screenshot placeholders

4. **Output**
   - Save to `stories/[module-name]/story-[n].md`
   - Update `stories/todos.md`

## Output
File: `stories/[module-name]/story-[n].md`

## Notes
- Use `all` as story number to generate all stories in sequence
- If screenshots exist, reference them instead of placeholders
- If flowcharts exist, embed them instead of notation