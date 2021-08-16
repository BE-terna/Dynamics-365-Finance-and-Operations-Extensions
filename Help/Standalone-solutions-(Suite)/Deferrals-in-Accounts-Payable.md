# Post Defferals in Accounts Payable

Deferrals refer to expenses or revenues, which are not recognized immediately on the income statement. Instead, they need to be deferred to a balance sheet account and appear later on the income statement.

In contrast to standard D365O functionality, this feature enables deferrals to be created directly from Vendor invoices or Vendor invoice journals by applying the pre-set deferral scheme to each invoice line. It is possible to overview posted and non-posted deferrals (on different list pages) and post them manually (by marking selected deferral lines to be posted), manually collectively (by defining date frame for deferrals to be posted)) or automatically (via batch processing).

This custom feature is part of the BE-ternaaSuiteDeferrals AdSuite D365O extension packet.

## **Setup**
---

### Deferral schemes

1. Open **Accounts payable > Setup > Deferrals > Deferral schemes**.
2. Multiple deferral schemes with separate rules can be defined: 


|**Parameter**| **Description** |
|--|--|
|Calendar Type  |Determines which calendar is used for deferrals. Fiscal, Calendar and Allocation key can be used in case of Fiscal and Calendar amounts are allocated evenly and in case of Allocation, key amounts are allocated according to rules defined in Period allocation lines. This means that a different portion of the amount can be allocated to each period.  |
|Period frequency  |Determines period as Monthly, Quarterly, Half-yearly or Yearly. In the case of Monthly Deferrals are generated on a monthly basis.  |
|Length  |Number of periods, defined in Period frequency. If the amount is supposed to be deferred in 6 months, Period frequency should be set to Monthly and Length to 6.  |
|Start deferrals on invoice date  |If set to Yes, it determines that the first deferral will be posted on the date of the invoice. This can be used in cases when the vendor invoice is issued in the middle of the year the cost refers to the whole year. All amounts that should be deferred into periods before the invoice date will be summed on the invoice date.  |
|Period key  |is enabled only if type Allocation key is defined in Calendar type. It defines the allocation key for deferrals. |
|Posting frequency  |Determines the frequency of the deferral posting within the period.   |
|Value posting  |Determines how the amount should be deferred. In the case of Even amount will be divided into even parts and in case of Scale, it will be weighed against the number of days in the period.  |
|Posting date|Defines when in the period transaction should be posted – Beginning, End or middle.|

 
 
### Number sequences

1. **Organization administration > Number sequences > Number sequences**.
2. Two number sequences need to be set up in Area Deferrals: 
   - Deferral voucher
   - Deferral ID

### Allow deferrals with project

1. **Accounts payable > Setup > Accounts payable parameters**.
2. Select to enable or disable deferrals on invoice lines linked to the project. 
3. If “Allow deferrals with project” is enabled, it is possible to select a deferral scheme on vendor invoice line with project ID. In this case, deferrals are not generated for project transactions. When this setup is not enabled, it is not possible to select deferrals on vendor invoice lines with project ID. 

### Posting definitions

1. **General ledger - Posting Setup - Posting definitions**.
2. Setup needs to be done in posting definitions (even if posting definitions are not enabled for other transactions). 
 
### Budget control

1. **Budgeting > Setup > Budget control > Budget control configuration**.
2. Deferrals can also be subject of the budget control process. Budget control will be performed if the Expense deferral option in Document and journals is marked. Option Check at line entry is disabled and cannot be enabled.
 
## **Generate deferrals**
---

1. **Accounts payable > Invoices > Pending Vendor Invoices**.
2. Line detail Deferral is added to the Pending vendor invoice line. 
 
   Every Vendor invoice line can be deferred separately, even using different **Deferral scheme**. Depending on the chosen deferral scheme, Deferral lines are generated. Default **Deferral date** depends on the setup defined on the Deferral scheme. The posting date of the first deferral line is the same as the Invoice posting date. All other deferral lines get posting date from Ledger posting setup on Deferral schemes. In this case, the Start date can be blank.<br>
<br>If deferrals refer to **previous periods** (e.g. Invoice received in March, but it refers to a whole year), the Start date needs to be entered somewhere in the past. In this case, Deferrals will be generated for current and future periods, and all deferrals that should be posted in previous periods will be summed in the current period. This amount will be posted to the cost account all other deferral lines will be posted deferrals account. This is only valid for deferral schemes with Start deferral on invoice date set to Yes. 
 
3. When the invoice is posted, lines get posted to cost accounts and at the same time correction transaction is created to move the amounts from cost to deferral account. Posting definitions are used in this process. 
It is possible to subsequently generate deferrals for invoice lines that have already been posted. In Invoice journal select desired transaction, navigate to tab Lines, and select the line for deferrals.
4. If “Allow deferrals with project” is disabled in the parameters, it is not possible to select deferrals on vendor invoice line with project ID. 
5. It is also not possible to create deferrals in invoice journal on vendor invoice line with project ID. 
 
## **Deferrals posting and inquiries**
---

Open: 
1. **Accounts payable > Inquiries and reports > Deferrals > Deferrals** or
2. **Accounts payable > Inquiries and reports > Deferrals > Unposted deferrals** or
3. **Accounts payable > Inquiries and reports > Deferrals > Posted deferrals** or
4. **Accounts payable > Inquiries and reports > Deferrals > Deferral lines**

After posting the Vendor invoice with deferral lines, a voucher is generated (cost > deferral). It can be accessed using the Voucher transactions option in the Deferral tab. 
  
All invoice lines, posted to Deferrals, are listed in the **Deferrals list**. Posted and unposted deferrals can be viewed in separate list pages (Posted/Unposted deferrals). In the **Posted deferrals list** are listed only deferrals that are completely transferred from deferrals to costs. All the others are listed in the **Unposted deferrals list**.
 
All the existing deferral lines are displayed. It is possible to filter between **Posted/Not posted/All** deferral lines.
 
Posting from deferrals to a cost account can be performed manually or automatically. 

###Deferrals for received Credit notes

Deferrals can also be posted in case of received **Credit notes**. The procedure is the same as described above, the only difference are negative amounts. 

### Manual posting

1. For manual posting go to the deferrals list, open one deferral and then go to Lines. Mark the line and click Post. A deferral voucher will be generated. 
2. Functions as View distributions, Subledger journal, Voucher transactions, Budget checking are available for each deferral line. 
3. Deferrals can also be manually posted from **Accounts payable > Inquiries and reports > Deferrals > Deferral lines** form by choosing a specific deferral (line) and clicking the **Post** button. From the same form, it is also possible to: View distributions, Subledger journal, Voucher transactions and performs Budget checking for each deferral line.

### Manual mass posting

1. Open **Accounts payable > Periodic tasks > Deferrals > Post deferrals**.
2. Mass posting of deferrals can be performed. 
3. The date period needs to be defined. All deferrals that have a posting date in the defined interval, will be posted. 

### Automatic posting

1. Open **Accounts payable > Periodic tasks > Deferrals > Post deferrals**.
2. Deferrals can be posted automatically if batch processing is defined. 

## **Budget check** 
---

Deferrals can be included in a budget check (if enabled in Budget check parameters). In this case, the budget is reserved at the moment of generating the invoice (standard) and reversed at the moment of posting the invoice. When posting deferrals (Deferrals > Expense account) budget is posted in the correct period. 

Budget check can also be performed periodically as Batch job. Go to **Accounts payable > Periodic tasks > Deferrals > Perform budget check on deferrals** and define recurrence rules. This way bufget check will be performed periodically for all generated deferral lines. 

Scenario: 
   - Generate Purchase order - Budget reservation is created in Encumbrances section 
   - Generate Vendor invoice from Purchase order - Budget reservation from the Purchase order is released. Budget reservation in section Actual expenditures is generated. 
   - Generate Deferrals for specific Vendor invoice line - Post Invoice - Budget in Actual expenditures is released (negative line with original amount is generated) 
   - Post Deferrals (deferrals - Expense) - Budget reservation is generated in the Actual expenditures section in the correct period. 

## **Reversal of Vendor invoice with deferrals** 
---
In cases when Vendor invoice has related deferrals, it can can be reversed only after the deferrals are also reversed. 

1. Go to **Accounts payable > All Vendors (and select specific Vendor) > Transactions (select Vendor invoice that needs to be reversed) > Reverse**. When user wants to reverse Vendor invoice with deferrals, error message appears. Invoice can not be reversed, until related deferrals are reversed.
1. Go to Deferrals list **Accounts payable > Inquiries and reports > Deferrals > Deferrals** and select specific deferral. Reverse **Deferral lines** first (if they are posted) and then reverse **Deferral header**. Deferral header can be reversed only if related deferral lines are reversed. If posted deferral lines exist, error will appear. In case when Deferral header is reversed, Post button on Deferral lines is disabled. 
1. Go to Vendor invoice that needs to be reversed and reverse it with reverse function. 

Information about **deferral voucher** is added to following Deferral list pages:
-  Deferrals
- Unposted Deferrals
- Posted deferrals
- Deferral lines (vidible only when filter is set to All).