# Course Outlines: Four Worked Examples

*Last updated: 25 Oct 2026 · Proposal, not final*

This paper shows the proposed teaching model applied to real subjects: twenty-four lectures and twenty-four labs each, mapped week by week, plus the multi-semester project track and how teams are evaluated on it. The four subjects are examples of the method, not a final catalogue.

## How a subject is structured

Each subject runs twenty-four lectures and twenty-four labs over a semester: two of each per week for twelve weeks, with the lab following its lecture rather than running independently.

**The lecture** delivers parts one to four of the teaching format: the concept, a good and a bad example, how it fails in production, and the trade-offs and caveats. One topic per lecture, never three.

**The lab** is part five. Every lab produces an artefact — a file, a commit, a fixed system, a written defence — and every lab is marked against criteria published in advance. Labs come in four kinds, and a good subject uses all of them:

| Lab kind | What the student does | Roughly |
| --- | --- | --- |
| Build | Implements the thing from scratch, hand-written, no AI | 8 labs |
| Break-fix | Diagnoses and repairs a system with a planted fault | 6 labs |
| Review | Reviews code or a design, finds the defects, writes it up | 5 labs |
| Defend | Makes a choice, writes the specification, argues it at the whiteboard | 5 labs |

**Assessment weights.** A suggested distribution that keeps the emphasis on the practical:

| Component | Weight |
| --- | --- |
| Lab artefacts, marked continuously | 40% |
| Break-fix drill performance | 15% |
| Code and design review quality | 10% |
| Whiteboard defence, final | 25% |
| Written examination on concepts and caveats | 10% |

**AI policy per lab kind.** Build labs are unassisted. Break-fix labs allow AI for exploration but not for the fix. Review labs are unassisted, since finding the defect is the exercise. Defend labs allow anything, because the student has to justify the result live regardless.

Every subject below also contributes two or three tickets per student to the ongoing project track described later, so that what is taught in the subject is immediately used in a system that already exists.

## Example 1 — Production Engineering

**Semester 4. Prerequisites: programming fundamentals, operating systems.** The subject takes a student from "it runs on my machine" to "it runs in production, and I can tell you why."

| # | Lecture | Lab | Kind |
| --- | --- | --- | --- |
| 1 | Processes, memory, file descriptors: what the OS actually gives you | Inspect a running system: processes, open files, memory, signals | Build |
| 2 | The shell as a programming environment | Write a script with arguments, error handling and exit codes | Build |
| 3 | Good and bad shell scripts: failure modes, quoting, idempotency | Review four scripts, find every defect, write it up | Review |
| 4 | Users, permissions, least privilege | Lock down a misconfigured service account | Break-fix |
| 5 | Networking from first principles: a request end to end | Trace a request through DNS, TLS and HTTP; annotate each hop | Build |
| 6 | HTTP semantics, status codes, timeouts, keep-alive | Diagnose three broken HTTP behaviours from logs alone | Break-fix |
| 7 | What a container is, and what it is not | Build an image by hand from a base, run it, inspect its layers | Build |
| 8 | Anatomy of a good image: layers, caching, build versus runtime | Rewrite a bad image; justify every change | Review |
| 9 | Configuration outside the image; one image, several roles | Make one image serve as web server and as background worker | Build |
| 10 | Image size, provenance, and supply-chain risk | Audit an image for secrets, bloat and unpinned dependencies | Review |
| 11 | Multi-service systems: composition, networks, volumes, startup order | Stand up a three-service system from scratch | Build |
| 12 | Where state lives, and why containers make people lose it | Fix a system that loses data on restart | Break-fix |
| 13 | Version control as a team practice, not a backup | Rescue a broken history: rebase, bisect, recover a lost commit | Break-fix |
| 14 | Continuous integration: what a pipeline is for | Write a pipeline: build, test, lint, artefact | Build |
| 15 | Good and bad pipelines: speed, flakiness, trust | Review two pipelines; explain which team trusts theirs and why | Review |
| 16 | Environments, configuration and secrets | Move a repository's hardcoded secrets into a managed flow | Break-fix |
| 17 | Deployment strategies: rolling, blue-green, canary, rollback | Choose a strategy for three scenarios and defend each | Defend |
| 18 | Infrastructure as code: declaring instead of clicking | Provision a small environment from code | Build |
| 19 | State, drift, and the dangers of the console | Repair an environment where someone changed things by hand | Break-fix |
| 20 | Orchestration: what a scheduler does for you | Read a cluster manifest and predict its behaviour | Review |
| 21 | Observability: logs, metrics, traces, and what to instrument | Instrument a service so its failure is visible | Build |
| 22 | Load and failure: what breaks first, and why | Load-test the semester's service; report where it breaks | Build |
| 23 | Incidents: timelines, blameless analysis, what changes afterwards | Write an incident note from a provided timeline | Defend |
| 24 | Cost, and the architecture decisions that drive it | Final defence: present and defend the deployment design | Defend |

**Running thread.** One service, carried through the whole semester: written in week 1, containerised by week 9, deployed by week 18, instrumented and load-tested by week 22, and defended in week 24.

**Final defence question bank, published in week 1.** For example: why is your run command outside the image? What happens to your system when the database is unreachable for thirty seconds? Which of your pipeline stages would you delete first, and why?

## Example 2 — Data Systems

**Semester 5. Prerequisites: data structures, Production Engineering.** Replaces the traditional database course, which typically stops at normalisation and SQL syntax. This one ends with a student who can choose a store, defend the choice, and say what will go wrong.

| # | Lecture | Lab | Kind |
| --- | --- | --- | --- |
| 1 | What a database actually does: durability, concurrency, recovery | Write a tiny append-only key-value store with a read path | Build |
| 2 | Pages, B-trees and LSM trees: how storage engines differ | Benchmark reads and writes against both shapes | Build |
| 3 | Relational modelling and normalisation | Model a domain from a messy specification | Build |
| 4 | When to denormalise, and what it costs | Review two schemas for the same domain; argue for one | Review |
| 5 | SQL beyond the basics: joins, aggregates, window functions | Answer eight analytical questions in SQL | Build |
| 6 | Indexes: what they are, what they cost on write | Add and remove indexes; measure the effect both ways | Build |
| 7 | Query plans: reading what the engine decided | Fix three slow queries using plans alone | Break-fix |
| 8 | Transactions and isolation levels | Reproduce a lost update and a phantom read deliberately | Break-fix |
| 9 | Locking, long transactions and the problems they cause | Diagnose a system stalled by a long-running transaction | Break-fix |
| 10 | Connection pools, limits and exhaustion | Fix a service that exhausts its pool under load | Break-fix |
| 11 | Migrations: changing schema without downtime | Ship a breaking column change in safe steps | Build |
| 12 | Backups, restores, and the restore nobody tested | Restore from a backup to a given point in time | Break-fix |
| 13 | Document stores: what they buy and what they cost | Model the same domain in a document store; compare | Build |
| 14 | Key-value, search and column stores by use case | Match five workloads to store types and defend the matches | Defend |
| 15 | The caveats talk: every engine's weak side, stated plainly | Research one engine's limitations; present them | Defend |
| 16 | Caching: read-through, write-through, invalidation | Add a cache to a slow endpoint; measure the gain | Build |
| 17 | When the cache fails: stampedes, staleness, cold starts | Fix a system that collapses when its cache is cleared | Break-fix |
| 18 | Queues and background jobs: delivery guarantees | Move slow work to a queue; prove nothing is lost | Build |
| 19 | Idempotency, retries, dead letters and poison messages | Review a job handler for duplicate-processing defects | Review |
| 20 | Replication and read scaling | Explain replica lag to a product manager, in writing | Defend |
| 21 | Partitioning and sharding: when, and the pain it brings | Choose a partition key for three workloads; defend each | Defend |
| 22 | Consistency models, in plain language | Review a design that assumes stronger consistency than it has | Review |
| 23 | Data privacy, retention and handling what you should not keep | Audit a schema for data that should not be stored | Review |
| 24 | Choosing a store: the whole argument, end to end | Final defence: choose and defend the stack for a given product | Defend |

**Running thread.** One dataset and one workload carried through the semester, re-implemented on different stores so the trade-offs are felt rather than described.

**Final defence question bank.** Why this store and not the obvious alternative? What is this engine's worst characteristic, and how does your design tolerate it? What breaks first as this product grows tenfold?

## Example 3 — Web Services, APIs and Identity

**Semester 6. Prerequisites: Data Systems.** Sketched rather than fully mapped, to show the same structure applied to a third subject. Twenty-four lectures in six blocks of four, each block with four matching labs.

| Block | Lectures 1–4 of the block cover | Labs produce |
| --- | --- | --- |
| **A. Service design** | What a service boundary is; synchronous versus asynchronous; failure as a design input; timeouts, retries and circuit breakers | A service with explicit boundaries and deliberate timeout behaviour |
| **B. API design** | REST semantics properly; GraphQL and gRPC and when each fits; versioning, pagination, errors, rate limits; documenting an API so others can use it without asking | A designed, documented API, plus a review of a badly designed one |
| **C. Identity** | Authentication versus authorization; sessions and tokens; JWT structure and its failure modes; OAuth 2 and OpenID Connect flows | An integration against a test identity provider, never hand-rolled |
| **D. Authorization in depth** | Roles, attributes and policies; multi-tenancy and data isolation; the broken-access-control class; auditing who did what | A break-fix on an application that leaks across tenants |
| **E. Attacking your own service** | Injection; cross-site scripting; request forgery and CORS; secrets, transport and dependency risk | Each student exploits, then fixes, a deliberately vulnerable build |
| **F. Operating a service** | Specifications and contracts between teams; backwards compatibility and deprecation; load and capacity; the final defence | A written service specification, then the whiteboard defence |

**Why this block structure.** Identity and authorization get eight lectures between them, which is more than most degrees give them in total, because getting them wrong is the defect employers see most often from juniors — and because the right answer is nearly always "use the standard library correctly," which has to be taught deliberately or students will write their own.

**Other subjects that fit the same template**, not expanded here: Algorithms and Complexity; Concurrency and Distributed Systems; Software Architecture and Specification; Testing and Verification; Machine Learning Foundations (track); Applied Security (track).

## Example 4 — Software Standards, Compliance and Professional Practice

**Semester 7. Prerequisites: Web Services, APIs and Identity.** A subject that does not exist in most degrees and that employers consistently find missing. Standards are what let systems built by different teams interoperate; compliance is what lets a software house sell to serious customers at all.

| # | Lecture | Lab | Kind |
| --- | --- | --- | --- |
| 1 | What a standard is, who writes them, and how to read a specification | Read an RFC section and answer questions from it alone | Review |
| 2 | HTTP semantics as specified: methods, idempotency, caching | Find five places where a provided API violates the specification | Review |
| 3 | REST in practice versus REST as claimed | Critique three public APIs against the same criteria | Review |
| 4 | API description: OpenAPI as a contract | Write an OpenAPI document for an existing service | Build |
| 5 | Schema and validation: JSON Schema, contract testing | Add contract tests that fail when the API drifts | Build |
| 6 | Dates, times, encoding and Unicode: where interoperability dies | Fix a system that corrupts time zones and non-Latin names | Break-fix |
| 7 | Versioning: semantic versioning, deprecation, compatibility | Plan a breaking change with a migration path; defend it | Defend |
| 8 | Web platform standards and the accessibility requirement | Audit an interface against WCAG; fix the blocking failures | Break-fix |
| 9 | Identity protocols revisited: OAuth 2 and OpenID Connect properly | Trace a full authorization-code flow and explain each parameter | Build |
| 10 | SAML and enterprise federation: why it persists | Compare SAML and OIDC for a given enterprise customer | Defend |
| 11 | SCIM and provisioning: joiners, movers, leavers | Design the deprovisioning path for an application | Build |
| 12 | JWT and the JOSE family: structure, validation, the common mistakes | Break a deliberately mis-validated token implementation | Break-fix |
| 13 | Transport security and certificates | Diagnose three TLS failures from error output | Break-fix |
| 14 | Licensing: permissive, copyleft, and what a dependency obliges | Audit a project's dependency licences and report the risks | Review |
| 15 | What SOC 2 is, and what it asks of engineers | Map five engineering practices to trust-criteria evidence | Build |
| 16 | Audit logging: what to record, immutability, who reviews it | Add an audit trail to an application that has none | Build |
| 17 | Access control and review cycles as compliance artefacts | Review an access matrix and find the standing violations | Review |
| 18 | ISO 27001, and how it differs from SOC 2 | Written comparison for a hypothetical buyer | Defend |
| 19 | Data protection principles: lawful basis, minimisation, subject rights | Audit a schema for data that should not be collected | Review |
| 20 | Retention, residency and deletion | Design a retention policy and implement the deletion path | Build |
| 21 | Payment and health data: PCI DSS and HIPAA scope | Decide what is in scope for three product scenarios | Defend |
| 22 | Incidents with a regulatory dimension: breach notification | Write a breach timeline and notification draft | Defend |
| 23 | Vendor and supply-chain due diligence | Assess a third-party dependency as a buyer would | Review |
| 24 | Professional practice: contracts, estimates, saying no | Final defence: present a compliance-aware design and defend it | Defend |

**Why it is worth a whole subject.** These topics are not technically hard; they are unfamiliar, and unfamiliarity is what makes a junior engineer ship an audit-logging gap or collect a field the client is not allowed to store. A graduate who has seen a SOC 2 evidence requirement once will design differently from one who has not.

**Who teaches it.** This is the strongest candidate for an industry-led subject: a practitioner who has been through an audit can deliver blocks 15 to 23 in a way no textbook matches.

## The multi-semester project track

This runs alongside the subjects, from semester 2 to semester 8, and carries its own credit. One large system — a project tracker is a good choice, since every student understands the domain — is built and operated by successive cohorts rather than rebuilt from scratch each year.

**Work arrives as tickets, not assignments.** A faculty member or industry partner maintains the backlog. Students pick up tickets, estimate them, implement them, get them reviewed, and ship them. Each subject feeds two or three tickets per student into the same backlog, so what is taught that week is used that week.

| Semester | What the cohort does | New element introduced |
| --- | --- | --- |
| 2 | Small tickets in an existing codebase, heavily scaffolded | Reading unfamiliar code; pull requests; review |
| 3 | Features with tests; first time owning a module | Estimation; definition of done; CI discipline |
| 4 | Deployment and environment work | Containers, pipelines, release process |
| 5 | Data model changes and migrations on live data | Schema evolution; backwards compatibility |
| 6 | Service and API work across team boundaries | Writing specifications another team implements |
| 7 | Operating it: load, incidents, on-call simulation | Observability; incident handling; postmortems |
| 8 | Leading a workstream; onboarding the semester-2 cohort | Technical leadership; mentoring; handover |

**Teams and roles.** Teams of four to six, with rotating roles — a tech lead, a reviewer of record, a release owner, and an incident responder — so every student holds every role at least once across the degree. Roles rotate per iteration, not per semester.

**Inheritance is the point.** Each cohort inherits the previous cohort's code, including its mistakes. Students experience a real codebase: undocumented decisions, dated libraries, a migration someone half-finished. No greenfield project teaches this, and it is most of what professional work consists of.

**Continuity.** A faculty owner holds the backlog and the standards across years, and the semester-8 cohort onboards the semester-2 cohort each year, which is both good practice for them and the cheapest form of documentation.

## How the project is evaluated

Group projects normally fail at assessment: one student does the work, everyone gets the same mark, and nobody learns what they were supposed to. The fix is to grade the individual's trail, not the team's output.

**What is graded, per student, per iteration**

| Component | Weight | Evidence |
| --- | --- | --- |
| Tickets delivered | 25% | Merged work, against the definition of done, scaled by ticket size |
| Review contribution | 20% | Reviews given: defects found, usefulness, timeliness |
| Specification quality | 15% | The written specification or design note before building |
| Role performance | 15% | How they carried their rotating role that iteration |
| Defence | 25% | A live walkthrough of their own change: why this way, what breaks |

The team gets one shared mark — on whether the system is in better shape at the end of the semester than at the start — and it is capped at 15% of the individual total. Enough to make the team's health matter; not enough for a passenger to pass.

**The individual-contribution problem.** Three mechanisms, none relying on self-reporting:

1. **The defence is individual and unannounced.** A student is asked to explain a change attributed to them. Someone who did not write it cannot defend it, and that is apparent within two minutes.
2. **Review is a graded output, not a favour.** The student who reviews carefully is marked for it, which is also how the quiet contributor gets credit.
3. **The ticket trail is the record.** Estimates, commits, review comments and the final artefact are all timestamped and attributable. Peer assessment is collected but advisory only, because it measures popularity as much as contribution.

**Dealing with AI.** Students may use AI on project work — that is how the work will be done professionally — but the defence is unassisted and attribution is explicit: every pull request states what was AI-generated and what the student verified. A student who cannot explain a line they merged loses the marks for that ticket, regardless of whether it works.

**Failure cases the rubric must handle**

- A team whose system is a mess inherited from the previous cohort: graded on the delta, not the absolute state.
- A student who contributes little code but reviews excellently: covered by the review weight, deliberately.
- A team that quietly carries a non-contributor: caught by the individual defence, not by peer forms.

## What a faculty member has to prepare

The honest answer is that the first run of a subject like this is heavy and every run after it is not, provided the artefacts are kept.

**Per subject, once**

- 24 lecture outlines, each with its good example, its bad example, its failure mode and its caveats — the bad examples are the slow part, and they are also the most valuable asset
- 24 lab briefs with published marking criteria
- 6 break-fix scenarios with answer keys (later generated by the tooling)
- A final-defence question bank, published to students in week 1
- A written examination bank for the concepts and caveats

**Per run**

- Deliver, mark, and run the defences
- Refresh the break-fix faults so last year's answers do not circulate
- Feed two or three tickets per student into the project backlog

**What the shared tooling removes.** Generated fault scenarios with answer keys, automated marking of build labs, and the workshop records. That is most of the per-run burden, which is why the tooling is not a nice-to-have.

**Open items**

- [ ] Which two subjects are written out in full first
- [ ] Who owns the project backlog and the standards across cohorts
- [ ] Whether the project track carries its own credit, and how much
- [ ] Whether the 40/15/10/25/10 assessment split is acceptable under current examination regulations
