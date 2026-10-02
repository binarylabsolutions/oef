# Public ledger

*Last updated: 30 Sep 2026 · Not final*

If the studio ever accepts money, every rupee that comes in and goes out is recorded in a public ledger that anyone can read, at any time, without logging in. Supporters should always be able to see where their money went.

## The rules

1. **No money before the ledger.** The ledger is public before the first donation is accepted.
2. **Everything is recorded.** Every incoming and outgoing transaction, of any size, including fees and refunds.
3. **Every budget is public.** Any budget given to a person, a creator, a project or a system shows who holds it, how much, what for, what has been spent, and what is left.
4. **Recorded within 7 days** of the money moving, with a receipt or proof attached.
5. **Two people approve every spend.** No one approves their own payment.
6. **No hidden accounts.** One dedicated studio account, never mixed with anyone's personal money. The founder's own contributions are recorded as donations like anyone else's.
7. **No profit.** Money only covers the mission's costs. Anything left over rolls into the next month's budget and is shown as such.
8. **Mistakes are corrected in public.** Entries are never deleted; a wrong entry gets a correcting entry with a note.
9. **Monthly summary.** The monthly public report (see [04-studio-operations.md](04-studio-operations.md)) includes money in, money out, balance, and budget status.

## What each transaction shows

| Field | Example | Public? |
| --- | --- | --- |
| ID | TX-2026-0014 | Yes |
| Date | 12 Oct 2026 | Yes |
| Direction | In / Out | Yes |
| Amount (PKR) | 25,000 | Yes |
| Category | Donation, tools, hosting, AI usage, equipment, travel, stipend, fees | Yes |
| Counterparty | Donor name or "Anonymous"; vendor name; payee name and role | Yes (donors choose) |
| Budget line | e.g. B-03 "AI tools, Q4 2026" | Yes |
| Purpose | "ClickUp plan for Oct" | Yes |
| Approved by | Two core-team names | Yes |
| Receipt | Link to invoice or proof, personal details blacked out | Yes |
| Earmark | Donor asked it to go to a specific project | Yes |

**Never public:** bank account numbers, CNIC numbers, phone numbers, addresses. Donors who choose anonymity are anonymous in public but known to the core team, so we can meet legal requirements.

## Budgets

| Field | Example |
| --- | --- |
| Budget line | B-03 |
| Name | AI tools, Q4 2026 |
| Holder | Person or system responsible (e.g. "Tools lead: <name>") |
| Allocated (PKR) | 60,000 |
| Spent (PKR) | Computed from linked transactions |
| Remaining (PKR) | Computed |
| Period | Oct–Dec 2026 |
| Reason | Why this budget exists, in one line |

Budgets are proposed in public, open for comment for 7 days, then approved by the core team.

## Donations

- Donors can give to the general fund or earmark a project (e.g. "subtitles in Pashto"). Earmarked money is only spent on that project; if the project ends, the donor is asked before it's moved.
- We refuse money that comes with conditions on content, or from sources that conflict with the charter.
- Creators who choose to [pay it forward](03-charter.md#pay-it-forward-a-polite-request-never-a-requirement) are recorded like any other donor; their gifts go to a budget line for supporting new creators.
- Money given through a video's "Support the team" button goes into a separate **contributor fund** and is paid out to contributors and creators each month; the studio keeps none of it ([19-supporting-the-team.md](19-supporting-the-team.md)).
- Supporters get no special access or influence. Thank-you credits in the monthly report are optional.

## How it's published

| Stage | Tool |
| --- | --- |
| First donation | A view-only public Google Sheet (tabs: Transactions, Budgets, Monthly summary) + a Drive folder of redacted receipts, linked from every creator's "support us" page |
| Open studio | A ledger page in the control panel, with filters by budget, month and project, and a CSV download |
| Later | Look into Open Collective or a similar transparent-funding platform, if it works for Pakistani entities and payment methods |

## Before we accept money

- [ ] Register a legal entity for the studio (options in Pakistan include a trust, a society, or a non-profit Section 42 company). **Get legal and tax advice first.**
- [ ] Register with the provincial charity regulator (e.g. the Punjab Charity Commission); fundraising before this is illegal ([20-legal-and-payments.md](20-legal-and-payments.md))
- [ ] Open a dedicated studio bank account
- [ ] Name at least two approvers
- [ ] Publish the empty ledger and this policy
- [ ] Add the ledger link to every "support us" page

**Payments to people:** the studio pays vetted experts ([09-paid-experts.md](09-paid-experts.md)); every payment shows the expert's name, role, hours and amount.
