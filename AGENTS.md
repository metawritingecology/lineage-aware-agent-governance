# Agent Rules for the Lineage-Aware Agent Governance Repository

This repository is a candidate, GitHub-visible public surface related to
Meta-Writing Ecology (MWE). It publishes a single boundary document
(`GOVERNANCE_SURFACE.md`) and its supporting files.

It does not represent the full MWE archive, backend corpus, complete registry,
complete methodology, internal routing state, or authority layer. It is a
candidate / related surface, not a confirmed MWE component.

Agents may perform approved technical and editorial tasks only.

## Role Allocation

### User-Led Conceptual Review

Use this review layer for conceptual decisions that require authorial judgment,
including structural reasoning, naming decisions, classification decisions,
public/private boundary review, OSF / GitHub / website positioning, and
relation-status decisions.

This layer may include AI-assisted discussion, but AI-generated output is not
repository authority.

Conceptual decisions become actionable only when explicitly approved by the
user / repository owner and translated into concrete implementation
instructions.

AI agents must not treat prior AI-assisted discussion as independent authorship,
source authority, or standing permission to modify conceptual files.

Final authority remains with the user / repository owner.

### Executing agent

Use an executing agent for routine editorial and repo-local maintenance:

- Markdown edits to the surface, only when explicitly instructed
- de-sensitization scans and hash verification
- link checks and inventory generation
- script maintenance
- mechanical repository maintenance

The executing agent must not decide:

- MWE model classification
- public/private status of this repository or any file
- candidate-to-confirmed relation promotion
- naming authority
- top-navigation inclusion on any MWE surface
- whether or when this surface is cross-linked from other MWE repositories
- license changes

### Independent review

Reserve an independent reviewer, of a distinct model lineage, for
boundary-sensitive work:

- public-surface consistency and de-sensitization audits
- relation-status checks (candidate vs confirmed)
- review of executing-agent output
- high-risk batch edits

An executing agent must not also be its own independent reviewer. A second
interface backed by the same model lineage is not an independent reviewer, and a
different machine or session does not by itself create one.

## Relation Status Rules

Preserve these distinctions:

- candidate relation
- navigation relation
- confirmed relation
- formal dependency
- ontology claim

Candidate or navigation relations must not be promoted into confirmed relations
without explicit user confirmation. This repository is a candidate / related
surface unless the owner states otherwise.

## Public Boundary Rule

Public-facing entries must not imply that this repository contains the full MWE
system, archive, registry, methodology, or authority structure.

If a public surface is readable, it must not be treated as complete.

## Symbol hygiene

When editing human-facing prose, use the proper not-equal symbol `≠` instead of
the ASCII marker `!=`.

Apply this only to prose-level content, including:

- Markdown content
- public documentation text
- visible page text
- boundary statements
- human-facing explanatory text

Do not replace `!=` or `!==` in:

- executable code
- JavaScript or TypeScript logic
- config files
- JSON
- scripts
- comparison expressions
- package files
- lockfiles
- generated files
- dependencies

Before committing prose/content edits, scan touched human-facing files for
literal `!=`. Replace `!=` with `≠` only when it appears as prose. If `!=`
appears outside the edited files, report it but do not expand scope unless
explicitly approved.

## Required Worklog

This requirement covers every **agent-participated** change to the repository
(a change an agent made or assisted). A purely manual, owner-only change is
outside agent-worklog scope, though the owner may still record one. When in
doubt, treat the change as agent-participated and log it.

After any agent-participated change, update `AGENT_WORKLOG.md` with:

- agent used
- task performed
- files changed
- tests or checks run
- unresolved questions
- risks or assumptions

For boundary-sensitive work that relied on an independent review, also record
the review so it is evidenced rather than merely asserted:

- reviewer (which reviewer / interface)
- reviewer lineage
- review mode (parallel blind, sequential blind, or corroboration)
- reviewed commit or snapshot
- review evidence / reference

Ordinary mechanical tasks do not need these extra fields. Where a field cannot
be established (for example a reviewer lineage that was not disclosed to the
executing agent), record it as unknown rather than omitting it.

## Worklog Governance

`AGENT_WORKLOG.md` is the single active append target for agent worklog entries.

Agents must preserve historical worklog entries byte-for-byte. Historical
entries are evidence of the state and authorization at the time they were
written; they must not be rewritten, reordered, summarized, normalized, or
deleted to match later repository, PR, deployment, or author-status changes.

Before the first modification of `AGENT_WORKLOG.md` in each task, run a
read-only local/remote inventory of other project work when remote evidence is
available. Exclude the current branch. Exclude routine bot/dependency branches
from the normal feature-work gate unless the task concerns dependency
integration; list them separately as the dependency queue.

Classify relevant non-bot work as one of: `completed_pushed_unmerged`,
`in_progress`, `hold`, `merged_directly`, `merged_via_pr_or_squash`,
`ambiguous`, or `author_status_unknown`.

Do not rely only on ancestry checks. A branch tip that is not an ancestor of
`main` may still have been merged by PR or squash merge. Prefer PR merge
metadata, then patch/tree equivalence, then direct ancestry, then explicit
author/worklog status, then branch age/name/workstream clues. Weak evidence must
produce `ambiguous`, not an unmerged-work claim.

If any relevant non-bot work is classified as `completed_pushed_unmerged`,
`ambiguous`, or `author_status_unknown`, stop before the first worklog write and
ask the author whether to include that work in the current integration cycle,
continue separately, classify it as `in_progress` or `hold`, or stop and process
the existing work first.

Author-declared `in_progress` or `hold` work must be listed but does not
repeatedly block unrelated work. Reconfirm only when `main` advances in a
relevant way, the branch or PR state changes, an integration operation occurs,
or the previous inventory is no longer current.

If GitHub or PR state is unavailable, distinguish available remote branch
evidence from unavailable PR state. Report uncertainty instead of inferring PR
status. Unknown PR state blocks only when the work is otherwise relevant and
lacks current author status.

The pre-append inventory is advisory evidence only. It does not authorize merge,
conflict resolution, PR creation, publication, deployment, branch deletion, or
status promotion.

Review `AGENT_WORKLOG.md` rollover eligibility at 4,000 lines, do not normally
exceed 5,000 lines without explicit author deferral, and also review after a
major integration cycle or quarterly, whichever trigger occurs first. Execute
rollover only as a separate authorized task after `main` is stable. Archived
worklogs are immutable historical evidence. `AGENT_WORKLOG.md` remains the
current append target after rollover.

When available, run `node scripts/check-agent-worklog-governance.mjs` as
read-only validation evidence. Among other checks it verifies the append-only
invariant mechanically, by confirming that the `origin/main` version of this
file is an exact byte prefix of the working copy. Its output does not determine
author status, merge readiness, integration priority, or authorization.

The user remains final authority for public release, naming, classification,
relation confirmation, top navigation, cross-linking, and merge / publication
decisions.
