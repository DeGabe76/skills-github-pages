<!DOCTYPE html>
<html lang="en"><head><meta charset="utf-8"><meta name="viewport" content="width=device-width">
<title>Generic SAP S/4HANA Fiori Maintenance-Order Job Aid</title>
<style>body{font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,sans-serif;max-width:760px;margin:2rem auto;padding:0 1rem;line-height:1.6;color:#333}
pre{background:#f6f8fa;padding:1rem;overflow-x:auto;border-radius:4px}code{font-size:.9em}
img{max-width:100%}table{border-collapse:collapse;width:100%}td,th{border:1px solid #ddd;padding:.5rem}</style>
</head><body>
# Job Aid | Maintenance Order Lifecycle in SAP S/4HANA Fiori

**Audience:** Maintenance requesters, planners, supervisors, technicians, and other authorized end users  
**Purpose:** Create, plan, release, execute/confirm, and technically complete a maintenance order using a generic SAP S/4HANA Fiori experience.  
**Applies to:** A baseline SAP S/4HANA Fiori implementation. App names, available fields, statuses, authorization, approval steps, and integrations vary by organization and configuration.

> **Use approved production data only.** The examples in this aid are intentionally redacted and fictional. Do not enter personal data, security-sensitive asset details, passwords, or unapproved attachments in training or demonstration orders.

---

## 1. Before You Begin

### Training assumptions

You have:

- An assigned business role that permits the activities in this job aid.
- Access to your organization’s Fiori launchpad and approved maintenance-order app(s), such as **Manage Maintenance Orders**, **Create Maintenance Order**, **Find Maintenance Orders and Operations**, or an equivalent catalog tile.
- The correct plant, planning plant, technical object, order type, work center, and notification/request information as applicable.
- Completed site safety, work-permit, and local maintenance-process training.
- Approval to create or change the order. This job aid does **not** grant authority to release work, confirm time, post material, or close an order.

### Know the lifecycle

| Stage | Typical user outcome | Common status indicator* |
|---|---|---|
| Create | An order exists with a scope and responsible parties. | Created / Outstanding |
| Plan | Operations, dates, labor, materials, and cost information are prepared. | Planned / In planning |
| Release | Work is authorized to proceed. | Released |
| Execute & confirm | Work is performed and actuals are recorded. | Partially confirmed / Confirmed |
| Technical completion | Technical work is closed; remaining administrative or financial closeout may follow. | Technically completed |

\*Status names and combinations are configuration-dependent. Treat the current system status and your local work instructions as the source of truth.

### Information to gather

| Item | Why it matters | Example (redacted/fictitious) |
|---|---|---|
| Technical object | Identifies the equipment or functional location to maintain. | `EQ-••••4821` |
| Maintenance plant / planning plant | Determines responsibility and organizational context. | `PLT-••` |
| Order type | Drives process, number range, controls, and settlement behavior. | `PM••` |
| Work description and priority | Defines the work and supports scheduling. | “Inspect abnormal vibration — non-emergency” |
| Requested/required dates | Supports planning and customer commitment. | `20XX-MM-DD` |
| Operations, work center, durations | Enables labor planning and confirmation. | “Inspection; WC-••; 2.0 H” |
| Parts/services | Supports procurement and staging where enabled. | “Bearing kit — material ID per catalog” |
| Safety and permit needs | Prevents work from being released or started unsafely. | “LOTO / permit review required” |

---

## 2. Quick Path

1. Open the approved maintenance-order app from the Fiori launchpad.
2. Create an order, or open the existing order assigned to you.
3. Enter the required header, technical object, scope, priority, and dates; **Save**.
4. Plan operations, labor, materials/services, and scheduling details; resolve errors; **Save**.
5. Complete required reviews or approvals, then **Release** the order if you are authorized.
6. Perform work only after required safety controls and release conditions are met. Record confirmations and actuals.
7. Verify all work and follow-up items are complete; then set **Technically Complete** if authorized.

---

## 3. Detailed Procedure

## A. Create the maintenance order

1. From the Fiori launchpad, open your approved order app.
   - Use the launchpad search if the tile is not on your home page.
   - Depending on configuration, select **Create**, **Create Order**, or **New**. Some organizations create an order from a maintenance notification instead.
2. Select or confirm the **order type**.
   - Choose only a type you are trained and authorized to use. The available list is configuration-dependent.
3. Complete the order header. At minimum, enter all mandatory fields marked with an asterisk (`*`) and any required local fields.
4. Enter or select the **technical object** (equipment and/or functional location, according to your process).
   - Confirm that the description, plant, and location shown match the asset requiring work.
5. Enter a short, action-oriented **description**, **priority**, and requested/required dates.
6. If a notification is required, create or link it using the app’s available action. Do not create duplicate orders when an existing notification or order already covers the issue.
7. Select **Save**. Record the order number displayed by the system.

**Creation check:** Reopen or review the saved order and confirm the correct technical object, description, responsible plant/work center (if applicable), priority, and status.

### Header field guidance

| Field | What to enter / verify | Good practice |
|---|---|---|
| Order type | The approved maintenance process/category. | Do not use a convenient-looking type as a workaround; ask the planner if unsure. |
| Short text / description | Clear symptom or work scope. | State the object/problem/action, e.g., “Inspect vibration at drive-end bearing.” |
| Technical object | Equipment or functional location. | Use search/value help; verify the returned object description before saving. |
| Maintenance / planning plant | The responsible organizational unit. | Values may default from the technical object; do not override without ownership confirmation. |
| Priority | Business urgency based on the approved priority matrix. | Priority does not replace emergency response or safety escalation. |
| Basic start / finish dates | Earliest planned work window or required completion. | Use realistic dates and update them if conditions change. |
| Main work center / responsible person | Owner of planning or execution, where used. | Select the accountable team, not an individual merely for visibility. |

> **Safety stop:** If the condition is unsafe, imminent, or emergency-related, follow the site emergency process first. Do not rely on normal order creation or priority alone to control immediate risk.

---

## B. Plan the order

Planning may be performed by a planner, supervisor, or another authorized role. You may not see all planning sections.

1. Open the saved order in the order app and choose **Edit** if required.
2. Review the **header**, technical object, linked notification, priority, and dates. Correct obvious data issues before adding detail.
3. In **Operations** (or equivalent), add or revise each work step.
   - Enter operation text, responsible work center, control key (if displayed), planned work, work unit, number of personnel/capacity, and duration as required.
   - Use a sequence that a technician can follow safely.
4. Add **components/materials**, external services, and/or purchase requisitions only through your approved process.
   - Check stock, reservation, procurement, and lead-time messages where those functions are enabled.
5. Add required safety instructions, permits, measurement points, checklists, attachments, or long text using the fields and document services available in your system.
6. Review **costs**, **scheduling**, and **capacity** information if your role includes these activities.
7. Select **Save**. Resolve validation messages before requesting release.

### Operation field guidance

| Field | What it means | Entry guidance |
|---|---|---|
| Operation / work text | The individual task to be performed. | Start with a verb; keep each task measurable and unambiguous. |
| Work center | Team or resource expected to perform the task. | Confirm plant/work center compatibility. |
| Control key | Controls how the operation is scheduled, confirmed, or costed. | Use the default/approved option; this is commonly configuration-controlled. |
| Planned work + unit | Estimated labor effort. | Enter the planned effort, not elapsed calendar time. |
| Number of capacities | Planned people/resources, if used. | Align with the actual crew assumption. |
| Duration / dates | Expected work-window length and schedule. | Consider access, permits, shutdowns, and material lead time. |

**Planning check:** The scope, operations, dates, labor, materials/services, safety needs, and responsible work center are complete enough for the next authorized reviewer to act.

---

## C. Release the order

Release authorizes the order for execution in many processes; it is not a substitute for permits, isolation, safety checks, or local work authorization.

1. Open the fully planned order.
2. Confirm all prerequisites required by your organization are complete, such as planning review, material availability, approval workflow, permits, and safety documentation.
3. Review the planned start/finish dates and the operations to be released.
4. Select **Release**, **Set to Released**, or the equivalent available action.
5. Read the resulting messages and verify that the order status shows the expected released indicator.
6. Save if the app does not save automatically, then communicate the released work according to local practice.

**If release is unavailable:** Do not change statuses by workaround. Check the message log and prerequisites, then contact the responsible planner/supervisor or support channel.

> **Configuration note:** Some organizations release at header level, operation level, through workflow, or automatically; others restrict release to planners or supervisors. Your app may use a different label or may not show a release action.

---

## D. Execute the work and record confirmations

1. Before starting work, verify the order/operation is released as required and complete all site safety, permit, isolation, and toolbox-talk steps.
2. Perform the work in accordance with the approved scope and procedures.
3. Open the assigned order or confirmation app. Depending on setup, this may be an action in the order or a separate **Confirm Maintenance Order Operation**-type app.
4. Select the correct order and operation. Verify the technical object and work text before recording actuals.
5. Enter the actual confirmation information required by your process, such as:
   - Actual work/time and unit
   - Personnel/capacity or employee reference, where authorized
   - Start/finish date and time
   - Final or partial confirmation indicator
   - Yield, reason code, damage/cause, or measurement result, if available
   - Completion text, findings, and follow-up work
6. Post or save the confirmation. Review the success message and resulting order/operation status.
7. Record material consumption, goods movements, measurement documents, or service-entry steps only in the approved app/process and only if your role permits it.
8. If the scope changes, stop and follow the local change-control process. Update the order or notify the planner before continuing where required.

### Confirmation quality checklist

- Is the confirmation against the correct **order and operation**?
- Does actual work reflect work performed, including the correct unit?
- Is the operation partial or final according to the real work status?
- Do the completion notes state what was found, done, and still required?
- Are follow-up defects or additional work captured in the approved process rather than hidden in free text?

**Example completion note (fictitious/redacted):**  
`Inspected drive-end area; corrected loose guard fastener. Test run satisfactory. No further action identified.`

---

## E. Technically complete the order (TECO)

Technical completion indicates that the technical work is complete. It may block or change subsequent processing, but it is not always the final financial or administrative close.

1. Confirm that all planned work is complete or appropriately closed, and that all required confirmations, findings, measurements, material postings, and follow-up actions have been addressed.
2. Verify that no active safety permit, isolation, or unresolved safety issue remains. Follow site procedures for returning equipment to service.
3. Open the order and review the header, operations, outstanding items, attachments, and status/messages.
4. Select **Technically Complete**, **Set to Technically Completed**, or the equivalent action.
5. Review any warnings carefully. Do not override an unresolved business or safety issue merely to close the order.
6. Save/confirm and verify the technical-completion status.
7. Communicate completion and retain required records according to local procedures.

> **Do not confuse TECO with final close.** Financial settlement, cost review, archiving, business completion, or final closure can be separate and configuration-dependent activities. Perform only the steps assigned to your role.

---

## 4. Common Errors and What to Do

| Message or symptom | Likely cause | End-user action |
|---|---|---|
| Required field is missing | A mandatory header, operation, date, or organizational field was not entered. | Read the message, complete the named field, and save again. |
| Technical object cannot be found or selected | Incorrect ID, wrong plant, inactive object, or missing authorization. | Use value help/search; verify the asset ID and plant. Escalate if the object should exist but is unavailable. |
| Cannot release order | Planning, approvals, dates, materials, status, or authorization prerequisites are incomplete. | Review the message and status; correct items in your role or route to the planner/supervisor. |
| Release action is not displayed | Your role or configuration does not allow release, or release occurs elsewhere. | Do not attempt a workaround; contact the authorized planner/supervisor. |
| Confirmation is rejected | Order/operation is not released, already closed, wrong confirmation data, or missing authorization. | Confirm the correct operation/status and actuals; ask the supervisor/planner to resolve status or role issues. |
| Cannot post time or material | Incorrect posting date, period closed, stock/valuation issue, reservation mismatch, or role restriction. | Preserve the evidence/message; use the approved correction or escalate to the relevant owner. |
| Cannot set TECO | Open operations, incomplete confirmations, outstanding documents, user status restrictions, or authorization issue. | Complete/review outstanding items and contact the planner/supervisor for status guidance. |
| Duplicate order discovered | Similar work was already created from a notification or earlier request. | Stop creating duplicates; link/update the existing record per local process and inform the owner. |
| Status differs from this aid | Local configuration or workflow changes the lifecycle. | Follow the current status text and local SOP; ask the process owner if the next step is unclear. |

---

## 5. Escalation Path

Use the message text, order number, affected operation, timestamp, and a screenshot that excludes sensitive data when raising an issue.

1. **Operational or safety issue:** Stop work when required by site rules; notify the responsible supervisor and follow the site safety/emergency process.
2. **Scope, priority, schedule, or technical decision:** Contact the maintenance planner or supervisor responsible for the order.
3. **Approval, release, or work-center ownership issue:** Contact the designated planner/supervisor or workflow approver.
4. **Material, service, purchasing, or inventory issue:** Contact the materials/procurement owner using the local support route; include the order/component reference.
5. **System error, missing app, authorization, or persistent validation issue:** Submit an IT/SAP support ticket through the approved channel. Include the exact message, app name, order number, time, and steps attempted—never include passwords or sensitive attachments.

**Do not:** share credentials, change order type/status solely to bypass a control, confirm work not performed, or technically complete work with unresolved safety or execution issues.

---

## 6. End-of-Order Checklist

Before you leave the order, confirm:

- [ ] Correct order, technical object, and plant are recorded.
- [ ] Scope and operations are clear and assigned to the appropriate team.
- [ ] Required safety, permit, and approval steps are complete.
- [ ] Order is released only by an authorized user/process.
- [ ] Actual work, findings, and required goods/service postings are recorded accurately.
- [ ] Follow-up work is captured in the approved process.
- [ ] Technical completion is set only when the technical work is genuinely complete and your role permits it.
- [ ] Required stakeholders have been notified.

---

## 7. Role Boundaries and Configuration Notes

This is an end-user aid, not a configuration guide. Do not attempt to alter order types, status profiles, control keys, authorizations, workflows, or master data to make a transaction proceed. Local configuration may determine:

- Which Fiori apps and actions are available.
- Mandatory fields, field labels, and default values.
- Whether orders originate from notifications, plans, projects, or other sources.
- Release rules, user statuses, approval workflows, and permitted status changes.
- Confirmation, time-entry, material, service, procurement, cost, and settlement processes.
- Whether TECO is available and what it restricts or triggers.

When local practice conflicts with this generic aid, follow the approved local procedure and contact the process owner for clarification.

---

**Document label:** Generic SAP S/4HANA Fiori maintenance-order end-user job aid  
**Data examples:** Fictitious and redacted  
**Owner for local adaptation:** Your maintenance-process owner / training lead

</body></html>