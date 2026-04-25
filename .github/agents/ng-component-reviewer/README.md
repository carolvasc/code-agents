# ng-component-reviewer

Angular component review agent focused on **modernization, state modeling, and maintainability**.

---

## Purpose

Helps evaluate whether a component should adopt modern Angular patterns safely and incrementally.

---

## What it analyzes

### Modernization opportunities
- standalone components
- `inject()`
- `input()`, `output()`
- signal-based APIs
- signal queries

### State modeling
- derived state complexity
- duplicated booleans
- unclear state structure
- opportunities for `computed()`

### Component design
- class size and responsibilities
- readability and naming
- logic leaking into template

### Rendering mindset
- predictable state
- unnecessary imperative logic
- simplification opportunities

### Performance & loading
- lazy loading candidates
- defer-readiness

---

## When to use

- Reviewing Angular components
- After Angular upgrade
- Before refactoring
- When template is too complex (state problem)
- When introducing signals

---

## Example usage

```text
Use the ng-component-reviewer agent on this component.
Do not modify code.
Focus on modernization and state simplification.

Output structure:
- Summary (modernization score + risk)
- Findings
- Modern Angular candidates
- Refactor options
- Scope control

Philosophy:
- Prefer stable Angular features
- Avoid unnecessary migrations
- Favor incremental changes
- Improve readability first
- Reduce cognitive load
```

## Installation
```code
.github/agents/ng-component-reviewer.agent.md
```