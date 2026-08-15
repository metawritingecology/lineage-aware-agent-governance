# Agent Worklog — lineage-aware-agent-governance

## Active Log Notice

This is the single active append target for agent worklog entries in this
repository. Append new dated entries below this notice. Never rewrite, reorder,
summarize, normalize, or delete historical entries. The governance rules for
this file are defined in `AGENTS.md`.

---

### 2026-08-15 Initial repository and governance setup

- Agent used: Claude Code (executing agent), on owner instruction.
- Task performed: created the initial repository (`README.md`,
  `GOVERNANCE_SURFACE.md`, `LICENSE`, `NOTICE`, `CITATION.cff`), then added
  agent-participation governance (`AGENTS.md`, this `AGENT_WORKLOG.md`, and
  `scripts/check-agent-worklog-governance.mjs`) adapted from the sibling
  Meta-Writing Ecology repositories. The sibling worklog histories were not
  copied; this log starts fresh.
- Files changed: `AGENTS.md` (new), `AGENT_WORKLOG.md` (new),
  `scripts/check-agent-worklog-governance.mjs` (new; only the `REPOSITORY`
  constant was changed to this repository).
- Checks run: repository pushed and remote HEAD verified equal to the local
  commit in earlier steps; the worklog governance check will be run as evidence
  once this entry is committed.
- Unresolved questions / decisions reserved to the owner: whether and when to
  make the repository public; cross-linking from other MWE repositories;
  `CITATION.cff` publish-time fields and a DOI-time personal-name author; and
  whether the boundary formulas in `GOVERNANCE_SURFACE.md` should convert `!=`
  to `≠` under the symbol-hygiene rule above.
- Risks / assumptions: the governance rules here are adapted, not verbatim
  copies, from the sibling repositories; an independent review is recommended
  before this surface is relied upon or made public.

### 2026-08-15 Symbol hygiene: convert prose != to the not-equal sign

- Agent used: Claude Code (executing agent), on owner instruction. Logged
  retroactively; this change shipped in commit `3d5d2063` before a worklog entry
  was written, which the second review correctly flagged.
- Task performed: converted 38 prose `!=` occurrences in `GOVERNANCE_SURFACE.md`
  and 1 in `README.md` to the not-equal sign, per the symbol-hygiene rule. The
  `!=` markers inside `AGENTS.md` and this file that describe the rule itself
  were left as literals.
- Files changed: `GOVERNANCE_SURFACE.md`, `README.md`.
- Checks run: 0 `!=` remaining in either file; strict UTF-8 decode, 0 U+FFFD.
- Unresolved questions: none for this change.
- Risks / assumptions: none; a mechanical notation change with no semantic edit.

### 2026-08-15 Second-review remediation

- Agent used: Claude Code (executing agent), on owner instruction, acting on an
  independent second review of the repository envelope.
- Task performed: (1) rewrote `NOTICE`, which was a verbatim sibling-repo file
  that mislabelled this repo as the MWE public corpus, listed four files not
  present here, and contained a personal name --- all removed; (2) fixed the
  licensing signal by placing `scripts/` under the MIT License (new
  `scripts/LICENSE`, SPDX headers) while text/diagrams stay CC BY 4.0, and
  synchronised `README.md`, `NOTICE`, and the surface's License section;
  (3) updated the repository-structure descriptions in `README.md` and
  `GOVERNANCE_SURFACE.md` to list the scaffolding files and separate conceptual
  surface from scaffolding; (4) fixed two real checker defects --- merged-PR
  evidence now requires the PR base to be the integration branch and the PR head
  to equal the current branch tip, and PRs are kept per head branch instead of
  overwritten; the integration tip and branch inventory now share one ls-remote
  observation window instead of a possibly-stale `origin/main`; (5) added a
  mechanical append-only check (the `origin/main` worklog must be an exact byte
  prefix of the working copy); (6) added a Rule Register, an enforcement-maturity
  note, a lineage-resolution and unknown-lineage fail-closed rule, a
  lineage-vs-review-context independence distinction, a live-record
  dependency-footprint / TOCTOU statement, and a layered route-identity model to
  `GOVERNANCE_SURFACE.md`; (7) clarified worklog scope in `AGENTS.md`.
- Files changed: `NOTICE`, `README.md`, `GOVERNANCE_SURFACE.md`, `AGENTS.md`,
  `AGENT_WORKLOG.md`, `scripts/check-agent-worklog-governance.mjs`, and new
  `scripts/LICENSE`.
- Checks run: `node --check` on the checker (syntax OK); the governance check
  itself run before commit (recorded in the round evidence); final sensitive
  scan across all files, including the personal-name pattern the first scan
  missed.
- Unresolved questions / owner-reserved: flip to public; MWE cross-linking;
  branch protection and CI enforcement at release; CITATION `url` / `version` /
  `date-released` and a DOI-time personal-name author.
- Risks / assumptions: the added conceptual sections and the checker changes are
  themselves adapted this round and warrant a further independent review before
  public release.

### 2026-08-15 Third-review remediation

- Agent used: Claude Code (executing agent), on owner instruction.
- Reviewer: independent third review, delivered as pasted findings by the owner.
- Reviewer lineage: unknown (not disclosed to the executing agent).
- Review mode: sequential (review of the pushed HEAD, not a parallel blind pass).
- Reviewed commit: `a992f71c`.
- Review evidence / reference: `versions\20260815-2300-review3-remediation\`
  (this round's evidence); the dispatched brief was
  `versions\20260815-2220-review3-brief\REVIEW3-BRIEF.md`.
- Task performed: (1) resolved the Route Identity vs Review Equivalence
  inconsistency introduced last round --- route identity now identifies the
  route while the lineage relation, not identity, gates reviewer independence,
  and "Review Equivalence Class = Lineage" was replaced with a Review
  Independence Gate stated as a non-transitive dependency predicate;
  (2) downgraded the panel formula to a Lineage-Distinct Review Panel with the
  Effective Independent Review Panel as a subset; (3) refined the blind-pass
  claim to direct-exposure prevention only and distinguished parallel from
  sequential blind review; (4) added an unknown-dependency fail-closed clause and
  a footprint-completeness requirement to the live-record section; (5) checker:
  append-only now binds to the observed integration-commit SHA (read-only fetch
  if absent) and fails closed when indeterminate, and ancestry now reads the
  merge-base exit code directly; (6) added `.gitattributes` pinning LF so the
  byte-prefix invariant does not depend on autocrlf; (7) added optional
  independent-review evidence fields to `AGENTS.md`; (8) minor: Status changed to
  "Independent Review" and the Fork/Derivative license sentence made
  mixed-license.
- Files changed: `GOVERNANCE_SURFACE.md`, `README.md`, `AGENTS.md`,
  `AGENT_WORKLOG.md`, `scripts/check-agent-worklog-governance.mjs`, and new
  `.gitattributes`.
- Checks run: `node --check` (syntax OK); the governance check run before commit;
  full recursive sensitive scan; strict UTF-8, 0 U+FFFD.
- Unresolved questions / owner-reserved: unchanged --- flip public, MWE
  cross-linking, branch protection and CI at release, CITATION
  url / version / date-released and a DOI-time personal-name author.
- Risks / assumptions: the reframings in points 1 to 4 change how the core model
  is stated; they restore internal consistency rather than add new claims, but
  warrant a further independent (ideally parallel blind) review before public
  release.
