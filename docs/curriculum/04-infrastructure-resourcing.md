# Infrastructure and Resourcing for the New Curriculum

*Last updated: 25 Oct 2026 · Proposal, not final*

The practical curriculum needs cloud accounts, AI access and lab machines, and almost all of it is available to accredited universities at no cost. The university does not need to fund this; it needs someone to apply as an institution.

## What the curriculum needs

Four things, in rough order of how hard they are to obtain.

1. **Cloud accounts for students.** Required for the cloud, infrastructure-as-code, deployment, scaling and reliability workshops. Must not require a student to hold a credit card.
2. **AI access.** Required for the specification-writing, AI code-review and break-fix exercises. Frontier models are not necessary; coding-capable open models are sufficient for teaching.
3. **Lab machines able to run containers.** The break-fix drills, the build-your-own projects and the long product project all run in containers on ordinary lab hardware.
4. **A place for the scenario and assessment tooling to run.** One reference system, a fault injector that plants defects in it, and automated marking. This is modest, and it is what makes the model repeatable year after year without new effort from faculty.

## Education programs at no cost

The cloud providers already give accredited institutions what this curriculum needs. Figures below are as published on 25 October 2026 and should be re-checked at application time.

| Program | What it provides | Who applies |
| --- | --- | --- |
| [AWS Academy](https://aws.amazon.com/training/awsacademy/) | A free ready-to-teach cloud curriculum for institutions, plus the Learner Lab: a long-running sandbox where educators set their own assignments, with access to over 100 AWS services and per-student usage visible to the instructor. Educators also get certification exam discounts and a complimentary Skill Builder subscription. | The institution. A Program Administrator submits an application; eligibility requires accredited degree, diploma or certificate programs |
| [Google Cloud for faculty](https://cloud.google.com/edu/faculty) | Up to $100 in credits per teaching staff member and up to $50 per student, applied for per course; the program operates outside the United States as well | Eligible faculty, per course |
| [Azure for Students](https://learn.microsoft.com/en-us/azure/education-hub/faq) | $100 in Azure credit for 12 months, renewable, with no credit card required; students sign in with their institution ID | Each student, with an institutional email |
| [GitHub Education](https://docs.github.com/en/education/about-github-education/github-education-for-students/about-github-education-for-students) | The Student Developer Pack for students aged 13 and over enrolled in a degree or diploma programme: free GitHub Pro, dozens of partner tools, and free Codespaces use up to 180 core hours per month, which can carry the lab environments | Each student; GitHub Classroom is set up by faculty |
| Open-model AI access | Free API tiers from several providers, and open coding models that can be self-hosted. Sufficient for teaching: frontier models are not required for specification writing, code review or break-fix exercises | Faculty, per course |

Two caveats for the board. GitHub paused new Copilot student sign-ups in April 2026, so Copilot access should not be assumed in course planning; the rest of the Pack, including Codespaces, is unaffected. And the AI labs' university programmes are generally licensed rather than free, which is the main argument for the on-campus option below.

## An on-campus AI lab

For AI access specifically, we recommend the university host open models on its own hardware rather than depend on per-student allowances from vendors.

**Why it works technically.** The teaching use cases are code generation, review and scenario generation. These are served well by mid-size open coding models, which run on a small number of GPU workstations. Running the largest open models is unnecessary, and so is frontier-model access.

**Why it is cheaper.** Hardware is a one-time cost that serves every cohort afterwards, where credits expire and have to be reapplied for each year. It also removes the dependency on a vendor's programme terms continuing to exist.

**Why it is also an asset to the university.** A departmental AI lab running the university's own models and agents is something the institution can point to in admissions and press: a visible investment in AI capability rather than a line item. It gives faculty a research platform, and it gives students something most Pakistani graduates do not have on their CV.

**What it needs.** A small set of GPU workstations, an inference server, and one person responsible for keeping it running. Sizing should be worked out against the pilot cohort before any purchase, and the pilot itself can run on free-tier API access while the case is made.

## Recommended sequence

Nothing here needs a budget decision before the pilot runs. The first three items are applications, not purchases.

1. **Apply to AWS Academy as an institution.** This is the single highest-value application and the only one that must come from the university rather than from individuals. It needs a named Program Administrator.
2. **Have the pilot instructor apply for Google Cloud teaching credits** for the pilot course, and direct students to Azure for Students and GitHub Education at the start of the semester.
3. **Set up GitHub Classroom** for the build-your-own project list, which gives automated test-based grading at no cost.
4. **Run the pilot on free-tier AI access**, and record what it actually consumes.
5. **Take the AI lab proposal to the board after the pilot**, costed against the measured usage rather than an estimate.

**Open items**

- [ ] Who is named as AWS Academy Program Administrator
- [ ] Whether the university's email domain supports student verification for Azure and GitHub
- [ ] Who owns and maintains the scenario and assessment tooling between cohorts

### Sources

- [AWS Academy](https://aws.amazon.com/training/awsacademy/)
- [Google Cloud for Education, faculty](https://cloud.google.com/edu/faculty)
- [Azure Education Hub FAQ](https://learn.microsoft.com/en-us/azure/education-hub/faq)
- [About GitHub Education for students](https://docs.github.com/en/education/about-github-education/github-education-for-students/about-github-education-for-students)
- [Copilot access for students](https://docs.github.com/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot/set-up-for-students)
