# nWave — AI-Powered Wave Development for GitHub Copilot

You are operating with the **nWave methodology** for structured, wave-based software development.

**Orchestrate → Wave → Deliver.**

---

## What is nWave?

nWave is a disciplined AI workflow framework that orchestrates specialized agents through sequential development **waves**. Every feature follows a structured lifecycle from discovery to deployment, enforcing TDD, phase tracking, and deterministic validation at every step.

**Core mission**: Replace ad-hoc AI coding with a structured, auditable, wave-based methodology.

---

## The Wave Sequence

Every feature flows through these waves in order:

```
DISCOVER → DISCUSS → DESIGN → DEVOPS → DISTILL → DELIVER
```

| Wave | Command | Agent | Output |
|------|---------|-------|--------|
| DISCOVER | `/nw:discover` | product-discoverer | Evidence, opportunity validation |
| DISCUSS | `/nw:discuss` | product-owner | User stories, acceptance criteria |
| DESIGN | `/nw:design` | solution-architect | Architecture, component boundaries |
| DEVOPS | `/nw:devops` | platform-architect | Infrastructure, CI/CD, deployment |
| DISTILL | `/nw:distill` | acceptance-designer | BDD test scenarios (Given-When-Then) |
| DELIVER | `/nw:deliver` | software-crafter | Working code via Outside-In TDD |

**Cross-wave agents**: researcher, troubleshooter, documentarist, visual-architect  
**Peer reviewers**: 11 specialist review agents (one per wave + cross-cutting reviewers)

---

## All Available Commands

| Command | Purpose |
|---------|---------|
| `/nw:new` | Start a new feature wave sequence |
| `/nw:discover` | Run DISCOVER wave — validate opportunity and gather evidence |
| `/nw:discuss` | Run DISCUSS wave — produce user stories and acceptance criteria |
| `/nw:design` | Run DESIGN wave — produce architecture and component boundaries |
| `/nw:devops` | Run DEVOPS wave — produce infrastructure and CI/CD plan |
| `/nw:distill` | Run DISTILL wave — produce BDD test scenarios |
| `/nw:deliver` | Run DELIVER wave — implement via Outside-In TDD |
| `/nw:execute` | Execute a single task within the current phase |
| `/nw:continue` | Resume interrupted wave from last checkpoint |
| `/nw:review` | Run peer review against current wave output |
| `/nw:rigor` | Run exhaustive quality audit (ACID, security, concurrency) |
| `/nw:refactor` | Refactor code while keeping tests green |
| `/nw:research` | Deep research on a technical question |
| `/nw:document` | Generate or update documentation |
| `/nw:diagram` | Generate architecture or flow diagrams |
| `/nw:roadmap` | Produce a feature roadmap |
| `/nw:finalize` | Close out a wave, commit and update state |
| `/nw:fast-forward` | Skip to a specific wave (experienced users only) |
| `/nw:forge` | Bootstrap a new project from scratch |
| `/nw:mikado` | Apply Mikado method for safe large refactors |
| `/nw:mutation-test` | Run mutation testing to validate test suite strength |
| `/nw:root-why` | 5-Whys root cause analysis |

---

## Intent Mapping

Recognize these natural language patterns and map to commands:

| User Says | Command |
|-----------|---------|
| "start a new feature", "new wave", "begin" | `/nw:new` |
| "validate this idea", "is this worth building" | `/nw:discover` |
| "write user stories", "define requirements" | `/nw:discuss` |
| "design the architecture", "how should we structure this" | `/nw:design` |
| "set up CI/CD", "infrastructure plan" | `/nw:devops` |
| "write BDD scenarios", "acceptance tests" | `/nw:distill` |
| "implement it", "write the code", "start coding" | `/nw:deliver` |
| "continue", "resume", "where were we" | `/nw:continue` |
| "review this", "check quality" | `/nw:review` |
| "deep audit", "production quality check" | `/nw:rigor` |
| "refactor", "clean up code" | `/nw:refactor` |
| "research X", "find out about" | `/nw:research` |
| "document this", "update docs" | `/nw:document` |
| "draw a diagram", "show the architecture" | `/nw:diagram` |
| "plan the roadmap" | `/nw:roadmap` |
| "done with this wave", "finalize" | `/nw:finalize` |
| "why is this failing", "root cause" | `/nw:root-why` |
| "mutation test", "check test suite" | `/nw:mutation-test` |

---

## TDD 5-Phase Cycle (DELIVER wave)

When implementing via `/nw:deliver`, always follow this exact cycle:

1. **PREPARE** — Set up test fixtures and scaffolding
2. **RED_ACCEPTANCE** — Write failing acceptance test (BDD Given-When-Then)
3. **RED_UNIT** — Write failing unit tests for the implementation
4. **GREEN** — Write minimum code to make all tests pass
5. **COMMIT** — Refactor, verify no regressions, commit with conventional message

**STOP if you are:**
- Writing production code before a failing test exists
- Marking a phase complete without running the test suite
- Batching multiple tasks into a single commit
- Skipping the RED phase because the test "seems obvious"

---

## DES — Deterministic Execution System

nWave enforces deterministic behaviour through DES, which validates every agent step:

- **Pre-tool-use**: Validates the next action before it executes
- **Post-tool-use**: Validates the output after execution
- **Subagent-stop**: Validates agent hand-off between waves

DES enforces:
- Phase sequencing (cannot skip waves without `/nw:fast-forward`)
- TDD schema compliance (9 mandatory sections checked per phase)
- Stale execution detection (abandoned phases are flagged)
- Audit log of every agent action

---

## Wave Output Artefacts

Each wave produces structured artefacts stored in the project:

| Wave | Artefact |
|------|----------|
| DISCOVER | `docs/discovery/opportunity-{id}.md` |
| DISCUSS | `docs/stories/story-{id}.md` |
| DESIGN | `docs/architecture/design-{id}.md` |
| DEVOPS | `docs/devops/platform-{id}.md` |
| DISTILL | `tests/acceptance/scenarios-{id}.feature` |
| DELIVER | Source code + unit tests + commit |

---

## Project Conventions (nWave Projects)

### Commits
Conventional commits are **required**:
```
type(scope): subject
```
- `feat` → minor version bump
- `fix`, `perf`, `refactor` → patch bump
- `docs`, `test`, `ci`, `chore` → no release
- `BREAKING CHANGE:` in footer → major bump

### Code Style (Python projects)
- Python >= 3.10, type hints everywhere
- Ruff: line length 88, double quotes
- `snake_case` functions/vars, `PascalCase` classes, `UPPER_SNAKE` constants
- Zero shell scripts — all automation in Python

### Testing Layers
1. **Unit** — fast, isolated, one concern per test
2. **Integration** — real resource interaction
3. **Acceptance** — BDD Given-When-Then
4. **E2E** — complete workflow
5. **Mutation** — test suite effectiveness

### Coverage
- Minimum: 60% (CI will fail below this)
- Target: 95%+ for new code

---

## Key Files Reference

| File | Purpose |
|------|---------|
| `nWave/framework-catalog.yaml` | Central agent/command/quality-gate registry |
| `nWave/agents/` | 23 agent specifications |
| `nWave/tasks/nw/` | 21 slash command definitions |
| `nWave/skills/` | 98 agent skill files |
| `src/des/application/orchestrator.py` | DES core orchestration |
| `pyproject.toml` | Version source of truth |
| `CLAUDE.md` | Full developer reference |

---

## Development Commands

```bash
# Testing
pipenv run pytest                          # All tests
pipenv run pytest tests/des/unit/          # DES unit tests
pipenv run pytest -m unit                  # All unit tests
pipenv run pytest --cov                    # With coverage

# Linting
ruff check src/ scripts/ tests/
ruff format .
mypy src/des/

# Build & Install
python scripts/build_dist.py
python -m nwave_ai.cli install

# Docs
python scripts/docgen.py
```

---

## Critical Rules — NEVER:

- Skip a wave without explicit user confirmation and `/nw:fast-forward`
- Write code before tests exist (Outside-In TDD is mandatory in DELIVER)
- Use shell scripts — Python only for all automation
- Hardcode paths — always use `$HOME` or config-driven paths
- Proceed past a phase boundary without DES validation passing
- Overwrite audit logs
- Bump versions manually — semantic-release handles all versioning

---

## Getting Started

1. **New feature?** → Type `/nw:new <feature description>` or "start a new feature"
2. **Resume work?** → Type `/nw:continue` or "where were we"
3. **Ready to implement?** → You must have completed DISTILL wave first — then `/nw:deliver`
4. **Code review?** → `/nw:review` or `/nw:rigor` for exhaustive audit
5. **Something broken?** → `/nw:root-why` for 5-Whys analysis

---

## How to Install nWave

```bash
pip install nwave-ai
nwave install
```

This installs the full framework (agents, commands, DES hooks, skills, templates) into your project.
See the [nWave README](https://github.com/mikrobe/nWave) for full documentation.
