# Create POPDV report

VAT taxpayer is obliged to, pursuant to Article 46, paragraph 1 of the Law on VAT, and in order to properly calculate and pay VAT, keeps records in a way that allows you to control the calculation and payment of VAT in each tax period. In that records are required to provide records of transactions, activities, respectively other business changes, in particular data relating to the circulation of goods and the service performed by the VAT taxpayer, that is, which was provided to him, by invoices or other documents which serve as invoices in accordance with the Law, respectively
documents confirming a business change (e.g., insurance contract, lease agreement concluded with a natural person, copyright contract, contract on the part, etc.), as well as other information relevant to the correct calculation of VAT.

## Setup

In order to be able to generate a POPDV form, the mandatory setup has to be completed.

### POPDV format

1. On the path Tax - Setup - Parameters - General ledger parameters - tab BE-terna localization, POPDV format should be assigned.

### Reporting codes

Reporting codes are used to direct amounts in appropriate columns of the report. List of all available reporting codes opens on the following path Modules - Tax - Setup - Sales tax - Sales tax reporting codes.
 
NOTE: Reporting codes used for the POPDV report should have the Serbian report layout assigned.

###  Sales tax authorities setup

In order to enable Serbian VAT reports layouts, this report needs to be defined on Tax authority.  

### Sales tax code setup

Each transaction that should be shown in the report should have an appropriate sales tax setup assigned. Setup that defines in which column of the report amounts will be shown are od the Report setup (for amounts with a positive sign) and Report setup – Credit note (for amounts with negative sign) tabs.
 
NOTE: Automatically reversed transactions will go in the same column as the original transaction.
The mapping between reporting codes and POPDV form is in the [File](Mapping.xlsx).
 
## Generating report

1. New VAT report is generated on the following path Modules - Tax - Declarations - Sales tax - Report sales tax for the settlement period.
2. In order to run the report, the parameters should be set as follows:
  - Settlement period – choose the one related to the new VAT setup.
  - From date – enter the starting date of the VAT period.
  - Sales tax payment version – choose the Original option.
  - Print report – turn this parameter to Yes if PPPDV the report should be printed.
  - With POPDV – turn this parameter to Yes in order to create POPDV form lines.
3. After click OK and PPPDV form will be displayed:
 
Besides creating the PPPDV report, new lines in the POPDV form for selected VAT periods will also be created. All POPDV forms are listed Modules - Tax - Declarations - Serbia - PDV - POPDV forms

## Detailed transactions
 
A detailed list of all transactions included in the report will be displayed after a click on the Transactions button.
 
All transactions are grouped in sections in accordance with the official form of the POPDV report. Inside of each section is listed transactions with all necessary details (Document number, Voucher, Document date, VAT date, Vendor/Customer name, VAT number, and amounts).

## Summary form – POPDV

Summary data in the form of POPDV data are shown when you click on the Summary button from the list of all POPDV forms.

## Export to XML

Function for export the data into an XML format in order to be able to upload it to the web portal of the Tax administration office is available on the header of the POPDV report list.
 
On the bottom of the screen following dialog will appear:
 
In order to save the file on the location on your computer, click the Save button. If you want to get the only preview of the file, click Open.
 


