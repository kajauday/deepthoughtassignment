# Task 1: Daily Clinic Inventory Micro-Audit
## STEP 1 — Identify High-Risk Medicines


| Medicine (Master Name) | Why High Risk |
|------------------------|--------------|
| Dolo 650               | High Daily Sales With Many Name Variants can cause manual entry mistakes|
| Azithromycin 500       | Same Variant uses Abbreviation which can cause errors and mismatch the bill with the stock, High Value Per Unit |
| Pantoprazole 40        | Frequently prescribed medicine  |


## STEP 2 — Daily Name-Variation Check

Because billing entries are done manually, the same medicine may be entered under different names. This step ensures that such name variations are identified for high-risk medicines and mapped to a single name to avoid error.

| Master Name | Variations Of Medicine | Action  |
|---------------------|---------------------------|--------------|
| Dolo 650            | Dolo, Dolo 650, Dolo kind | Map All Variations to master name "Dolo 650" |
| Azithromycin 500    | Azithro, Azithromycin    | Map all variations to "Azithromycin 500" |
| Pantoprazole 40     | Pantop, Pantoprazole     | Map those entries as "Pantoprazole 40" |


**Action**
- If multiple names refer to the same medicine,Map them under one master name.
- If a name is unclear, Inform billing staff and update it.

## STEP 3 — Daily Usage Reasonableness Check

This step checks whether the daily usage of high-risk medicines is reasonable by comparing expected closing stock with actual closing stock. It helps identify quantity errors, missed billing entries, or inventory leakage early.


| Medicine | Expected Closing Stock | Actual Closing Stock | Difference | Action |
|---------|------------------------|----------------------|------------|--------|
| Dolo 650 | 1460 | 1440 | -20 | Verify sales entries for missed or incorrect quantities |
| Azithromycin 500 | 490 | 480 | -10 | Verify billing quantities and sale entries |

**Action**
- Recheck sales entries for the day
- Correct any quantiy error or entry error

  ## STEP 4 — Random Bill Spot Check (5–10 mins/day)

This step involves randomly selecting a few bills from the daily sales register to check for billing accuracy of high-risk medicines. This helps catch human errors at the individual bill level that may not be visible in total stock checks.

**What you do:**
- Randomly select bills from the daily sales register
- Focus only on bills that include high-risk medicines
- Verify medicine name , its quantity , if its the correct variation.

| Bill No | Entered Medicine | Issue Found | Action |
|--------|------------------|-------------|--------|
| B101 | Dolo | Name not mapped to master name | Corrected to "Dolo 650" |
| B103 | Dolo kind | Quantity error | Corrected quantity in billing |

**What you flag:**
- Wrong or non-mapped medicine names
- Incorrect quantities

**Action:**
- Correct the bill entry immediately
- Inform billing staff about the mistake and update it.

## STEP 5 — Weekly Pattern Tracking (15 mins/week)

This step miantains an error log.

| Date | Medicine | Error Type | Repeated? |
|------|----------|------------|-----------|
| Aug 1 | Dolo 650 | Name variation | Yes |
| Aug 2 | Dolo 650 | Name variation | Yes |
| Aug 4 | Azithromycin 500 | Wrong quantity | No |

**What you flag:**
- Same error type occurring more than 3 times in a week
- Same medicine repeatedly having errors

**Action:**
- If the same error repeats then retrain billing staff and update it
- If multiple medicines show similar issues, update the standard operating procedure


## STEP 6 — Doctor Escalation Rules

This step defines clear rules for when inventory or billing issues should be escalated to the doctor. The goal is to protect the doctor’s time by not effecting the operating procedure.


**Doctor is involved only if:**
- Inventory error affects availability of a medicine 
- Financial impact is significant and cannot be resolved through correcting bills
- Same issue keeps raising even after trying to correct it.


**Action:**
- Escalate only on issues which are verified , not raw data and issues which are not 100% certain
- Keep escalation brief and focused on the issue.
- Focus on solution of the issue and not where the issue came from or who is to blame.


## Daily Checklist

- Review sales entries for high-risk medicines only
- Check for new or unusual medicine name variations and map them to master names
- Perform usage reasonableness check by comparing expected vs actual closing stock
- Randomly check 3–5 bills involving high-risk medicines for correct name and quantity
- Correct any obvious errors found and log them for weekly review


## Weekly Checklist

- Review error logs from daily checks
- Identify repeated errors or patterns by medicine or error type
- Retrain billing staff if the same mistake repeats multiple times
- Update standard billing instructions if required
- Escalate to doctor only if issues affect treatment availability or have material financial impact



# Task 2: Patient Care & Communication System


## STEP 1 — Message Type Classification

Patient messages are classified into simple, non-overlapping types so clinic staff can decide handling immediately and direct it to doctor only when its needed .

| Message Type | What it Covers | Doctor Input Needed? |
|-------------|---------------|----------------------|
| Appointment & Follow-up | Visit reminders, rescheduling, missed appointments | No |
| Medicine Usage Info | How/when to take medicines already prescribed | No |
| Recovery Doubts| What is normal after treatment or procedure | No |
| New Symptom Query | Any new, worsening, or unclear symptom | Yes |
| Medication Change Request | Requests to start/stop/change dosage | Yes |

**Action Rules:**
- “No” are handled by staff.
- “Yes” types are escalated to doctor review.

## STEP 2 — Care Control Sheet (Daily Working Sheet)

All patient communication for the day is tracked in one Google Sheet to ensure nothing is missed and doctor involvement is controlled.

**Sheet Name:** Care_Control - UPLOADED THE GOOGLE SHEET 

| Patient Name | Phone | Visit Type | Message Type | Message Content | Doctor Approval | Status |
|-------------|-------|------------|--------------|-----------------|-----------------|--------|
| Ramesh K | +91 9876543210 | OPD | Post-Procedure | Blank | Required | Pending |
| Sita N | +91 847368901 | OPD | Custom | Auto-filled | Not Required | Waiting |
| Uday K | +91 7582015678 | Procedure | Follow-up | Auto-filled | Not Required | Pending |
| Rajagopal L | +91 748295732 | OPD | Follow-up | Blank | Required | Waiting |
| Sripathi M | +91 4648592732 | Procedure | Custom | Blank | Required | Waiting |



**Rules:**
- One row = one patient message
- Message Content is auto-filled only for “No Doctor Input” types
- Doctor Approval is marked **Required** only for the last two message types from Step 1
- Status controls workflow: Pending → Waiting → Sent → Closed

## STEP 3 — Daily Follow-up & Message Queue (Google Sheets)

This step ensures that patient messages are sent on time and that doctor attention is only required for pending decision-critical cases.

**Sheet Used:** Care_Control

| Patient Name | Phone | Visit Type | Message Type | Message Content | Doctor Approval | Status |
|-------------|-------|------------|--------------|-----------------|-----------------|--------|
| Ramesh K | +91 9876543210 | OPD | Post-Procedure | Blank | Required | Pending |
| Sita N | +91 847368901 | OPD | Custom | Auto-filled | Not Required | Waiting |
| Uday K | +91 7582015678 | Procedure | Follow-up | Auto-filled | Not Required | Pending |
| Rajagopal L | +91 748295732 | OPD | Follow-up | Blank | Required | Waiting |
| Sripathi M | +91 4648592732 | Procedure | Custom | Blank | Required | Waiting |


**Daily Process:**
- Clinic staff filters the Auto-Send Queue and sends template messages
- After sending, Status is updated to “Sent”
- Doctor reviews only the Doctor Review Queue and provides short instructions
- Staff updates Message Content and sets Status to “Sent”

**Action Rules:**
- No row should remain in “Pending” status at end of day
- Doctor reviews only filtered rows marked “Doctor Input Required = Yes”
- Unsent messages are carried forward and reviewed first the next day


## STEP 4 — Patient Question Handling

| Patient | Phone | Question | Answer | Status |
|--------|-------|----------|--------|--------|
| Ramesh K | 91 9876503210 | Is Headache a common side effect? | NO | Done |
| Uday K | 91 7702594925 | I need a change in dosage |  | Pending |


**Action:**
- If Status = Done → Send response to patient and close the entry
- If Status = Pending → Move to doctor review queue in next review window
- No question remains unanswered at day end
- unresolved items are carried forward and donefirst next day


## STEP 5 — Message Dispatch Rules

Messages are sent only when all required conditions are met to avoid partial or incorrect communication.

**Dispatch Conditions:**
- Message Content is filled
- Doctor Approval = Not Required OR Approved
- Status = Pending or Waiting

**After Sending:**
- Update Status to Sent
- Do not resend the same message on the same day



## STEP 6 — End-of-Day Closing Check

A short daily check ensures no patient communication is missed.

**Before clinic closes:**
- Filter rows where Status ≠ Sent and Status ≠ Closed
- Resolve simple issues immediately
- Carry forward unresolved doctor-dependent cases to next day

**Rule:**
- No sheet is closed with unanswered patient queries


## STEP 7 — Optional Automation & Integration

-Once the manual workflow is stable, this system can be automated using Google Apps Script by scanning the Care_Control and Patient_Questions sheets for rows marked as Pending. For messages that do not require doctor approval, the script can automatically send the prepared message via a WhatsApp API and immediately update the status to Sent. For doctor-dependent cases, automation is triggered only after the approval field is marked Approved, ensuring no medical judgment is bypassed. This automation reduces repetitive staff work, maintains the same control logic as the manual process, and ensures that failures or exceptions remain visible in the sheet instead of silently failing.
  












