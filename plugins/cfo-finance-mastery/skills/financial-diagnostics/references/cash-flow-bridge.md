---
name: Cash Flow Bridge & Working Capital Timing
description: Understand how cash flow connects income statement to balance sheet, manage seasonal cash swings, and model cash recovery timing.
---

# Cash Flow Bridge & Working Capital Timing

## Cash Flow Statement: The Bridge Between P&L and Balance Sheet

**The fundamental relationship:**

```
Income Statement (accrual):
  Profit = Revenue - Expenses (timing of cash is irrelevant)

Balance Sheet (position):
  Shows AR (customers owe you), AP (you owe vendors), Inventory (products you own)

Cash Flow Statement (movement):
  Shows when cash ACTUALLY moves
  = Profit +/- changes in working capital
```

**Example:**
```
January P&L shows $50K profit (accrual basis)
January balance sheet shows AR increased $50K (customers owe you the $50K)
January cash flow shows $0 cash from operations (profit offset by AR increase)

Actual bank account: Unchanged, despite "profitable" month
```

---

## The Three Sections of Cash Flow

### Operating Activities: Cash from Running the Business

**Start with:** Net Income (from P&L)

**Add back non-cash expenses:**
- **Depreciation:** $5K expensed on P&L; no cash paid. Add it back.
- **Amortization:** Similar to depreciation for intangible assets.
- **Stock-based compensation (if applicable):** Expensed but no cash paid.

**Adjust for working capital changes:**

**Accounts Receivable changes:**
- If AR increases (customers owe more): Subtract from operating cash (cash not collected)
- If AR decreases (collected from customers): Add to operating cash (cash received)

Formula:
```
Change in AR = Current AR - Prior AR
If positive (AR grew), subtract from operating cash (cash outflow)
If negative (AR shrank), add to operating cash (cash inflow)
```

**Example:**
```
Prior month AR: $100K
Current month AR: $150K
Change: +$50K (increase)
Impact on operating cash: -$50K (customers owe $50K more; you haven't collected it)
```

**Inventory changes:**
- If inventory increases: Subtract from operating cash (cash spent on inventory)
- If inventory decreases: Add to operating cash (sold inventory; cash received)

Formula:
```
Change in Inventory = Current Inventory - Prior Inventory
If positive (inventory grew), subtract from operating cash
If negative (inventory shrank), add to operating cash
```

**Example:**
```
Prior month inventory: $200K
Current month inventory: $220K
Change: +$20K (increase)
Impact on operating cash: -$20K (spent $20K on inventory)
```

**Accounts Payable changes:**
- If AP increases: Add to operating cash (delayed paying vendors = cash stays with you)
- If AP decreases: Subtract from operating cash (paid vendors = cash leaves)

Formula:
```
Change in AP = Current AP - Prior AP
If positive (AP grew), add to operating cash (delayed payment)
If negative (AP shrank), subtract from operating cash (paid vendors)
```

**Example:**
```
Prior month AP: $80K
Current month AP: $100K
Change: +$20K (increase)
Impact on operating cash: +$20K (delayed paying vendors; cash stays with you)
```

**Other adjustments:**
- Accrued expenses: Similar to AP (increases = cash stays, decreases = cash leaves)
- Deferred revenue: Increases = cash already collected (add back)
- Changes in prepaid expenses: Increases = cash spent (subtract)

**Operating Cash Flow Formula:**
```
Operating Cash Flow = Net Income
                    + Depreciation & Amortization
                    - Increase in AR (or + Decrease in AR)
                    - Increase in Inventory (or + Decrease in Inventory)
                    + Increase in AP (or - Decrease in AP)
                    + Increase in Accrued Expenses
                    +/- Other working capital changes
```

### Investing Activities: Cash from Asset Purchases/Sales

**Equipment, vehicles, computers purchases:** Negative (cash outflow)
**Equipment sales:** Positive (cash inflow)
**Investments:** Negative (cash outflow to buy) or positive (cash inflow to sell)
**Business acquisitions:** Negative (cash spent to acquire)

**Key insight:** This section shows whether you're growing (high investment) or harvesting (low investment with sales of assets).

### Financing Activities: Cash from Debt, Equity, Dividends

**Debt increases:** Positive (cash received from new loan)
**Debt repayment:** Negative (cash paid to lenders)
**Equity injections:** Positive (investors contribute capital)
**Owner draws/dividends:** Negative (cash extracted by owners)

**Key insight:** This section shows how the business is funded (debt vs. equity) and how profits are distributed.

---

## The Complete Cash Flow Formula

```
Operating Cash Flow
  + Investing Cash Flow
  + Financing Cash Flow
= Net Change in Cash

Beginning Cash + Net Change in Cash = Ending Cash
```

**Example:**
```
Operating Cash Flow:        $50,000 (profitable operations)
Investing Cash Flow:       -$30,000 (purchased equipment)
Financing Cash Flow:       -$10,000 (repaid debt)
Net Change in Cash:        $10,000
Beginning Cash:            $40,000
Ending Cash:              $50,000
```

---

## Red Flags in Cash Flow

### Operating Cash Flow Negative (Despite Profit)

**Pattern:**
```
Net Income: $100,000 (P&L shows profit)
Operating Cash Flow: -$50,000 (cash declining)
```

**Diagnosis:**
- AR increased more than profit (customers owe you money not collected)
- Inventory increased significantly (cash tied up in stock)
- AP decreased (paid vendors; cash outflow)
- All three combined: Recipe for cash crisis

**Solution:**
1. Accelerate AR collection (focus on DSO improvement)
2. Reduce inventory purchases (manage demand forecasting)
3. Negotiate AP terms extension (delay vendor payments if terms allow)
4. Consider short-term financing to bridge gap

### Large Gap Between Net Income and Operating Cash Flow

**Rule:** Operating cash flow should be within 20% of net income (same direction).

**Example red flags:**
```
Net Income: $50,000
Operating Cash Flow: $30,000
Difference: $20,000 (40% gap)
This is high; working capital is consuming significant cash.

Net Income: $50,000
Operating Cash Flow: -$20,000
Complete disconnect; major working capital problem.
```

### Investing Cash Flow Trend

**Healthy scaling business:** Investing cash flow negative (buying equipment to support growth)
**Mature business:** Investing cash flow near zero (maintenance CapEx only)
**Declining business:** Investing cash flow positive (selling equipment, not replacing)

**Example:**
```
Year 1: Investing cash flow -$200,000 (aggressive equipment purchases)
Year 2: Investing cash flow -$150,000 (continued growth investment)
Year 3: Investing cash flow -$50,000 (growth slowing, maintenance only)
Year 4: Investing cash flow +$30,000 (selling equipment, harvesting phase)
```

### Financing Cash Flow Pattern

**Scaling startup:** Financing positive (debt/equity injections funding losses)
**Profitable business:** Financing negative (repaying debt, extracting owner draws)
**Overleveraged business:** Financing positive but operations negative (using debt to cover losses)

**Red flag:**
```
Operating Cash Flow: -$100,000 (business burning cash)
Financing Cash Flow: +$150,000 (new debt/equity funding the burn)
Net effect: Cash position stable but dependent on external funding
Sustainability: Unsustainable unless operations improve
```

---

## Seasonal Cash Flow Planning

Seasonal businesses face predictable cash swings. The key is planning ahead.

### Identifying Seasonality in Cash Flow

**Example: Retail business with Christmas peak**

```
Month    Sales    Cash Impact   Running Cash
Jan      $50K     -$20K         $30K (post-holiday slump)
Feb      $60K     +$10K         $40K
Mar      $65K     +$15K         $55K
Apr      $70K     +$20K         $75K
May      $75K     +$25K         $100K
Jun      $80K     +$30K         $130K
Jul      $70K     +$20K         $150K
Aug      $65K     +$15K         $165K
Sep      $80K     +$30K         $195K
Oct      $100K    +$50K         $245K (inventory buildup for holidays)
Nov      $120K    +$70K         $315K (peak season)
Dec      $150K    +$100K        $415K (Christmas peak)
```

**Observations:**
1. Cash peaks in December (highest revenue + highest operating cash flow)
2. Cash dips in January (lowest revenue)
3. Inventory buildup in Oct-Nov (AP increases; AP increase = cash inflow helping cash position)
4. Cash burn risk: If January DSO increases (customers slow to pay), cash swing is severe

### Seasonal Cash Planning Strategy

**Step 1: Calculate seasonal factors**

For each month, calculate seasonal index:
```
Seasonal Index = Average Month Sales / Annual Average Sales

Example:
Annual average sales: $80K/month
December sales: $150K
December seasonal index: $150K / $80K = 1.875 (Christmas is 1.875x average)

January sales: $50K
January seasonal index: $50K / $80K = 0.625 (January is 0.625x average)
```

**Step 2: Plan cash reserves**

Set a minimum cash balance based on seasonal low:
```
If January is seasonal low ($50K sales) and DSO is 30 days,
AR collection in January will be prior month (December) revenue = $150K.

Minimum cash needed to cover:
- Operating expenses in January: $40K (estimate based on revenue)
- AP payments scheduled: $50K (estimated)
- Other obligations: $10K

Total needed: $100K

Current cash in December (end): $415K
Planned minimum: $100K
Cash cushion: $315K
```

**Step 3: Forecast cash needs through low season**

```
December Cash:        $415K
January Operating:    -$40K
January AP Payments:  -$50K
January Receivables:  +$120K (collecting December revenue)
January Ending Cash:  $445K (strong, ready for Q1)
```

**Step 4: Plan for peak season builds**

In months before peak season, you need cash for inventory:
```
October (preparing for holiday peak):
- Inventory purchases: -$80K (in advance)
- Operating expenses: -$50K
- Revenue/collections: +$100K
- Net cash impact: -$30K

In this scenario, AP increases help (delayed vendor payment keeps cash):
- If you negotiate Net 60 with suppliers, October inventory purchase
  won't be paid until December (preserves cash for November/December)
```

---

## Tax Payments & Cash Planning

**Critical:** Tax payments are cash outflows not on your P&L until accrued.

### Quarterly Estimated Tax Payments

**Pattern:**
```
Q1 (Jan-Mar) profit: $30K
Estimated quarterly tax (25% of profit): $7,500 payment due Apr 15

On P&L: Tax expense is recorded Jan-Mar ($7,500)
In Cash: $7,500 leaves bank account on Apr 15

If DSO is 30 days and Q1 sales were made on credit (not yet collected by Apr 15),
you're paying taxes on revenue you haven't collected yet.
Cash crisis trigger.
```

### Year-End Tax Bill

**Pattern:**
```
Annual profit: $100K
Annual tax bill: $25K (due Jan 15 next year)

This is NOT an expense on current year P&L (it's future payment).
But it's a cash outflow next year.
Cash flow projection must account for this.

If you don't set aside $25K in December/January, January becomes cash-negative.
```

### Planning for Tax Cash Outflow

**Rule:** Set aside 25-35% of monthly profit for taxes.

**Example:**
```
Monthly profit: $10K
Set aside for taxes: $3K (30%)
Actual available cash: $7K

If monthly tax is $3K set-aside:
Jan-Mar tax + Q1 payment = covered
Q2 set-aside + Q2 payment = covered
etc.
```

---

## Working Capital Cycle & Cash Timing

### The Complete Cycle

```
Day 1:  Purchase inventory on Net 30 terms (cash stays with you for 30 days)
        AP increases; no immediate cash impact

Day 15: Sell inventory to customer on Net 30 terms
        Revenue recognized; AR increases
        Cash timing: 30 days until payment

Day 30: Pay vendor for Day 1 inventory
        Cash outflow = inventory cost

Day 45: Receive payment from customer (Day 15 sale)
        Cash inflow = revenue collected

Net timing: Day 30 payment vs Day 45 collection = 15-day cash gap
           Must carry 15 days of working capital from own funds
```

**If you grow 10% month-over-month with unchanged DSO/DPO/DIO:**
```
Current working capital requirement: $100K
Month 2: Working capital requirement: $110K (+$10K)
Month 3: Working capital requirement: $121K (+$11K)
Month 4: Working capital requirement: $133K (+$12K)
Month 6: Working capital requirement: $161K (+$28K cumulative from Month 1)

Growth = automatic working capital drain. Plan for financing.
```

### Cash Conversion Cycle Optimization

**Formula:**
```
Cash Conversion Cycle = DSO (days to collect) + DIO (days in inventory) - DPO (days to pay)
```

**Example:**
```
Current:
DSO: 45 days
DIO: 30 days
DPO: 30 days
Cycle: 45 + 30 - 30 = 45 days

After optimization:
DSO: 30 days (better collections)
DIO: 25 days (leaner inventory)
DPO: 45 days (negotiated longer terms)
Cycle: 30 + 25 - 45 = 10 days

Impact: 35-day improvement = 35 days of additional cash freed
        If monthly revenue is $100K, that's $116K in freed cash
```

---

## Cash Flow Forecasting Template

**Build a 12-month rolling forecast:**

```
                Jan     Feb     Mar     Apr     May     Jun
Revenue (accrual) $100K  $105K  $110K  $115K  $120K  $125K

Operating Cash Flow:
  Net Income      $ 20K  $ 21K  $ 22K  $ 23K  $ 24K  $ 25K
  + Depreciation  $  2K  $  2K  $  2K  $  2K  $  2K  $  2K
  - Change in AR  $ -5K  $ -2K  $ -3K  $ -2K  $ -3K  $ -2K
  - Change in Inv $ -5K  $ -3K  $ -2K  $ -3K  $ -2K  $ -2K
  + Change in AP  $  3K  $  2K  $  2K  $  2K  $  3K  $  2K
Operating CF      $ 15K  $ 20K  $ 21K  $ 22K  $ 24K  $ 25K

Investing CF      $ -10K $ -5K  $ -5K  $ -8K  $ -10K $ -8K
Financing CF      $  0K  $  0K  $  0K  $  0K  $  0K  $  0K
Net Change        $  5K  $ 15K  $ 16K  $ 14K  $ 14K  $ 17K

Beginning Cash    $ 40K  $ 45K  $ 60K  $ 76K  $ 90K  $104K
Ending Cash       $ 45K  $ 60K  $ 76K  $ 90K  $104K  $121K
Minimum Required  $ 30K  $ 30K  $ 30K  $ 30K  $ 30K  $ 30K
Surplus/(Deficit) $ 15K  $ 30K  $ 46K  $ 60K  $ 74K  $ 91K
```

**Key metrics to track:**
- Operating CF trending positive (good)
- Cash above minimum required (safe)
- Cash surplus growing (financial flexibility)
- If any month shows deficit, that's a borrowing trigger

