# Business Impact Analysis and Response Windows

## Business Impact Analysis (BIA)

### 1. List the business functions
Start from what the organisation does end to end: the activities that earn revenue, serve customers, keep the organisation legal and keep people safe, and the support functions they depend on (IT, finance, HR, facilities). Use the organisation profile, workspace documents and the risk register. Keep it to the level of a function or process, not a task.

### 2. Decide which are critical
A function is a **Critical Business Function (CBF)** if losing it for a short time causes unacceptable harm. Test each function against the impact dimensions that matter for this organisation: safety, revenue and cash, customers and contractual commitments, legal and regulatory obligations, reputation, and the ability to run other functions. Write the impact over time in words a manager would use ("after 4 hours orders cannot be shipped, after 2 days customers start cancelling"). Typically 3 to 8 CBFs matter for a scenario; more than 10 usually means the level is too detailed.

### 3. Set the recovery parameters for each CBF
When asking the user for any of these, use the explanations in `plain-language-terms.md`, word for word. The definitions below are for the agent.

- **MTPD (Maximum Tolerable Period of Disruption)**: the longest the function can be unavailable before the harm becomes unacceptable or irreversible.
- **RTO (Recovery Time Objective)**: the target time to restore the function to its minimum service level. The RTO must be shorter than the MTPD.
- **RPO (Recovery Point Objective)**: for functions that depend on data, the maximum age of the data when restored, so the maximum data loss. It drives backup frequency.
- **Minimum service level**: the reduced level the function must deliver during the disruption (for example "process urgent orders only, by phone, up to 50 a day").
- **Dependencies**: the people (roles and minimum numbers), systems and data, equipment, suppliers, sites and records the function needs at the minimum service level.
- **Owner**: the role accountable for the function during the disruption.

Use the user's values. Where none are given, propose a sensible value for the industry and mark it `[TBC: confirm RTO, assumed 4 hours]`. Keep the parameters consistent: RTO under MTPD, and a system's RTO no longer than the RTO of the CBFs that depend on it.

### 4. Rank the CBFs
Rank by MTPD (shortest first), then by the size of the impact. The rank sets the order in which the Response phase addresses the functions and the order of recovery.

### BIA table
| ID | Function | Why critical | Impact over time | MTPD | RTO | RPO | Minimum service level | Key dependencies | Owner |
|---|---|---|---|---|---|---|---|---|---|
| CBF1 | ... | ... | 1h / 4h / 24h / 1 week | ... | ... | ... | ... | ... | ... |

---

## Response Windows

### Choosing the windows
The standard set is `T+0 to 1h`, `T+1h to 3h`, `T+3h to 6h`, `T+6h to 12h`, `T+12h to 24h`, `T+24h to 48h` and `Beyond 48h`. Choose from it using two inputs:
1. **The shortest RTOs.** Every CBF must be first addressed, with actions that move it towards its minimum service level, in a window that ends no later than its RTO. A CBF with a 2 hour RTO needs actions in `T+0 to 1h` and `T+1h to 3h`.
2. **The scenario's tempo.** A fast moving event with an end in sight (power cut, short IT outage) may end at 24 hours. A slow, long event (pandemic, loss of the main site, a major supplier failure) needs the later windows, and `Beyond 48h` expands into named periods such as `Day 3 to 7`, `Week 2 to 4` and `Month 2 onwards`.

Merge adjacent windows that would hold the same actions. Split a window when a deadline falls inside it (for example a 72 hour breach notification deadline deserves its own `T+48h to 72h` window). Say in the plan why the windows were chosen.

### What each window typically contains
| Window | Typical objectives |
|---|---|
| T+0 to 1h | People safe and accounted for. Event confirmed, severity declared, Crisis Management Team activated, logs started. Containment where possible (isolate systems, shut off utilities, secure the site). First holding message to staff. |
| T+1h to 3h | Impact assessed per CBF. Workarounds started for the CBFs with the shortest RTOs. Affected customers and suppliers told what is known. Notifications with short deadlines made (emergency services, insurer, regulator where required). |
| T+3h to 6h | Remaining CBFs moving to minimum service level. Alternate site or remote work in use. First situation report to leadership. External statement if the event is public. |
| T+6h to 12h | All CBFs at or above minimum service level or an explicit decision recorded for any that are not. Staff rota set for the next 24 hours. Suppliers and partners aligned on the workaround. |
| T+12h to 24h | Operations stabilised. Routine update cadence running. Recovery planning started, with the recovery order confirmed. Review of the day with the team. |
| T+24h to 48h | Sustained operations. Fatigue, welfare and cost managed. Recovery actions underway. Longer notification deadlines met. Customers told what to expect and when. |
| Beyond 48h | Operate at minimum service level for as long as needed, revisit priorities weekly, prepare the transition to Recover, and decide stand-down when the criteria are met. |

### Writing the actions in a window
- Order: safety, then assessment and activation, then CBFs in RTO order, then communications and logistics.
- One action per line, starting with a verb, with the owner role and the CBFs protected: `Switch order processing to the manual form and phone line (Operations Lead) CBF1`.
- State the communications due in the window and who sends them.
- End with the completion check: the conditions that tell the Crisis Leader the window's objectives are met, so the team knows when to move on.
- Actions the organisation cannot yet do (no alternate site, no tested backup) are still written, with the dependency marked `[TBC]`, and a matching Ready action is added so the gap is closed before an activation.

### Linking to the kri skill
When `kri_register.csv` exists for the risk, its Red thresholds are the activation triggers and its Amber thresholds can trigger "stand-by" actions (brief the team, check readiness). Quote the KRI ID and threshold in Section 5 of the plan.
