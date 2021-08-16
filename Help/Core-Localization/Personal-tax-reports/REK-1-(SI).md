# Prepare REK-1 report

REK-1 is a Slovenian personal tax report, which legal entities or natural persons who perform business activities are obliged to report to the Slovenian tax authority (FURS) if they pay incomes from employment. Report layout and the required conditions are based on paragraph 8, Article 58 of the Tax Procedure Act - ZDavP-2.

Since salaries are standardly not calculated in D365, the Slovenian REK-1 reporting feature enables only the generation of the legally required reporting in terms of employee travel expenses. Transactions for REK-1 reporting are generated automatically from expense reports and invoices for travel expenses, but they can also be manually added. Export (XML) in the format, required by the Slovenian tax authorities and a preview (HTML) of the REK-1 report are also part of this localized feature.

##**Setup**
---

### General ledger parameters - ER format

1. Open General ledger > Ledger setup > General ledger parameters.
2. To define the export format, navigate to BE-terna localization and section Electronic reporting. Select “REK1 report” in the field “REK 1 electronic reporting format".
 
### Income type

For REK-1 reporting it is necessary to create income types. Income types define which field on iREK will the transaction be recorded in. Create as many income types as there are reporting fields (the naming in the Income type field is optional). 
By selecting the appropriate value in the field "iREK field B", the amount of the transaction (that carries the information about income type) will be displayed inadequate fields on REK-1 report.

1. Open Tax > Setup > Adriatic > Expenses > Income types.
2. “REK Income Type” value is entered in Tax > Setup > Slovenia > Withholding tax > REK Income Types.
 
### _Income type for cash advances_

_NOTE: Deprecated with version 8.1!_

_1. Open Expense management > Setup > General > Expense management parameters._
_2. Income type for cash advances needs to be defined in the “BE-terna” section. This ensures that cash advances are also generated in REK-1 transactions and reported._ 
 
### Payment methods

1. Open Expense management > Setup > General > Payment methods.

For each of the payment methods it is required to define the moment when the transaction becomes relevant for reporting by choosing Income reporting mode:


|**Value**|**Description**|
|--|--|
|At settlement  |expense transaction becomes a candidate for reporting when it is settled (paid)  |
|At expense posting  |expense transaction is included in the list of candidates for REK-1 after expense cost is posted  |
|No reporting  |it is not included in REK-1 reporting  |

If income reporting mode “At settlement” or “At expense posting” is chosen, it is necessary to define Income type, created for REK-1.

Trigger for reporting is the payment to the worker (reimbursement). In case of credit card there are two options:
   - Business trip cost, paid with a credit card, can be reported from expense report if payment method has income reporting mode “At expense posting”; such transaction will become a candidate for REK reporting right after the expense report is posted. In this case, the REK reporting field “For worker” on vendor invoice for credit card expense should be left empty, otherwise, the transaction would be reported twice (first, after posting expense report, and second, after vendor invoice for credit card expenses is paid).
   - Travel expense, paid with a credit card, can also be reported from vendor invoice which carries information about worker (more in chapter Purchase document entry). In this case, expense-paid with a credit card, if it is entered on the expense report, should have income reporting mode “No reporting”. This way, the transaction from the expense report will not become a candidate for REK reporting – expense will be reported from the vendor invoice. 

### Expense categories

Open Expense management > Setup > General > Expense categories.

Additional setup is added to Expense categories: 
1. **Income type.** Select adequate income types for each of the expense categories that need to be reported. Values for Income types are added manually and should be created in such way that one category fits one income type (can be reported in one “B06” field). 
2. **Options for REK-1** Following values are available: 

|**Value**|**Description**|
|--|--|
|Default|Default setup for newly created entries  |
|Always exclude  |Transactions that should not be reported in REK-1. In this case field Income type should be empty.  |
|Report by event date  |  |
 
Information about Income type is recorded on vendor transaction upon expense posting.

###_Methods of payment_
_NOTE: Deprecated with version 8.1!_

_Open Accounts payable > Payment setup > Methods of payment._

_If value"Income type" is marked in Methods of payment (Payment attributes section), information about income type is transferred from vendor transaction to payment journal line when journal line is generated by using Payment proposal function._ 

_If transactions to vendor payment journal are transferred using “Settle transactions”, information about Income type is not transferred from transaction to vendor payment journal line. Attempt to post such payment journal line results in error – it is necessary to manually choose Income type in tab Payment before posting._
 
## **Purchase document entry**
---

Vendor invoice or Purchase order line details allow reporting of the business trip cost for a worker in tab Personal tax. Select adequate Income type and Worker in the REK-1 section. 
 
Creating a vendor invoice, linked to purchase order, transfers information for REK-1 reporting from purchase order to invoice Line details. 
The transaction that was posted from vendor invoice with information about worker does not carry Income type information (VendTrans Income type field is empty) but is always included in the list of candidates for REK-1 after it has been paid.

## **Generating REK-1 transactions**
---

Open Tax > Declarations > Slovenia > REK reporting > REK-1 > Personal tax transactions.

Transactions to report need to be collected in Personal tax transactions form first. Only entries generated in this form can be reported in REK-1. Use button **“Generate transactions”** to define the date period for transferring REK-1 transactions. 

Transactions are generated from three sources (when each transaction is generated – after posting, after settlement – depends on setup on payment methods):


|**Source**|**Description**|
|--|--|
|Expense lines|from posted expense reports when the method of payment’s income reporting mode is “At expense posting”.  |
|Posted vendor invoice lines|from paid vendor invoices with a link to the worker (after vendor invoice, with link to the worker, is settled, it becomes a candidate for REK-1 reporting).  |
|Vendor transactions|from paid reimbursement to work when the method of payment’s income reporting mode is “At settlement”.  |

   
Message details upon generating displays number of lines that have been added from each source.

Personal tax transactions form can be filtered by “Open” transactions (not yet reported), “Reported”, and “All”. Following fields are displayed: 


|**Field**|**Description**|
|--|--|
|Date  |payment date (if income reporting mode is “At settlement” or in case of vendor invoice transaction) or transaction date (when income reporting mode is “At expense posting”).  |
|Worker  |worker for whom the business trip cost will be reported.  |
|Amount  |transaction amount (in case of vendor invoice amount reported is base + VAT).  |
|Income type  |income type of the transaction  |
|Linked  |source from which each entry was generated (options are: Vendor invoice line, Expense line, Vendor transaction; manually added lines have value “Not linked”).  |
|Reporting number  | number of created REK-1 report that contains this transaction; once a line has a reporting number, it cannot be edited anymore. If REK-1 report has not yet been generated, such transaction will have an empty value in field Reporting number. If the REK-1 report is deleted, information about the reporting number is automatically deleted.|
|Generated  |marked with a checkmark are those transactions that are created through “Generate transactions” functionality; manually added entries do not have a checkmark in this field.  |
|Description  |displays additional information about the transferred line; for manually added lines this is a free text field.  |


  
Button “Open source” displays source document for the selected transaction (Expense report for expense line, for vendor invoice line Invoice journal, is displayed, and Vendor transaction is opened for vendor transaction for the worker).
 
It is possible to manually adjust the Amount of the lines that have not yet been reported. Information about the original amount remains in the Description. The adjusted amount is reported to REK-1.
 
### Manually adding transactions

Manually adding transactions to REK-1 transactions form is enabled because of all cases that cannot be covered by automation (cancellations, prepayments, partial payments of vendor invoices…). 

1. Create a new entry using the button “New”. 
2. Define date, select worker, and entry cost amount. The manually added line has the value “Not linked” in column Linked and no checkmark in field Generated. 
3. Enter any text in the Description field.
 
## **Generate and Export REK-1**
---

1. Open Tax > Declarations > Slovenia > REK-1 reporting _or_ Tax > Declarations > Slovenia > REK-1 forms > button Read transactions.
2. Enter any date in a month to report transactions of that month that have not yet been reported (by entering a date in February, all entries from REK-1 transactions in February that do not have reporting number, will be reported). 
3. After confirming, the REK-1 report is generated. Multiple reports can be generated in one month.

To **view generated reports** go to Tax > Declarations > Slovenia > REK-1 forms

1. Click on button “View transactions” or dispayed Date:  entries that are included in the selected REK-1 report will be dispayed.
2. Click on "Preview" to check the report. The report is opened in an separate tab. REK-1 reporting fields are populated with amounts. 
3. Use “Export to XML” to export the report to the XML format for eDavki. 
 
## **Test cases**
---

  - [Transactions with different income reporting modes on the expense report](Test-Scenario-REK1.zip): 
REK-1 transactions are generated according to the setup of income reporting mode on payment methods. Only transactions from REK-1 transactions form are reported in the REK-1 report.
   - [Always exclude transaction from REK-1 reporting](Test-Scenario-REK1.zip):
Transactions from Expense report that have set up on expense category "Always exclude" are not included in REK-1 transactions and therefore, not reported.
   - [Transaction with income reporting mode No reporting](Test-Scenario-REK1.zip): Transactions from Expense report that have payment method with "No reporting" income reporting mode are not included in REK-1 transactions and therefore, not reported.
   - [Cash advance for worker](Test-Scenario-REK1.zip): Deprecated with version 8.1
   - [Reporting reimbursements of business trip costs for worker](Test-Scenario-REK1.zip): According to setup on payment methods, REK-1 transactions are reported after being paid to the worker.
   - [Partial reimbursement (in installments) of business trip costs for worker](Test-Scenario-REK1.zip): Deprecated with version 8.1<br>
If the amount to be paid to the worker is paid in installments, it is possible to generate each installment respectively in the form of the REK-1 transaction.
   - [One vendor invoice for one worker](Test-Scenario-REK1.zip): It is possible to connect the vendor invoices with the worker who the cost is paid for.
   - [One vendor invoice for multiple workers](Test-Scenario-REK1.zip): It is possible to connect the vendor invoices with multiple workers who the cost is paid for by dividing the cost to as many vendor invoice lines as there are workers.
   - [Payment of vendor invoice in installments](Test-Scenario-REK1.zip): In case of paying vendor invoice in installments, REK transaction for the first installment is generated in the full amount of vendor liability. Before reporting, it is necessary to manually adjust the value to the amount paid by installment. The following installments have to be manually entered in REK transactions.
   - [Manual correction of REK-1 transaction](Test-Scenario-REK1.zip): It is possible to manually correct the amount to be reported or add another entry to the list of transactions to be reported.
 
