# Brief for resume review / rewrite

Prepared September 28, 2026 for someone Robin is paying to review or refine a Senior Salesforce Developer / Architect resume.

This file is for an external reviewer. Prefer it over the internal session handover. Do not invent metrics, titles, certifications, or outcomes. If a claim is not here or in the interview notes, ask Robin.

## What Robin wants from you

- Target roles: **Senior Salesforce Developer** or **Salesforce Architect** (CPQ / Quote-to-Cash). Write so either search can use the same resume. Do not make Architect the current Qualtrics title.
- Differentiators: Salesforce CPQ / QCP depth, finance partnership (Crediting, Renewals, RevOps, FP&A), architecture under ambiguity, diagnosis and testing standards
- Deliverable: ATS-friendly resume, single column, no tables or icons, two pages unless it truly fits one
- LinkedIn is not drafted yet. Include it only if Robin asked for it in the same engagement. Adapt resume bullets; do not paste them verbatim
- Salesforce CPQ / Quote-to-Cash knowledge and a discovery pass beat a generic rewrite
- The implementation section is long on purpose. Tighten it. Do not replace it with generic “maintained CPQ” bullets

## Files to use

1. [11_Robin_Lee_Senior_Salesforce_Developer_Resume.md](11_Robin_Lee_Senior_Salesforce_Developer_Resume.md) — working draft. Start here. Remove the “working draft” footer before treating it as finished copy.
2. [09_Transition_Timeline_Interview.md](09_Transition_Timeline_Interview.md) — source of truth. Prefer Robin’s words over polish when they conflict.
3. This file — constraints and approved numbers.

## Contact and location

- Public name: Seungmin (Robin) Lee
- Phone: 770-668-0544
- Email: seungmin.lee@live.com
- LinkedIn: linkedin.com/in/seungmlee
- Header: **Open to remote | Relocating**
- Lives in Utah. Do **not** list a Utah city if that invites local Utah jobs. Robin wants to **avoid Utah-based roles**
- Search is remote and other cities (Seattle is fine as an example). Do **not** list a Seattle address
- Do **not** list U.S. citizenship

## Titles and tenure

Qualtrics does not really use public role names like Junior Salesforce Developer. Those are descriptive labels, not official HR titles.

| Period | How to show it |
|---|---|
| Nov 2019 – Mar 2021 | Product Specialist (client-facing XM / 360) |
| Mar 2021 – Mar 2022 | Software Test Engineer (Salesforce org) |
| Mar 2022 – Present | **Salesforce Developer** |
| Mar 2024 | Promoted to **L4** (regular developer level, internal) |

Do **not** make “Senior Salesforce Developer” or “Salesforce Architect” the current Qualtrics title. Those are targets for the next job.

Do **not** claim six years of Salesforce development. Development starts March 2022. Broader Salesforce experience starts March 2021 (testing).

Structure under the developer role: **one Qualtrics job**, two phase subtitles:

1. *Salesforce CPQ implementation* · March 2022 – 2025 (includes the custom/legacy CPQ start; that is not its own section)
2. *Quote-to-Cash overhaul* · 2025 – Present

Never use “homebrew.” Say custom CPQ or legacy CPQ platform. That stack is the start of the Salesforce CPQ implementation chapter, not its own section.

## Positioning

> Senior Salesforce Developer or Architect who translates finance and operational needs into reliable, scalable Salesforce CPQ / Quote-to-Cash solutions and raises team delivery quality.

Company context (not Robin’s personal book of business): Salesforce org of about 5,000–6,000 users (CPQ, Service Cloud, Experience Cloud, Platform); about $2–3 billion annual revenue; about 80,000 closed deals a year; global currencies.

## Stories that must survive polish

Keep the substance of these even if you shorten the wording.

**Salesforce CPQ implementation**

- Started on custom quote-calculation logic, then owned QCP after consultants rolled off the 2023 Salesforce CPQ implementation before it was finished
- Amendment-heavy architecture; incorrect ACV/QR often came from upstream pricing, subscriptions, or validations
- Out-of-the-box twinning did not update product data on amendments or renewals. Robin chose calculate-time QCP sync instead of a historical rewrite that would have required disabling org-wide CPQ and Apex triggers
- Testing had to cover New Business, Amendment, and Renewal, not New Business only
- March 2024 L4: owned Revenue, ACV, quota-relief, and forecasting for Crediting/Renewals at the deal level and RevOps/FP&A at company/quarterly reporting
- Crediting/Renewals were last-line approvers and could correct calculation data so fixed values carried to the next amendment or renewal. Robin mined overrides and shipped lasting fixes by volume. This is authorized last-line approval, not an uncontrolled finance override
- 2025: lead developer on usage-to-subscription pricing with variable proration; not sole architect of that overhaul. Extra architecture from this period shipped in Q2C, not as a 2025 outcome

**Quote-to-Cash**

- Role shifted from IC developer to technical design and code review: 2 Qualtrics developers, 5 contractors covering Qualtrics capacity, 10+ contractors on the project. Do **not** write this as managing a team of 17
- Contract-based ACV so amendments no longer rewrote term length (mid-year-two change on a 3-year contract had been calculating as a 2-year deal)
- One engine on legacy and new data; avoided a historical rewrite and dual methodologies
- $10M+ Deloitte-led / contractor-led program is allowed. Do **not** say “no refund”
- Delayed May 2026 go-live. ACV/QR was ready; remaining ACV/QR asks were deal processing. Other areas without backward compatibility needed repeated hotfixes. Do **not** write that Q2C “failed spectacularly” or that Robin’s ACV/QR work failed

**Software Test Engineer**

- Salesforce org testing; the year built fluency in Salesforce and org automations
- Tested stated requirements and implied platform requirements stakeholders would have asked for if they knew the technology
- Took stakeholder back-and-forth so other testers were not stuck mediating
- Documented test steps so automation could start; little documentation existed. Do **not** claim an automation suite shipped
- Do **not** put “primary tester on 139 of 181 tickets” on the resume (internal promotion evidence)
- Do **not** restack the older 10 → 50 page onboarding-docs story unless Robin says it is a separate effort

**Product Specialist**

- Client-facing; 4.8/5 reviews vs 4.5 average
- Bot-detection alternative without a code change (treated as the same 2021 IP-restricted survey-protection story unless Robin says otherwise)
- Do **not** put mentoring, internal workflow automations, or “lower productivity” on the resume

**Education**

- B.S. Materials Science and Engineering, Georgia Tech, May 2019; minor in Physics; Highest Honors
- Four papers, one first author (Computational NanoBio Tech Lab)

## Approved numbers

| Claim | Meaning | Notes |
|---|---|---|
| ACV 2.8% vs 3% cutoff; QR 5.3% vs 5% cutoff (Q3 2025) | Share of **reviewed larger-dollar closed deals** that needed Crediting to correct ACV/QR | 3% / 5% are agreed **cutoffs** so resources could move elsewhere, not stretch goals. Say cutoff or target, not goal |
| QR 11.8% → 5.3% | Same reviewed-deal intervention rate, Q4 2024 → Q3 2025 | |
| ACV gross-absolute corrections −82% ($485.5M → $87.2M) | \|negative\| + positive correction dollars, Q4 2024 → Q3 2025 | Robin considers this public-safe. Do not paste the full tracker table or the Q4 negative/positive split |
| $10M+ contractors | Q2C program | “$10M+ contractor-led” is OK |
| Org ~5–6k users, ~$2–3B, ~80k closed deals | Company context | Not Robin’s personal book |
| 4.8/5 vs 4.5 | Product Specialist customer reviews | |

**Adjustments % is not** a share of all ~80,000 closed deals and **not** a share of ACV/QR dollars.

## Do not use

- 16% → 8% of deals (retired memory; not in the tracker)
- Older eval 75% reduction, or mixing ~3.5% / 3% eval lines with the tracker
- “Prevented a 6–9 month delay” as fact
- Completed Salesforce certifications, or unfinished / delayed cert study
- Copado, Jenkins, Gearset, or a CI/CD stack Robin did not name
- Salesforce CLI written as SFDX
- Ownership of the Cancel & Replace package (it may appear in skills; Robin did not say they owned it)
- “Homebrew,” blaming consultants or the business, accusing reps of gaming pay, “on a whim,” “no training”
- Pricing “changed with no regard” for existing data
- Uncontrolled finance overrides
- Utah as a job-search location; Seattle as current residence; U.S. citizenship
- VERIFY leftovers from evals unless Robin confirms: ~$250M Q3 wording, ~800 contracts remediation

## Skills Robin named

Salesforce CPQ (SteelBrick), Cancel & Replace (package name only), QCP JavaScript, Apex, LWC, Flow, SOQL, Salesforce CLI, Git.

Do not add Service Cloud or Experience Cloud as personal skills. Those are org products, already in the company-context line.

## Still loose (ask Robin, do not guess)

- Whether bot-detection is the same as the 2021 IP-restricted survey-protection story
- Whether a Q2C “5% of closed deals” memory uses the same reviewed-deal denominator as the tracker
- Exact month the Salesforce CPQ implementation should start (March 2022 vs 2023); current draft uses March 2022 because custom CPQ is folded into that chapter
- Paper titles if you want research more specific than “four papers, one first author”

## Review posture

Tighten for a hiring manager who knows Salesforce CPQ. Keep finance-owned ACV/QR, the twinning/QCP decision, the cutoff metrics, and the Q2C design/review role. If you need a number that is not in the approved table, leave it out or ask.
