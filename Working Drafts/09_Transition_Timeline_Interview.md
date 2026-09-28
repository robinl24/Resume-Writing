# Transition Timeline Interview Notes

This is the working record of Robin Lee's answers. Preserve factual detail here before converting it into concise resume or LinkedIn language.

## 2023 — Migration from custom CPQ to Salesforce CPQ

### Background and reason for the transition

The legacy CPQ system was not standardized. When problems occurred, the process relied heavily on creating new opportunities, which could break connections to historical information.

The legacy Annual Contract Value (ACV) and Quota Relief (QR) calculations were difficult to maintain. This risk increased when the calculations' lead developer and maintainer left the company.

The required business capabilities were largely unchanged, but the legacy quoting experience was inadequate for sales representatives and the Deal Support team. Salesforce CPQ promised a better sales and quoting experience.

Nearly every stakeholder group was affected. The principal users were Sales Representatives and Deal Support. Reporting teams, including Data Integrity, also had to update reports to use new fields and data structures.

The project originally had a deadline before the end of a fiscal quarter. Custom business requirements delayed the implementation. Ownership then had to transfer quickly from ATG consultants to the internal Qualtrics team, whose members initially had little Salesforce CPQ experience and no prior familiarity with ATG's custom implementation.

### Robin's role and challenges

Robin worked with ATG consultants during the 2023 transition from Qualtrics' custom CPQ platform to Salesforce CPQ.

Before ATG rolled off, Robin was a junior developer with limited stakeholder-facing responsibility. Stakeholder communication generally consisted of confirming when changes had been deployed successfully.

Before becoming a developer, Robin worked as a Software Test Engineer/QA engineer for the Salesforce organization. In that role, Robin learned Salesforce behavior and the organization's testing practices while reviewing defect reports submitted by stakeholders. This created a user-centered perspective on Salesforce changes and an understanding of how system defects affected business users.

Robin was responsible for maintaining the custom QCP script and helping move business processes from the legacy system to Salesforce CPQ.

Budget constraints caused the consultants to roll off before the transition was complete. Robin had to develop Salesforce CPQ expertise independently, diagnose unfamiliar problems, and help sustain the incomplete transition.

The Salesforce CPQ architecture relied heavily on amendments, an uncommon and particularly complex implementation characteristic.

The rules governing ACV, Quota Relief, and forecasting changed frequently, requiring recurring system changes to support evolving business requirements.

### Responsibilities after ATG rolled off

After ATG rolled off, the internal team was not familiar with Salesforce CPQ and even less familiar with the custom JavaScript Quote Calculator Plugin (QCP). Robin became responsible for learning QCP in depth and owning bug fixes for ACV and Quota Relief.

The first work was relatively straightforward: building on or fixing functionality ATG had already developed. Robin soon had to own all of the QCP JavaScript and learn nearly all supporting Salesforce CPQ automations. QCP was the core of the calculations, but incorrect upstream inputs—such as pricing, subscriptions, and validations—caused the calculations to fail even when QCP itself was not the root cause.

While most of the team focused on new development layered on top of ATG's work, Robin was asked to determine why those changes were negatively affecting the rest of the system. The problems were usually discovered when ACV/QR reporting numbers were incorrect, even though the actual defect was often upstream and caused by changes Robin had not been consulted on.

Robin learned Salesforce CPQ behavior through trial-and-error testing in sandboxes and became the primary debugger for CPQ-related issues. Certification study was delayed because this diagnostic work was treated as essential; do not include the delayed certification on the resume unless a completed credential can be named later.

Knowledge among senior developers was effectively reset by the volume of org changes. Robin pushed for testing-process improvements because basic cases were being missed: the team was still testing as if the org were the legacy system, not a heavily customized Salesforce CPQ implementation. One key change Robin advocated was testing New Business, Amendment, and Renewal scenarios for all price rules and custom automations. The testing team had previously checked only New Business scenarios. Robin's testing showed that Salesforce CPQ's out-of-the-box automation treats those three scenarios differently, so custom automations also needed to treat them differently.

When ACV/QR accuracy did not meet business requirements, Robin became more involved with stakeholders because project managers were less familiar with the new system. That was the start of Robin driving business-facing solutions that would work within CPQ architecture rather than only delivering isolated code fixes.

### Example diagnosed after ATG rolled off: Salesforce CPQ twinning

Salesforce CPQ's out-of-the-box twinning feature was advertised as a way to copy values onto a Quote Line when matching field API names and types exist on the Product, Product Option, or Subscription.

Twinning failed in a way the team first treated as a bug. If the business changed a value on the Product, that new value was not twinned onto existing Quote Lines. It only flowed onto a Quote Line when the Product was added as an entirely new line. The updated parent data did not sync on amendments or renewals, even though the team expected downstream records to pick up the new product information.

Robin identified two possible solutions:

1. Update all Quote Lines and Subscriptions so the new product information could be used going forward. This carried considerable risk of changing historical data that should remain as originally processed, including amendment history. Making those updates would also require turning off CPQ and Apex triggers at the org level.
2. Build a system that updates Quote Lines in real time only when a quote is calculated or actively being processed. That approach would support the business's frequent small product-data changes, avoid turning off triggers, and let admins change product data without having to reason through every repercussion for active quotes and historical records.

Robin chose the second solution and decided it needed to live in QCP so the sync happened in real time rather than being delayed by Apex triggers. Robin shared the findings with the team because the limitation affected everyone's work.

Robin wrote the QCP code so new fields could be added to a list when they needed real-time syncing. That later expanded into a more advanced pattern: not just a few fields, but updating Quote Line data so older products could behave differently on amendment or renewal. One example is a product that had been priced at a fixed price later using slab/volume pricing on amendment or renewal.

After the QCP sync shipped, the business reported fewer defects. Most remaining defects could be fixed by recalculating an existing quote. Recalculation later became the de-facto restart step for users checking whether a recent deployment had fixed their quote.

Product-data updates were no longer bottlenecked by Robin's overloaded engineering team. The remaining bottleneck was business approval. The architecture then worked from the latest product data, so when old quotes with stale data were amended or renewed, quote data could be corrected and improved going forward.

The same pattern also gave the business flexibility to change policies, such as sales-representative incentives, overnight, with the change affecting deals the same day.

### Details still to capture

- Exact fiscal quarter and revised implementation or launch date
- Specific unfinished ATG components inherited after the handoff
- Who approved the QCP twinning solution and when it shipped
- CPQ-specific user count (Sales, Deal Support, Crediting, Renewals), if known separately from org-wide 5,000–6,000 users
- Whether the New Business / Amendment / Renewal testing standard was formally adopted and what quality change followed
- When the later volume/slab-pricing expansion shipped and what deals or products it enabled
- How often incentive or product-data changes were made same-day after the QCP sync shipped

## 2024 — Ownership of financial calculations

### Initial notes

Robin became the owner of Salesforce's management of Revenue, ACV, Quota Relief, and forecasting numbers.

Robin moved from Software Test Engineer to Junior Salesforce Developer in March 2022. After the 2023 transition work, Robin was promoted to L4 in March 2024. L4 is the regular developer level. Qualtrics does not really use public role names like Junior Salesforce Developer or Salesforce Developer; those are descriptive labels, not official HR titles. Do not present Junior / Salesforce Developer as official company titles. Robin believes the March 2024 promotion was likely due to the transitional work after ATG rolled off. The current public resume draft’s “Promoted to internal engineering level L4 in 2023” is incorrect.

### What ownership included in practice

Owning this part of the business meant regular out-of-sprint meetings with different business groups. Those meetings were not accounted for in sprint planning.

The main stakeholders were Crediting and Renewals. They cared about accuracy because they reviewed each quote. When a quote was wrong, they contacted Robin directly to review the problem and fix it for the immediate deal. That created a recurring burden: diagnose the issue, fix the current deal, then design and develop the lasting bug fix.

To reduce that burden, Robin enabled self-help for many deals so Crediting and Renewals could adjust system calculations and push a deal through without waiting for a hotfix.

### How the self-help adjustment worked

Crediting and Renewals could go in and override the system calculations so reporting numbers were corrected. The corrected numbers then rolled to the next amendment or renewal, so only the fixed data was propagated.

The capability existed for two reasons:

1. Edge scenarios the business introduced with little or no warning to the engineering team.
2. Underlying data issues from insufficient user training and from transitional data created when Salesforce CPQ was installed and adopted.

Resume language should stay neutral: do not use “on a whim,” and do not blame users or training. Frame as last-minute edge cases and CPQ-adoption / data-quality corrections.

### Self-help controls and follow-up

The Crediting and Renewals team were the last line of approvers, so they could change the data on their own. Overrides were later data-mined for potential recurring problems. Robin implemented lasting system fixes from that list, prioritized by volume.

This is authorized last-line finance approval plus a feedback loop into engineering, not an uncontrolled override. Specific field-level limits (what they could vs could not change) were not named.

RevOps and FP&A leaders also contacted Robin directly when reporting numbers changed. Accuracy was no longer only a Salesforce-data concern. It had to be reliable for company financial reporting at two levels: the micro level of each quote or deal for Crediting and Renewals, and the macro level of business and quarterly reporting for FP&A.

### Org scale (confirmed)

These are company / Salesforce-org figures, not CPQ-only user counts:

- About 5,000–6,000 users in the Salesforce org
- Products in the org: Salesforce CPQ, Salesforce Service Cloud, Experience Cloud, and Salesforce Platform
- Global currencies
- About $2–3 billion annual revenue
- About 80,000 closed deals a year

### Details still to capture

- Optional: which fields or calculation types Crediting/Renewals could override, if useful later
- How often Crediting or Renewals contacted Robin before and after self-help
- Frequency and complexity of business-rule changes
- Measurable improvements, incidents resolved, or manual work reduced
- Specific FP&A or RevOps reporting questions Robin had to explain or correct
- CPQ-specific user or quote volume, if known separately from org-wide 5,000–6,000 users

## 2025 — Pricing and ACV/QR changes

### Initial notes

Major changes to pricing and ACV/QR calculations initially proceeded without Robin's involvement and against Robin's technical recommendations. After the changes encountered testing failures, Robin was brought into the work.

Outside consultants later supported recommendations Robin had raised earlier. Resume language should emphasize technical judgment, risk identification, and recovery—not disagreement or criticism of stakeholders.

### What the 2025 pricing overhaul was

In 2025 the business wanted to overhaul pricing of the main product lines. The old model was usage-based pricing. The business wanted subscription-based pricing.

A business requirement for prices with variable proration caused major confusion between the business and Crediting teams when calculating revenue. The complexity of that proration caused downstream ACV/QR problems because pricing was changed on the product data without regard for existing data and how it would work.

The initial push for an immediate resolution took nearly six months to fix the immediate problems. It then took another six months to reconcile the ACV/QR calculations, because pricing now changed dynamically and ACV/QR had to account for those changes.

This is when there was a major effort to reduce the number of manual adjustments made by the Crediting team. Work continued through all of 2025 until the agreed adjustment-rate cutoffs were reached.

Robin later provided the tracked Crediting metrics (not memory). **Retire “about 16% of deals to 8%.”** That pair does not appear in the tracker. The remembered 82% and “net difference under 0.3%” do match the tracker.

Tracked quarterly rates (ACV adjustments / ACV distance from goal / QR adjustments / QR distance from goal):

- Q4 2024: 4.4% / +1.4% / 11.8% / +6.8%
- Q1 2025: 5.7% / +2.7% / 8.4% / +3.4%
- Q2 2025: 3.3% / +0.3% / 6.9% / +1.9%
- Q3 2025: 2.8% / −0.2% / 5.3% / +0.3%

Robin confirmed 3% ACV and 5% QR are agreed **cutoff parameters / targets**, not aspirational goals. Once adjustment rates reached those cutoffs, resources could be diverted elsewhere. Resume language should say “agreed cutoff” or “target,” not “goal.”

**What “Adjustments %” measures:** deals that needed manual Crediting intervention to correct ACV or QR, divided by closed deals that require review (generally larger-dollar deals). It is **not** a share of all ~80,000 closed deals and **not** a share of ACV/QR dollars. Do not write “2.8% of closed deals” without “reviewed” or “larger deals.” The dollar columns are the size of those corrections, not the percentage base.

Q1 ACV getting worse (5.7%) matches the pricing-overhaul shock; QR improved every quarter; Q3 is the first quarter ACV beat the 3% cutoff (2.8%). QR finished Q3 at 5.3%, 0.3% above the 5% cutoff.

Q3 2025 months: July 2.9% / −0.1% ACV and 4.4% / −0.6% QR; August 2.0% / −1.0% ACV and 3.9% / −1.1% QR; September 3.4% / +0.4% ACV and 6.4% / +1.4% QR. July and August beat both targets; September slipped. Use Q3, not September, as the year result unless Robin says otherwise.

Gross absolute correction dollars (|negative| + positive):

- ACV: Q4 2024 $485.5M → Q3 2025 $87.2M (**82.0% drop** — this is the remembered 82%)
- QR: Q4 2024 $663.6M → Q3 2025 $101.2M (~85% drop)
- Q2 2025 dollars rose again (ACV $200.6M, QR $223.6M); do not tell a straight-line dollar story.

Robin considers the tracker public-safe even though Qualtrics is PE-owned and not a public company. Still prefer rates, targets, and the 82% / $485.5M → $87.2M ACV drop over dumping the full table or the Q4 negative/positive split ($359M / $127M ACV). Those line items read like leaked finance ops. Do not mix this tracker with the older eval “~3.5% nearing 3%” line or the Q2C “5% of closed deals” memory until Robin says they are the same metric. The $10M contractor figure is a separate claim and is still unconfirmed for a public resume.

Resume language should stay neutral: do not say pricing was changed “with no regard” for existing data.

### Robin's role in the 2025 work

Robin was the lead developer and also had a part in the architectural design. Robin was in multiple meetings with stakeholders to drive discussions on what needed to be improved. Robin reviewed a large sample of the manual adjustments to create bug tickets.

Additional architectural design work from this period was not approved at the time. It was later approved in the next project, the Quote-to-Cash transition. Capture that design under the 2025–2026 Deloitte Q2C section rather than treating it as a shipped 2025 outcome.

This is enough detail to write the 2025 adjustment-reduction bullets. Do not claim sole architect of the 2025 overhaul. The earlier “started without Robin / testing failed” note is no longer the primary story unless Robin restates it.

### Details still to capture

- Whether Q2C launched in September 2025 (September rates slipped)
- Exact product lines
- Whether the Q2C “5% of closed deals” memory used this same reviewed-deal denominator
## 2025–2026 — Deloitte Quote-to-Cash improvement

### Initial notes

Robin worked with Deloitte consultants on a major Quote-to-Cash improvement initiative and owned work related to ACV and Quota Relief.

Robin developed and reviewed the approach proactively for more than six months while communicating with multiple stakeholders. The proposal was initially rejected in early 2025 because business stakeholders were not aligned. During the later Quote-to-Cash initiative, consultants accepted it as the solution that most closely satisfied the combined business requirements.

Robin's design was accepted within approximately one week; implementation and the rigorous testing Robin requested took nearly six months rather than the consultants' initial estimate of one to two months.

The assertion that this work avoided an additional six-to-nine-month delay is an estimate and should not appear as a definitive resume claim without supporting evidence.

### Why the old calculations did not scale

The business had built up multiple layers of rules and edge cases that may have been important when the company was smaller and the goal was to satisfy sales-rep compensation. As the company grew, those one-off rules added up and the system was collapsing under growing customizations. Even the people in charge of the calculations had trouble keeping track of their own requests and what the system was expected to do.

Robin identified that the calculation methodology the business insisted on created an incentive for reps to push work onto Sales Support, because it produced extra compensation with minimal revenue increase for the company. Robin had reported this as a known feature of how the business calculated things for years.

Resume language must stay neutral. Do not say the system was “collapsing,” do not accuse reps of gaming compensation, and do not blame Sales Support. Frame as accumulated one-off compensation rules that no longer scaled, plus an amendment model that rewarded contract changes that did not bring in significant revenue.

### Standard vs Qualtrics-specific ACV

Standard / contract-based calculations: a contract has its own ACV.

Qualtrics-specific calculations treated each amendment as completely changing the contract. A change overwrote nearly everything done before the amendment. Example: a 3-year contract changed in the middle of the second year effectively caused calculations to treat it as a 2-year contract. Robin described this as very unintuitive.

### Proposed architecture

Robin proposed contract-based calculations. That would standardize ACV so changes were not incentivized unless they brought in significant revenue.

Backward compatibility meant the new calculations could run on both new and existing data. That minimized the intricate historical data that would otherwise have needed to be fixed and updated. It also meant maintaining one calculation methodology that worked for legacy and new calculations, instead of two.

Consultants’ design and the business initially treated backward compatibility as unnecessary. Robin’s foresight in making everything backwards compatible went against that. Resume language: do not say “against the contractor’s design” or “the business misunderstood its own requirements.” Frame as insisting on backward compatibility so one engine could run on legacy and new data.

### Role during Q2C

Robin’s role changed significantly from individual-contributor developer to technical design and reviewing code. Scope of review:

- 2 Qualtrics developers
- 5 contracted developers covering capacity on the Qualtrics side
- Over 10 developers contracted to help directly with the project

Do **not** write this as people management of 17 developers. Frame as technical design and code review across those groups.

### Launch under acquisition pressure

The Q2C project was rushed because the business was under pressure from acquiring a new company and needed to complete the project regardless of the end state. If ACV/QR calculations were off significantly, the entire project would be at risk. More than $10 million had been spent on contractors. Robin said the contractor figure of over $10 million can probably be mentioned. Resume may use “$10M+ contractor-led Quote-to-Cash.” Do not say “no refund.”

### Launch outcome

Launch was delayed many times. The org eventually rolled out in **May 2026**. Robin said the rollout “failed spectacularly.” Keep that phrasing in notes only.

Resume language: a delayed May go-live with severe defects in areas that lacked backward compatibility. Do **not** write that Robin’s ACV/QR work failed. Earlier account still stands unless Robin restates it: ACV/QR calculations were ready; remaining ACV/QR asks were deal processing, not calculation bugs; other systems needed repeated hotfixes.

Robin first described launch as about a 5% error rate, meaning the share of closed deals that needed Crediting to fix system-calculated numbers. That “5% of deals” memory is **not** the same number as the tracker’s QR 5.3% or the 5% QR cutoff until Robin says it is. Do not write 16% → 8% → 5%. Pre-Q2C tracked rates are the 2025 series above (Q3 ACV 2.8%, QR 5.3%).

While other systems were failing and raising hotfix after hotfix, ACV/QR — which used to be one of the most error-prone and hotfix-prone parts of the system — was finding that the calculations were fine. Remaining asks were to improve the processing of deals, not to correct calculation bugs.

Other parts of the system were constantly flagged as bugs and failures because the business had agreed to a new system that did not need to rely on legacy data and therefore had minimal or no backward compatibility.

Earlier note that ACV/QR “retained approximately the same error rate as before” is superseded. Prefer the tracker for 2025; keep the Q2C “5% of closed deals” line only if Robin confirms it is a deal-count metric separate from the QR target.

### Details still to capture

- Whether “failed spectacularly” is the overall Q2C program (other systems) vs ACV/QR
- Whether the Q2C “5% of closed deals” memory used the reviewed-deal denominator

## Hands-on skills named so far

Robin named Salesforce SteelBrick CPQ and the Cancel & Replace package. SteelBrick is the original Salesforce CPQ product name; public resume language should lead with **Salesforce CPQ** and can add SteelBrick in parentheses if space allows. Cancel & Replace is a CPQ package for replacement/amendment flows; it fits the amendment-heavy and contract-based ACV stories. Do not claim Robin implemented or owned Cancel & Replace until that is stated.

Robin used **Salesforce CLI** and **Git** in regular work and noted this is not super common in smaller orgs. Robin first said SFDX, then corrected the public name to Salesforce CLI. Resume should list Salesforce CLI and Git, not SFDX. Do not name Copado, Jenkins, Gearset, or a full CI/CD stack unless Robin does.

Already evidenced in earlier stories, even if not listed here: QCP JavaScript, Salesforce CPQ automations, amendment/renewal/new-business testing, Crediting/Renewals tooling.

Robin also used **Apex, LWC, Flow, and SOQL**. Skills list for drafts: Salesforce CPQ (SteelBrick), Cancel & Replace, QCP JavaScript, Apex, LWC, Flow, SOQL, Salesforce CLI, Git. No completed Salesforce certification. Do not mention delayed or unfinished certification study.

## Software Test Engineer (2021–2022)

The main STE experience Robin wants highlighted: attention to stated user requirements, plus finding the requirements stakeholders would have wanted if they knew the technology better. That led to better stakeholder acceptance and a relationship with testers so testers did not have to handle back-and-forth communication with stakeholders.

Testing was in Salesforce. That year also let Robin get familiar with Salesforce and the org automations as a whole, which later supported the move into development. Resume can say Salesforce org testing and end-to-end fluency in org automations; do not make it sound like a student internship.

Robin also began documenting testing steps for new and old development to start automated tests. Previously the team had little to no documentation. Resume: documented test steps so automation could start; do not claim an automation suite shipped. The older 10 → 50 page onboarding-docs story may overlap; do not put both on the resume unless Robin says they are different.

Resume language: do not condescend to stakeholders. Frame as translating stated needs and implied platform requirements, then absorbing the clarification loop so testers could stay on testing. Do **not** put 139/181 primary-tester volume on the resume; Robin treats that as internal promotion evidence.

## Product Specialist (2019–2021)

Client-facing role. Robin held consistent **4.8/5** customer review scores against averages of **4.5**. Productivity was lower than some peers; Robin compensated with quality of service. Do **not** put the lower-productivity note on the resume.

Without a code change, Robin built an alternative to the product’s insufficiently reliable bot-detection system. The 2021 resume’s IP-restricted survey-response / survey-protection work is treated as the same story unless Robin says otherwise. Resume language: do not attack the product; say built-in bot detection was not reliable enough for some clients, and Robin delivered a configuration workaround.

Do **not** put mentoring or internal workflow automations on the resume. Those stay in older source files only.

## Contact and location

Do **not** list U.S. citizenship. Robin does not think it is necessary after already holding U.S. jobs.

Robin wants to **actively avoid Utah-based roles**. Current residence is still Utah. Do not invent a Seattle address.

The search is **remote and other cities**, not Seattle-only. Public drafts should signal openness to remote and relocation (Seattle still fine as one example) without inviting Utah-local roles.

Contact confirmed unchanged: Seungmin (Robin) Lee, 770-668-0544, seungmin.lee@live.com, linkedin.com/in/seungmlee.

## Current interview question

Leftovers are answered. Launch is May 2026. Ready to draft the resume.
