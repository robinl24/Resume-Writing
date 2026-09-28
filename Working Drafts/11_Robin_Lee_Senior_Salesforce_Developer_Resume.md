# Seungmin (Robin) Lee

Open to remote | Relocating  
770-668-0544 | seungmin.lee@live.com | linkedin.com/in/seungmlee

Salesforce developer and architect who translates Crediting, Renewals, RevOps, and FP&A needs into reliable Salesforce CPQ and Quote-to-Cash solutions. Owns ACV and quota-relief accuracy on an amendment-heavy org, from deal-level diagnosis through company reporting, and raises delivery quality through architecture, testing standards, and finance partnership.

## Skills

Salesforce CPQ (SteelBrick), Quote Calculator Plugin (QCP), Cancel & Replace Managed Package, Apex, JavaScript, Lightning Web Components (LWC), Flow, SOQL, Salesforce CLI, Git

## Experience

**Salesforce Developer** — Qualtrics  
March 2022 – Present  
Promoted to L4, March 2024  

Salesforce org of about 5,000–6,000 users (CPQ, Service Cloud, Experience Cloud, Platform); about $2–3 billion annual revenue; about 80,000 closed deals a year; global currencies. Core developer through the move from custom CPQ to Salesforce CPQ, then through Quote-to-Cash.

*Salesforce CPQ implementation* · March 2022 – 2025

- Maintained custom quote-calculation logic on the legacy CPQ platform, then took technical ownership of QCP after consultants rolled off the 2023 Salesforce CPQ implementation before it was finished. The legacy stack was not standardized; ACV and quota-relief rules were hard to maintain, and quoting problems often broke the link to historical deals. Became the primary debugger for an amendment-heavy architecture, tracing incorrect ACV/QR reporting to upstream pricing, subscription, and validation changes.
- Designed a calculate-time QCP sync after diagnosing that out-of-the-box twinning did not update product data on amendments or renewals; avoided a historical-data rewrite that would have required disabling org-wide CPQ and Apex triggers. Moved product-data changes off the engineering critical path so policy and incentive updates could take effect the same day on active deals.
- Pushed testing to cover New Business, Amendment, and Renewal for price rules and custom automations, not New Business only. Moved calculated-field updates from Apex async jobs into QCP JavaScript so values refresh on save.
- After the March 2024 L4 promotion, owned Revenue, ACV, quota-relief, and forecasting accuracy for Crediting and Renewals at the deal level and for RevOps and FP&A at the company and quarterly reporting level. Gave Crediting and Renewals last-line approval to correct calculation data so fixed values carried to the next amendment or renewal; mined those overrides and shipped lasting fixes by volume.
- Lead developer on a 2025 usage-to-subscription pricing overhaul with variable proration. Drove stakeholder discussions, reviewed a large sample of Crediting adjustments into bug tickets, and reconciled ACV/QR for dynamic product pricing until reviewed larger-dollar deals reached agreed cutoffs so Crediting capacity could move to other work (Q3 2025: ACV 2.8% vs 3% cutoff; QR 5.3% vs 5% cutoff).
- Cut ACV gross-absolute Crediting corrections 82% ($485.5M in Q4 2024 to $87.2M in Q3 2025) and brought QR manual-intervention rates on reviewed deals from 11.8% to 5.3%.

*Quote-to-Cash overhaul* · 2025 – Present

- Role shifted from IC developer to technical designer and code reviewer as a primary role: 2 Qualtrics developers, 5 contractors covering Qualtrics capacity, and 10+ contractors on the project itself.
- Designed contract-based ACV and quota-relief calculations for a $10M+ Deloitte-led Quote-to-Cash program so amendments no longer rewrote contract term length (a change in the middle of year two on a 3-year contract had been calculating as a 2-year deal). Built one engine that ran on legacy and new data, avoiding a historical rewrite and dual methodologies.
- Delivered ACV/QR ready for a delayed May 2026 go-live. Remaining ACV/QR work was deal-processing improvements; other areas that launched without backward compatibility required repeated hotfixes.

**Software Test Engineer** — Qualtrics  
March 2021 – March 2022  
Salesforce org testing; used the year to learn Salesforce and the org’s automations end to end.

- Tested against what stakeholders asked for and the requirements they would have added if they knew the Salesforce behavior underneath, which improved stakeholder acceptance of changes.
- Took on the stakeholder back-and-forth so other testers could stay on testing instead of mediating requirement gaps.
- Documented test steps for new and existing development so the team could start automating tests; little test documentation existed before.

**Product Specialist** — Qualtrics  
November 2019 – March 2021  
Client-facing support on the Qualtrics XM / 360 platform.

- Held a consistent 4.8/5 customer review score against a 4.5 average by focusing on quality of service.
- Built an alternative to the product’s bot-detection controls without a code change, using configuration (including IP-restricted survey responses) so clients could protect surveys when the built-in controls were not reliable enough.

## Education

**B.S. Materials Science and Engineering**, Georgia Institute of Technology  
Minor in Physics · Highest Honors · May 2019

Undergraduate research, Computational NanoBio Tech Lab: four papers, one first author; presented micelle reactant transport at AIChE.

---

*Working draft, September 23, 2026. Built from interview notes. Not a final designed PDF.*
