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






