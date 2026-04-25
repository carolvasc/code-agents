# Repository README

````md
# Code Agents

GitHub Copilot, Codex and Claude Code custom agents for reviewing and modernizing Angular codebases.

This repository provides reusable Copilot agents focused on practical Angular modernization, template maintainability, accessibility, and component-level refactoring opportunities.

The agents were created from real-world usage in Angular projects that migrated from Angular 15 to newer versions and need a safe, incremental way to adopt modern Angular features without unnecessary rewrites.

## Why this exists

Many Angular codebases upgrade framework versions but do not immediately adopt newer patterns such as modern control flow, `@defer`, `@let`, standalone components, `inject()`, or signal-based APIs.

This repository helps teams answer a practical question:

> When I touch this file, is there a modernization opportunity that is actually worth applying now?

The goal is not to force new syntax everywhere. The goal is to support scoped, high-signal reviews that improve maintainability, accessibility, readability, and performance.

## Included agents

| Agent | Purpose |
|---|---|
| [`ng-template-reviewer`](./agents/ng-template-reviewer/README.md) | Reviews Angular templates for complexity, logic-heavy HTML, modern control flow, `@defer`, `@let`, self-closing tags, expensive bindings, and structural accessibility. |
| [`ng-component-reviewer`](./agents/ng-component-reviewer/README.md) | Reviews Angular component classes for practical modernization through Angular 19, including standalone readiness, `inject()`, signal-based APIs, state simplification, lazy-loading candidates, and scoped refactor opportunities. |

## Agents vs Skills

This repository currently starts with custom agents.

Custom agents are best for specialized judgment and focused diagnosis. For example:

- review this Angular template
- assess whether this component is a good candidate for modernization
- classify recommendations by risk and adoption timing

Future skills will be added for repeatable workflows. For example:

- local code review against `develop` or `main`
- Angular feature checklist
- Jest test authoring checklist
- bugfix verification workflow

The intended model is:

- **Agents** diagnose specialized areas
- **Skills** orchestrate repeatable workflows
- **Repository instructions** define global project rules

## Recommended repository structure

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
````

You can keep the distributable agent files under `agents/<agent-name>/` and copy them into `.github/agents/` in the target repository.

## Installation

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

### Option 2: Repository-level usage

If you want the agents available only in a specific Angular project, add them directly to that project's `.github/agents/` directory.

### Option 3: Organization-level usage

For organization-wide usage, adapt the files to your organization's Copilot custom agent setup and governance model.

## Usage examples

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

## Design principles

These agents follow a few core principles:

1. **Diagnosis first**
   By default, agents should not modify files unless explicitly instructed.

2. **Stable Angular only**
   Recommendations should focus on stable Angular features through Angular 19.

3. **No modernization for novelty**
   A newer Angular API is not automatically better for every file.

4. **Opportunistic modernization**
   Prefer improvements in files already being changed.

5. **Scope control**
   Recommendations should distinguish between what is worth doing now and what belongs in the backlog.

6. **Accessibility and maintainability matter**
   Accessibility, clarity, and testability take priority over cosmetic syntax changes.

## Suggested global Copilot instructions

For Angular repositories, consider adding this to your `AGENTS.md` or Copilot custom instructions:

```md
# Angular modernization policy

- Prefer stable Angular features only.
- Favor opportunistic modernization in files already being changed.
- Do not force syntax migrations without a clear readability, maintenance, accessibility, or performance gain.
- Keep refactors scoped to the current task unless explicitly asked otherwise.
- Accessibility and testability take precedence over stylistic modernization.
- By default, reviewers should diagnose first and avoid changing files unless explicitly instructed.
```

## Contributing

Contributions are welcome.

Good contributions include:

* new Angular-focused agents
* refinements to review criteria
* examples of prompts and outputs
* PO-UI-specific review rules
* accessibility-focused improvements
* skills for repeatable Angular workflows

## License

MIT

````