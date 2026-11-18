# BCP Plan Template and Tailoring Guide

This is the full structure of a comprehensive plan. Each section is tagged:
- **Core**: include in every plan, including Quick plans. Reduce it rather than omit it.
- **Standard**: include in comprehensive plans unless it clearly does not apply to the scenario or organisation. Omit with a one line reason in the summary.
- **Conditional**: include only when the scenario or organisation needs it.

The template is a menu. Add items the scenario needs even if they are not listed (see "Scenario Specific Additions" at the end), and record every addition and omission in the summary's "Structure Decisions".

---

## Document Control (Core)
Title (`Business Continuity Plan: <Scenario> - <Organisation>`), version, date, plan owner, approver, next review date, distribution list, and a **version history** table: version, date, session, summary of changes.

## 1. Introduction
- 1.1 **Purpose and scope** (Core): what the plan protects, which parts of the organisation it covers, what it does not cover.
- 1.2 **Scenario description** (Core): what happens, how it starts, warning signs, likely duration, worst credible case. From the erm register when available. One main scenario per plan. A related scenario that the main one is likely to trigger (for example a fire that also takes out the IT systems) is described here as a labelled sub-section, and its specific actions appear as labelled sub-sections in Sections 5, 7 and 8.
- 1.3 **Objectives** (Core): for example protect people, keep the Critical Business Functions running at the minimum service level, meet legal obligations, protect reputation, return to normal within a target.
- 1.4 **Assumptions and exclusions** (Standard): what the plan assumes is still available (for example mobile networks, a second site) and what it does not cover.

## 2. Business Impact Analysis
- 2.1 **Critical Business Functions** (Core): ranked table with ID (`CBF1`, `CBF2`, ...), function, why it is critical, impact if lost over time, MTPD, RTO, RPO, minimum service level, owner. Method in `bia-and-response-windows.md`. A Quick plan lists the top 3 to 5 with RTO and minimum service level only.
- 2.2 **Dependencies** (Standard): per CBF, the people, systems, data, suppliers, sites and records it needs. These feed Section 4.

## 3. Roles and Responsibilities
- 3.1 **Crisis Management Team** (Core): role, responsibilities, primary, alternate, contact reference. Typical roles: Crisis Leader (decides activation, escalation and stand-down), BCP Coordinator (runs the plan, keeps the logs), Operations Lead, IT Lead, People and Welfare Lead, Communications Lead, Finance Lead, Legal and Compliance Lead. Merge roles in small organisations; one person may hold several, but every role must have an alternate.
- 3.2 **Key personnel per CBF** (Standard): the minimum people needed to run each CBF at its minimum service level, with backups and cross-training gaps.
- 3.3 **Decision rights** (Standard): who decides activation, severity changes, emergency spending, public statements, regulator contact, stand-down. A short RACI table works well.

## 4. Critical Resources
- 4.1 **People** (Core): minimum staffing per CBF and where they work from during the disruption.
- 4.2 **IT systems and data** (Core where any CBF depends on IT): system, CBFs served, RTO, RPO, backup location, restore method, alternate or manual workaround.
- 4.3 **Equipment** (Standard): laptops, phones, authentication tokens, specialist equipment, spares and where they are kept.
- 4.4 **Facilities and alternate sites** (Standard; Core for site loss scenarios): primary site, alternate arrangements (work from home, secondary office, partner or serviced office), capacity, how quickly each can be ready, what must be pre-positioned there.
- 4.5 **Critical suppliers and partners** (Standard): supplier, what they provide, CBFs affected, their continuity arrangements, alternate supplier, contract or SLA terms, contact reference.
- 4.6 **Vital records** (Standard): the records needed to operate and to recover (contracts, customer data, insurance, licences, keys and credentials), where the copies are and who can reach them.
- 4.7 **Emergency funds and insurance** (Standard): emergency spending authority and limits, access to cash or credit when normal systems are down, policies that respond to the scenario and the notification requirements.

## 5. Activation and Escalation
- 5.1 **Triggers** (Core): the events or thresholds that start the plan. Use kri Red thresholds when available. Include "any member of staff can raise an alert" and where to raise it.
- 5.2 **Severity levels** (Standard): for example Level 1 (incident, handled by the function), Level 2 (disruption, plan partly activated), Level 3 (crisis, full activation). Who declares each level.
- 5.3 **Activation procedure** (Core): who activates, how the Crisis Management Team is assembled (call tree, messaging group, meeting point or virtual room), what is said in the first alert.
- 5.4 **Logs** (Standard): start the incident log and decision log at activation (templates in the appendices).

## 6. Phase 1: READY (Core)
Preparations completed now, before any activation, so that the Response can happen. Table: Action ID, action, owner, due date, status. Typical content:
- Alternate site, remote work capacity and equipment pre-positioned.
- Backups tested, restore times measured, credentials held outside the affected systems.
- Contact directory and call tree kept current and held offline.
- Supplier agreements and alternates in place.
- Pre-approved message templates, spokesperson trained.
- Staff briefed on the plan, exercises run, role cards and checklists distributed.
- Insurance checked, emergency spending authority agreed.
- Monitoring of the triggers in Section 5 (for example the KRIs).

## 7. Phase 2: RESPONSE (Core)
Time windows chosen for the scenario (see `bia-and-response-windows.md`). Each window has: **objectives**, **actions** (numbered, each with owner role and CBFs protected), **communications due**, and **completion check** (how the Crisis Leader knows the window's objectives are met). Typical windows:
- 7.1 **T+0 to 1h**: life safety, account for people, confirm the event, declare severity, activate the team, start the logs, first holding message to staff, contain or isolate where possible.
- 7.2 **T+1h to 3h**: assess the impact on each CBF, start workarounds for the CBFs with the shortest RTOs, brief customers and suppliers who are affected now, make mandatory notifications with short deadlines.
- 7.3 **T+3h to 6h** and 7.4 **T+6h to 12h**: bring remaining CBFs to minimum service level, move to the alternate site or remote work, first situation report, external statement if public.
- 7.5 **T+12h to 24h** and 7.6 **T+24h to 48h**: stabilise, confirm all CBFs at or above minimum service, rotate staff, plan recovery, routine updates.
- 7.7 **Beyond 48h** (as needed, for example Day 3 to 7, Week 2 onwards): sustain operations, manage fatigue and cost, prepare the transition to Recover.
Use only the windows the scenario needs and merge or split them as the RTOs require.

## 8. Phase 3: RECOVER (Core)
- 8.1 **Recovery priorities and order**: which CBFs, systems and sites come back first and why.
- 8.2 **Restoring systems, data and the primary site**: steps, validation before use, data reconciliation.
- 8.3 **Clearing backlogs and resuming normal service**: catching up on deferred work, telling customers normal service has resumed.
- 8.4 **Stand-down criteria**: the conditions for ending the Response phase and for closing the plan.
- 8.5 **Post-incident review** (Standard): within a set time after closure, covering what happened, what worked, what did not, and the plan changes needed.

## 9. Communications Plan (Core)
- 9.1 **Stakeholder map**: stakeholder, what they need to know, channel, who speaks to them, how often.
- 9.2 **Internal communications**:
  - **Notification to the Board and senior management**: who notifies them, how, how soon after activation, what the first notification contains (what happened, impact on people and CBFs, actions under way, decisions needed, next update), and the update cadence after that.
  - **Staff**: alert channel and backup channel, cadence, approver, what staff should and should not say externally.
- 9.3 **External communications and media** (Standard; Core where the scenario could become public): spokesperson and alternate, holding statement, approval path, social media monitoring, enquiry handling.
  - **Boilerplate responses to anticipated enquiries**: anticipate the questions each external group is likely to ask after this scenario (customers, media, suppliers, partners, regulators, investors or lenders, the local community), and prepare a short, approved response for each in a table: enquirer, likely question, response, who may give it, and when it must be escalated instead. Draft the questions from the scenario, the impacts and the stakeholder map, for example "Is my order affected?", "Was anyone hurt?", "What caused it?", "Is my data safe?", "When will service be back?", "Will you meet our contract?". Responses state only confirmed facts, never speculate on the cause or blame anyone, and point to the next update. Front line staff (customer service, reception, drivers) get the responses they are allowed to give.
- 9.4 **Regulatory and contractual notifications** (Conditional, Core where they exist): who must be told, by whom, by when, through which channel, and the template.
- 9.5 **Message templates per phase**: first alert, situation update, customer notice, media holding statement, all clear.

## 10. Testing, Training and Maintenance (Standard)
Exercise schedule (walkthrough, tabletop, full test), training and induction, review triggers (after an incident or exercise, on major change, at least yearly), version control and distribution.

## Appendices (as needed)
- A. Contact directory and call tree (Core; names and numbers can be placeholders or held in a separate restricted file).
- B. Incident log and decision log templates (Standard).
- C. Situation report template (Standard).
- D. Role cards and checklists (Standard).
- E. Message templates (Core).
- F. Glossary (Standard): the terms used in the plan, explained with the wording in `plain-language-terms.md`.

---

## Quick Plan (Core items only)
Two to three pages: document control; scenario and objectives; top 3 to 5 CBFs with RTO and minimum service level; Crisis Management Team with alternates; triggers and activation; Ready actions; Response for the first 24 hours (windows chosen to fit); Recover outline with stand-down criteria; stakeholder map and first messages; contact directory placeholder. Everything else goes on the gap list for a later session.

---

## Maturity Levels by Section
Version 1 brings every included section to Level 1, and each later version aims to raise every section by one level (see "Maturity Levels" in `SKILL.md`). Level 4 (Validated) is the same for every section: tested in an exercise and updated afterwards.

| Section | Level 1 Outline | Level 2 Developed | Level 3 Detailed |
|---|---|---|---|
| Document control and 1 Introduction | Scenario, scope and objectives drafted from the context | Objectives, scope and assumptions confirmed by the user, owner and approver named | Approved, distribution list and review date set |
| 2 Business Impact Analysis | CBFs listed and ranked with assumed MTPD, RTO and minimum service levels | MTPD, RTO and minimum service levels confirmed, dependencies identified | RPOs confirmed, dependencies named (specific systems, suppliers, people), impact over time quantified |
| 3 Roles | Crisis Management Team roles and responsibilities | Primary for every role named, decision rights agreed | Alternates named for every role, key personnel per CBF, cross-training gaps closed or planned |
| 4 Resources | Resource types per CBF and alternate site options | Main arrangements identified (alternate site, key suppliers, vital records locations) | Contracts or agreements in place, capacities and lead times confirmed, contacts recorded |
| 5 Activation | Triggers, severity levels and activation steps | Triggers agreed (KRIs where available), who declares each level, call tree tool chosen | Call tree tested, contact numbers held offline |
| 6 Ready | Key preparation actions with owner roles | Every action owned with a due date | Actions under way or done, with status tracked |
| 7 Response | Windows with objectives, actions, communications and completion checks | Every action owned, windows matched to confirmed RTOs | Step by step procedures, checklists and role cards for each window |
| 8 Recover | Recovery order, stand-down criteria, review | Recovery priorities and stand-down criteria confirmed | Detailed restoration steps, responsibilities and target dates |
| 9 Communications | Stakeholder map, Board and senior management notification, message template outlines, list of anticipated enquiries | Spokesperson, channels and notification bodies confirmed, draft boilerplate responses for each anticipated enquiry | Full pre-approved templates and boilerplate responses, notification deadlines confirmed (legal advice where needed) |
| 10 Testing and maintenance | Exercise and review approach | Exercise dates and owner set | Exercise scenarios and evaluation criteria prepared |
| Appendices | Template headings and placeholders | Contact directory mostly filled, logs and sitrep templates ready | Directory complete and held offline, all role cards and templates complete |

## Choosing a Scenario
Follow these steps as part of the context discovery whenever the user has no scenario, is unsure, or brings one not suited to a BCP (see "Choosing the Scenario" in `SKILL.md` for what makes a good BCP scenario). Ask 1 to 3 questions at a time.
1. Learn enough about the organisation: what it does, where it works from, which systems, suppliers and people it relies on most, and any past incidents or near misses.
2. If an erm register or a risk-discovery register exists, shortlist the risks that are abrupt events rated HIGH or CRITICAL. These are usually Operational.
3. Propose 2 to 3 candidate scenarios from the table below or beyond it. Give each a one line reason it fits: how sudden it is, how severe, and what it would stop. Recommend one. A good first plan covers the scenario with the worst plausible impact on the most critical activities, or the single point of failure the business relies on most.
4. The user decides. Record the choice, the candidates considered and the reasons in the summary's "Scenario Choice".

---

## Scenario Specific Additions
Examples of items a scenario often needs beyond the template. They are prompts, not a checklist: ask what else this scenario and this organisation need.

| Scenario type | Consider adding |
|---|---|
| Major fire | Evacuation, assembly point and headcount, fire service liaison, site security and salvage once released, insurer and loss adjuster, relocation to the alternate site, replacing equipment and stock, smoke and water damage to records, mail and deliveries redirected, lease and landlord terms |
| Major flooding | Flood warnings as triggers, moving equipment and stock to higher ground, safe shutdown of power and equipment, staff unable to travel, access to the site, water damaged records and IT, drying and cleaning contractors, insurer, related power and telecoms loss |
| Extreme weather disruption (typhoon, storm, heatwave, haze, heavy snow) | Official warnings and advisories as triggers, staff travel safety and work from home, site closure and reopening decisions, heat or air quality protection for staff, supply and delivery delays, related power and telecoms loss |
| Critical IT system outage | Failure detection and the vendor or hosting escalation path, manual workarounds, a decision point to switch to the backup or disaster recovery environment, data reconciliation after restoration, customer facing service status messages, related data loss |
| Cybersecurity breach (ransomware, data breach) | Isolation and containment steps, evidence preservation and forensics, ransom decision policy and legal position, data breach notification deadlines to regulators and affected people, clean rebuild and verification before reconnecting, credential resets, cyber insurer and law enforcement contact |
| Large-scale product recall | Stop ship and quarantine of stock, batch tracing and customer identification, regulator reporting, recall notices and media statements, retailer and distributor coordination, collection logistics, replacement or refund process, root cause investigation |
| Bank failure | Alternate bank accounts held in advance, access to cash, payroll and supplier payments through another bank, customer payment instructions changed, deposit insurance and the claims process, lender and investor communications, payment card and merchant services |
| Utility or telecoms outage | Generator and fuel, battery life of key equipment, mobile hotspots, manual procedures, when to send staff home |
| Pandemic or health emergency | Health and hygiene policy, split teams and remote work capacity, absence thresholds that trigger actions, travel policy, sustained operations over weeks |
| Sudden failure of a key supplier or partner | Alternate sourcing and qualification time, inventory buffer, contract and termination rights, customer commitments that depend on the supplier, in-sourcing options |
| Sudden loss of a key person | Succession and delegation of authority, access to their knowledge, credentials and relationships, client reassurance, welfare of the team |
| Security threat or civil unrest | Lockdown or shelter procedures, staff travel safety, police and authority advisories, site closure decisions |
| Sudden suspension of a licence or regulated activity | Legal counsel engagement, remediation plan, customer and regulator communications, operating under restrictions |

Also consider items driven by the organisation rather than the scenario: a single site, a small team where one person holds several roles, customers with contractual service levels, regulated activities, seasonal peaks, or operations in several countries.
