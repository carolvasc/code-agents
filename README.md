# Code Agents

![Angular](https://img.shields.io/badge/Angular-15→19-red)
![AI Agents](https://img.shields.io/badge/AI-Agents-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-active-success)

Codex, Claude Code and GitHub Copilot custom agents for reviewing and modernizing Angular codebases.

This repository provides reusable agents focused on practical Angular modernization, template maintainability, accessibility, and component-level refactoring opportunities.

The agents were created from real-world usage in Angular projects that migrated from older versions to newer versions and need a safe, incremental way to adopt modern Angular features without unnecessary rewrites.

## ✨ What makes this different?

These agents are designed based on real-world Angular migration scenarios.

Instead of forcing modern Angular syntax everywhere, they help answer:

> 💡 “Is this change worth doing in this file, right now?”

**Focus areas:**
- ⚙️ Incremental modernization (Angular 15 → 19)
- 🧩 Maintainability over trends
- ♿ Accessibility-first mindset
- 🚀 Real performance impact (not micro-optimizations)

---

## 🎯 Why this exists

Many Angular codebases upgrade framework versions but do not immediately adopt newer patterns such as modern control flow, `@defer`, `@let`, standalone components, `inject()`, or signal-based APIs.

This repository helps teams answer a practical question:

> 💭 When I touch this file, is there an improvement opportunity that is actually worth applying now?

The goal is not to force new syntax everywhere.  
The goal is to support **scoped, high-signal reviews** that improve:

- readability
- maintainability
- accessibility
- performance

---

## 🤖 Included agents

| Agent | Purpose |
|------|---------|
| [`ng-template-reviewer`](./.github/agents/ng-template-reviewer/README.md) | Reviews Angular templates focusing on complexity, logic-heavy HTML, modern control flow (`@if`, `@for`), `@let`, `@defer` opportunities, self-closing tags, expensive bindings, and structural accessibility. |
| [`ng-component-reviewer`](./.github/agents/ng-component-reviewer/README.md) | Reviews Angular component classes for practical modernization (Angular 19), including standalone readiness, `inject()`, signal-based APIs (`input()`, `output()`, queries), state simplification, lazy-loading opportunities, and scoped refactor suggestions. |

---

## 🧠 Agents vs Skills

This repository currently starts with custom agents.

**Custom agents are best for:**
- 🔍 Specialized judgment
- 🧩 Focused diagnosis

Examples:
- review this Angular template
- assess modernization opportunity
- classify recommendations by risk

**Future skills will cover:**
- 🔁 Repeatable workflows
- 📋 Checklists and automation

Examples:
- local code review against `develop`/`main`
- Angular feature checklist
- Jest test authoring checklist
- bugfix verification workflow

**Model:**
- 🤖 Agents → diagnose
- 🧩 Skills → orchestrate
- 📘 Repo instructions → define rules

---

## 🗂️ Recommended repository structure

```text
.github/
  agents/
    ng-template-reviewer.agent.md
    ng-component-reviewer.agent.md

agents/
  ng-template-reviewer/
    README.md
    ng-template-reviewer.agent.md
  ng-component-reviewer/
    README.md
    ng-component-reviewer.agent.md

README.md
LICENSE
```

You can keep the distributable agent files under `agents/<agent-name>/` and copy them into `.github/agents/` in the target repository.

---

## ⚙️ Installation

### Option 1: Manual installation

Copy the desired `.agent.md` file into the target repository:

```text
.github/agents/<agent-name>.agent.md
```

Example:

```text
.github/agents/ng-template-reviewer.agent.md
.github/agents/ng-component-reviewer.agent.md
```

Commit the files to the repository default branch.

---

### Option 2: Repository-level usage

If you want the agents available only in a specific Angular project, add them directly to that project's `.github/agents/` directory.

---

### Option 3: Organization-level usage

For organization-wide usage, adapt the files to your organization's Copilot custom agent setup and governance model.

---

## 🧪 Usage examples

### Review an Angular template

```text
Use the ng-template-reviewer agent on this component template.
Focus on template complexity, @if/@for quality, @let opportunities, @defer candidates, self-closing tags, expensive bindings, and structural accessibility.
Do not modify code. Return findings grouped by adoption timing.
```

### Review an Angular component class

```text
Use the ng-component-reviewer agent on this component class.
Focus on standalone value, inject() migration value, signal input/output/query opportunities, signals/computed state, and realistic modernization for this file.
Do not modify code.
```

---

## 🧩 Design principles

These agents follow a few core principles:

1. 🧠 **Diagnosis first**  
   Do not modify files unless explicitly instructed.

2. 🧱 **Stable Angular only**  
   Focus on stable features through Angular 19.

3. 🚫 **No modernization for novelty**  
   Newer APIs are not always better.

4. ⚡ **Opportunistic modernization**  
   Improve files that are already being touched.

5. 🎯 **Scope control**  
   Separate “do now” vs “backlog”.

6. ♿ **Accessibility and maintainability first**  
   Prioritize clarity and usability over syntax.

---

## 🧭 Suggested global Copilot instructions

For Angular repositories, consider adding this to your `AGENTS.md`:

```md
# Angular modernization policy

- Prefer stable Angular features only.
- Favor opportunistic modernization in files already being changed.
- Do not force syntax migrations without a clear readability, maintenance, accessibility, or performance gain.
- Keep refactors scoped to the current task unless explicitly asked otherwise.
- Accessibility and testability take precedence over stylistic modernization.
- By default, reviewers should diagnose first and avoid changing files unless explicitly instructed.
```

---

## 🤝 Contributing

Contributions are welcome.

Good contributions include:

- ✨ new Angular-focused agents
- 🔍 refinements to review criteria
- 📄 examples of prompts and outputs
- 🎨 PO-UI-specific review rules
- ♿ accessibility improvements
- 🔁 skills for repeatable Angular workflows