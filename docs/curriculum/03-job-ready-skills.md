# Job-Ready: What a Graduate Must Know on Day One

*Last updated: 25 Oct 2026 · Proposal, not final*

This is the list a graduate should be able to meet in order to join a software house and be productive without six months of remedial training. It is written as capabilities with a depth level attached, not as a syllabus, so a course designer can map it to subjects and an employer can use it as a hiring checklist.

## How to read this list

Not everything needs the same depth, and pretending otherwise is why syllabi become unteachable. Every item below carries one of three levels.

| Level | What it means | How it is evidenced |
| --- | --- | --- |
| **Aware** | Knows the concept exists, what problem it solves, and when to go and learn it. Can follow a conversation about it without being lost | A written or oral answer |
| **Can use** | Can do it with documentation at hand, and can tell a working result from a broken one | A lab artefact or a project commit |
| **Can defend** | Can choose between the options, explain the trade-offs, and say what breaks if the choice is wrong | A whiteboard defence or a review of someone else's work |

Most of this list is **can use**. The **can defend** items are the small set a graduate will actually be judged on in their first year of work, and they are deliberately few. **Aware** items exist so that a graduate recognises an unfamiliar term in a standup rather than freezing.

The list is technology-neutral where it can be. Where a specific tool is named, it is as an example of its category, and a graduate who knows one will pick up the competitor in a week.

## Build and run software

| Capability | Level |
| --- | --- |
| Write, read and debug non-trivial code by hand in one language, unassisted | Can defend |
| Pick up a second and third language without a course | Can use |
| Choose a data structure for a problem and reason about its cost | Can defend |
| Read someone else's unfamiliar code and summarise what it does | Can defend |
| Use a debugger, read a stack trace, and bisect a failure to its cause | Can use |
| Git: branches, merges, rebases, conflict resolution, history archaeology | Can use |
| Write unit, integration and end-to-end tests, and know which to reach for | Can use |
| Explain what a test suite does not prove | Can defend |
| Profile a slow program and find where the time goes | Can use |
| Memory model of the language they use: allocation, collection, leaks | Aware |
| Concurrency: threads, async, race conditions, deadlocks, idempotency | Can use |
| Package management, dependency versioning, lockfiles, and supply-chain risk | Can use |
| Read documentation and source as the primary route to an answer | Can defend |

The first and the last rows are the ones that matter most, and neither can be faked in an interview.

## Systems and infrastructure

| Capability | Level |
| --- | --- |
| Work in a Linux shell: processes, permissions, files, pipes, logs, signals | Can use |
| Write a shell script that takes arguments, handles errors and returns correct exit codes | Can use |
| Explain what happens between a request leaving a browser and a response arriving | Can defend |
| DNS, TLS, HTTP semantics, status codes, headers, keep-alive, timeouts | Can use |
| Read a network trace or a request log and locate a failure | Can use |
| Write a container image, separate build from runtime, keep configuration outside it | Can defend |
| Tell a good container image from a bad one, and say why | Can defend |
| Container orchestration: what a scheduler does, pods, services, rollouts | Aware |
| Deploy an application to a cloud provider and reach it from the internet | Can use |
| Name the core cloud service categories: compute, storage, managed databases, queues, CDN, identity | Can use |
| Provision infrastructure from code rather than from a console, and explain why | Can defend |
| Write a basic infrastructure-as-code module and understand state and drift | Can use |
| Set up a CI pipeline: build, test, lint, artefact, deploy on green | Can use |
| Explain the difference between continuous integration, delivery and deployment | Can use |
| Environments, configuration, secrets management, and what never goes in a repository | Can defend |
| Load-test a service, read the result, and say where it breaks | Can defend |
| Observability: structured logs, metrics, traces, alerting, what to instrument | Can use |
| Read a production incident timeline and explain what went wrong | Can use |
| Cost: what a cloud bill is made of, and which decisions drive it | Aware |

On infrastructure as code specifically: a graduate does not need to provision a production estate. They need to know that infrastructure is declared, versioned and reviewed like code, and to be able to work inside someone else's modules without doing damage.

## Data, APIs, identity and security

| Capability | Level |
| --- | --- |
| Design a relational schema, normalise it, and know when to denormalise | Can defend |
| Write non-trivial SQL: joins, aggregates, window functions, subqueries | Can use |
| Read a query plan and fix a missing or misused index | Can defend |
| Transactions, isolation levels, locking, and what a long transaction does | Can use |
| Compare relational, document, key-value, search and column stores by trade-off | Can defend |
| Name the caveats of whichever engine they chose, not just its strengths | Can defend |
| Migrations: how schema changes ship without downtime | Can use |
| Caching: what to cache, invalidation, stampedes, and behaviour when the cache is gone | Can defend |
| Queues and background jobs: delivery guarantees, retries, idempotency, dead letters | Can defend |
| Design an API and apply a standard: REST semantics, GraphQL or gRPC | Can defend |
| Versioning, pagination, rate limiting, error shapes, and documenting an API | Can use |
| Authentication versus authorization, stated precisely | Can defend |
| Sessions, tokens, JWT structure and its failure modes, refresh and rotation | Can use |
| Federated identity: OAuth 2 and OpenID Connect flows and what each is for | Can use |
| Why authentication and cryptography are never hand-rolled | Can defend |
| Demonstrate and then fix injection, cross-site scripting, and broken access control | Can defend |
| Secrets handling, password storage, transport security, and least privilege | Can use |
| Read a dependency vulnerability report and decide what to do about it | Can use |
| Threat modelling: who the attacker is and what they want | Aware |

The security rows are the ones employers assume are covered and most often find are not. They are also the cheapest to teach well, because breaking a deliberately vulnerable application is a memorable afternoon.

## Working in a team

This is the section that decides whether a graduate is a net contributor in month one or a net cost, and it is almost entirely absent from the degree today.

| Capability | Level |
| --- | --- |
| Write a specification someone else, or an AI, can implement without asking | Can defend |
| Write acceptance criteria that make "done" unambiguous | Can defend |
| Take a vague request and turn it into scoped tickets | Can use |
| Work in an issue tracker: states, estimates, dependencies, keeping it honest | Can use |
| Understand how a team plans work: backlog, iteration, stand-up, retrospective | Can use |
| Branching and release practice: trunk or feature branches, review, tagging, rollback | Can use |
| Open a pull request that is small, described, and reviewable | Can defend |
| Review someone else's pull request usefully, including saying nothing when it is fine | Can defend |
| Give and take technical disagreement without it becoming personal | Can defend |
| Write a design document for a change before building it | Can use |
| Write an incident note: what happened, impact, cause, what changes | Can use |
| Ask for help at the right moment, with the right context attached | Can defend |
| Estimate, and communicate early when an estimate is wrong | Can use |
| Direct an AI with a precise specification, then verify what it produced | Can defend |
| Judge when AI output is wrong, and refuse to merge code they cannot explain | Can defend |
| Keep a public portfolio: repositories, project history, written notes | Can use |

The last two rows are new and they are not optional. A graduate who merges code they cannot explain is a liability regardless of how fast they produce it.

## Tools: the concept is required, the tool is a choice

A graduate does not need to know every tool in a category. They need the concept at the level stated earlier, plus hands-on experience with **at least one** tool in the row. Someone who has used one well picks up its competitor in days; someone who knows none is starting from zero.

The university chooses which tool in each row it teaches, and that choice can change year to year without changing this list. Named tools are examples of their category, in no order of preference.

| Concept required | Tools that count as experience (any one) |
| --- | --- |
| Version control and pull-request workflow | GitHub, GitLab, Bitbucket, Azure Repos |
| Project and work management | Jira, ClickUp, Asana, Linear, Trello, GitHub Projects |
| Specifications and team documentation | Confluence, Notion, in-repository Markdown, Google Docs |
| Containerization | Docker, Podman, Buildah; Compose for multi-service |
| Orchestration (awareness level) | Kubernetes, Amazon ECS, Nomad, Docker Swarm |
| CI and delivery pipelines | GitHub Actions, GitLab CI, Jenkins, CircleCI, Azure Pipelines, Buildkite |
| Infrastructure as code | Terraform or OpenTofu, Pulumi, CloudFormation, Ansible |
| A cloud platform | AWS, Azure, Google Cloud, DigitalOcean, Hetzner |
| Unit and integration testing | JUnit, pytest, Jest, Vitest, Go testing, PHPUnit, xUnit |
| End-to-end and UI testing | Playwright, Cypress, Selenium |
| API testing and collections | Postman with Newman, Insomnia, Bruno, Hoppscotch, REST Client |
| Load and performance testing | k6, JMeter, Locust, Gatling, Artillery |
| Static analysis and code audit | SonarQube, CodeQL, Semgrep, and the language linter in use |
| Dependency and secret scanning | Dependabot, Renovate, Snyk, Trivy, gitleaks |
| Log aggregation and search | OpenSearch or ELK, Grafana Loki, CloudWatch Logs, Datadog, Seq |
| Metrics and dashboards | Prometheus with Grafana, Datadog, CloudWatch, Azure Monitor |
| Distributed tracing | OpenTelemetry with Jaeger, Zipkin or Tempo |
| Error tracking | Sentry, Rollbar, Bugsnag |
| AI and LLM observability | Langfuse, LangSmith, Helicone, Arize Phoenix, OpenTelemetry GenAI conventions |
| Relational database | PostgreSQL, MySQL or MariaDB, SQL Server, SQLite |
| Non-relational store | MongoDB, Redis or Valkey, DynamoDB, Elasticsearch |
| Queues and background work | RabbitMQ, Redis streams, Amazon SQS, Kafka, NATS, Celery, Sidekiq |
| Identity provider integration | Keycloak, Auth0, Okta, Amazon Cognito, Microsoft Entra ID, Firebase Auth |
| API description and contracts | OpenAPI or Swagger, GraphQL schema, Protocol Buffers |
| Secrets management | HashiCorp Vault, AWS Secrets Manager, SOPS, Doppler, platform secret stores |
| An AI coding assistant, used with verification | Any current assistant, with the attribution and review discipline above |

**Two rules keep this from becoming vendor training.** First, a student must port something once: take a pipeline, a container or a test suite built on one tool and move it to a competitor. That is what proves the concept rather than the interface was learned. Second, every exam question is asked at the concept level — what a pipeline stage is for, not which YAML key names it.

## Frameworks: one ecosystem, learned properly

A graduate should have taken one batteries-included framework all the way through a real application: routing, data layer, migrations, authentication, background jobs, validation, testing and deployment. One, not five. Which one depends on the ecosystem they work in, and the point is never the framework itself — it is understanding what a mature framework hands you for free and why writing those parts yourself is usually a defect.

| Ecosystem | Frameworks that count (any one) |
| --- | --- |
| PHP | Laravel, Symfony |
| JavaScript and TypeScript, full stack | Next.js, Nuxt, SvelteKit, Remix |
| JavaScript and TypeScript, backend | NestJS, AdonisJS, Fastify with a structured setup |
| Headless backend and content platforms | Payload, Keystone, Strapi, Directus |
| Python | Django (batteries included), or FastAPI with the surrounding pieces assembled deliberately |
| Java | Spring Boot, Quarkus, Micronaut |
| C# and .NET | ASP.NET Core |
| Ruby | Ruby on Rails |
| Go | Standard library with Chi, Echo or Gin, plus a migration and job library chosen explicitly |
| Elixir | Phoenix |
| Front end specifically | React, Vue, Svelte or Angular, with its standard routing and state approach |

**What they must be able to answer afterwards**, whichever one they used: what does this framework do for me on every request? Where does authentication actually happen? How are migrations applied in production? What runs my background jobs, and what happens if one fails twice? Which parts of this would I have to build myself on a framework that does less?

The minimal-framework ecosystems — Go, FastAPI — are worth one deliberate contrast exercise, because assembling the pieces yourself is what reveals what the batteries-included option was doing all along.

## Cloud and infrastructure primitives

Cloud providers rename the same dozen primitives. A graduate who knows the primitives moves between providers; one who memorised a console does not. The concept column is what is examined; the rest is vocabulary.

| Primitive | AWS | Azure | Google Cloud |
| --- | --- | --- | --- |
| Private network | VPC | Virtual Network | VPC |
| Subnets and routing | Subnets, route tables | Subnets, route tables | Subnets, routes |
| Host-level firewall | Security groups | Network security groups | Firewall rules |
| Virtual machines | EC2 | Virtual Machines | Compute Engine |
| Managed containers | ECS, EKS, Fargate | Container Apps, AKS | Cloud Run, GKE |
| Functions | Lambda | Functions | Cloud Functions |
| Load balancing | ELB and ALB | Load Balancer, Application Gateway | Cloud Load Balancing |
| Object storage | S3 | Blob Storage | Cloud Storage |
| Managed relational database | RDS, Aurora | Azure Database | Cloud SQL |
| Managed queue | SQS | Service Bus | Pub/Sub |
| Identity and permissions | IAM | Entra ID with RBAC | IAM |
| Secrets | Secrets Manager | Key Vault | Secret Manager |
| DNS | Route 53 | Azure DNS | Cloud DNS |
| Content delivery | CloudFront | Front Door | Cloud CDN |
| Logs and metrics | CloudWatch | Azure Monitor | Cloud Logging and Monitoring |
| Native infrastructure as code | CloudFormation | Bicep | Config Connector |

**The concepts behind the table**, which is what the examination asks about: why a database sits in a private subnet and a load balancer does not; what a security group rule actually permits; why an identity role is attached to a service rather than a key being copied into it; what a managed service takes off your hands and what it takes away from your control; and what the same architecture costs on each provider.

**A worked observability stack**, as an example of how these pieces fit rather than a recommendation: errors to Sentry, logs shipped to Loki and queried in Grafana, metrics scraped by Prometheus and shown on the same dashboards, traces emitted through OpenTelemetry. Any component can be swapped for a competitor, and the student should be able to say what each layer answers: what broke, what was happening around it, how often, and where the time went.

## Standards and compliance

This is the most commonly missing block, and the one that most often separates a graduate who can be trusted with client work from one who cannot. Standards are what let systems built by different teams work together; compliance is what lets a software house sell to serious customers at all.

| Area | What the graduate should know | Level |
| --- | --- | --- |
| HTTP and REST semantics | Methods, status codes, idempotency, caching, content negotiation, as the specification actually defines them | Can defend |
| API description | OpenAPI, GraphQL schemas, Protocol Buffers: a contract others build against | Can use |
| Data interchange | JSON Schema, ISO 8601 and UTC, Unicode and encoding, CSV pitfalls | Can use |
| Web platform standards | HTML and DOM standards, and WCAG accessibility as a requirement rather than a nicety | Can use |
| Identity protocols | OAuth 2, OpenID Connect, SAML, SCIM for provisioning, JWT and the JOSE family | Can defend |
| Transport and cryptography | TLS, certificates, hashing versus encryption, where to not improvise | Can use |
| Versioning conventions | Semantic versioning, deprecation policy, backwards compatibility, changelogs | Can defend |
| Licensing | Permissive versus copyleft, what a dependency's licence obliges, attribution | Can use |
| SOC 2 | What a report is, what the trust criteria cover, what evidence auditors want, and what it means for engineers day to day | Aware, can use for audit logging and access control |
| ISO 27001 | What certification means and how it differs from SOC 2 | Aware |
| Data protection law | GDPR principles, lawful basis, subject rights, deletion and export; local equivalents | Aware |
| Data retention and residency | Retention schedules, where data may be stored, what must not be collected | Can use |
| Audit logging | What must be recorded, immutability, who reviews it | Can use |
| Payment and health data | PCI DSS and HIPAA exist and why their scope matters before a design starts | Aware |

**For engineers, compliance is mostly design constraints.** A graduate does not need to run an audit. They need to recognise, before they build, that this table requires an audit trail, that this field cannot be logged, that this access needs to be revocable and reviewed, and that retention is a product decision with a legal floor and ceiling.

There is enough material here for a subject of its own; a worked outline for "Software Standards, Compliance and Professional Practice" sits in the course outlines paper.

## The day-one test

A single scenario that checks the whole list. A graduate joins a team on Monday and is given a ticket in an existing codebase they have never seen.

By Friday they should have: cloned and run the project locally, including its containers and dependencies; found the relevant code by reading rather than by asking; written the change with tests; run it through CI and fixed what failed; opened a reviewable pull request with a clear description; responded to review comments; and, when asked in stand-up why they solved it that way, given a straight answer.

Nothing in that week is exotic. It is also well beyond what most graduates can currently do, and it is the bar the curriculum should be built backwards from.

### What is deliberately not on the list

- **Deep expertise in any one framework.** Frameworks are learned on the job in a fortnight, and the one a student learns is rarely the one their employer uses.
- **Machine learning and model training**, unless the student takes that track. Using an AI tool well is on the list; building models is specialization.
- **Mobile or desktop platform specifics.** Tools, not disciplines.
- **Production operations at scale.** Knowing what a load balancer, an autoscaler and an on-call rotation are is enough; running them is a job, not a degree requirement.
- **Certification.** A verified record of what the student actually built and defended is worth more, and this list is written so it can be assessed that way.
