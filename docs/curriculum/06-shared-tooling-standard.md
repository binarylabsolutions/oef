# Shared Tooling and Open Standard

*Last updated: 25 Oct 2026 · Proposal, not final*

The curriculum only becomes repeatable if the expertise lives in tooling rather than in individual instructors. This paper covers what that tooling is, in what order it should be built, and how it stays available to other universities rather than exclusive to one.

## Why tooling, and why open

A curriculum document changes nothing on its own. The practical parts of this model — break-fix drills, scored workshops, project assessments — all need fresh content every semester, and producing that by hand each year is exactly the workload no department has. If the scenarios are generated and marked automatically, the cost of running the programme in year five is close to the cost in year one.

Tooling also solves the faculty problem. When every scenario carries its answer key and its marking criteria, the instructor assesses against a rubric rather than having to be the production expert.

The materials should be non-exclusive. Nothing proposed here is specific to one institution, the problems it addresses are nationwide, and a standard adopted by several universities is worth more to employers than one department's internal scheme. The work therefore sits with a separate initiative that any university can adopt, rather than becoming the property of whichever institution pilots it first.

## The four tools

**1. The scenario generator.** One reference system — a project tracker, for example — kept in a known-good state, plus a fault injector that plants defects into its code and its infrastructure: a missing index, an unbounded retry, a container that will not start, a broken token flow, a connection leak. Each generated scenario ships with a hidden answer key, so marking is automatic and every cohort gets fresh faults rather than last year's answers. It runs in containers on ordinary lab machines.

This tool should also produce an architecture view of the reference system, so students diagnose at the diagram level first and drill into the code second. Reading ten thousand lines cold is not a realistic exercise; forming a hypothesis from the architecture and then confirming it in code is how the work is actually done.

**2. The workshop and assessment system.** Each workshop defined as at most five concepts with a fixed, deterministic assessment and a published rubric. The system generates the assessment, marks it, and records the score. Its job is to keep standards consistent across instructors, cohorts and institutions — without that, a score means nothing outside the room it was awarded in.

**3. The verifiable record.** The workshop sheet that accompanies the transcript: every workshop, its concepts, its score, each entry linked to the artefact the student produced and verifiable online by identifier. Issued in an open credential format so it can be attached to a profile anywhere, not only to a university PDF.

**4. The guided project platform.** The build-your-own project list — an HTTP server, a small database, a job queue, a rate limiter — delivered as guided steps with automated tests, in the style of the better commercial learning platforms. GitHub Classroom already provides the autograding, so the first version is a curated project list and test suites rather than a new platform.

## Build order

The pilot does not need all four. The order below starts with what can be assembled from existing tools and defers anything that needs real engineering.

| Stage | What is built | Needed by |
| --- | --- | --- |
| 1 | Curated project list with test suites, run through GitHub Classroom | The pilot elective, first week |
| 2 | Six to eight workshops: content, rubric, fixed assessment | The pilot elective |
| 3 | Reference system with a handful of hand-made fault scenarios and answer keys | The pilot's break-fix drills |
| 4 | Automated fault injection and marking | Second cohort, when hand-made scenarios stop scaling |
| 5 | Verifiable record with online verification and open credentials | First graduating cohort |
| 6 | Guided learning platform | Only if the earlier stages prove out |

Stage 1 is the cheapest useful thing in the whole proposal: a project list and test suites, costing nothing but the time to curate them, and usable next semester.

## Funding and governance

**Free for students, always.** The curriculum, the project list, the workshop content and the assessment tooling are provided to universities at no charge, and nothing a student needs to complete the programme sits behind a payment.

**Paid where it is a professional service.** Faculty training is a different matter: it is delivered to institutions, not students, and it takes real time. Teacher training, train-the-trainer programmes and implementation support can be charged for, and that revenue is what would make the free side sustainable.

**Non-exclusive by design.** Everything developed here is available to other universities on the same terms. The first university to pilot it is the first adopter rather than the owner, which is also the stronger position for the university: being known for having started the standard is worth more than controlling it.

**Governance, eventually.** If several universities adopt the same workshops and assessments, the question of who maintains the standard and verifies the records has to be answered. That resembles what professional bodies do for the licensed engineering disciplines, and is worth planning for — but after the pilot has produced results, not before.

**Open items**

- [ ] Which licence the materials are released under
- [ ] Who maintains the reference system and scenario library between cohorts
- [ ] Whether the first teacher-training cohort is delivered free to establish the model
