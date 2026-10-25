# Software Engineering Education in the AI Era

*Last updated: 25 Oct 2026 · Proposal, not final*

AI has made writing code cheap, so the degree should stop spending most of its four years on it. This paper proposes that a university keep coding as a literacy, move systems knowledge and engineering judgement to the centre of the curriculum, and prove both through a workshop and project record employers can verify.

## Why the curriculum must change

The skill our degree spends most of its time on is being abstracted away, and the degree is not even delivering that skill.

Every abstraction shift in computing has moved value upward. Assembly programmers once hand-tuned what compilers produced badly; once compilers became trustworthy, almost nobody read assembly, and the work moved to higher languages. Photography did the same to painting: composition, lighting and perspective stayed valuable, but brush control stopped being the price of entry, and a new craft formed around deciding what image to make.

Natural language is now becoming the top abstraction over code. If that holds, the scarce skills are specifying what to build, choosing an approach and defending it, and verifying the result — not typing the implementation.

The second argument does not depend on any prediction about AI. Our graduates today frequently cannot write working code after four years, and most have never met Docker, a cloud console, a load balancer, a queue, a cache, an API standard, an authentication protocol or a common vulnerability class. The current curriculum already fails at its own target. Changing it is not a bet on AI; it is overdue either way.

## Principles

Seven principles decide what goes in every course and every assessment.

1. **Coding stays, as a literacy.** Year one is hand-written code with no AI assistance. A student who has never struggled to write code cannot read, judge or correct it, and fluency has to become automatic before attention is free for the problem itself.
2. **Judgement is the new core.** The graduate's defensible skill is the whiteboard defence: why this database, this queue, this boundary, and what breaks if it is wrong.
3. **Specifications outrank implementations.** Tests prove only that code matches the specification. A wrong specification passes every test, so writing specifications and acceptance criteria is a graded skill, not a formality.
4. **Depth over coverage.** Fewer topics, each taken to production standard. A list of terms memorised for an exam reproduces the problem we already have.
5. **Categories and standards, not brands.** Teach caching, not Redis; teach federated identity, not one vendor's SDK. Brands are the examples, never the syllabus.
6. **Assemble before you build.** Students learn to use battle-tested libraries and frameworks for solved problems — authentication, cryptography, queues, admin layers — and learn why hand-rolling them is a defect, not an achievement.
7. **Nothing is examined that was not practised.** Every concept has a lab in which the student breaks it, fixes it, or defends it.

## Degree structure

We recommend one generalist Computer Science bachelor's degree, with specialization carried as a spine across semesters rather than swapped into the final year.

*Diagram: degree structure, 4 lanes over 8 semesters. See the [original document](https://claude.ai/artifact/RCLtnJDBb3cP3uGCKoof8Z).*

Three changes follow from this shape.

**One degree, not many.** Separate bachelor's programmes in AI, security, mobile or web development sell well but do not hold up. AI and security are high-abstraction fields that rest on programming, data and mathematics; a student cannot be good at them without the foundation first. Mobile and web are tools, not disciplines. Specialization belongs at master's level, where the foundation already exists.

**A track that actually chains.** Today a track means two or three swapped courses in the final year, which leaves no room for prerequisites. One track course per semester from semester 3, plus two in the final year, gives eight track courses that can depend on each other. Students choose their track at the end of year 1, once they have seen the material.

**Repurposed general education.** Where general-education courses are mandated and cannot be dropped, their content should be aimed at the degree: communication becomes technical writing (specifications, documentation, pull-request and incident write-ups); mathematics emphasises discrete mathematics, linear algebra and statistics over calculus; accounting becomes the economics of software (cloud cost, pricing, unit economics). The requirement is satisfied and the hours stop being wasted.

## What every graduate must know

These are the domains our graduates currently leave without. Each is stated as a capability, not a syllabus, and each is taught through the format in the next section.

| Domain | A graduate can |
| --- | --- |
| Programming fluency | Write, read and debug non-trivial code by hand in at least two languages, without assistance |
| Data structures and algorithms | Choose a structure for a problem, reason about cost, and explain why an implementation is slow |
| Operating systems and Linux | Work in a shell, write scripts with arguments and correct exit codes, inspect processes, memory and files |
| Networking | Explain what happens between a request and a response, read a trace, and diagnose latency or failure |
| Databases | Compare relational, document and key-value stores by their trade-offs; design a schema; read a query plan; name the caveats of the engine they chose |
| Caching and queues | Explain when to cache and when not to, what happens when a cache or queue fails, and how background jobs are retried |
| APIs and integration | Design an API, apply a standard (REST, GraphQL, gRPC), version it, and document it |
| Identity and authentication | Explain how sessions, tokens and federated identity work, and why these are never hand-rolled |
| Security | Demonstrate and then fix the common vulnerability classes, including injection, cross-site scripting, broken access control and secret handling |
| Containers and deployment | Write and critique a container image, separate build from runtime, and deploy with configuration kept outside the image |
| Cloud and infrastructure as code | Provision resources from code, explain cost and failure modes, and avoid manual console changes |
| Scaling and reliability | Load-test a service, read the results, and explain where it breaks and what to change |
| Delivery practice | Use version control properly, write tests, run CI, review code, and write specifications and incident notes |
| Working with AI | Write a specification an AI can implement, review and verify what it produces, and defend the design it chose |

## How each topic is taught

Every concept in the table above is taught in the same five-part format. This is what separates knowing a term from being able to use it.

1. **The concept.** What it is and what problem it solves, taught at the category level.
2. **A good example and a bad one.** Two artefacts side by side, with the reasoning. A container image whose run command is left to the deployment layer, so one image serves several roles, against one that hard-codes its process. A script that takes arguments and returns correct exit codes, against one that fails silently.
3. **How it fails.** The failure mode in production: what a full cache does, what an unacknowledged message does, what a long-running transaction does.
4. **The trade-offs and the caveats.** Every technology's weak side, stated explicitly. Students should leave with the reflex of asking "what are the shortcomings of this?" before adopting anything, rather than reading a vendor's own claims.
5. **The lab.** The student breaks it, fixes it, or defends the choice.

The habit this builds is the transferable part. A student who knows one relational engine's limitations well will interrogate the next technology the same way, including ones that do not exist yet.

## Practice system

Theory does not become automatic through lectures. It becomes automatic through repetition, the way a musician becomes fluent on an instrument before music theory is of any use. The degree therefore carries four practice tracks that run alongside the courses.

**Workshops.** Short, focused sessions on one tool or concept each: containers, cloud provisioning, infrastructure as code, queues, caching, load testing, identity, CI. Each workshop covers at most five concepts, has a fixed assessment, and ends with a score. Over four years a student completes somewhere between twenty and fifty of them, which is the practical content that is missing today.

**Build-your-own projects.** The university publishes a list of fifty to a hundred small implementation projects: an HTTP server, a small database, a key-value store, a job queue, a rate limiter, an OAuth client against a test provider. Students pick from the list, build with automated tests, and get graded on whether the tests pass. This is where the hand-coding fluency of principle 1 is built, and it is deliberately re-implementing solved problems, because the point is understanding, not production use.

**One long product project.** A single large system — a project tracker, for instance — carried across several semesters, with work handed out as tickets rather than as assignments. Students learn branching, code review, release process, ticket hygiene and handover: what commercial software development actually looks like. Teams rotate so students see unfamiliar code and inherit other people's decisions.

**GitHub from semester 1.** Every student has an account from the first semester, with all coursework in it. Graders should count tests passed and projects completed, not commit counts or activity streaks, which are easy to fake.

## The student record

Alongside the transcript, each graduate receives a workshop sheet: every workshop attempted, the concepts it covered, and the score awarded.

- Each entry carries a unique identifier and is verifiable online against the university's records, so an employer can confirm it.
- Scores should be published in an open credential format so they can be attached to a profile elsewhere, not only to a PDF the university issues.
- Practical assessments should weigh more than written ones, and each score should link to the artefact the student actually produced.

The value of this record depends entirely on its strictness. If most students score full marks, employers will ignore the sheet and we will have added paperwork without adding signal. The grading bar has to be set so that a high score is uncommon, and the tooling that generates and marks the assessments should enforce that rather than leaving it to individual instructors.

## Assessment

AI makes take-home work trivial to fake, so assessment has to move toward things that cannot be outsourced: diagnosis, review and defence.

**Break-fix drills.** Students are given a working system with a fault injected into it — a slow query, a container that will not start, a leaking connection pool, a broken authentication flow — and must diagnose and fix it under time pressure. Repeated often enough, diagnosis becomes reflex.

**Reviewing AI-written code.** Students review a stream of pull requests containing planted defects: a hand-rolled authentication routine, a missing index, an unbounded retry, a secret in the image. Finding the problem, not writing the code, is the graded skill.

**Whiteboard defence.** The central exam format. The student is given a system and must justify its design decisions and challenge the ones that are wrong: why this datastore rather than that one, where the boundary sits, what happens under load. This is where specification and judgement are examined.

**No-AI workshops.** Workshop assessments run without AI assistance, though whiteboards, diagrams and architecture views are allowed and encouraged. Reading ten thousand lines unaided is not a realistic exercise for a student; reading an architecture view, forming a hypothesis and then drilling into the relevant code is, and it is also how experienced engineers work.

A note on specifications: tests only prove that code matches the specification it was given. A wrong specification passes every test. Assessment should therefore include writing specifications and acceptance criteria that another student, or an AI, then implements.

## Faculty readiness

This is the part of the proposal most likely to fail, and it should be addressed directly rather than assumed away. Most faculty teaching these courses have not run production systems, and a curriculum that depends on the instructor being the expert will not survive contact with the timetable.

Three measures make the plan work without that assumption.

1. **Put the expertise in the materials.** Every workshop and every break-fix scenario ships with its answer key, the reasoning behind it, and the marking criteria. The instructor facilitates and assesses against a rubric rather than supplying the knowledge.
2. **Bring practitioners into the labs.** Working engineers — including remote contributors from the diaspora — run or co-run the practical sessions, while faculty carry the theory courses they already teach well.
3. **Train the faculty first.** Faculty go through the same workshops and drills, with the same assessments, in a summer cohort before the student cohort starts. This is also a natural place for paid professional training, delivered separately from the student-facing material.

## Pilot

We recommend the board approve a single pilot elective rather than a curriculum-wide change, so the approach can be judged on evidence.

**Scope.** One elective course of roughly thirty students, built on the format in this paper: the five-part teaching format, six to eight workshops with scored assessments, a set of build-your-own projects, break-fix drills, and a whiteboard defence as the final examination.

**Sequence.** Faculty training cohort first, then the elective runs, then the board reviews results before anything is extended into the core degree.

**Metrics the board should judge it on.**

| Metric | How it is measured |
| --- | --- |
| Diagnostic capability | Break-fix drill scores at the start of the course against the end |
| Defence quality | Whiteboard defence marks against a published rubric |
| Practical depth | Workshops completed and passed per student |
| Portfolio evidence | Build-your-own projects completed with tests passing |
| Employment outcome | Placement rate and starting role of pilot students against a comparison group |
| Employer judgement | Structured feedback from industry reviewers on the pilot cohort's work |

**Open items for the board.**

- [ ] Which general-education courses can be repurposed, and which are fixed by regulation
- [ ] Which semester the pilot elective runs in, and who teaches it
- [ ] Whether a short module on responsible AI use is added, which accreditation review is likely to ask for
