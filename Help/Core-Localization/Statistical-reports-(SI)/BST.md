# BST report

BST report on transactions by residents with non-residents for services and part of a trade, and given or received capital transfers is a monthly report on purchases/sales and capital transfers between residents and non-residents. Legal entities obliged to report are informed about their obligations by the Bank of Slovenian based on the importance of their business activities with the non-residents. The report is based on transactions from the sent and received invoices. Credit notes are reported as corrections for the original period of the invoice. If obliged to report, legal entities must submit the report until the 20th day in the current month for the past month, electronically in an adequate XML format.
This localization feature enables the preparation and export of the report in the TXT file format based on the pre-set BST reporting codes for transactions with non-residents, with which legal entity has been involved throughout the reporting period.

## **Setup**
---	 

### BST setup location

1. Open **General ledger > Financial report setup > Slovenia > BST options**. And define following parameters: 
   - The **country to be excluded** from reporting needs to be set since the report is generated for transactions with non-residents.   
   - The **report format** must be defined for export purposes. Select from list.
4. Open **General ledger > Financial report setup > Slovenia > BST setup** and **add BST codes**. Codes can be added with function Tools > Add standard. The list can be edited.  Only transactions with an appropriate type (receipts/expenditure) will be included in the report. Every BST code can be marked as inactive.  Such transactions will not be included in the report. 
4. Open **General ledger > Financial report setup > Slovenia > BST excluded posting types**. Add all posting types that need to be excluded from BST report. 

### BST setup on Main accounts
1. Open **General ledger > Chart of accounts > Accounts > Main accounts**. 
BST setup is added to the main account on the chart of accounts. BST report will be generated based on BST code on main accounts and ISO code on country/region setup.  


### Electronic reports configuration 

1. Open **Workspaces > Electronic reporting > Reporting configurations**.
2. Choose Repositories > BE-terna localization > Open.
3. Find BST report > Import all.
4. The report will now be available in BST options.  

## **Generate BST report** 
---

The report can be generated with the following steps.
1. Create a **new report period** with the New button	  
2. Set **From and To date**. The system will set default dates to the previous month, but they can be changed. Only one report can be generated for the period. 	 
3. **Read transactions**: Transactions are generated for the chosen period. The report will include only transactions, posted to the account with BST code and vendor/customer with country code different from SVN (or country setup in BST setup).   

The report consists of two parts. The upper part (»Transactions«) includes all transactions, that comply with the above-mentioned conditions. In the bottom part (»Sums«) transactions are summed by BST codes and country ISO codes. All fields in Sums can be edited manually.  

## **BST report export** 
---

The report can be exported to TXT file. It will be generated according to the report format, defined in the BST setup.  
