# Prepare REK-2 report

REK-2 is a Slovenian personal tax report, which taxpayers are legally (ZDoh-2) obliged to report to the Slovenian tax authority (FURS) if they pay income, other than income from the employment. A taxpayer may also authorize another person to calculate and pay tax on his behalf. The data shall be reported to the tax authority (FURS) by all taxpayers when the payment of other income according to ZDoh-2 (excluding income from employment), from which the tax, the withholding tax, and social security contributions are paid:
-	income from another contractual relationship,
-	income from activities,
-	income from letting out property,
-	income from transfer of property right,
-	other income (Article 104 ZDoh-2),
-	interest and dividends.

In terms of this localization feature, REK-2 report generation is enabled for Slovenian legal entities. Transaction amounts, required to be reported with REK-2 are calculated using vendor invoices and tax codes with separate Settlement period types. Reports can be generated at the time when adequate transactions are added to the payment journal. REK-2 report can be previewed (HTML) and exported in the XML format, structured in a way to comply with the requirements of the Slovenian tax authority (FURS).

Additionally, this localization feature enables Slovenian legal entities to create Notices of payment for paid and not yet paid contractual work and Summary statements of income. Summary statement of income for each customer (contractor) can be generated after income payments have been posted. Thus, both documents are used to inform the payees (contractors) about the income, taxes, and payment of contributions. Additionally, both – Notice of payment and Summary statement of income can be exported to various formats (e.g. Word or PDF).

## **Setup**
---

### General ledger parameters

1. Open General ledger – Ledger setup – General ledger parameters.
2. To be able to preview and export the REK-2 report, it is necessary to select the “REK-2 electronic reporting format”.
 
### Income types and income tax income types

1. Open Tax – Setup – Adriatic – Personal tax – Income types.
2. It is necessary to set up REK income types for reporting purposes. Using the button “New” entry with income type and description is created.
3. Open Tax – Setup – Adriatic – Personal tax – Income tax income types.
4. Using the button “New” entry with income tax income type and description is created.
 
### Sales tax authorities

1. Open Tax – Indirect taxes – Sales tax – Sales tax authorities.
2. Additional tax authority needs to be created for purposes of REK-2 functionality. In the field “Vendor account” vendor FURS is chosen (vendor who the entries for personal tax payments in vendor payment journal and liabilities for payments will be created). Value in field “Report layout” has to be “Default” since REK-2 entries are not reported in VAT books).

### Sales tax settlement periods

1. Open Tax – Indirect taxes – Sales tax – Sales tax settlement periods.
2. The new sales tax settlement period has to be created for REK-2 purposes.
3. The tax authority, created earlier, has to be selected in the field “Authority”. We will be using the “Monthly” period interval unit with interval duration “1”. Since the same functionality is being used for VAT and REK-2, it is necessary to define Period type value as “REK-2”. This setup enables that upon closing the period only entries for REK-2 will be considered in the calculation (period type “REK-2” prevents the generation of DDV-O report and settlement of VAT entries).
4. Set **Post personal tax without VAT date** to **Yes** to enable posting of REK-2 tax transactions without VAT date. In this case VAT date will be populated automatically with payment date when payment journal is posted.  
5. Set **Period type** to **Personal tax**

### Ledger posting groups

1. Open Tax – Setup – Sales tax – Ledger posting groups.
2. The new ledger posting group is opened for ledger posting (main account defined in field “Sales tax receivable”). According to our business practice, we open as many ledger posting groups as there are different ledger accounts we want to post liabilities to.
 
There is no need to set up a Settlement account since closing the period will post REK-2 entries to the vendor, defined as tax authority on sales tax settlement period for REK-2. 

### Sales tax codes

1. Open Tax – Indirect taxes – Sales tax – Sales tax codes.
2. REK income type is defined on sales tax code. For every income type there are individual sales tax codes for deductions and contributions:
   - Income tax
   - Each of the contributions to gross
   - Each of the deductions from gross 
3. Under General, settlement period and ledger posting group, created for REK-2 purposes, and currency are defined. 
4. Sales tax codes are created for deductions, calculated from gross amount, as well as for contributions to gross. For correct calculation of deductions from gross the functionality of negative tax is used on those sales tax codes that define deductions from gross. Enabling field “Allow negative sales tax percentage” allows the entry of negative sales tax code value. Bellow, there is an example for entering “PIZ iz bruta” setup of 15.5%. 
5. Sales tax code percentage is entered in form Value.

When entering the value for income tax it is important to enter also potential personal exemption, tax allowances, and contributions that reduce the basis for calculation.  There are additional fields in form Value (“Personal tax” part) that are considered for the calculation for income tax percentage.  
 
“Personal tax” part: field Value should be entered in negative amount for income tax; fields Personal exemption, Tax allowances (10%), and Contributions (PIZ (15,5%) + ZZ (6,36%) is 21,86%) are populated with adequate percentages. The percentage of sales tax code value is automatically updated after entering. 

Contributions to the gross increase in total employer cost. For each of the contributions to gross it is, therefore, necessary to create two sales tax codes – one with a positive value and 100% non-deductible (result is posting on cost account), the other with a negative value and 0% non-deductible (result is posting on liabilities account for withholding tax). 
 
#### Setup for REK-2 reporting

There are fields in BE-terna localization part on sales tax codes that need to be correctly populated in order for REK-2 reporting to work.
   - Personal tax reporting: REK-2
   - Income type: chosen from Tax – Setup – Adriatic – Personal tax – Income types
   - In case of sales tax code for income tax, fields Deduction type and Contribution type are populated with “None”, field Tax income type has to have a value from Tax – Setup – Adriatic – Personal tax – Income tax income types (same as in the picture above)
   - Deduction type: in case of entry paid by employee (deduction from gross), one of the following values has to be chosen: PIZ, ZZ, Parental care, Employment; field “Tax income type” has to be empty.
   - Contribution type: in case of entry paid by employer, it is necessary to choose one of the following options in this field: PIZ, ZZ, Parental care, Employment, Work injuries, Special tax, Contingent or temporary work levy. Same reporting setup needs to be done on both sales tax codes – positive and negative one.
   - Tax income type: in case of income tax entry, value is chosen from Tax – Setup – Adriatic – Personal tax – Income tax income types.
  
#### Reliefs and certificates

If payment is done to contractors who exercise certain reliefs on income tax it is necessary to create additional sales tax codes with the appropriate settings. Recommended is to create new procurement categories for income types with relief and define new item sales tax groups (procurement category is then chosen on the purchase order/vendor invoice for the contractors that exercises a certain relief). It is also possible to create new sales tax groups and allocate them to respective vendors. 

BE-terna localization tab on sales tax code allows “Benefit type” and “Required certificate” to be chosen in section Reporting. Choosing a certain relief does not automatically affect the calculation – it is necessary to manually enter the appropriate value (e.g. if relief for cultural workers is selected on sales tax code, it is necessary to enter the appropriate percentage of relief to Values; sole indication that it is a relief for cultural workers does not affect the amount).

For this purpose, new fields are added to sales tax codes, BE-terna localization. It is possible to choose among the following relief options:
   - DTC reduced tax: enable if income tax is subjected to tax reduction under double taxation convention. 
      - Required certificate: choose certificate type, in case that is needed to exercise tax reduction (individual certificates are entered on vendor card – more in Chapter Vendor certifications) 
 
Certification types are entered in Procurement and sourcing – Setup – Vendors – Certification type.
 
The certificate number that is entered on vendor card, and the corresponding percentage of the personal income tax rate, which is entered in sales tax code value, are recorded in field D11 of the REK report.
   - Withholding rate deduction: enable if income tax is subjected to reduced deductions.
 
Fields 110 and 203 of the REK-2 report are populated with information about tax base amount and reduced deduction amount.
   - Additional tax reduction (cultural workers): checkmark to determine whether the income is subject to additional relief for the self-employed in culture (the gross amount is recorded in field 102 of REK-2 report)
 
#### Benefits

“Benefit type” field is added to the Sales tax code tab BE-terna localization. Options to select are Personal vehicle, Accommodation, Insurance premium, and Other.
 
Test case presented in chapter Benefits.

#####	Payment setup

Payment section of the BE-terna localization tab on sales tax codes enables entry of payment data, such as Vendor account (Slovenian tax authority FURS, in our case), Bank account to which the payment of personal tax will be executed, Payment ID, and Central bank purpose code. Entered data are transferred to the vendor journal payment line using the Payment proposal.
 
### Sales tax groups

1. Open Tax – Indirect taxes – Sales tax – Sales tax groups.
2. Add adequate sales tax codes to sales tax groups.
 
### Item sales tax groups

1. Open Tax – Indirect taxes – Sales tax – Item sales tax groups.
2. Create item sales tax group for each REK income type and add adequate sales tax codes. 
 
### Procurement categories

1. Open Procurement and sourcing – Procurement categories.
2. Create a procurement category for each income type and define the Item sales tax group. 
3. Procurement categories need an adequate ledger account for posting – this setup is done in Inventory management – Setup – Posting – Posting. 
 
If the cost of contract work is posted via the vendor invoice, the ledger account setup is done under “Purchase expenditure for expense” transaction type. In case product receipts are used, posting setup also needs to be done in the “Purchase expenditure, un-invoiced” section.

### Vendor certifications

1. Certificates regarding reliefs or international conventions are entered on vendor card -> button Certifications. 
2. Mandatory fields to enter are: 
   - Certification type and Certification number,
   - Certifying organizations (e.g. Slovenian tax authority or Ministry for culture),
   - Certification date. 
3. If Certification type is chosen on sales tax code and a certificate for the same certification type is entered on the vendor, then the certificate number is recorded in REK-2 field D11. 
 
## **Purchase order and/or Vendor invoice**
---

1. Contract work is entered on the separate Purchase order/Vendor invoice for each contractor (vendor) by choosing an adequate procurement category in the document line (in case of using price lists, service item should be used). Entering multiple income types on one source document (multiple procurement categories on the purchase order/vendor invoice) is also supported. Gross amounts are entered on the purchase line. If the entry of net amount is required, “Prices include sales tax” needs to be marked in the document header, tab Setup (test case in chapter Entry of Net amount). 
2. Item sales tax group (from procurement category) and sales tax group (from vendor) are automatically populated in the line details – Setup. 
3. “Sales tax” button (in tab Purchase) shows sales tax transactions via sales tax codes (income tax, contributions, and deductions for the chosen income type).
4. The new tab “Personal tax” is added to line details. Here, specific real estate data can be entered such as Cadastral county, Plot, and Building number. A new purchase line is needed for each building number. REK reporting data is transferred to the vendor invoice, where it can be edited. 
5. Real estate data from vendor invoice is recorded in the area "Podatki o nepremičninah" on the iREK. Test case presented in chapter Reporting regarding real estate.
6. After the purchase order is confirmed, it can be linked to the vendor invoice. One purchase order can be mapped to one vendor invoice. 
7. Data from a purchase order is transferred to the vendor invoice. In Info part of vendor invoice under “Invoice totals” net amount of vendor payment can be seen (field Invoice amount) as well as personal tax amount in field Sales tax (income tax + deductions from gross).
8. Posting the vendor invoice results in posting vendor, Tax and GL transactions. 
9. **VAT date** in generated Tax transactions is left **empty** if **Post personal tax without VAT date** is set to **Yes** in Tax settlement period setup. 
 
### Separate number sequence for Purchase pool

1. Open Procurement and sourcing – Setup – Purchase orders – Purchase pools.
2. If using standard functionality for the massive creation of invoices, the localization allows defining Number sequence for invoices, created from purchase orders through the purchase pool. 
3. Navigate to Purchase pools and create a pool for REK-2. Define number sequence for invoices, which is the localization field.  
4. When generating invoices from purchase orders using the purchase pool, they are numbered according to the number sequence defined in the pool. If the number sequence is not defined, the invoice number has to be added manually. See chapter 9.19 for more details.

## **Payments**
---

1. Prepare vendor payment journal lines (e.g. through standard payment proposal functionality).
2. Net payment to the vendor is transferred to the payment journal line. 
3. Personal tax payment is executed at the same time as net payment. For that reason, the function with which personal tax payments are proposed is added to the payment journal. Payment lines to FURS and to the vendor are created in the same payment journal. 
4. Payment lines for deductions and contributions are created through Functions – Create personal tax payments. 
5. Enter the payment date and bank account to execute payments.
6. After confirming payment lines for deductions and contributions to FURS are created. 
 
Note: changing the amount on vendor payment line is not recorded in the REK-2 report. Test case presented in chapter Correcting payment journal line amount is not recorded in the report.

At this stage, it is already possible to create the REK-2 report (navigate to chapter REK-2 report for details). Correcting or deleting payment journal lines is not possible while the report exists, as lines are locked for editing. Correction is possible after deleting the existing REK-2 report.
Vendor payment journal lines are settled with posting of journal/bank statement. After posting, transactions of personal tax payments are created on the FURS vendor and the existing Tax transactions are populated with VAT date.  
 
### Payment compensation

1. Function “Create personal tax payments” in the payment journal has been updated to allow the creation of personal tax payments for transactions that have been compensated. Option “Include” personal tax payments for the closed transaction has been added. 
2. Enter the payment date and bank account to execute payments. In “Closed transactions” section mark field “Include” and enter “From date, To date” (date period of settlement of compensated transactions). After confirming, personal tax payment lines are created in vendor payment journal. 
 
### Subsequent personal tax payment

1. If the vendor payment journal has been accidentally posted without payment lines for deductions and contributions, personal tax payments can be subsequently generated. 
2. Use function Create personal tax payments with enabled “Include” closed transactions and define the date period of closed transactions to generate personal tax payment lines. 

## **REK-2 report**
---

1. REK-2 report can be generated from posted or unposted vendor payment journals.
2. Creating the REK-2 report can be done through Tax – Declarations – Slovenia – REK reporting – REK-2 – REK-2 reporting or through Tax – Declarations – Slovenia – REK reporting – REK-2 – REK-2 forms -> button Read transactions.
3. REK-2 reporting parameters:
   - Date: enter payment date for which to report REK-2 transactions.
   - Income Type: select in case of reporting only for particular income type; if left empty, REK-2 reports will be generated for all income types for the selected date.
   - Include transactions from unposted journals: enable if transactions from unposted vendor payment journals are also to be included in the REK-2 report. Otherwise, the report will be created from the posted payment journal.
After confirming, info about created the REK-2 report is displayed. Generated reports by payment date and income type can be found in Tax – Declarations – Slovenia – REK reporting – REK-2 – REK-2 forms. 
4. By clicking on the “Preview” the selected report is displayed in the new tab.

Warning: Correcting or deleting payment journal lines is not possible while the report exists, as lines are locked for editing. Correction is possible only after deleting the existing REK-2 report.
 
Export report by selecting “Export to XML” and manually upload it to eDavki.
 
## **Personal tax payments list** 
---

1. Open Tax – Inquiries and reports – Withholding tax inquiries – Personal tax payments.
2. An overview of contractual amounts is available in this form. The form is populated with data right after the vendor invoice has been posted. 
 
## **Notice of payment**
---

1. Open Tax – Inquiries and reports – Withholding tax reports – Slovenia – Notice of payment.
2. It is possible to create a Notice of payment for paid and not yet paid contractual work. 
3. Click on “Filter” to open a query window and define reporting criteria – default ones are Vendor account and Payment date. Click on “Add” to add additional filters (such as the Accounting date – the date when the transaction was posted).
4. The notice includes the vendor’s address, tax identification number, and bank account, the expected date of payment (due date from vendor invoice), and specification of payment.
5. Click on to define new reporting criteria. 
6. Export to various formats is supported.
 
It is possible to display one or more prints, according to selected filters. If a notice includes different income types, the specification for each income type is displayed on a new page, while the recipient data is shown only on the first page. Click the arrows Left – Right to move between pages or select “Go to” to enter the page number.
 
## **Summary statement of income**
---

1. Open Tax – Inquiries and reports – Withholding tax reports – Slovenia – Summary statement of income.
2. It is possible to generate a summary statement of income right after the payment has been posted. Transactions that have not yet been paid will not be recorded in the summary statement.
Define dates From/To. Click “Filter” to enter additional criteria (such as Vendor account to limit the report to the selected vendor). 
3. After confirmation, a summary statement of income for the selected period is created – tax registration number, address, and summarized amounts via income type for each of the vendors are seen on a separate page. Click the arrows Left – Right to move between pages or select “Go to” to enter the page number.
4. The statement can be exported to various formats.
 
## **Closing tax settlement period**
---

1. Open Tax – Declarations – Sales tax – Report sales tax for the settlement period.
Using this functionality, a sales tax report is created, enabling the user to check sales tax transactions for REK-2 before posting them. 
2. Select the settlement period for REK-2 and define “From date” (any date in a month that needs to be settled).
3. After confirming, another window is opened. Enable “Include details” if an additional section of the report “Details” is to be displayed in sums for each sales tax code. 
4. Confirming generates sales tax reports.
5. Open Tax – Declarations – Settle and post sales tax.
6. The closing tax settlement period is executed once a month – after payment of all liabilities for the selected period has been processed. Using tax settlement functionality, liability for personal tax payments is posted to vendor FURS (vendor, defined in Sales tax authority which is chosen in the Sales tax settlement period for REK-2). 
7. Enter the settlement period for REK-2, the first day of the month that needs to be closed, and the date on which the transaction will be posted. After confirming, a window for generating sales tax report is opened. 
 
Ignore possible messages about Customer/Vendor name not specified.
 
From account 2650 (defined in ledger posting group REK-2) amount is posted to the vendor account.
 
The process creates a payment liability to vendor FURS. 
 
If vendor payment journals are already posted with bank statements, payments and liabilities need to be manually settled using “Settle transactions” functionality on the vendor. 
 
Upon closing the tax period, liability for payment is posted in sum to the vendor. Mark transactions of payments and liabilities and click “Post” to settle them.
 
8. Check transaction settlement on vendor transactions.
 
## **Test cases**
---

- [Starting source document is Purchase order](Test-Scenario-REK2.zip)
- [Starting source document is Vendor invoice](Test-Scenario-REK2.zip)
- [Entry of Gross amount](Test-Scenario-REK2.zip)
- [Entry of Net amount](Test-Scenario-REK2.zip)
- Reliefs and certificates:
   - [Additional tax reduction (cultural workers)](Test-Scenario-REK2.zip)
   - [DTC reduced tax with required certificate](Test-Scenario-REK2.zip)
   - [Withholding rate deduction](Test-Scenario-REK2.zip)
- [Benefits](Test-Scenario-REK2.zip)
- Different income types for one party paid on the same day 
   - [Multiple source documents](Test-Scenario-REK2.zip)
   - [One source document with multiple lines](Test-Scenario-REK2.zip)
- [Multiple payments of the same income type to one party on the same day](Test-Scenario-REK2.zip)
- [Payment of the same income type to multiple parties on the same day](Test-Scenario-REK2.zip)
- [Different income types for different parties on the same day](Test-Scenario-REK2.zip)
- [Payment to vendor liable for Slovenian VAT](Test-Scenario-REK2.zip)
- Personal tax payments from closed transactions
   - [Compensation (total amount)](Test-Scenario-REK2.zip)
   - [Compensation (partial amount)](Test-Scenario-REK2.zip)
- Reporting regarding real estate
   - [One building land from one party (starting with purchase order)](Test-Scenario-REK2.zip)
   - [Multiple building lands from one party (starting with vendor invoice)](Test-Scenario-REK2.zip)
- Dependency between payment journal and REK-2 report 
   - [Generating REK-2 report from posted payment journal](Test-Scenario-REK2.zip)
   - [Generating report from created (not yet posted) payment journal](Test-Scenario-REK2.zip)
   - [Correcting or deleting payment journal lines is not possible while report exists](Test-Scenario-REK2.zip)
   - [Correcting payment journal line amount is not recorded in the report](Test-Scenario-REK2.zip)
- [Overview of personal tax payments](Test-Scenario-REK2.zip)
- [Summary statement of income paid during the period of above test cases](Test-Scenario-REK2.zip)
- Notice of payment 
   - [From not yet paid contract work](Test-Scenario-REK2.zip)
   - [From paid contract work – date of payment is later than due date from the invoice](Test-Scenario-REK2.zip)
- [Closing tax settlement period](Test-Scenario-REK2.zip)
 
### Massive creation of invoices through purchase pool

For the creation of vendor invoices for contractual work out of purchase orders, it is possible to use the standard functionality of massive invoicing. 

1. Open Procurement and sourcing – Setup – Purchase orders – Purchase pools.
2. Navigate to Purchase pools and create a pool for REK-2. Define number sequence for invoices, which is the localization field.
3. Select the Purchase pool on Vendor who only has contract work invoiced.
4. The data transfers to purchase order upon creating.
5. Vendor invoices can be massively created from confirmed purchase orders. Navigate to Accounts payable – Invoices – Pending vendor invoices and select “From purchase order”. 
6. Choose the “REK-2” pool in the Criteria section and confirm.
7. Invoice is created for every purchase order that meets the criteria. If the purchase order is without product receipt, be careful to select “Default from Ordered quantity” before creating invoices. If needed, edit the invoices before posting.
