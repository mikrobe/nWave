# nWave — AI-Powered Wave Development for GitHub Copilot

You are operating with the **nWave methodology** for structured, wave-based software development.
All guidance lives in the `/nWave/` directory of this repository. You are doc-driven: read the
documents, adopt the agent roles, follow the command specs, apply the skills, and produce
artefacts using the templates. There is nothing to install or execute.

> **Start here**: Read [`/nWave/README.md`](/nWave/README.md) for a full overview of the framework
> before doing anything else in an unfamiliar project.

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

**Cross-wave agents**: researcher, troubleshooter, documentarist  
**Peer reviewers**: one reviewer agent per specialist role (see `/nWave/agents/`)

---

## All Available Commands

| Command | Purpose |
|---------|---------|
| `/nw:new` | Start a new feature wave sequence |
| `/nw:discover` | DISCOVER wave — validate opportunity, gather evidence |
| `/nw:discuss` | DISCUSS wave — produce user stories and acceptance criteria |
| `/nw:design` | DESIGN wave — produce architecture and component boundaries |
| `/nw:devops` | DEVOPS wave — produce infrastructure and CI/CD plan |
| `/nw:distill` | DISTILL wave — produce BDD test scenarios |
| `/nw:deliver` | DELIVER wave — implement via Outside-In TDD |
| `/nw:execute` | Execute a single task within the current wave |
| `/nw:continue` | Resume an interrupted wave from last checkpoint |
| `/nw:review` | Run peer review against current wave output |
| `/nw:rigor` | Exhaustive quality audit (correctness, security, concurrency) |
| `/nw:refactor` | Refactor code while keeping all tests green |
| `/nw:research` | Deep research on a technical question |
| `/nw:document` | Generate or update documentation |
| `/nw:diagram` | Generate architecture or flow diagrams |
| `/nw:roadmap` | Produce a feature roadmap |
| `/nw:finalize` | Close out a wave, commit and update state |
| `/nw:fast-forward` | Skip to a specific wave (requires explicit user confirmation) |
| `/nw:forge` | Bootstrap a new project from scratch |
| `/nw:mikado` | Apply Mikado method for safe large refactors |
| `/nw:mutation-test` | Validate test suite effectiveness |
| `/nw:root-why` | 5-Whys root cause analysis |

---

## Intent Mapping

Recognize natural language and map to the correct command:

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
| "check my tests", "mutation test" | `/nw:mutation-test` |

---

## How to Execute Any Wave (Doc-Driven Protocol)

For every wave or command request, follow this exact reading order:

1. **Read the command spec** — open `/nWave/tasks/nw/<command>.md` and follow it precisely.
2. **Adopt the agent role** — read the matching agent in `/nWave/agents/nw-<agent-name>.md` to
   understand its mindset, responsibilities, and output standards.
3. **Apply relevant skills** — before producing output, consult the corresponding skill folder
   at `/nWave/skills/<agent-name>/` to ensure rigor, completeness, and edge-case coverage.
4. **Use the right template** — structure all artefacts using the closest template from
   `/nWave/templates/`. Never invent output structure.
5. **Check shared rules** — always honour `/nWave/data/wizard-shared-rules.md` which defines
   cross-wave constraints all agents must respect.
6. **Consult methodology/config data** — use `/nWave/data/methodologies/` and
   `/nWave/data/config/` for canonical checklists, quality gates, and configuration constants.

---

## `/nWave/agents/` — Agent Specifications

Each agent file defines: role identity, responsibilities, output format, quality bars, and
behavioural constraints. **Adopt the agent's persona** when executing its wave.

| Agent File | Role | Used In Wave |
|------------|------|--------------|
| `nw-product-discoverer.md` | Validates product opportunities through evidence | DISCOVER |
| `nw-product-discoverer-reviewer.md` | Peer-reviews discovery output | DISCOVER review |
| `nw-product-owner.md` | Produces user stories and acceptance criteria | DISCUSS |
| `nw-product-owner-reviewer.md` | Peer-reviews requirements quality | DISCUSS review |
| `nw-solution-architect.md` | Designs system architecture and component boundaries | DESIGN |
| `nw-solution-architect-reviewer.md` | Peer-reviews architecture decisions | DESIGN review |
| `nw-platform-architect.md` | Plans infrastructure, CI/CD, deployment strategy | DEVOPS |
| `nw-platform-architect-reviewer.md` | Peer-reviews platform and ops decisions | DEVOPS review |
| `nw-acceptance-designer.md` | Authors BDD test scenarios (Given-When-Then) | DISTILL |
| `nw-acceptance-designer-reviewer.md` | Peer-reviews test scenario completeness | DISTILL review |
| `nw-software-crafter.md` | Implements via Outside-In TDD | DELIVER |
| `nw-software-crafter-reviewer.md` | Peer-reviews code quality and TDD discipline | DELIVER review |
| `nw-functional-software-crafter.md` | Implements in a functional style | DELIVER (functional) |
| `nw-researcher.md` | Deep technical research on any topic | Cross-wave |
| `nw-researcher-reviewer.md` | Peer-reviews research quality | Cross-wave |
| `nw-troubleshooter.md` | Root cause analysis and bug hunting | Cross-wave |
| `nw-troubleshooter-reviewer.md` | Peer-reviews troubleshooting diagnosis | Cross-wave |
| `nw-documentarist.md` | Produces and maintains documentation | Cross-wave |
| `nw-documentarist-reviewer.md` | Peer-reviews documentation quality | Cross-wave |
| `nw-data-engineer.md` | Data modelling, pipelines, storage design | Cross-wave |
| `nw-data-engineer-reviewer.md` | Peer-reviews data engineering decisions | Cross-wave |
| `nw-agent-builder.md` | Designs and builds new nWave agents | Framework extension |
| `nw-agent-builder-reviewer.md` | Peer-reviews new agent definitions | Framework extension |

---

## `/nWave/tasks/nw/` — Command Specifications

Each file is the **canonical definition** of a `/nw:*` command. Follow it exactly — do not
invent steps, change sequencing, or omit required sections.

| File | Command |
|------|---------|
| `new.md` | `/nw:new` |
| `discover.md` | `/nw:discover` |
| `discuss.md` | `/nw:discuss` |
| `design.md` | `/nw:design` |
| `devops.md` | `/nw:devops` |
| `distill.md` | `/nw:distill` |
| `deliver.md` | `/nw:deliver` |
| `execute.md` | `/nw:execute` |
| `continue.md` | `/nw:continue` |
| `review.md` | `/nw:review` |
| `rigor.md` | `/nw:rigor` |
| `refactor.md` | `/nw:refactor` |
| `research.md` | `/nw:research` |
| `document.md` | `/nw:document` |
| `diagram.md` | `/nw:diagram` |
| `roadmap.md` | `/nw:roadmap` |
| `finalize.md` | `/nw:finalize` |
| `fast-forward.md` | `/nw:fast-forward` |
| `forge.md` | `/nw:forge` |
| `mikado.md` | `/nw:mikado` |
| `mutation-test.md` | `/nw:mutation-test` |
| `root-why.md` | `/nw:root-why` |

---

## `/nWave/skills/` — Deep Domain Playbooks

Skills are **deep guidance files** grouped by agent. Before producing any wave deliverable,
read the skills for the active agent. Skills define edge cases, quality bars, worked
examples, and anti-patterns to avoid.

Skill folders mirror agent names:

```
nWave/skills/
├── product-discoverer/          # Discovery research techniques, validation patterns
├── product-discoverer-reviewer/ # How to review discovery quality
├── product-owner/               # Story writing, criteria precision, scope control
├── product-owner-reviewer/      # How to review requirements completeness
├── solution-architect/          # Architecture patterns, trade-off analysis
├── solution-architect-reviewer/ # How to review architectural decisions
├── platform-architect/          # Infrastructure patterns, CI/CD, observability
├── platform-architect-reviewer/ # How to review platform decisions
├── acceptance-designer/         # BDD scenario writing, coverage heuristics
├── software-crafter/            # TDD discipline, Outside-In patterns, refactoring
├── software-crafter-reviewer/   # How to review code and TDD quality
├── functional-software-crafter/ # Functional programming patterns for DELIVER
├── researcher/                  # Research methodology, source evaluation
├── troubleshooter/              # Debugging frameworks, root cause techniques
├── documentarist/               # Documentation standards and structure
├── data-engineer/               # Data modelling, pipeline, storage patterns
└── agent-builder/               # How to design new nWave agents
```

**Rule**: If a skill file exists for the active agent, it is mandatory reading before producing output.

---

## `/nWave/templates/` — Output Structure

Templates define the **required structure** for all wave artefacts and framework documents.
Always use the closest matching template. Never produce unstructured free-form output
when a template exists.

| Template File | Use For |
|---------------|---------|
| `deliver-outside-in-tdd.yaml` | TDD implementation plan and task breakdown (DELIVER) |
| `design-architecture-interactive.yaml` | Architecture design session output (DESIGN) |
| `devops-production-readiness.yaml` | Infrastructure and production readiness (DEVOPS) |
| `discuss-requirements-interactive.yaml` | Requirements elicitation and user stories (DISCUSS) |
| `distill-acceptance-tests.yaml` | BDD acceptance test scenarios (DISTILL) |
| `nwave-complete-methodology.yaml` | Full methodology reference for wave orchestration |
| `execution-log-template.yaml` | Wave execution log structure |
| `roadmap-schema.yaml` | Roadmap artefact structure |
| `AGENT_TEMPLATE.md` | Structure for defining a new agent |
| `COMMAND_TEMPLATE.md` | Structure for defining a new command |
| `COMMAND_TEMPLATE.yaml` | YAML form of a new command definition |
| `REVIEWER_TEMPLATE.md` | Structure for defining a new reviewer agent |
| `SKILL_TEMPLATE.md` | Structure for defining a new skill |
| `step-tdd-cycle-schema.json` | Canonical TDD 5-phase cycle schema (v4.0) |
| `validation-schemas.json` | All DES validation schemas for phase compliance |

---

## `/nWave/data/` — Methodology Reference and Configuration

Data provides **canonical constants, shared rules, and methodology references** used across
all waves. Always check here for authoritative values before assuming defaults.

```
nWave/data/
├── wizard-shared-rules.md   # Cross-wave rules ALL agents must honour — read this first
├── config/                  # Framework configuration constants
├── methodologies/           # Methodology definitions and canonical checklists
└── research/                # Reference research underpinning the framework
```

**`wizard-shared-rules.md` is mandatory** — it contains constraints that override any
wave-specific behaviour. Read it at the start of every session.

---

## TDD 5-Phase Cycle (DELIVER wave)

When implementing via `/nw:deliver`, follow the canonical schema in
`/nWave/templates/step-tdd-cycle-schema.json`:

1. **PREPARE** — establish test fixtures, scaffolding, and preconditions
2. **RED_ACCEPTANCE** — write a failing acceptance test (BDD Given-When-Then)
3. **RED_UNIT** — write failing unit tests for the target behaviour
4. **GREEN** — write the minimum code to make all tests pass
5. **COMMIT** — refactor without regressions, commit with conventional message

**STOP and do not proceed if:**
- Production code would be written before a failing test exists
- A phase is marked complete without verifying tests pass
- Multiple unrelated tasks are batched into a single commit
- The RED phase is being skipped because a test "seems obvious"

---

## Wave Output Artefacts

| Wave | Artefact Location |
|------|-------------------|
| DISCOVER | `docs/discovery/opportunity-{id}.md` |
| DISCUSS | `docs/stories/story-{id}.md` |
| DESIGN | `docs/architecture/design-{id}.md` |
| DEVOPS | `docs/devops/platform-{id}.md` |
| DISTILL | `tests/acceptance/scenarios-{id}.feature` |
| DELIVER | Source code + test files + conventional commit |

---

## Commit Convention

All commits must follow **Conventional Commits**:

```
type(scope): subject
```

| Type | Effect |
|------|--------|
| `feat` | Minor version bump |
| `fix`, `perf`, `refactor` | Patch bump |
| `docs`, `test`, `ci`, `chore` | No release |
| `BREAKING CHANGE:` in footer | Major bump |

---

## Critical Rules — NEVER:

- Skip a wave without explicit user confirmation and `/nw:fast-forward`
- Write production code before a failing test exists
- Produce structured output (stories, designs, scenarios, plans) without reading the
  matching template from `/nWave/templates/`
- Produce wave output without reading the agent spec from `/nWave/agents/`
- Ignore skills in `/nWave/skills/` for the active agent
- Override or ignore constraints in `/nWave/data/wizard-shared-rules.md`
- Suggest running scripts, hooks, installers, CLI tools, or any executable from this
  repository — nWave operates through documents and code changes only
- Reference `scripts/`, `src/des/`, or any Python runtime component — those are internal
  to the nWave framework development and are not part of the user-facing methodology

---

## Getting Started

1. **Read** [`/nWave/README.md`](/nWave/README.md) to orient yourself.
2. **Read** `/nWave/data/wizard-shared-rules.md` — these apply to every wave.
3. **New feature?** → `/nw:new <feature description>`
4. **Resume work?** → `/nw:continue`
5. **Ready to code?** → Complete DISTILL wave first, then `/nw:deliver`
6. **Review output?** → `/nw:review` or `/nw:rigor` for exhaustive audit
7. **Something broken?** → `/nw:root-why`
8. **Extend the framework?** → Use `AGENT_TEMPLATE.md`, `COMMAND_TEMPLATE.md`, or
   `SKILL_TEMPLATE.md` from `/nWave/templates/`
