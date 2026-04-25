# ng-template-reviewer

Angular template review agent focused on **readability, maintainability, accessibility, and modern Angular features**.

---

## Purpose

Helps identify when Angular templates:

- are too complex
- contain too much logic
- are hard to read or maintain
- could benefit from modern Angular features (when it makes sense)

---

## What it analyzes

### Structure
- template size and complexity
- nested conditions and rendering branches
- repeated fragments

### Logic in HTML
- long boolean expressions
- chained ternaries
- repeated async pipe usage
- logic that should be in the component

### Modern Angular features
- `@if`, `@for`, `@switch`
- `@let`
- `@defer`
- `@empty`

### Performance
- expensive bindings
- repeated expressions
- unnecessary DOM churn

### Accessibility
- semantic HTML
- headings hierarchy
- proper interactive elements
- form structure
- focus and dynamic content behavior

### Template hygiene
- self-closing tags
- unnecessary wrappers
- `ng-container` usage

---

## When to use

- Before committing a component
- After upgrading Angular
- When template feels “messy”
- When reviewing PRs
- When introducing modern Angular features

---

## Example usage

```text
Use the ng-template-reviewer agent on this template.
Do not modify code.
Return findings grouped by:
- severity
- adoption timing (now / later / backlog)

Output structure: 
- Summary
- Findings (severity + explanation + suggestion)
- Modern Angular opportunities
- Refactor options
- Scope control

Philosophy:
- No forced modernization
- No unnecessary refactors
- Prefer small improvements
- Optimize for readability first
- Only suggest changes with real value
```

## Installation
```code
.github/agents/ng-template-reviewer.agent.md
```