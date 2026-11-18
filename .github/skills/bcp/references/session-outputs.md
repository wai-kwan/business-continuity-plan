# Session Outputs: Plan Document, Action Tracker and Progress Summary

Read this before writing a new version of the plan, the action tracker and the summary.

## Plan Document Conventions
- Start with document control: title, scenario, organisation, version, date, owner, approver, next review date, distribution, and a version history table (one row per version, with the session number and what changed).
- Use tables for the Business Impact Analysis, roles, resources, each Response window and the stakeholder map, and numbered steps inside windows.
- Keep placeholders visible (`[TBC: ...]`) so reviewers can find them.
- Write plain, direct language that someone can follow under stress: short sentences, one action per line, role names rather than department descriptions.
- Write the markdown copy first and build the Word document from it, so the two always match.

## Action Tracker (`<slug>_bcp_actions_v<N>.csv`)
One row per Ready, Response and Recover action, in exactly these 9 columns:

`Action ID,Phase,Window,Action,Owner,CBFs Protected,Due or Trigger,Status,Notes`

- **Action ID**: `RD1, RD2, ...` for Ready, `RS1, RS2, ...` for Response, `RC1, RC2, ...` for Recover. Continue numbering from the previous version and never renumber existing actions, since the user may refer to them by ID.
- **Phase**: `Ready`, `Response` or `Recover`.
- **Window**: `Before activation` for Ready. For Response, the window such as `T+0 to 1h`, `T+1h to 3h`, `T+24h to 48h` or `Beyond 48h`. For Recover, `After stand-down` or a day range such as `Day 3 to 10`.
- **Action**: one action, starting with a verb, matching the wording in the plan.
- **Owner**: a role, with the name when known (`IT Lead (TBC)` until named).
- **CBFs Protected**: the Critical Business Function IDs the action protects, for example `CBF1 CBF3`, or `All`.
- **Due or Trigger**: a date or lead time for Ready actions, and the trigger or deadline for Response and Recover actions.
- **Status**: `Planned`, `In progress`, `Done` or `TBC`.
- **Notes**: anything the owner needs, including `[TBC: ...]` placeholders.

Formatting follows the same discipline as the erm and kri skills: a single comma with no space after it, double quotes around any cell containing a comma or quote, no line breaks inside cells, and no cell starting with a hyphen or minus sign. Write the file with a CSV library so the quoting is correct.

### Worked example (ransomware scenario)
```csv
Action ID,Phase,Window,Action,Owner,CBFs Protected,Due or Trigger,Status,Notes
RD1,Ready,Before activation,Test restore of the order system backup and record the restore time,IT Lead (TBC),CBF1 CBF2,Quarterly and before peak season,Planned,[TBC: last tested date]
RD2,Ready,Before activation,Keep the offline contact directory and call tree current,BCP Coordinator,All,Monthly,In progress,Held on the shared drive and printed at both sites
RD3,Ready,Before activation,Agree the manual order form and phone line workaround with the operations team,Operations Lead,CBF1,2026-12-31,Planned,Workaround covers up to 50 urgent orders a day
RD4,Ready,Before activation,Pre-approve the staff alert and customer holding statement templates,Communications Lead,All,2026-12-31,Planned,Templates in Appendix E
RD5,Ready,Before activation,Confirm the cyber insurance policy response and the insurer hotline,Finance Lead,All,2026-11-30,Done,Policy number held in the vital records file
RS1,Response,T+0 to 1h,Isolate the affected systems from the network and preserve evidence,IT Lead,CBF1 CBF2 CBF3,On confirmation of the attack,Planned,Do not power off servers unless instructed by forensics
RS2,Response,T+0 to 1h,Declare the severity level and activate the Crisis Management Team through the call tree,Crisis Leader,All,On confirmation of the attack,Planned,Virtual room link in Appendix A
RS3,Response,T+0 to 1h,Send the first holding message to all staff on the backup channel,Communications Lead,All,Within 1 hour of activation,Planned,Template E1
RS4,Response,T+1h to 3h,Start the manual order process and divert customer calls to the phone line,Operations Lead,CBF1,Within 3 hours of activation,Planned,RTO for CBF1 is 4 hours
RS5,Response,T+1h to 3h,Notify the cyber insurer and engage the forensic provider,Finance Lead,All,Within 3 hours of activation,Planned,Insurer requires notice before any remediation spend
RS6,Response,T+3h to 6h,Issue the first situation report to leadership and set the update cadence,BCP Coordinator,All,By T+6h,Planned,Sitrep template in Appendix C
RS7,Response,T+24h to 48h,Assess whether personal data was accessed and make the regulatory notification if required,Legal and Compliance Lead,All,Within 72 hours of becoming aware,Planned,[TBC: confirm the notification deadline that applies]
RC1,Recover,After stand-down,Rebuild the order system from clean images and restore data to the last verified backup,IT Lead,CBF1 CBF2,When forensics confirm containment,Planned,Validate before reconnecting to the network
RC2,Recover,After stand-down,Enter the orders taken manually into the restored system and reconcile with customers,Operations Lead,CBF1,Within 2 days of system restoration,Planned,
RC3,Recover,After stand-down,Hold the post-incident review and update the plan,BCP Coordinator,All,Within 2 weeks of closure,Planned,
```

---

## Progress Summary (`<slug>_bcp_summary_v<N>.md`)
The next session reads this first, so keep it factual and complete. Do not record personal data beyond role holders' names where the user put them in the plan.

Save as `<slug>_bcp_summary_v<N>.md`. The next session reads this first, so keep it factual and complete. Do not record personal data beyond role holders' names where the user put them in the plan.

```markdown
# BCP Progress Summary: <Scenario> - <Organisation>

## Plan Details
| Item | Detail |
|---|---|
| Plan file | <slug>_bcp_v<N>.docx (markdown copy <slug>_bcp_v<N>.md) |
| Action tracker | <slug>_bcp_actions_v<N>.csv |
| Version | v<N> |
| Date | YYYY-MM-DD |
| Scenario | one line |
| Source of scenario | erm register row R<n> / user description / chosen with the skill / existing plan |
| Related scenarios included | none / name, because it is likely triggered by the main scenario / name, included at the user's request |
| Depth | Comprehensive / Quick plan |
| Start mode this session | New / Continue with plan and summary / Continue from plan only / Add scenario |
| Response windows used | for example T+0 to 1h, T+1h to 3h, T+3h to 12h, T+12h to 24h, T+24h to 48h, Day 3 to 7 |
| Maturity | Target for this version: Level n. Sections at target: x of m. Placeholders remaining: p |

## Version History
| Version | Date | Session | What changed |
|---|---|---|---|
| v1 | YYYY-MM-DD | 1 | First full draft from the scenario and organisation profile |
| v2 | YYYY-MM-DD | 2 | Crisis Management Team named, RTOs confirmed for CBF1 to CBF3, alternate site added |

## Completeness by Section
| Section | Level | Placeholders | What moved it up this version | Holding it back |
|---|---|---|---|---|
| 1 Introduction | 2 | 1 | Objectives confirmed | Peak season dates |
| 2 Business Impact Analysis | 2 | 4 | RTOs confirmed for CBF1 to CBF3 | RTOs for CBF4 and CBF5 assumed |
| 3 Roles | 2 | 6 | Crisis Leader and BCP Coordinator named | Alternates not yet named |
| 4 Resources | 1 | 9 | | Waiting on the user: alternate site unknown |
| 5 Activation | 2 | 0 | KRI R2.K1 Red threshold used as trigger | |
| 6 Ready | 2 | 2 | Owners confirmed | |
| 7 Response | 2 | 3 | Actions owned in every window | |
| 8 Recover | 2 | 1 | Recovery order confirmed | |
| 9 Communications | 2 | 5 | Stakeholder channels confirmed | Spokesperson not named |
| 10 Testing and maintenance | 2 | 0 | Exercise date set | |
| Appendices | 1 | 12 | | Contact directory is all placeholders |
Level values: 1 Outline, 2 Developed, 3 Detailed, 4 Validated (see "Maturity Levels" in `plan-template.md`), or Omitted. A section below the target, or more than one level behind the others, must say what is holding it back.

## Context and Sources
The essential context (objective of the BCP, entity, scenario, assets to protect) and the useful context gathered, each with its source (prompt, document name, website, existing plan, erm register row), so later sessions do not ask again. Note anything flagged as out of date.

## Scenario Choice
Why this scenario was chosen (first session only, carried forward afterwards): the candidates considered and the reason for the choice, or "given by the user".

## Structure Decisions
- Omitted: <section or item>, because <reason>.
- Reduced: <section>, to <what remains>, because <reason>.
- Added: <item>, because <reason specific to the scenario or organisation>.

## Facts Confirmed by the User
Short list of the facts supplied so far (for example CBF list and RTOs, team members, systems, sites, suppliers, notification obligations), so they are not asked again.

## Assumptions Still to Confirm
Values proposed by the skill and marked [TBC] in the plan, with the assumed value.

## Gaps Closed This Session
| Gap | Section | How it was closed |
|---|---|---|
| Crisis Leader not named | 3.1 | Named by the user, with an alternate |
| RTO for CBF1 assumed | 2.1 | Confirmed by the user as 4 hours |

## Open Gaps and Next Session
Every gap from the Step 6 review that is still open, including new gaps found this session, highest priority first.

| Priority | Gap | Section | Why it matters |
|---|---|---|---|
| High | Name the Crisis Leader and alternate | 3.1 | Nobody can activate the plan without them |
| High | Confirm RTO for CBF1 | 2.1 | Sets the first Response window |
| Medium | Identify the alternate site | 4.4 | Needed for Response T+3h to 6h |
| Low | Draft the glossary | Appendix F | |
Suggested focus for the next session: <one or two sentences>.

## Session Notes
What was done this session in a few lines, questions the user skipped or deferred, and anything the user asked to change later.
```
