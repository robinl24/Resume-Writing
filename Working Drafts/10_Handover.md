# Resume Refresh Handover

Last updated: September 28, 2026. Working draft: [11_Robin_Lee_Senior_Salesforce_Developer_Resume.md](11_Robin_Lee_Senior_Salesforce_Developer_Resume.md). Writer-facing brief: [12_Resume_Reviewer_Handover.md](12_Resume_Reviewer_Handover.md).

This file is the handoff for the next person or session. Do not invent metrics, titles, or outcomes. Prefer the user's words in [09_Transition_Timeline_Interview.md](09_Transition_Timeline_Interview.md) over polished resume language.

## Goal

Robin Lee (legal name Seungmin / SeungMin Lee) wants a new resume and LinkedIn update after nearly six years. Target roles are **Senior Salesforce Developer** or **Salesforce Architect**, with finance partnership and senior-level ownership as the differentiators. Robin currently lives in Utah. Job search is **remote and other cities** (Seattle still fine). **Actively avoid Utah-based roles.**

Work in small question-and-answer batches. Robin answers questions better than filling outlines.

## Who

- Public name on drafts: Seungmin (Robin) Lee
- Phone: 770-668-0544
- Email: seungmin.lee@live.com
- LinkedIn: linkedin.com/in/seungmlee
- Current residence is Utah. Do not list a Seattle address before Robin lives there.
- Job search: **remote and other cities**, not Seattle-only. Still **avoid Utah-based roles**. Do not list a Seattle address. Prefer “Open to remote | Relocating” (Seattle can be one example) over “Utah | open to local roles.”
- Education: B.S. Materials Science and Engineering, Georgia Tech, May 2019; minor in Physics; Highest Honors
- Do **not** list U.S. citizenship. Robin does not think it is necessary after prior U.S. jobs.

## Source files

Original materials:

- `LeeSeungMinResume_2021Qualtrics__v2.docx.pdf` — last public resume, about 2021
- `Qualtrics Self Evals/` — self-evaluations from 2021 through Q3 2025
- Searchable text copies in `Extracted Sources/`
- Current interview-based draft: `Working Drafts/11_Robin_Lee_Senior_Salesforce_Developer_Resume.md` (one Qualtrics developer role, two phase subtitles: Salesforce CPQ implementation, Quote-to-Cash). Custom/legacy CPQ is the start of the implementation chapter, not its own section. Never use “homebrew.”
- Writer-facing brief (send this, not this internal file, to a paid reviewer): `Working Drafts/12_Resume_Reviewer_Handover.md`
- Older two-page PDF (missing 2023–2026 interview stories): `Working Drafts/Robin_Lee_Senior_Salesforce_Developer_Resume.pdf`

Self-evaluations used earlier in this project:

- Self-Rating 2021 Q3
- 360 Self-Rating 2022 Q1, Q3, Q4
- 360 Self-Rating 2023 Q2
- 2023 Q4 through 2025 Q3 PDFs

Several 2023–2025 PDF tables were clipped on the right. Incomplete claims are marked VERIFY, not guessed.

Earlier working drafts (`00` through `08`, evidence bank, LinkedIn draft, Seattle strategy, writer comparison) were created in a prior session and are **not currently in the folder**. Recreate them from this handover and the interview notes if needed. Do not treat the current PDF resume as final; it is missing the 2023–2026 transition stories Robin later provided.

## Career timeline (confirmed or strongly supported)

- Product Specialist, Qualtrics — November 2019–March 2021
- Software Test Engineer / QA for the Salesforce org — March 2021–March 2022
- March 2022: moved from Software Test Engineer to junior developer
- March 2024: promoted to L4, which is the regular developer level
- Qualtrics does not really use public role names like Junior Salesforce Developer or Salesforce Developer. Treat those as descriptive labels, not official HR titles.
- Current public resume draft still says “Salesforce Developer | March 2022–Present” and “Promoted to internal engineering level L4 in 2023.” Correct the L4 date to March 2024 before publishing.
- Org scale: about 5,000–6,000 Salesforce users; CPQ, Service Cloud, Experience Cloud, and Platform; global currencies; about $2–3B annual revenue; about 80,000 closed deals a year. Use as company context, not as Robin’s personal book of business.

## Positioning

Use this narrative:

> Senior Salesforce Developer or Architect who translates finance and operational needs into reliable, scalable Salesforce CPQ / Quote-to-Cash solutions and raises team delivery quality.

Supporting themes:

1. Salesforce CPQ and QCP depth
2. Finance-domain partnership (Crediting, Renewals, RevOps, FP&A, Deal Desk)
3. Architecture and integration/ownership decisions
4. Senior-level diagnosis, testing standards, and enablement

Do not claim six years of Salesforce development. Development tenure starts March 2022. Broader Salesforce experience starts March 2021.

## Transition stories Robin added in conversation

These are the major components Robin said were missing from self-evaluations. Full detail is in [09_Transition_Timeline_Interview.md](09_Transition_Timeline_Interview.md).

### 2023 — Custom CPQ to Salesforce CPQ with ATG

- Legacy CPQ was not standardized. Problems often led to creating new opportunities and losing historical connections.
- Legacy ACV/QR logic was hard to maintain after the lead maintainer left.
- Salesforce CPQ was chosen mainly to improve the quoting experience for Sales and Deal Support.
- Data Integrity and reporting teams had to adopt new fields.
- Original deadline was before fiscal-quarter end; custom requirements delayed it.
- ATG consultants rolled off before completion due to budget constraints.
- Internal team had little Salesforce CPQ or QCP experience.
- Architecture is amendment-heavy, which is uncommon and increases complexity.
- ACV/QR/forecasting rules changed frequently.

Robin’s path:

- Before ATG rolled off: junior developer; stakeholder communication was mostly “deployed successfully.”
- Earlier STE/QA background: reviewed stakeholder bug tickets; user-minded testing view.
- After ATG rolled off: owned QCP learning and ACV/QR bug fixes; then owned all QCP JavaScript and nearly all supporting CPQ automations.
- Team built new work on top of ATG. Robin diagnosed why those changes broke the system. Problems usually surfaced as incorrect ACV/QR, but the cause was often upstream (pricing, subscriptions, validations) and Robin had not been consulted.
- Became the primary CPQ debugger through sandbox trial and error.
- Pushed testing to cover New Business, Amendments, and Renewals, not only New Business.
- Started working directly with stakeholders when project managers were less familiar with CPQ.

Do **not** put delayed Salesforce certification on the resume unless a completed credential is named.

### 2023 example — CPQ twinning

- Out-of-the-box twinning copies Product / Product Option / Subscription values onto Quote Lines when API names and types match.
- Product updates did **not** flow to existing quote lines on amendments or renewals; they only appeared when the product was added as a new line.
- Option 1: bulk-update quote lines and subscriptions. Risk: rewrite historical data; requires turning off CPQ and Apex triggers org-wide.
- Option 2 (chosen): real-time QCP update only when a quote is calculated / actively processed. Protects history, avoids trigger shutdown, lets admins change product data without engineering as the bottleneck.
- Robin built list-driven QCP field sync so new fields could be added easily.
- Later expansion: old products could behave differently on amendment/renewal (example: fixed price → slab/volume pricing).
- Outcomes: fewer business-reported defects; recalculation became the users’ de-facto restart; product-data bottleneck moved to business approval; stale quote data could be cleaned on amendment/renewal; incentive/policy changes could affect deals the same day.

### 2024 — Owner of Revenue, ACV, QR, forecasting

- Promoted to L4 (regular developer) in March 2024.
- Regular out-of-sprint meetings with business groups, not in sprint accounting.
- Crediting and Renewals reviewed each quote and contacted Robin directly when a deal was wrong. Robin had to diagnose, fix the immediate deal, then design and ship the lasting fix.
- Built self-help so Crediting/Renewals could override system calculations, correct reporting numbers, and propagate only the fixed data to the next amendment or renewal. Used for last-minute edge cases and for data issues from CPQ adoption and uneven user training.
- Controls: Crediting/Renewals were the last line of approvers and could change the data themselves. Robin later data-mined overrides for recurring problems and implemented lasting fixes by volume priority. This is authorized last-line approval plus a feedback loop, not an uncontrolled override. Resume language must stay neutral; do not use “on a whim” or blame training.
- RevOps and FP&A leaders contacted Robin when reporting numbers changed.
- Accountability became both micro (each quote/deal) and macro (business/quarterly financial reporting).

### 2025 — Pricing and ACV/QR changes

- Business overhauled main product-line pricing from usage-based to subscription-based.
- Variable-proration requirements created confusion between business and Crediting on revenue, then broke downstream ACV/QR because product-data pricing changes did not account for existing data.
- Nearly 6 months to fix immediate problems, then another 6 months to reconcile ACV/QR for dynamic pricing.
- Crediting tracker (use this; **retire 16% → 8%**). 3% ACV and 5% QR are agreed **cutoffs / targets** so resources can be diverted elsewhere, not aspirational goals. **Adjustments %** = deals needing manual ACV/QR correction ÷ closed deals that require review (generally larger-dollar deals). Not all ~80k closed deals and not a share of ACV/QR dollars. Quarterly ACV: 4.4% → 5.7% → 3.3% → 2.8%. QR: 11.8% → 8.4% → 6.9% → 5.3%. Q3 beat the 3% ACV cutoff (2.8%) and was 0.3% above the 5% QR cutoff. ACV gross absolute $ Q4 2024 $485.5M → Q3 $87.2M (82%). Robin considers the tracker public-safe. “Over $10 million” on Q2C contractors may be used as “$10M+ contractor-led.” Do not say “no refund.”
- Robin was lead developer, contributed to architectural design, drove stakeholder discussions on what to improve, and reviewed a large sample of manual adjustments to file bug tickets. Enough for 2025 bullets. Do not claim sole architect of the overhaul.
- Extra architectural design from this period was not approved until the next Q2C transition. Treat that design as Q2C work, not a shipped 2025 outcome.
- Resume language stays neutral. Do not say pricing was changed “with no regard” for existing data. The older “started without Robin / testing failed” note is secondary unless Robin restates it.

### 2025–2026 — Deloitte Quote-to-Cash

- Years of one-off compensation / edge-case rules no longer scaled; even calculation owners had trouble tracking expected behavior.
- Qualtrics-specific ACV treated each amendment as rewriting the contract. Example: a 3-year contract amended mid-year 2 calculated as a 2-year contract. That also created an incentive to change deals without significant new revenue. Resume must not accuse reps of gaming pay.
- Robin proposed contract-based ACV: one standardized methodology, changes only when they bring significant revenue.
- Backward compatibility: one engine ran on new and existing data, avoiding a historical-data rewrite and dual methodologies. Consultants and business initially treated this as unnecessary.
- During Q2C Robin’s role shifted from IC developer to technical design and code review: 2 Qualtrics developers, 5 contractors covering Qualtrics capacity, and 10+ project contractors. Do not write this as managing a team of 17.
- Q2C was rushed around an acquisition. If ACV/QR were significantly wrong, the project was at risk. Robin said **over $10 million** on contractors can be mentioned as “$10M+ contractor-led.” Do not say “no refund.”
- Launch delayed many times; org rolled out in **May 2026**. Robin said it “failed spectacularly” — notes only. Resume: delayed May 2026 go-live; other areas without backward compatibility had severe defects; do **not** write that ACV/QR failed. Earlier account: ACV/QR calculations were ready; remaining asks were deal processing.
- Pre-launch tracked rates are Q3 2025: ACV 2.8%, QR 5.3% of reviewed larger deals. Do **not** treat the “5% of closed deals” memory as the QR cutoff until confirmed.
- Do **not** use the 6–9 month delay figure as fact. Do not say “against the contractor’s design” or “the business misunderstood its requirements.”

## Evidence already pulled from evaluations / old resume

Use only if still accurate after Robin’s newer stories:

- 75% reduction in manual ACV/QR intervention — older eval; prefer tracker 82% ACV gross-absolute drop Q4 2024 → Q3 2025
- ACV/QR diagnosis from multiple days to a few hours
- 40 technical designs / 182 story points
- Apex async → QCP JavaScript so calculated fields update on save
- Pricing standardization, discount schedules, selective proration, simplified amendments
- ~$250M Q3 reporting figure — VERIFY wording (prevented vs corrected vs identified)
- ~800 contracts data-integrity scoping — VERIFY remediation result
- ACV/QR adjustment-rate figures around 3.5% / 3% — clipped 2025 Q2 eval; tracker is the source of truth (Q2 ACV 3.3%, target 3%)
- STE highlight: Salesforce org testing that also built fluency in Salesforce and org automations; stated plus implied technical requirements; better stakeholder acceptance; absorbed stakeholder back-and-forth so testers were not stuck mediating; documented test steps for new and old development to start automation (little/no docs before). Do not claim automation shipped. Do not put 139/181 on the resume. Do not stack the older 10 → 50 page onboarding story unless Robin says it is separate.
- Product Specialist: client-facing; 4.8/5 reviews vs 4.5 average; bot-detection workaround without code changes (likely the 2021 IP-restricted survey-protection story). Do not put mentoring, internal workflow automations, or “lower productivity” on the resume.
- Research: four papers, one first author

Named so far: Salesforce CPQ (SteelBrick), Cancel & Replace, QCP JavaScript, Apex, LWC, Flow, SOQL, Salesforce CLI, Git. Use **Salesforce CLI**, not SFDX. Do not claim ownership of Cancel & Replace until Robin says so. Do not invent Copado/Jenkins/Gearset. **No completed Salesforce certification.** Do not list unfinished or delayed certs.

## Writing rules

- Keep an evidence bank / interview file separate from polished wording.
- Formula for bullets: action + technical/business scope + measurable result.
- Show seniority through architecture, diagnosis, testing standards, stakeholder work, and ownership during ambiguity.
- Neutral language only. Avoid “homebrew,” “consultants had to be relieved,” “no training,” and criticizing stakeholders or consultants.
- Do not invent precision. Mark unknown metrics VERIFY.
- ATS-friendly resume: single column, no tables/icons, two pages unless it truly fits one.
- LinkedIn should adapt resume bullets, not paste them verbatim.
- Do not list a Seattle address. Signal remote and relocation to other cities; **avoid Utah-based roles**. Do not list U.S. citizenship.

## Interview status

Method: one question at a time; append answers to `09_Transition_Timeline_Interview.md`.

Completed:

1. Why the org moved to Salesforce CPQ
2. Role before ATG rolled off, plus STE/QA background
3. Responsibilities after ATG rolled off
4. Concrete diagnosis example (twinning)
5. Which solution was chosen and what Robin built
6. What changed after the QCP sync shipped
7. February promotion junior → regular developer (later corrected to March 2024)
8. What 2024 ownership meant day to day
9. Title clarification: March 2022 STE → junior developer; L4 = regular developer; company does not use those public role names
10. Org scale: 5,000–6,000 users; CPQ / Service Cloud / Experience Cloud / Platform; global currencies; $2–3B revenue; ~80,000 closed deals a year
11. Self-help mechanism: Crediting/Renewals override calculations; corrected numbers roll to the next amendment/renewal; used for last-minute edge cases and CPQ-adoption / training-related data issues
12. Self-help controls: Crediting/Renewals were last-line approvers and could change data themselves; Robin data-mined overrides and shipped lasting fixes by volume priority
13. L4 promotion date confirmed as March 2024, not February 2024 and not “L4 in 2023”
14. 2025 pricing overhaul: usage-based → subscription with variable proration; ~6 months immediate fix + ~6 months ACV/QR reconcile
15. 2025 role: lead developer, part of architectural design, stakeholder discussions, reviewed a large sample of manual adjustments into bug tickets; extra architecture deferred to Q2C
16. Q2C architecture: contract-based ACV vs amendment-as-rewrite; one engine on legacy and new data; launch-ready under acquisition pressure; other non-backward-compatible areas needed hotfixes
17. Crediting tracker Q4 2024–Q3 2025 recorded; 16% → 8% retired; 82% matches ACV gross-absolute dollars
18. 3% ACV / 5% QR are agreed cutoffs so resources can be diverted; say target/cutoff, not goal
19. Adjustments % = reviewed larger closed deals needing ACV/QR correction, not all closed deals and not ACV/QR dollars
20. Skills named: Salesforce SteelBrick CPQ and Cancel & Replace package; lead with Salesforce CPQ on the resume
21. Regular-work tooling: Salesforce CLI and Git (not SFDX); uncommon in smaller orgs; do not invent a larger CI/CD stack
22. No completed Salesforce certification; skip unfinished certs
23. Do not list U.S. citizenship. Actively avoid Utah-based roles
24. Search is remote and other cities, not Seattle-only. Contact info unchanged
25. Q2C launch delayed many times; rolled out May 2026; “failed spectacularly” is notes-only, not resume copy
26. $10M+ contractors may be mentioned; no “no refund”
27. Also used Apex, LWC, Flow, and SOQL

**Current unanswered question**

None required. Launch is May 2026. Ready to draft.

## Next work after the interview

1. Fold the 2023–2026 stories into the master resume. The twinning/QCP sync and 2024 finance-ownership stories should replace or strengthen the generic “core developer / maintainer” bullets.
2. Rebuild Word/PDF if a generator still exists; otherwise rewrite the two-page draft from the interview notes.
3. Draft LinkedIn headline, About, and experience to match.
4. Signal remote + relocation to other cities (Seattle fine as an example). Do not attract Utah-based roles. Do not list a Seattle address or U.S. citizenship.
5. Only then evaluate paid writers. Prefer Salesforce/CPQ knowledge, discovery interview, no fabricated metrics.

## Safe draft bullets from conversation

These are working language, not final resume copy:

- Took technical ownership of QCP pricing logic during the 2023 migration from a custom CPQ platform to Salesforce CPQ, sustaining the implementation after consultants rolled off before completion.
- Became the primary debugger for an amendment-heavy Salesforce CPQ architecture, tracing incorrect ACV/QR reporting back to upstream pricing, subscription, and validation changes.
- Designed a calculate-time QCP sync after diagnosing that out-of-the-box twinning did not update product data on amendments or renewals; avoided a historical-data rewrite that would have required disabling org-wide triggers.
- Reduced business-reported quote defects and moved product-data changes off the engineering critical path, so policy and incentive updates could take effect the same day on active deals.
- After a March 2024 promotion to L4, owned Revenue, ACV, quota-relief, and forecasting accuracy for Crediting and Renewals at the deal level and for RevOps and FP&A at the company/quarterly level.
- Gave Crediting and Renewals last-line approval to correct calculation data so reporting stayed accurate and fixed values carried to the next amendment or renewal; mined those overrides for recurring issues and shipped lasting fixes by volume.
- As lead developer on a 2025 usage-to-subscription pricing overhaul, drove stakeholder discussions, reviewed a large sample of Crediting adjustments into bug tickets, and reconciled ACV/QR for variable proration until reviewed larger deals reached the agreed cutoffs so Crediting capacity could move to other work (Q3 2025: ACV 2.8% vs 3% cutoff, QR 5.3% vs 5% cutoff).
- Cut ACV gross-absolute Crediting corrections 82% ($485.5M in Q4 2024 to $87.2M in Q3 2025) and brought QR manual-intervention rates on reviewed deals from 11.8% to 5.3% against a 5% cutoff.
- Designed contract-based ACV/QR for a $10M+ Deloitte-led Quote-to-Cash program so amendments no longer rewrote term length (a mid-year-two change on a 3-year contract had been calculating as a 2-year contract); one engine ran on legacy and new data, which avoided a historical rewrite and dual methodologies.
- Delivered ACV/QR ready for a delayed May 2026 Q2C go-live; remaining ACV/QR work was deal-processing improvements, while areas without backward compatibility required repeated hotfixes.

## Do not do on handover

- Do not edit the plan file.
- Do not claim completed Salesforce certifications.
- Do not use the 6–9 month delay figure as fact.
- Do not accuse sales reps of gaming compensation, blame consultants, or say the business misunderstood its requirements.
- “Over $10 million” on Q2C contractors may appear as “$10M+ contractor-led.” Do not say “no refund.”
- Do not write that Q2C “failed spectacularly” on the resume. Delayed May 2026 go-live; other areas broke; ACV/QR stayed calculation-correct unless Robin says otherwise.
- Do not use 16% → 8% of deals. Do not write tracker rates as a share of all ~80,000 closed deals; the base is closed deals that require review (generally larger-dollar). Do not mix tracker rates with the older 75% eval or the Q2C “5% of closed deals” memory until Robin says they use the same denominator.
- Robin considers the Crediting tracker public-safe. Still do not paste the full table or Q4 negative/positive split on the resume; use rates, targets, and the 82% / $485.5M → $87.2M ACV drop.
- Do not describe the self-help adjustments as uncontrolled finance overrides. Crediting/Renewals were last-line approvers; overrides fed a volume-prioritized fix backlog.
- Do not list Seattle as current residence.
- Do not list U.S. citizenship.
- Do not write the resume as open to Utah-based roles.
- Do not stop asking questions and jump to a final resume until 2025–2026 is interviewed at the same depth as 2023.
