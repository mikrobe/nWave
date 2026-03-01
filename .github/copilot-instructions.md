# Draft - Context-Driven Development

You are operating with the Draft methodology for Context-Driven Development.

**Measure twice, code once.**

## Core Workflow

**Context -> Spec & Plan -> Implement**

Every feature follows this lifecycle:
1. **Setup** - Initialize project context (once per project)
2. **New Track** - Create specification and plan
3. **Implement** - Execute tasks with TDD workflow
4. **Verify** - Confirm acceptance criteria met

## Project Context Files

When `draft/` exists in the project, always consider:
- `draft/.ai-context.md` - Source of truth for AI agents (dense codebase understanding)
- `draft/architecture.md` - Human-readable engineering guide (derived from .ai-context.md)
- `draft/product.md` - Product vision and goals
- `draft/tech-stack.md` - Technical constraints
- `draft/workflow.md` - TDD and commit preferences
- `draft/tracks.md` - Active work items

## Available Commands

| Command | Purpose |
|---------|---------| 
| `draft` | Show overview and available commands |
| `draft init` | Initialize project (run once) |
| `draft index [--init-missing]` | Aggregate monorepo service contexts |
| `draft new-track <description>` | Create feature/bug track |
| `draft decompose` | Module decomposition with dependency mapping |
| `draft implement` | Execute tasks from plan |
| `draft coverage` | Code coverage report (target 95%+) |
| `draft bughunt [--track <id>]` | Systematic bug discovery |
| `draft review [--track <id>]` | Three-stage code review |
| `draft deep-review [module]` | Exhaustive production-grade module audit |
| `draft adr [title]` | Architecture Decision Records |
| `draft status` | Show progress overview |
| `draft revert` | Git-aware rollback |
| `draft change <description>` | Handle mid-track requirement changes |
| `draft jira-preview [track-id]` | Generate jira-export.md for review |
| `draft jira-create [track-id]` | Create Jira issues from export via MCP |

## Intent Mapping

Recognize these natural language patterns:

| User Says | Action |
|-----------|--------|
| "set up the project" | Run init |
| "index services", "aggregate context" | Run index |
| "new feature", "add X" | Create new track |
| "break into modules", "decompose" | Run decompose |
| "start implementing" | Execute implement |
| "check coverage", "test coverage" | Run coverage |
| "hunt bugs", "find bugs" | Run bug hunt |
| "review code", "review track", "check quality" | Run review |
| "deep review", "production audit", "module audit" | Run deep-review |
| "what's the status" | Show status |
| "undo", "revert" | Run revert |
| "requirements changed", "scope changed", "update the spec" | Run change |
| "preview jira", "export to jira" | Run jira-preview |
| "create jira", "push to jira" | Run jira-create |
| "document decision", "create ADR" | Create architecture decision record |
| "help", "what commands" | Show draft overview |
| "the plan" | Read active track's plan.md |
| "the spec" | Read active track's spec.md |

## Tracks

A **track** is a high-level unit of work (feature, bug fix, refactor). Each track contains:
- `spec.md` - Requirements and acceptance criteria
- `plan.md` - Phased task breakdown
- `metadata.json` - Status and timestamps

Located at: `draft/tracks/<track-id>/`

## Status Markers

Recognize and use these throughout plan.md:
- `[ ]` - Pending
- `[~]` - In Progress
- `[x]` - Completed
- `[!]` - Blocked


---

## Draft Overview

When user says "help" or "draft":

Draft is a methodology for structured software development: **Context → Spec & Plan → Implement**

## Red Flags - STOP if you're:

- Jumping straight to implementation without reading existing Draft context
- Suggesting `draft implement` before a track has an approved spec and plan
- Not checking `draft/tracks.md` for existing active tracks before creating new ones
- Skipping the recommended command and going freeform
- Ignoring existing .ai-context.md, product.md, tech-stack.md, or workflow.md context

**Read context first. Follow the workflow.**

---

## Available Commands

| Command | Purpose |
|---------|---------|
| `draft init` | Initialize project (run once) |
| `draft index` | Aggregate monorepo service contexts (run at root) |
| `draft new-track` | Create feature/bug track with spec and plan |
| `draft implement` | Execute tasks from plan with TDD |
| `draft status` | Show progress overview |
| `draft revert` | Git-aware rollback |
| `draft decompose` | Module decomposition with dependency mapping |
| `draft coverage` | Code coverage report (target 95%+) |
| `draft deep-review` | Module lifecycle audit (ACID compliance, enterprise quality) |
| `draft bughunt` | Exhaustive bug hunt |
| `draft review` | Code review orchestrator |
| `draft adr` | Architecture Decision Records |
| `draft change` | Handle mid-track requirement changes |
| `draft jira-preview` | Generate Jira export for review |
| `draft jira-create` | Push issues to Jira via MCP |

## Quick Start

1. **First time?** Run `draft init` to initialize your project
2. **Starting a feature?** Run `draft new-track "your feature description"`
3. **Ready to code?** Run `draft implement` to execute tasks
4. **Check progress?** Run `draft status`

## Core Workflow

Every feature follows this lifecycle:
1. **Setup** - Initialize project context (once per project)
2. **New Track** - Create specification and plan
3. **Implement** - Execute tasks with TDD workflow
4. **Verify** - Confirm acceptance criteria met
5. **Quality** - Run `draft review` for code review, `draft bughunt` for bug hunting, `draft deep-review` for module audits

## Context Files

When `draft/` exists, these files guide development:
- `draft/architecture.md` - Source of truth: human-readable engineering reference (30-45 pages)
- `draft/.ai-context.md` - Derived from architecture.md: token-optimized AI context (200-400 lines)
- `draft/product.md` - Product vision and goals
- `draft/tech-stack.md` - Technical constraints
- `draft/workflow.md` - TDD and commit preferences
- `draft/tracks.md` - Active work items

## Status Markers

Used throughout plan.md files:

| Marker | Meaning |
|--------|---------|
| `[ ]` | Pending |
| `[~]` | In Progress |
| `[x]` | Completed |
| `[!]` | Blocked |

## Intent Mapping

You can also use natural language:

| Say this... | Runs this |
|-------------|-----------|
| "set up the project" | `draft init` |
| "index services", "aggregate context" | `draft index` |
| "new feature", "add X" | `draft new-track` |
| "start implementing" | `draft implement` |
| "what's the status" | `draft status` |
| "undo", "revert" | `draft revert` |
| "break into modules" | `draft decompose` |
| "check coverage" | `draft coverage` |
| "deep review", "module audit", "production audit" | `draft deep-review` |
| "hunt bugs", "find bugs" | `draft bughunt` |
| "review code", "review track", "check quality" | `draft review` |
| "document decision", "create ADR" | `draft adr` |
| "requirements changed", "scope changed", "update the spec" | `draft change` |
| "preview jira", "export to jira" | `draft jira-preview` |
| "create jira issues" | `draft jira-create` |

## Need Help?

- Run `/draft` (this command) for overview
- Run `draft status` to see current state
- Check `draft/tracks/<track_id>/spec.md` for requirements
- Check `draft/tracks/<track_id>/plan.md` for task details

---

## Init Command

When user says "init draft" or "draft init [refresh]":

You are initializing a Draft project for Context-Driven Development.

## Red Flags - STOP if you're:

- Re-initializing a project that already has `draft/` without using `refresh` mode
- Skipping brownfield analysis for an existing codebase
- Rushing through product definition questions without probing for detail
- Auto-generating tech-stack.md without verifying detected dependencies
- Not presenting .ai-context.md for developer review before proceeding
- Overwriting existing tracks.md (this destroys track history)

**Initialize once, refresh to update. Never overwrite without confirmation.**

---

## Standard File Metadata

**ALL files in `draft/` MUST include this metadata header.**

### Gathering Git Information

Before generating any file, run these commands:

```bash
basename "$(pwd)"
git branch --show-current
git rev-parse --abbrev-ref --symbolic-full-name @{upstream} 2>/dev/null || echo "none"
git rev-parse HEAD
git rev-parse --short HEAD
git log -1 --format="%ci"
git log -1 --format="%s"
git status --porcelain | head -1
```

### Metadata Template

```yaml
---
project: "{PROJECT_NAME}"
module: "{MODULE_NAME or 'root'}"
generated_by: "draft:{COMMAND_NAME}"
generated_at: "{ISO_TIMESTAMP}"
git:
  branch: "{LOCAL_BRANCH}"
  remote: "{REMOTE/BRANCH or 'none'}"
  commit: "{FULL_SHA}"
  commit_short: "{SHORT_SHA}"
  commit_date: "{COMMIT_DATE}"
  commit_message: "{FIRST_LINE_OF_COMMIT_MESSAGE}"
  dirty: {true|false}
synced_to_commit: "{FULL_SHA}"
---
```

---

## Pre-Check

Check for arguments:
- `refresh`: Update existing context without full re-init

```bash
ls draft/ 2>/dev/null
```

If `draft/` exists with context files:
- Announce: "Project already initialized. Use `draft init refresh` to update context or `draft new-track` to create a feature."
- Stop here.

### Monorepo Detection

Check for monorepo indicators:
- Multiple `package.json` / `go.mod` / `Cargo.toml` in child directories
- `lerna.json`, `pnpm-workspace.yaml`, `nx.json`, or `turbo.json` at root
- `packages/`, `apps/`, `services/` directories with independent manifests

### Refresh Mode

If the user runs `draft init refresh`:

1. **Tech Stack Refresh**: Re-scan dependency files. Compare with `draft/tech-stack.md`. Propose updates.
2. **Architecture Refresh**: Use metadata-based incremental analysis via `synced_to_commit`.
3. **Product Refinement**: Ask if product vision/goals need updates.
4. **Workflow Review**: Ask if workflow settings need changing.
5. **Preserve**: Do NOT modify `draft/tracks.md` unless explicitly requested.

## Step 1: Project Discovery

Analyze the current directory:

**Brownfield (Existing)** indicators:
- Has `package.json`, `requirements.txt`, `go.mod`, `Cargo.toml`, etc.
- Has `src/`, `lib/`, or similar code directories
- Has git history with commits

**Greenfield (New)** indicators:
- Empty or near-empty directory
- Only has README or basic config

If **Brownfield**: proceed to Step 1.5 (Architecture Discovery).
If **Greenfield**: skip to Step 2 (Product Definition).

---

## Step 1.5: Architecture Discovery (Brownfield Only)

Perform exhaustive analysis of the existing codebase.

**Outputs**:
- `draft/architecture.md` — Human-readable, **30-45 page** engineering reference (PRIMARY)
- `draft/.ai-context.md` — Token-optimized, 200-400 lines, condensed from architecture.md (DERIVED)

### Exhaustive Analysis Mandate

**CRITICAL**: This analysis must be EXHAUSTIVE:
- **Read ALL relevant source files**
- **Enumerate ALL implementations**
- **Generate REAL Mermaid diagrams**
- **Include ACTUAL code snippets**
- **Populate ALL tables**
- **Target 30-45 pages**

### Analysis Phases

#### Phase 1: Discovery (Broad Scan)
1. Map the directory tree
2. Read build / dependency files
3. Read API definition files
4. Read interface / type definition files

#### Phase 2: Wiring
5. Find the entry point
6. Follow the orchestrator
7. Find the registry / registration code
8. Map the dependency wiring

#### Phase 3: Depth
9. Trace data flows end-to-end
10. Read implementation files
11. Identify concurrency model
12. Find safety checks

#### Phase 4: Periphery
13. Catalog external dependencies
14. Examine test infrastructure
15. Scan for configuration
16. Look for documentation

#### Phase 5: Synthesis
17. Cross-reference
18. Validate completeness
19. Identify patterns
20. Generate diagrams

---

## architecture.md Specification

Generate `draft/architecture.md` — comprehensive human-readable engineering reference.

**Target length: 30–45 pages**

### Report Sections

1. Executive Summary
2. AI Agent Quick Reference
3. System Identity & Purpose
4. Architecture Overview (with Mermaid flowchart TD)
5. Component Map & Interactions
6. Data Flow — End to End (multiple Mermaid flowcharts)
7. Core Modules Deep Dive (stateDiagram-v2 per stateful module)
8. Concurrency Model & Thread Safety
9. Framework & Extension Points
10. Full Catalog of Implementations
11. Secondary Subsystem (V2/Redesign, if applicable)
12. API & Interface Definitions
13. External Dependencies
14. Cross-Module Integration Points (sequence diagrams)
15. Critical Invariants & Safety Rules
16. Security Architecture
17. Observability & Telemetry
18. Error Handling & Failure Modes
19. State Management & Persistence
20. Reusable Modules for Future Projects
21. Key Design Patterns
22. Configuration & Tuning
23. Performance Characteristics & Hot Paths
24. How to Extend — Step-by-Step Cookbooks
25. Build System & Development Workflow
26. Testing Infrastructure
27. Known Technical Debt & Limitations
28. Glossary
- Appendix A: File Structure Summary
- Appendix B: Data Source → Implementation Mapping
- Appendix C: Output Flow
- Appendix D: Mermaid Sequence Diagrams

---

## .ai-context.md Specification

Generate `draft/.ai-context.md` — machine-optimized context file (200-400 lines).

### Required Sections

```
## META
type: {microservice|cli|library|daemon|webapp|api}
lang: {language} {version}
pattern: {Hexagonal|MVC|Pipeline|Event-driven|Layered}
build: {exact command}
test: {exact command}
entry: {file}:{function|class}
config: {mechanism}@{location}

## GRAPH:COMPONENTS
## GRAPH:DEPENDENCIES
## GRAPH:DATAFLOW
## WIRING
## INVARIANTS
## INTERFACES
## CATALOG:{Category}
## THREADS
## CONFIG
## ERRORS
## CONCURRENCY
## EXTEND:{ExtensionType}
## TEST
## FILES
## VOCAB
## REFS
```

---

## Step 2: Product Definition

Create `draft/product.md`. Engage in structured dialogue:

1. **Vision**: What does this product do and why does it matter?
2. **Users**: Who uses this? What are their primary needs?
3. **Core Features**: P0/P1/P2 features
4. **Success Criteria**: How will you measure success?
5. **Constraints**: Technical, business, or timeline constraints
6. **Non-Goals**: What is explicitly out of scope?

## Step 3: Tech Stack

Auto-detect from `package.json`, `requirements.txt`, `go.mod`, `Cargo.toml`, etc.
Create `draft/tech-stack.md`. Present for verification.

## Step 4: Workflow Configuration

Create `draft/workflow.md`. Ask about:
- TDD preference (strict/flexible/none)
- Commit style and frequency
- Validation settings

## Step 5: Initialize Tracks

Create `draft/tracks.md` with Active/Completed/Archived sections.

## Step 6: Create Directory Structure

```bash
mkdir -p draft/tracks
```

---

## Condensation Subroutine: Generate .ai-context.md from architecture.md

Transform `architecture.md` into machine-optimized `.ai-context.md`.

### Transformation Rules

| architecture.md Section | .ai-context.md Section | Transformation |
|------------------------|------------------------|----------------|
| Executive Summary | META | Extract key-value pairs only |
| Architecture Overview (Mermaid) | GRAPH:COMPONENTS | Convert to tree notation |
| Data Flow (Mermaid) | GRAPH:DATAFLOW | Convert to arrow notation |
| External Dependencies | GRAPH:DEPENDENCIES | `A -[proto]-> B` format |
| Dependency Injection | WIRING | mechanism + tokens list |
| Critical Invariants | INVARIANTS | One line per invariant with category prefix |
| Framework/Extension Points | INTERFACES + EXTEND | Signatures + cookbook steps |
| Full Catalog | CATALOG:{Category} | Pipe-separated table rows |
| Concurrency Model | THREADS + CONCURRENCY | Tables + rules |
| Configuration | CONFIG | Pipe-separated table rows |
| Error Handling | ERRORS | Key: value pairs |
| Build/Test | TEST + META | Exact commands |
| File Structure | FILES | Concept: path mappings |
| Glossary | VOCAB | Term: definition pairs |

---

## New Track Command

When user says "new feature" or "draft new-track <description>":

You are creating a new track for Context-Driven Development.

## Red Flags - STOP if you're:

- Creating a track without reading existing Draft context
- Asking questions without contributing expertise or trade-off analysis
- Rushing through intake without probing deeper with "why"
- Generating spec/plan without user confirmation at checkpoints
- Skipping risk identification
- Not citing sources when giving architectural advice

---

## Pre-Check

1. Verify Draft is initialized.
2. Check for `--quick` flag — if present, use Quick Mode (Step 1.5).
3. Load project context: `product.md`, `tech-stack.md`, `.ai-context.md`, `workflow.md`, `tracks.md`.

## Step 1: Generate Track ID

Create kebab-case ID from description. Check for collisions; append `-<ISO-date>` if needed.

## Step 1.5: Quick Mode (`--quick` only)

Ask only:
1. "What exactly needs to change? (1-2 sentences)"
2. "How will you know it's done? (acceptance criteria)"

Generate minimal `spec.md` and flat `plan.md`. Skip Steps 2–7.

## Step 2: Create Draft Files

Create `draft/tracks/<track_id>/spec-draft.md` and `plan-draft.md` with YAML frontmatter.

## Step 3: Collaborative Intake

Walk through intake phases as an active collaborator:
- Phase 1: Existing Documentation
- Phase 2: Problem Space
- Phase 3: Solution Space
- Phase 4: Risk & Constraints
- Phase 5: Success Criteria

For bugs (Step 3B):
- Phase 1: Symptoms & Context
- Phase 2: Reproduction
- Phase 3: Blast Radius
- Phase 4: Code Locality

## Step 4: Draft Review & Refinement

Present spec-draft.md summary, list Open Questions, ask to refine or finalize.

## Step 4.5: Elicitation Pass

Stress-test the spec with 3 challenge techniques based on track type:

**Feature tracks:** Pre-mortem, Scope Boundary, Edge Case Storm
**Bug tracks:** Root Cause Depth, Blast Radius, Regression Risk
**Refactor tracks:** Behavior Preservation, Integration Impact, Rollback Complexity

## Step 5: Finalize Specification

Rename `spec-draft.md` → `spec.md`. Add Conversation Log summary.

## Step 6: Create Plan

Build phased plan-draft.md:
- Phase 1: Foundation / Setup
- Phase 2: Core Implementation
- Phase 3: Integration & Polish

## Step 7: Finalize Plan

Rename `plan-draft.md` → `plan.md`. Validate phases against spec ACs.

## Step 8: Create Metadata & Update Tracks

Create `metadata.json`. Update `draft/tracks.md` Active section.

---

## Implement Command

When user says "implement" or "draft implement":

## Red Flags - STOP if you're:

- Implementing without an approved spec and plan
- Skipping TDD cycle when workflow.md has TDD enabled
- Marking a task `[x]` without fresh verification evidence
- Batching multiple tasks into a single commit
- Proceeding past a phase boundary without running the three-stage review
- Writing production code before a failing test (when TDD is strict)

## Step 1: Load Context

1. Find active track from `draft/tracks.md`
2. Read track's `spec.md` and `plan.md`
3. Read `draft/workflow.md`, `draft/tech-stack.md`
4. Check for architecture context (`.ai-context.md` or `architecture.md`)
5. Load production invariants from `## INVARIANTS` section

## Step 1.5: Readiness Gate (Fresh Start Only)

- AC Coverage Check: every AC has at least one corresponding task
- Sync Check: `synced_to_commit` values match between spec and plan

## Step 2: Find Next Task

Scan `plan.md` for first `[ ]` (pending) or `[~]` (in progress). Skip `[x]` and notify on `[!]`.

## Step 2.5: Write Story (Architecture Mode Only)

Write natural-language algorithm as comment block at top of target file:

```
// Story: [Module/File Name]
//
// Input:  [what this receives]
// Process:
//   1. [first step]
//   2. [second step]
// Output: [what this produces]
//
// Dependencies: [what this relies on]
// Side effects: [mutations, I/O, external calls]
```

**CHECKPOINT:** Present Story to developer. Wait for approval.

## Step 3: Execute Task

### Step 3.0: Design Before Code (Architecture Mode Only)

**3.0a. Execution State Design**

```
EXECUTION STATE: [Task/Module Name]
Input State:     variableName: Type — purpose
Intermediate:    variableName: Type — purpose
Output State:    variableName: Type — purpose
Error State:     variableName: Type — purpose
```

**CHECKPOINT:** Wait for approval.

**3.0b. Function Skeleton Generation**

Generate stubs with complete signatures, one-line docstrings, no implementation bodies.

**CHECKPOINT:** Wait for approval.

### Step 3.0c: Production Robustness Patterns (REQUIRED)

Apply while writing code:

#### Atomicity
| Trigger | Required Pattern |
|---------|-----------------| 
| Multi-step state mutation | Wrap in transaction or try/finally with rollback |
| File write | Write to temp file + atomic rename |
| DB write + in-memory update | DB-first; update memory only on DB success |
| Resource acquisition | Release in `finally`/`defer`/RAII |

#### Isolation
| Trigger | Required Pattern |
|---------|-----------------|
| Method mutates shared state | Acquire existing lock before mutation |
| Lifecycle operations | Use dedicated lifecycle lock |
| Returning internal state | Return deep copy or frozen snapshot |
| Acquiring second lock while holding one | Follow documented lock ordering |
| DB I/O while holding state lock | Move I/O outside lock scope |

#### Durability
| Trigger | Required Pattern |
|---------|-----------------|
| Critical state that must survive crashes | Recoverable from DB/disk alone |
| Async DB write | Await the write; no fire-and-forget |
| Audit trail / event log | Append-only pattern |

#### Defensive Boundaries
| Trigger | Required Pattern |
|---------|-----------------|
| External numeric data in arithmetic | Guard with `isFinite()`/`isnan()` |
| External API response consumed | Validate fields exist and have correct types |
| SQL with dynamic values | Parameterized queries only |
| Dynamic SQL identifiers | Validate against explicit allowlist |

#### Idempotency
| Trigger | Required Pattern |
|---------|-----------------|
| Retriable operations | Use dedup key; check-before-write or upsert |
| State transitions | Validate transition is legal from current state |
| Alert/notification emission | Dedup on (type, entity_id, time_window) |

#### Fail-Closed
| Trigger | Required Pattern |
|---------|-----------------|
| Error path determining access/action | Default to safe/restrictive/deny |
| Missing/null data for a decision | Treat as deny/reject/skip |
| Config missing or unparseable | Use restrictive default (safe mode) |

### Step 3.1: Implement (TDD Workflow)

**If TDD Enabled:**

**RED - Write Failing Test**
1. Create/update test file
2. Write test capturing the requirement
3. RUN test — VERIFY it FAILS
4. Show output with failure

**GREEN - Implement Minimum Code**
1. Write MINIMUM code to make test pass
2. RUN test — VERIFY it PASSES
3. Show output with pass

**REFACTOR - Clean with Tests Green**
1. Review code for improvements
2. Refactor while keeping tests green
3. RUN all related tests
4. Show final test output

**If TDD Not Enabled:**
1. Implement the task
2. Test manually or run existing tests

### Step 3.2: Commit

Follow `workflow.md` commit conventions. One task, one commit.

```bash
git add <specific files>
git commit -m "<type>(<scope>): <description>"
```

## Step 4: Update Plan

Mark task `[x]` in `plan.md`. Update `metadata.json` counters.

## Step 5: Phase Completion Check

When all tasks in a phase are `[x]`:

Run three-stage review:
1. **Requirements** — All ACs for this phase met?
2. **Quality** — Code follows tech-stack.md patterns?
3. **Tests** — Coverage meets threshold?

**CHECKPOINT:** Present review to developer before advancing to next phase.

## Step 6: Track Completion

When all phases complete:
1. Update `metadata.json` status to `"completed"`
2. Move track from Active to Completed in `draft/tracks.md`
3. Announce completion

---

## Coverage Command

When user says "check coverage" or "draft coverage":

Run code coverage analysis targeting 95%+ coverage.

1. Run test suite with coverage enabled
2. Identify files/functions below threshold
3. Generate coverage report
4. Suggest tests for uncovered paths

---

## Bughunt Command

When user says "hunt bugs" or "draft bughunt":

Systematic bug discovery across the codebase.

## Red Flags - STOP if you're:

- Reporting issues without reproduction steps
- Conflating style issues with bugs
- Not checking invariants from .ai-context.md

### Process

1. Load `.ai-context.md` invariants and critical paths
2. Scan for violation patterns:
   - Data safety violations (missing transactions, unvalidated input)
   - Security issues (OWASP Top 10)
   - Concurrency issues (race conditions, deadlocks)
   - Error handling gaps (swallowed exceptions, missing retries)
   - Performance issues (N+1 queries, unbounded loops)
3. Generate `draft/bughunt-report.md` with severity ratings

### Report Format

```markdown
# Bug Hunt Report

## Summary
| Severity | Count |
|----------|-------|
| Critical | X |
| High | Y |
| Medium | Z |
| Low | W |

## Critical Issues
### [Issue Title]
**File:** path/to/file.ext:line
**Description:** What's wrong
**Reproduction:** Steps to reproduce
**Fix:** Recommended fix
```

---

## Review Command

When user says "review code" or "draft review":

Three-stage code review orchestrator.

## Stage 1: Requirements Review
- Does implementation match spec.md acceptance criteria?
- Are all edge cases handled?
- Are non-goals respected?

## Stage 2: Quality Review
- Does code follow tech-stack.md patterns?
- Are production robustness patterns applied?
- Is error handling complete?
- Are invariants from .ai-context.md respected?

## Stage 3: Test Review
- Does test coverage meet thresholds?
- Are tests testing the right things?
- Are edge cases covered?

Generate `draft/tracks/<id>/review-report.md`.

---

## Deep Review Command

When user says "deep review" or "draft deep-review [module]":

Exhaustive production-grade module audit.

### Audit Dimensions

1. **ACID Compliance** — transactions, atomicity, consistency
2. **Security** — auth, input validation, secrets management
3. **Concurrency** — thread safety, lock ordering, race conditions
4. **Error Handling** — propagation, recovery, observability
5. **Performance** — hot paths, N+1, memory leaks
6. **Testability** — coverage, test quality, mock patterns
7. **Maintainability** — complexity, coupling, naming

---

## ADR Command

When user says "document decision" or "draft adr [title]":

Create Architecture Decision Record.

```markdown
# ADR-{number}: {Title}

**Date:** {date}
**Status:** Proposed | Accepted | Deprecated | Superseded

## Context
[What is the issue that we're seeing that is motivating this decision?]

## Decision
[What is the change that we're proposing and/or doing?]

## Consequences
[What becomes easier or more difficult because of this change?]
```

Save to `draft/adr/{number}-{kebab-title}.md`.

---

## Status Command

When user says "what's the status" or "draft status":

Show progress overview.

```
═══════════════════════════════════════════════════════════
                    DRAFT STATUS
═══════════════════════════════════════════════════════════

Project: {name}
Branch:  {branch}

ACTIVE TRACKS
─────────────────────────────────────────────────────────
Track: {track_id} — {title}
  Status:  {Planning|In Progress|Review}
  Phase:   {current}/{total}
  Tasks:   {completed}/{total} completed
  Created: {date}

COMPLETED TRACKS
─────────────────────────────────────────────────────────
  {track_id} — {title} (completed {date})

═══════════════════════════════════════════════════════════
```

---

## Revert Command

When user says "undo" or "draft revert":

Git-aware rollback.

1. Check `git log` for recent commits on current branch
2. Identify commits associated with current track (by message convention)
3. Present options:
   - Revert last commit
   - Revert to phase start
   - Revert to track start
4. Show exactly what will change
5. **CHECKPOINT:** Confirm before executing

```bash
# Soft revert (keep changes staged)
git revert --no-commit HEAD

# Hard revert (discard changes)
git reset --hard HEAD~{n}
```

---

## Change Command

When user says "requirements changed" or "draft change <description>":

Handle mid-track requirement changes.

1. Read current `spec.md` and `plan.md`
2. Analyze impact of the change
3. Identify affected tasks (completed vs pending)
4. Propose spec updates
5. Propose plan updates (which tasks to modify/add/remove)
6. **CHECKPOINT:** Present impact analysis. Wait for approval.
7. Update `spec.md` and `plan.md`
8. Add entry to Conversation Log in spec.md

---

## Jira Preview Command

When user says "preview jira" or "draft jira-preview [track-id]":

Generate Jira export preview.

1. Read track's `spec.md` and `plan.md`
2. Map to Jira issue structure:
   - Track → Epic
   - Phases → Stories
   - Tasks → Sub-tasks
3. Generate `draft/tracks/<id>/jira-export.md` for review

```markdown
# Jira Export Preview: {track_id}

## Epic
**Summary:** {track title}
**Description:** {spec problem statement}
**Labels:** draft-generated

## Stories (by Phase)

### Story: Phase 1 — {phase goal}
**Points:** {estimate}
**Acceptance Criteria:**
- {AC from spec}

#### Sub-tasks
- [ ] {task from plan}
```

---

## Jira Create Command

When user says "create jira" or "draft jira-create [track-id]":

Push issues to Jira via MCP.

1. Read `draft/tracks/<id>/jira-export.md` (generate if missing)
2. Confirm with user before creating
3. Use Jira MCP tool to create Epic, Stories, and Sub-tasks
4. Record created issue keys in `metadata.json`

---

## Index Command

When user says "index services" or "draft index [--init-missing]":

Build federated knowledge index for monorepo.

## Red Flags - STOP if you're:

- Running at a non-root directory in a monorepo
- Indexing services without `draft/` directories
- Overwriting root-level context without confirming

### Process

1. Parse arguments (`--init-missing`, `bughunt`)
2. Discover services (depth=1 only)
3. Categorize (initialized vs uninitialized)
4. Handle uninitialized (prompt if `--init-missing`)
5. Aggregate context from initialized services
6. Detect inter-service dependencies
7. Generate root aggregated files:
   - `draft/service-index.md`
   - `draft/dependency-graph.md`
   - `draft/tech-matrix.md`
   - `draft/product.md` (synthesized)
   - `draft/architecture.md` (system-of-systems)
   - `draft/.ai-context.md` (condensed)
8. Create `draft/config.yaml`

---

## Decompose Command

When user says "break into modules" or "draft decompose":

Module decomposition with dependency mapping.

## Red Flags - STOP if you're:

- Defining modules without understanding the codebase
- Creating modules with circular dependencies
- Making modules too large (>5 files) or too small (single function)
- Not waiting for developer approval at checkpoints

### Module Guidelines

- Each module: single responsibility
- Target 1-3 files per module
- Clear API boundary
- Testable in isolation

### CHECKPOINT 1: Module Breakdown

Present all proposed modules. Wait for developer approval.

### CHECKPOINT 2: Dependency Analysis

Present dependency diagram + implementation order. Wait for approval.

### Output

Write architecture document:
- Project-wide: Update `draft/architecture.md`, regenerate `draft/.ai-context.md`
- Track-scoped: `draft/tracks/<id>/architecture.md`
