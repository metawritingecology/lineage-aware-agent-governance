# Lineage-Aware Multi-Agent Governance Surface

-   **Status:** Public Draft / Independent Review
-   **Document type:** Operational boundary surface
-   **Context:** Meta-Writing Ecology --- candidate / related public
    surface, not a confirmed MWE component
-   **Release level:** Selected structural projection
-   **License:** CC BY 4.0
-   **Authority boundary:** This document does not expose or replace the
    complete internal operational policy, live routing state,
    authorization structure, credential topology, or operator decision
    process from which it was derived.

## Orientation

This document presents a selected public structural account of routing,
review independence, capacity, evidence, convergence, and retained human
authority observed in a high-intensity multi-agent working environment.

It is not a complete operational methodology.

It does not provide a production-ready orchestration system, enterprise
governance product, compliance framework, security architecture,
benchmark, or deterministic policy engine.

The structures described here emerged from actual operation, including
routing conflicts, reviewer saturation, non-convergent revision cycles,
changing model availability, and the need to distinguish delegated
execution from retained judgment.

Some rules are explicit and mechanically checkable. Others remain
heuristic, experimental, or dependent on operator judgment.

Public documentation of a rule does not imply that the underlying
judgment has been fully formalized.

---

## Application Boundary

This surface may be used to examine structural questions such as:

-   how agent routes are distinguished;
-   how reviewer independence is represented;
-   how execution and review roles remain separated;
-   how capacity and availability affect routing;
-   how repeated review is prevented from becoming unbounded inference;
-   how evidence remains attached to completion claims;
-   how mutable operational records differ from static artifacts;
-   how delegated execution remains separated from retained
    answerability.

It should not be interpreted as establishing:

-   universal model rankings;
-   statistical independence between model providers;
-   a complete security model;
-   a general-purpose AI governance standard;
-   an enterprise access-control architecture;
-   a validated productivity methodology;
-   a claim that additional agents necessarily improve outcomes;
-   a claim that the published surface reproduces the internal operating
    system.

The public surface is intentionally incomplete.

`Public visibility ≠ operational completeness`

---

## Structural Separation

A route's identity is represented as a composition of two dimensions:

`Route = Interface × Lineage`

These two dimensions should not be collapsed into one identifier.

Other properties --- such as the execution environment a route runs in,
or the role it is authorized to perform --- are treated as gates and
attributes layered on top of this identity, not as additional identity
dimensions. This separation is deliberate: route identity *identifies the
route*, while the lineage relation between routes governs reviewer
anti-duplication, and gates and attributes determine dispatchability.
Route identity is not by itself the independence test --- two routes with
different identities can still fail to be independent because they share a
lineage. The three must not be conflated.

### Interface

The access surface through which an agent is invoked.

Examples may include browser interfaces, command-line interfaces, direct
APIs, IDE integrations, or aggregation layers.

### Lineage

The model or provider family used as an operational proxy when
evaluating reviewer independence.

Lineage is not asserted here as statistical, epistemic, or architectural
independence.

It is a governance boundary used to prevent multiple interfaces backed
by the same underlying family from being represented as multiple
independent confirmations.

### Lineage resolution

"Model or provider family" spans two scales, and real routes create boundary
cases: the same model served by different providers, the same provider serving
different model families, fine-tuned or distilled derivatives, aggregators that
swap the backing model dynamically, a stable model alias whose provider updates
the version underneath, an open base model hosted by several parties, or a route
whose lineage simply cannot be determined.

Two rules keep this fail-closed:

-   Resolve lineage at dispatch and record it. A fine-tuned or distilled
    derivative binds on both its base and its tuner until ruled otherwise.
-   When lineage cannot be determined, leave it unresolved, and do not let an
    unresolved lineage increase the effective independent reviewer count:

`Unknown lineage ≠ a new independent lineage`

An unidentifiable route therefore cannot be counted as added independence.

### Environment (gate, not identity)

The execution context in which a route operates.

Environment may affect capability, security, concurrency, persistence,
or operational availability. It therefore acts
as a gate on whether a route may accept a given piece of work, and where
that work may run.

Environment does not alter route identity. Running the same lineage in a
different execution context does not create a new route, and does not by
itself produce an additional independent opinion.

### Role (attribute, not identity)

The function a route is authorized to perform within a workflow.

Examples include planning, execution, review, supplementary scanning,
adversarial testing, or fallback execution.

Role is an authorization attribute attached to a route, not an identity
dimension. The same interface-and-lineage identity may be authorized for
different roles at different times without becoming a different route.

### Layered identity

To keep governance identity from being mistaken for a complete runtime endpoint
key, four layers are distinguished:

``` text
Governance Route Identity = Interface × Lineage
Dispatch Instance         = Route Identity × Environment
Review Independence Gate  = lineage relation between routes
Authorized Use            = Dispatch Instance × Role
```

Route Identity identifies the route; it is not by itself the independence test.
Two routes with different identities --- for example `Browser × GPT` and
`API × GPT` --- are two route identities but not two independent reviewers,
because they share a lineage. A Dispatch Instance is the concrete runtime
binding: the same Interface × Lineage in two environments is one route identity
but two dispatch instances, which may differ in credentials, tool access,
network boundary, filesystem, and disclosure authorization. The Review
Independence Gate is not a property of a single route but a *relation between*
routes, evaluated on lineage. Authorized Use is a dispatch instance acting in a
specific role.

Implementers should not use `Interface × Lineage` as a complete runtime endpoint
key; that is the Dispatch Instance's responsibility.

The independence gate is a relation, not a partition, and this matters once
derivatives exist. A fine-tuned or distilled model binds on both its base and
its tuner, so with `A = Base-X + Tuner-P`, `B = Base-X + Tuner-Q`, and
`C = Base-Y + Tuner-P`, `A` shares a base with `B` and a tuner with `C`, while
`B` and `C` share nothing directly. The dependency relation is therefore not
transitive, so lineage does not cleanly partition reviewers into disjoint
equivalence classes. State the gate as a predicate rather than a class:

`Independent(A, B) only if no disqualifying lineage dependency is known between A and B`

Unknown dependencies fail closed, exactly as an unknown lineage does: absence of
*known* shared lineage is not proof of independence.

---

## Non-Equivalence Rules

The following distinctions are foundational to this public surface:

-   interface ≠ lineage
-   availability ≠ independence
-   redundancy ≠ independent confirmation
-   execution ≠ independent review
-   model output ≠ completion evidence
-   process exit ≠ verified success
-   public route description ≠ live route availability
-   remaining quota ≠ operational suitability
-   low cost ≠ qualification
-   repeated inference ≠ information gain
-   delegation ≠ transferred answerability
-   public policy surface ≠ complete internal policy
-   documented heuristic ≠ validated invariant
-   source provenance ≠ downstream endorsement

These distinctions describe boundaries.

They should not be converted into stronger claims without additional
evidence.

---

## Review Independence

Different interfaces using the same lineage may provide useful
redundancy, alternate availability, or implementation diversity.

They should not automatically be counted as independent reviewers.

Conceptually:

`Nominal Reviewer Count ≠ Effective Independent Reviewer Count`

A limited operational approximation counts only lineage distinctness:

`Lineage-Distinct Review Panel = Distinct Qualified Lineages Represented`

This is not the effective independent panel; it is only an upper bound on it:

`Effective Independent Review Panel ⊆ Lineage-Distinct Review Panel`

because a lineage-distinct reviewer that runs a corroboration pass rather than a
blind pass adds no review-context independence (see below). Distinct lineages
are, in any case, not a claim of true independence.

Shared training data, architectural convergence, benchmark optimization,
common information sources, correlated failure modes, or other
dependencies may remain.

The lineage rule therefore establishes a **minimum anti-duplication
boundary**, not a proof of epistemic independence.

### Lineage independence is not review-context independence

Lineage independence is necessary but not sufficient. A second reviewer of a
distinct lineage that is shown the first reviewer's full output --- its
findings, its rejection reasoning, its proposed fixes --- is no longer
informationally independent: its framing, issue selection, and semantic anchors
have already been set by the first review.

`Reviewer independence ≠ informational independence`

At least two axes therefore matter:

-   **Lineage independence** --- the reviewers do not share a model lineage.
-   **Review-context independence** --- the later reviewer is not primed by the
    earlier reviewer's framing.

A blind pass (a reviewer receiving only the artifact and the criteria, not the
prior review) prevents *direct* exposure to the prior review's framing; a
corroboration pass (a reviewer shown the prior findings) does not, and should be
recorded as such. But a blind pass does not by itself guarantee informational
independence: in a *sequential* review the earlier reviewer's influence can
still reach the later one indirectly --- through an artifact that was revised in
response to it, or through acceptance criteria that were changed because of it.

The stricter, genuinely context-independent case is a *parallel blind review*:
the same artifact snapshot, the same criteria snapshot, no prior-review output,
and passes run in parallel. Sequential blind review is a weaker, distinct
category and should be labelled as such. This is a further reason the lineage
rule is only a minimum anti-duplication boundary: it bounds one axis and leaves
the other to be managed explicitly.

---

## Execution / Review Boundary

An executor may inspect its own work.

Self-checking may be useful.

Self-checking does not become independent review merely because it
occurs in a separate run, interface, session, or machine.

Where independent review is required:

`Executor ≠ Independent Reviewer`

If a lineage participates in execution and later participates in review,
that relationship should remain visible rather than being represented as
independent confirmation.

---

## Qualification Before Optimization

Cost and remaining capacity are routing variables.

They are not authorization variables.

A route should first satisfy applicable requirements concerning:

-   task sensitivity;
-   required capability;
-   review tier;
-   evidence;
-   external disclosure;
-   protected resources;
-   execution environment;
-   operator authorization.

Only qualified routes enter cost or capacity optimization.

Conceptually:

`Requirements -> Qualified Route Set -> Capacity / Cost Selection`

not:

`Available Routes -> Cheapest Route -> Retroactive Qualification`

Price should not silently lower assurance requirements.

---

## Capacity as a Multi-Dimensional State

Agent capacity is not represented by a single quota percentage.

Relevant dimensions may include:

1.  **Financial capacity** --- remaining monetary or prepaid balance.
2.  **Quota capacity** --- remaining subscription allowance.
3.  **Concurrency capacity** --- whether the route can presently accept
    work.
4.  **Lineage capacity** --- whether an additional qualified lineage
    remains available.
5.  **Temporal capacity** --- time until constrained capacity becomes
    available again.
6.  **Transfer capacity** --- cost and friction involved in moving work
    to another route.

These dimensions are not interchangeable.

`Subscription ≠ availability ≠ independence`

A route with little remaining quota may remain operationally sufficient
if replenishment is near.

A route with substantial remaining quota may still be unusable if it
fails qualification, disclosure, independence, or environment
requirements.

---

## Temporal Scarcity

Operational scarcity depends partly on time.

A descriptive heuristic is:

`Operational Scarcity ~ Low Remaining Capacity × Long Reset Horizon × Lack of Qualified Substitutes`

This expression is not a calibrated quantitative model.

Its purpose is to prevent a static quota percentage from being mistaken
for the complete state of a resource.

In systems with asynchronous provider reset windows, routing becomes a
rolling capacity problem rather than a single-budget problem.

---

## Fallback Without False Independence

A fallback route may restore access without adding an independent
opinion.

Example:

``` text
Primary Interface
      |
   unavailable
      v
Fallback Interface
      |
      v
Same Lineage
```

Result:

`Availability restored`

but:

`Independent lineage count unchanged`

This distinction prevents interface diversity from being converted into
reviewer diversity.

---

## Convergence Boundary

Repeated review can improve an artifact.

Repeated review can also become a closed computational loop.

A revision cycle should therefore be evaluated for evidence of movement
rather than continued merely because another inference remains
technically possible.

Possible indicators of movement include:

-   new actionable defects;
-   reduction in unresolved defects;
-   clarification of acceptance conditions;
-   material artifact improvement;
-   new evidence affecting the decision;
-   resolution of a previously identified contradiction.

A simplified flow is:

``` text
Execution
    |
    v
Review
    |
    v
Revision
    |
    v
Review
    |
    v
Convergence Check
   / \
  /   \
movement   insufficient movement
  |              |
repeat           v
             Human Owner
```

The exact threshold for insufficient movement may remain
operator-dependent.

This surface does not claim a universal numerical threshold.

---

## Human Escalation

Human escalation is not treated as evidence that the agent system has
necessarily failed.

Some states cannot be resolved by additional inference alone.

Examples may include:

-   conflicting policy interpretations;
-   ambiguous acceptance conditions;
-   unresolved reviewer disagreement;
-   repeated rejection without new information;
-   authority questions;
-   exceptions;
-   risk decisions not delegated to agents.

In these cases, continued autonomous inference may increase compute
without increasing resolution.

The authority transition is therefore:

`Agent Loop -> Boundary Reached -> Human Owner`

not:

`Agent Loop -> Unlimited Additional Agent Loop`

---

## Retained Answerability

Execution may be delegated.

Answerability remains retained unless explicitly transferred through an
authorized structure.

The operator may delegate:

-   decomposition;
-   drafting;
-   implementation;
-   testing;
-   scanning;
-   review.

This does not automatically delegate:

-   final acceptance;
-   interpretation of policy conflict;
-   exception authority;
-   reviewer-panel composition;
-   high-risk authorization;
-   responsibility for the accepted state.

`Delegated execution ≠ transferred answerability`

This surface is structurally adjacent to the broader Meta-Writing
Ecology boundary between delegated execution and retained judgment.

Adjacency does not by itself establish formal dependency or ontology
status.

---

## Evidence / Completion Boundary

An agent statement that work is complete is not necessarily completion
evidence.

Likewise:

`exit status == 0`

does not necessarily establish:

`intended operation completed correctly`

Depending on task conditions, evidence may include:

-   artifact identity;
-   target identity;
-   repository state;
-   test results;
-   logs;
-   completion sentinels;
-   reviewer findings;
-   explicit approval;
-   required authorization records.

Evidence requirements should follow the relevant task boundary.

Agent confidence is not a substitute for required evidence.

---

## Live Operational Records

Some records are expected to change during normal system operation.

Examples may include route state, availability state, dispatcher state,
or other explicitly designated operational records.

A verification model designed for static artifacts may become
self-conflicting when applied unchanged to legitimately mutable records.

The structural distinction is:

``` text
Static Artifact
      |
      v
Whole-artifact identity may be appropriate


Live Operational Record
      |
      v
Read identity
+ relied-upon content
+ relevant operational state
```

The objective is not to weaken integrity.

The objective is to bind verification to the information actually relied
upon by a decision.

A change to relied-upon content may require fail-closed behavior.

An unrelated legitimate concurrent update does not necessarily
invalidate the earlier read.

Designation as a live operational record must itself remain bounded.

`Mutable ≠ exempt from verification`

`Live record ≠ unrestricted exception`

### Proving a concurrent update is unrelated

"An unrelated update does not invalidate the earlier read" is only safe if
"unrelated" can be shown, not assumed. The weak version --- "this field did not
change, so it is fine" --- fails when a different field changed the meaning of
the field that was read.

A more complete statement binds the decision to a declared footprint:

`Decision = f(snapshot, dependency footprint)`

Revalidation then targets neither the whole file nor an arbitrary field, but:

-   the relied-upon fields,
-   plus any declared dependencies of those fields,
-   plus the snapshot / version identity under which they were read.

If any of those changed between read and use, fail closed; an update entirely
outside that footprint does not invalidate the read. This is a
time-of-check-to-time-of-use (TOCTOU) boundary, and stating the footprint
explicitly is what keeps relied-upon-content verification from degrading into an
exploitable "the one field I looked at is unchanged" loophole (Review
Question 8).

This is only safe if the footprint is complete. The dangerous case is not the
declared dependency but the *undeclared* one, and it fails closed the same way
an unknown lineage does:

`Unknown dependency ≠ unrelated dependency`

If the completeness of the dependency footprint cannot be established, broaden
the verification boundary or fail closed. "Outside the footprint" may be treated
as unrelated only when the footprint is known to be complete; otherwise an
apparently unrelated change may have altered the meaning of a relied-upon field
through a dependency that was never declared.

---

## Reviewer Saturation

Review capacity is finite.

A workflow can exhaust useful independent review capacity while
execution capacity remains available.

This produces a distinct state:

`Execution capacity > Qualified independent review capacity`

Possible responses include:

-   waiting for review capacity to return;
-   reducing the artifact into independently reviewable slices;
-   escalating to the operator;
-   using an explicitly permitted adversarial-testing route;
-   deferring acceptance.

Adding another interface from an already represented lineage does not
resolve reviewer-lineage saturation.

---

## Adversarial Testing Boundary

Adversarial testing may be used to search for failure modes after
ordinary review routes become insufficient, saturated, or structurally
repetitive.

It should not automatically be treated as another independent reviewer
vote.

Its function is different.

`Review asks: Is the artifact acceptable under the review criteria?`

`Adversarial testing asks: Under what conditions does the artifact fail?`

The two operations may overlap, but they should not be collapsed.

A successful adversarial pass does not prove correctness.

A failed adversarial pass may expose a new boundary requiring policy
revision, artifact revision, or operator judgment.

---

## Governance Overhead

Governance consumes computation.

The existence of a control does not establish that the control is
cost-effective.

For analytical purposes, compute may be separated into:

### Productive compute

Work directly contributing to an accepted artifact, state transition, or
decision.

### Necessary assurance overhead

Work required to establish sufficient confidence, such as context
acquisition, testing, evidence verification, or independent review.

### Avoidable compute

Work that does not materially improve the accepted state or confidence
boundary.

Possible examples include:

-   repeated loading of unchanged context;
-   duplicated same-lineage review represented as independent review;
-   non-convergent revision cycles;
-   repeated findings without new actionable information;
-   unnecessary review stages;
-   work discarded because routing constraints were checked too late.

This classification remains observational.

The current surface does not define a universal compute-efficiency
threshold.

---

## Operational Failure Case: Non-Convergent Review

A real operational pattern motivating this surface involved an artifact
repeatedly moving between execution and review without adequate
convergence.

The relevant structural failure was not simply:

`many revisions`

The relevant question became:

`Does another cycle still produce information?`

A generalized failure sequence is:

``` text
Reviewer rejects
      |
      v
Executor revises
      |
      v
Reviewer rejects
      |
      v
Executor revises
      |
      v
Rejection structure persists
      |
      v
Marginal information gain approaches zero
      |
      v
Escalate
```

Possible underlying causes include:

-   conflicting rules;
-   unstable reviewer interpretation;
-   ambiguous acceptance criteria;
-   incomplete authority;
-   executor misunderstanding;
-   incompatible simultaneous requirements.

The operational response was to introduce a bounded escalation principle
rather than allow indefinite autonomous cycling.

The public surface does not expose the original artifact, exact
operational thresholds, or internal routing details.

---

## Operational Failure Case: Mutable Registry Conflict

Another operational pattern involved applying static-artifact
verification assumptions to a record whose legitimate function required
ongoing modification.

A whole-file identity check could treat an unrelated concurrent update
as invalidation even when the content relied upon by the current
operation had not changed.

The resulting structural question was:

> What exactly must remain stable for a decision based on a live record
> to remain valid?

The emerging answer was not to remove verification.

It was to narrow verification toward the read and relied-upon content
while retaining fail-closed behavior when relevant state changes.

This remains an operationally derived rule and should be independently
challenged.

---

## Rule-State Classification

Not all governance statements have the same status.

A public implementation may distinguish at least four states:

### HARD

A rule intended to be mechanically checkable or treated as an invariant
within its declared scope.

### HEURISTIC

A repeatable operating judgment supported by experience but not treated
as universally valid.

### OWNER

A decision intentionally retained by the human operator.

### EXPERIMENTAL

A rule or interpretation still undergoing observation, review, or
failure testing.

Movement between these states should not be assumed.

For example:

`OWNER -> HEURISTIC`

requires evidence that previously tacit judgment can be represented
consistently.

Likewise:

`HEURISTIC -> HARD`

requires more than repeated personal use.

## Rule Register

The taxonomy above is only descriptive until each rule is assigned a state. This
register does that. It is part of the surface, not a separate specification, and
the state assignments are themselves open to challenge.

| Rule | State | Scope | Enforcement |
|---|---|---|---|
| Executor cannot count as its own independent reviewer | HARD | independent review | procedural |
| Same lineage across interfaces / machines / sessions is one reviewer | HARD | independent review | procedural |
| Unknown lineage does not increase independent reviewer count | HARD | independent review | procedural |
| Lineage independence ≠ review-context independence | HEURISTIC | independent review | procedural |
| Qualification before cost / capacity optimization | HARD | routing | operator |
| Price cannot lower task tier, review floor, evidence, protected paths, or owner authority | HARD | routing / authority | operator |
| Route identity = Interface × Lineage (environment / role are gate / attribute) | HARD | routing identity | procedural |
| Convergence-movement test before another review cycle | HEURISTIC | review loop | operator |
| Human escalation is an authority transition, not an agent failure | HEURISTIC | escalation | operator |
| Model output or exit status is not completion evidence | HARD | evidence | mechanical where evidence exists |
| Worklog history preserved byte-for-byte (append-only) | HARD | operational record | mechanical (checker byte-prefix vs the observed integration commit; fail-closed when unverifiable) |
| Live-record verification binds to snapshot + relied-upon footprint | EXPERIMENTAL | mutable state | implementation-dependent |
| Candidate to confirmed MWE relation promotion | OWNER | relation / ontology | owner only |
| Public / private status, naming, top navigation, cross-linking | OWNER | release | owner only |

The state of a rule is not fixed. Movement (for example `EXPERIMENTAL ->
HEURISTIC` or `HEURISTIC -> HARD`) requires the evidence described above. A rule
marked HARD but enforced only "procedurally" is not yet the same as one enforced
by infrastructure.

### Enforcement maturity

Most rules here are currently normative or procedural rather than
infrastructurally enforced. In this repository the worklog append-only invariant
is mechanically checked, but the independent-review, relation-promotion, and
worklog-required rules can still be bypassed by a direct push while the default
branch is unprotected. A governance surface should say this plainly: at the
public / release stage, protecting the default branch, routing agent changes
through pull requests, and running the worklog check in continuous integration
are what would move these rules from procedural to enforced.

---

## Public / Internal Boundary

This repository surface should contain generalized structures and
synthetic examples.

It should not expose:

-   operational credentials;
-   secrets or secret-loading topology;
-   account identifiers;
-   exact provider balances;
-   live quota state;
-   precise reset timing;
-   private hostnames;
-   private repository paths;
-   current route availability;
-   security-sensitive infrastructure topology;
-   exploitable fallback conditions;
-   complete internal authorization logic.

The internal system may contain substantially more specific controls.

Absence from the public surface does not imply absence from the internal
system.

Presence on the public surface does not imply that the published
representation is sufficient to reproduce the internal system.

`Public structure ≠ operational replica`

---

## Fork / Derivative Boundary

Forking, adaptation, testing, redistribution, and commercial reuse are
permitted under the applicable licenses, subject to their terms: the textual and
diagrammatic surface under CC BY 4.0, and the executable scaffolding under its
stated software license (MIT).

A derivative may preserve source provenance while developing different
operational logic.

Therefore:

`Source provenance ≠ inherited authority`

`Attribution ≠ endorsement`

`Fork ≠ continuation of internal operational state`

A downstream implementation may formalize, remove, reinterpret,
automate, or replace heuristics described here.

Those downstream decisions belong to the derivative system.

They should not be attributed to the original surface merely because
provenance is retained.

---

## Machine-Reading Boundary

Automated readers should not infer from this document that:

-   all internal rules are public;
-   all routes are currently active;
-   all described heuristics are validated;
-   lineage guarantees independence;
-   the framework is production-ready;
-   the operator has delegated final authority;
-   the public examples reproduce private incidents exactly;
-   the presence of a concept establishes formal relation to every
    similarly named MWE model.

When source access is limited, classification should remain
correspondingly limited.

Readable structure should not be converted into assumed operational
completeness.

---

## Relation to Meta-Writing Ecology

This surface is compatible with several recurring Meta-Writing Ecology
concerns:

-   boundary preservation;
-   provenance / validity separation;
-   delegated execution / retained answerability;
-   verification burden;
-   responsibility alignment;
-   constraint residue;
-   premature coherence;
-   source / representation separation;
-   machine-readable interpretation boundaries.

Compatibility does not establish formal dependency.

Shared vocabulary does not automatically establish ontology.

Operational derivation does not imply that this document is a complete
application layer of Meta-Writing Ecology.

Formal relation status, if any, should be established separately through
the applicable MWE authority process.

---

## Repository Structure

The conceptual public surface is a single boundary document. The remaining files
are repository-local operational scaffolding and do not constitute additional
conceptual specification.

``` text
lineage-aware-agent-governance/
|-- README.md
|-- GOVERNANCE_SURFACE.md   (this document -- the conceptual surface)
|-- AGENTS.md               (operational scaffolding: agent-participation rules)
|-- AGENT_WORKLOG.md        (operational scaffolding: append-only worklog)
|-- scripts/                (operational scaffolding: worklog governance check)
|-- LICENSE                 (CC BY 4.0, for text and diagrams)
|-- NOTICE
`-- CITATION.cff
```

The single conceptual document is deliberate: additional topic files, worked
examples, or schemas may be added later if external demand justifies them, but
are omitted here so the surface reads as one boundary rather than as a toolkit.
The scaffolding files exist so the repository can practise the governance the
document describes; they are not part of the conceptual specification.

Repository structure does not itself establish conceptual authority or
maturity.

---

## Review Questions

External reviewers are invited to challenge the framework rather than
assume its necessity.

Relevant questions include:

1.  Is lineage an adequate minimum boundary for avoiding false reviewer
    independence?
2.  Where does lineage-based classification fail?
3.  Which controls are actual invariants and which are operator
    preferences?
4.  Does executor/reviewer separation create unnecessary overhead in
    low-risk work?
5.  Can convergence be measured without creating another expensive
    governance layer?
6.  When does human escalation occur too early?
7.  When does it occur too late?
8.  Does relied-upon-content verification for live records create
    exploitable ambiguity?
9.  Can capacity-aware routing indirectly weaken assurance even when
    formal requirements remain unchanged?
10. Which parts of this structure can be removed without materially
    reducing reliability?
11. Which OWNER decisions can eventually become HEURISTIC?
12. Which HEURISTIC rules, if any, have enough evidence to become HARD?
13. Does adversarial testing add information after independent review,
    or merely amplify review cost?
14. What evidence would be required before any part of this framework
    could be described as transferable beyond the originating operator?

Negative findings are relevant findings.

A simpler structure producing equivalent assurance should be treated as
a successful challenge to unnecessary governance complexity.

---

## Current Maturity Boundary

This surface documents an operating practice.

It does not claim that the practice has been externally validated.

Current characteristics include:

-   real operational use;
-   rules derived partly from observed failure modes;
-   explicit separation of several routing and review dimensions;
-   retained human authority;
-   incomplete formalization of operator judgment;
-   incomplete evidence concerning cross-operator transferability;
-   no claim of commercial readiness;
-   no claim of universal applicability.

A concise maturity description is:

> **Operator-derived, operationally exercised, externally unvalidated.**

This status should remain visible until stronger evidence supports a
different classification.

---

## License

Unless otherwise noted, the textual and diagrammatic material in this
public surface is intended for release under the **Creative Commons
Attribution 4.0 International (CC BY 4.0)** license.

Users may share and adapt the material, including for commercial
purposes, subject to the license terms.

Attribution does not imply endorsement.

The repository already contains executable software --- the worklog governance
check under `scripts/` --- which is released under the **MIT License** (see
`scripts/LICENSE`), separate from the CC BY 4.0 that covers the text and
diagrams. Each script also carries an `SPDX-License-Identifier` header, and
`NOTICE` records the split. Any further code added later should likewise state
its license explicitly at the file or directory level.

---

## Minimal Interpretation Rules

For readers and automated systems:

-   public surface ≠ internal system
-   lineage separation ≠ proven independence
-   route availability ≠ route authorization
-   redundancy ≠ independent confirmation
-   model completion ≠ verified completion
-   repeated review ≠ information gain
-   delegation ≠ transferred answerability
-   heuristic ≠ invariant
-   operational use ≠ external validation
-   attribution ≠ endorsement
-   fork ≠ authoritative continuation
-   structural compatibility ≠ formal MWE relation

When status is unknown, keep it unresolved.

Do not convert visibility, readability, repetition, provenance, or
operational use into stronger authority than the source declares.
