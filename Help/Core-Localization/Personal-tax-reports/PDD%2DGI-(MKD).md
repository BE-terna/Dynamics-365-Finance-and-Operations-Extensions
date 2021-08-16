# Create PDD-GI report

This topic provides country/region-specific information about personal tax reporting in accordance with the Macedonian legislative requirements. 

## Setup 

### General ledger parameters 

1. Open General ledger – Ledger setup – General ledger parameters.
2. To be able to preview and export a personal tax report, it is necessary to select electronic reporting formats for PDD-GI. 

### Income types  

1. Open Tax – Setup – Adriatic – Personal tax – Income types.
2. It is necessary to set up income types for reporting purposes. Using the button “New” entry with income type and description is created. Income type is constructed in format: “income type.subincome.paymenttype”. 

### Non cash type 

1. Accounts payable – Non-cash personal receivables – Non-cash type.
2. Create non-cash types for reporting non-cash personal receivables. Define default sales tax group and sales tax item group, select offset account, and define whether tax is included for each of the types.  

### Sales tax authorities 

1. Open Tax – Indirect taxes – Sales tax – Sales tax authorities 
2. Additional tax authority needs to be created for purposes of Personal tax functionality. Value in field “Report layout” has to be “Default” since personal tax entries are not reported in VAT books). In the field “Vendor account” vendor is selected (vendor who the entries for personal tax payments in vendor payment journal and liabilities for payments will be created). 

### Sales tax settlement periods 

1. Open Tax – Indirect taxes – Sales tax – Sales tax settlement periods.
2. A new sales tax settlement period should be created for personal tax purposes. 

The tax authority, created earlier, should be selected in the field “Authority”. We will be using the “Monthly” period interval unit with interval duration “1”. Since the same functionality is being used for VAT and personal tax, it is necessary to define Period type value as “Personal tax”. This setup enables that upon closing the period only entries for personal tax will be considered in the calculation (period type “Personal tax” prevents the generation of VAT report and settlement of VAT entries).  

### Ledger posting groups 

1. Open Tax – Setup – Sales tax – Ledger posting groups.
2. The new ledger posting group is opened for ledger posting. According to our business practice, we open as many ledger posting groups as there are different ledger accounts we want to post liabilities to. 

If a vendor account is defined on tax authority, there is no need to set up a Settlement account since closing the period will post personal tax entries to the vendor, defined as tax authority on sales tax settlement period for personal tax.  

### Sales tax codes 

1. Open Tax – Indirect taxes – Sales tax – Sales tax codes.
2. Personal tax income type is defined on sales tax code. For every income type, there are sales tax codes with a personal tax setup. 
3. Under General, settlement period and ledger posting group, created for personal tax purposes, and currency are defined.  

Sales tax codes are created for deductions, calculated from the gross amount. For correct calculation of deductions from gross the functionality of negative tax is used on those sales tax codes that define deductions from gross. Enabling field “Allow negative sales tax percentage” allows the entry of negative sales tax code value.  

Sales tax code percentage is entered in form Values. When entering the value for income tax it is important to enter also potential personal exemption, tax allowances, and contributions that reduce the basis for calculation.  There are additional fields in form Value (“Personal tax” part) that are considered for the calculation for income tax percentage. The percentage of sales tax code value is automatically updated after entering.  

#### Setup for personal tax reporting 

1. Setup in the BE-terna localization tab on sales tax codes needs to be correctly populated for personal tax reporting to work: 
   - Personal tax reporting: PDD-GI 
   - Income type: selected from Tax – Setup – Adriatic – Personal tax – Income types 

#### Payment setup 

Payment section of the BE-terna localization tab on sales tax codes enables entry of payment data, such as Vendor account, Bank account to which the payment of personal tax will be executed, Payment ID, and Central bank purpose code. Entered data are transferred to the vendor journal payment line using the Payment proposal. 

### Sales tax groups 

1. Open Tax – Indirect taxes – Sales tax – Sales tax groups.
2. Add adequate sales tax codes to sales tax groups. 

### Item sales tax groups 

1. Open Tax – Indirect taxes – Sales tax – Item sales tax groups.
2. Create item sales tax group for each personal tax income type and add adequate sales tax codes.  

### Procurement categories 

1. Open Procurement and sourcing – Procurement categories.
2. Create a procurement category for each income type and define the Item sales tax group.  
3. Procurement categories need an adequate ledger account for posting – this setup is done in Inventory management – Setup – Posting – Posting.  

If the cost of contract work is posted via the vendor invoice, the ledger account setup is done under “Purchase expenditure for expense” transaction type. In case product receipts are used, posting setup also needs to be done in the “Purchase expenditure, un-invoiced” section. 

## Personal tax transactions 

### Purchase order and/or Vendor invoice 

1. Enter Purchase order/Vendor invoice for each vendor by choosing an adequate procurement category in the document line (in case of using price lists, service item should be used). Entering multiple income types on one source document (multiple procurement categories on the purchase order/vendor invoice) is also supported. Gross amounts are entered on the purchase line. If the entry of net amount is required, “Prices include sales tax” needs to be marked in the document header, tab Setup. 
2. Item sales tax group (from procurement category) and sales tax group (from vendor) are automatically populated in the line details – Setup.  
3. After posting vendor invoices, vendor transactions and tax transactions are created. 

#### Non-cash personal receivables 

1. The new tab “Personal tax” is added to purchase order and vendor invoice line details. Here, non-cash personal receivables can be defined. Select Yes for the line to be marked as non-cash receivable, define the non-cash type, and select the receiving worker.  
2. After the invoice is posted, non-cash receivables can be generated in Accounts payable – Non-cash personal receivables – Non-cash personal receivables. 
3. Use button New to create a new document. 
4. Add date and select Non-cash type. Upon selecting the non-cash type, sales tax group, item sales tax group, an offset account, defined on the type, are transferred to the document.  
5. Click “Import vendor invoice lines” to transfer invoice lines. Define dates From and To (the period for posted vendor transaction).  
6. Upon confirming, the non-cash personal receivable line is automatically (after Refresh) created with reference to the vendor invoice.  
7. Post the non-cash receivables with button Post. 
8. See chapter Other transactions on how to create personal tax payments for non-cash receivables. 

### Expense report 

Personal tax transactions can also be created through expense reports. Expenses need to be posted with sales tax codes for personal tax.  

If “Allow grouping of transactions via offset account” is active in Expense management parameters, vendor transaction is summarized upon posting, whereas tax transactions are (separately) posted with expense report transaction dates. 

In this case, the “Other transaction” option needs to be selected when creating personal tax payments, to correctly transfer all tax transactions to vendor payment journal. See chapter Other transactions on how to create personal tax payments. 

## Payments 

Prepare vendor payment journal lines (e.g. through standard payment proposal functionality). The vendor transaction is transferred to the payment journal line.   

1. Payment lines for personal tax payments are created through Functions – Create personal tax payments.  
2. Enter the payment date and bank account to execute payments. If the bank account is left empty, the offset account transfers from the method of payment of the vendor, selected on the sales tax code. 
3. After confirming, payment lines are created, including a detailed message about the created personal tax payments. 
4. At this stage, it is already possible to create a personal tax report (navigate to chapter Personal tax report for details). Correcting or deleting payment journal lines is not possible while the report exists, as lines are locked for editing. Correction is possible after deleting an existent personal tax report. 

### Include closed transactions 

1. Function “Create personal tax payments” in the payment journal has been updated to allow the creation of personal tax payments for transactions that have already been settled. Option “Include” personal tax payments for the closed transaction has been added.  
2. In “Closed transactions” section mark field “Include” and enter “From date, To date” (date period of settlement of transactions). After confirming, personal tax payment lines are created in vendor payment journal.  

### Other transactions 

1. Create personal tax payments for non-cash personal receivables or expense reports, where vendor transaction is summed by offset account but tax transactions are posted on dates from expense report, using Functions – Create personal tax payments -> Include other transactions. Select Yes in field Include and define From/To dates for posted personal tax transactions. 
2. After confirmation, personal tax payments are created. 

## Personal tax report 

1. Personal tax reports can be generated from posted or unposted vendor payment journals. 
2. Creating a personal tax report can be done through Tax – Declarations – Macedonia – PDD-GI – PDD-GI reporting. 
 Or through Tax – Declarations – Macedonia – PDD-GI – PDD-GI forms -> button Read transactions. 
3. Personal tax reporting parameters: 
   - From date, To date: enter from/to payment dates for which to report personal tax transactions. 
   - Include transactions from unposted journals: enable if transactions from unposted vendor payment journals are also to be included in the personal tax reports. Otherwise, the report will be created from the posted payment journal. 
4. After confirming, infolog about created a personal tax report is displayed. Generated reports by payment date and income type can be found in Tax – Declarations – Macedonia – PDD-GI – PDD-GI forms.  
5. By clicking on “Details”, reporting transactions for the selected reports are displayed. It is possible to manually edit fields First name, Last name, Bank account number, and payment date. Bank account number transfers from Third-party bank account identification field from the vendor payment journal; if it is not defined there, then it transfers from the vendor’s default bank account.  

County transfers from the party’s primary address. It is a mandatory field for reporting. 

Note: Correcting or deleting payment journal lines is not possible while the report exists, as lines are locked for editing. Correction is possible only after deleting the existing personal tax report. 

6. Export report by selecting “Export to Excel” or “Export to XML”. 

### Import transactions 

It is possible to import reporting transactions. Select “Import transactions” and select a file. 

## Personal tax payments  

1. Open Tax – Inquiries and reports – Withholding tax inquiries – Personal tax payments.
2. An overview of personal tax amounts is available in this form. The form is populated with data right after the vendor invoice has been posted. When the vendor payment journal is created, the field Payment date is populated with a value. 

## Closing tax settlement period 

1. Open Tax – Declarations – Sales tax – Report sales tax for the settlement period.
2. Using this functionality, a sales tax report is created, enabling the user to check tax transactions for the personal tax before posting them.  
3. Select the settlement period for personal tax and define “From date” (any date in a month that needs to be settled). 
4. After confirming, another window is opened. Enable “Include details” if an additional section of the report “Details” is to be displayed in sums for each sales tax code.  
5. Confirming generates sales tax reports.
6. Open Tax – Declarations – Settle and post sales tax.
7. The closing tax settlement period is executed once a month – after payment of all liabilities for the selected period has been processed. Using tax settlement functionality, liability for personal tax payments is posted to the vendor, defined in Sales tax authority which is chosen in the Sales tax settlement period for personal tax).  
8. Enter settlement period for personal tax, the first day of the month that needs to be closed, and date on which the transaction will be posted. After confirming, a window for generating sales tax report is opened.<br>  

   Ignore possible messages about Customer/Vendor name not specified. 

9. From accounts, defined in ledger posting groups for personal tax, the amount is posted to the vendor account.<br> 
The process creates a payment liability in sum for the period to personal tax vendor.  
10. If vendor payment journals are already posted with bank statements, payments and liabilities need to be manually settled using “Settle transactions” functionality on the vendor.  