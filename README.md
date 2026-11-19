# Buildium + QuickBooks Online: Property Management Bookkeeping Workflow

A monthly workflow for books that live in two places: Buildium for rent, owners, vendors and trust bank accounts, and QuickBooks Online for the owner's or the management company's own books.

It covers both sides:

- **Investors and owners** whose properties are run in Buildium (by them or by a property manager), and whose CPA wants the books in QuickBooks Online.
- **Property management companies** that run trust accounting in Buildium and keep the company's own books in QuickBooks Online.

## What's included

| File | What it is |
|---|---|
| buildium-to-qbo-account-mapping.csv | Example mapping from Buildium GL accounts to QuickBooks Online accounts and classes |

## The rule that matters most

**Money held in trust is not the property manager's money.** Rent collected for owners and tenant security deposits sit in the trust account on behalf of other people. For the management company they are liabilities, not income. The company's income is its management fees, leasing fees and similar charges.

Most problems in property management books come from mixing these up.

## Part 1: Owner books in QuickBooks Online

Record each month in QuickBooks from the Buildium **Rental Owner Statement**, one property at a time, tagged with the property's class.

Add one asset account to QuickBooks: **1040 Cash Held by Property Manager** (Other Current Assets). It holds the owner's money that is still sitting in the manager's trust account, such as the reserve.

### Worked example: 123 Oak St, March

From the owner statement: rent $1,800, late fee $50, repairs $300, management fee $144, distribution to the owner's bank $1,406.

**Step 1. Record the month from the owner statement:**

| Account | Debit | Credit |
|---|---:|---:|
| 1040 Cash Held by Property Manager | 1,406 | |
| 6090 Repairs | 300 | |
| 6060 Management Fees | 144 | |
| 4000 Rental Income | | 1,800 |
| 4020 Late Fees | | 50 |
| **Total** | **1,850** | **1,850** |

**Step 2. Match the distribution in Bank transactions** as a transfer:

| Account | Debit | Credit |
|---|---:|---:|
| 1000 Operating Checking | 1,406 | |
| 1040 Cash Held by Property Manager | | 1,406 |

After step 2, 1040 Cash Held by Property Manager should equal the ending balance on the owner statement (here $0, because everything was paid out).

Account numbers match [qbo-real-estate-chart-of-accounts](https://github.com/shoaibabu843-gif/qbo-real-estate-chart-of-accounts). Use buildium-to-qbo-account-mapping.csv to map your own Buildium accounts.

### Owner side checklist

- [ ] Rental Owner Statement received for every property
- [ ] One summary entry per property per month, tagged with its class
- [ ] Distribution deposits matched as transfers from 1040, not recorded as income
- [ ] 1040 balance agrees with the owner statement ending balance
- [ ] Security deposits held by the manager tie to the tenant list, if you track them on your books
- [ ] Large repairs reviewed: repair (expense) or improvement (capitalize)

## Part 2: Management company books

### In Buildium (trust accounting)

- [ ] Reconcile every trust and operating bank account in Buildium to the bank statement
- [ ] Run the bank account balance breakdown and confirm no owner has a negative balance
- [ ] Confirm the security deposit liability agrees with the tenant deposit list
- [ ] Charge management and leasing fees in Buildium and pay them from trust to the company's operating account
- [ ] Send Rental Owner Statements

### Three-way reconciliation (every month, for every trust account)

| Must agree | Source |
|---|---|
| Adjusted bank balance | Bank statement, plus deposits in transit, minus outstanding checks |
| Book balance | Buildium bank reconciliation |
| Total owed to owners and tenants | Owner ending balances plus security deposits and prepaid rent held |

If any of the three differ, stop and find the difference before sending owner statements.

### In QuickBooks Online (company books)

- [ ] Management and leasing fees transferred from trust recorded as income: 4200 Management Fee Income, 4210 Leasing Fee Income
- [ ] Company expenses (payroll, office, software, insurance) paid only from the company's operating account, never from trust
- [ ] Operating bank account reconciled in QuickBooks
- [ ] Profit and Loss reviewed

## Common mistakes

- Recording rent collected for owners as the management company's income
- Recording owner distributions as an expense on the owner's books
- Paying company bills from the trust account
- Recording the management fee twice: once from the owner statement and again from the bank feed
- Letting an owner's balance go negative, which means other owners' money is covering it
- Security deposit liability that no longer agrees with the tenant list

## Notes

- Trust accounting rules are set by each state, so check the rules where the properties are.
- If you use an integration between Buildium and QuickBooks, still tie the QuickBooks numbers back to the owner statement and the Buildium bank reconciliation every month.
- This is a bookkeeping workflow, not legal or tax advice.

---

**Need Buildium and QuickBooks books kept in sync?** I'm Md Abu Shoaib, a bookkeeper for real estate investors and property managers.
👉 [Hire me on Upwork](https://www.upwork.com/freelancers/~011eae234a1e1ba092)
