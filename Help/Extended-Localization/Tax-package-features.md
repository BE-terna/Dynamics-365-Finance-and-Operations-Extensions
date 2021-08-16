This section summarizes TAX package features, developed in the scope of the LOC_TAX extended localization packet.

-----

# Defaulting VAT date and VAT payable date

As part of the localization package VAT date is added to some documents (for more details check Localization features) and can be entered manually. With tax package, user is able to setup defaulting rules for VAT date calculations. It is possible to set up a VAT date and VAT payable date defaulting. Options for defaulting are:
-	None: VAT date has to be entered manually
-	Posting date: VAT date defaults from posting date (field “Date” in journals and FTI, “Invoice date” on Sales invoice)
-	Document date: field “Invoice date” on the vendor invoice
-	Document receipt date: applicable only for inbound documents

This additional setup for defaulting VAT dates exists in the parameters of the following modules: General ledger, Accounts Payable and Accounts Receivable.

[Detailed documentation](/Help/Extended-Localization/Tax-package-features/Defaulting-VAT-date-and-VAT-payable-date)

-----

# Closing of the Settlement period

VAT settlement period can be closed using extended localization features.  

Field “Closed” is added to Period intervals. If the field is marked, the period is closed for VAT posting. This means that sales tax transactions can’t be posted in that period. The field can be un-marked whenever wanted.  

[Detailed documentation](/Help/Extended-Localization/Tax-package-features/Closing-of-Settlement-period)

-----

# Import of Slovenian taxable persons (SI)
 
This extended localization feature enables the import of Slovenian taxpayers from the Financial Administration of the Republic of Slovenia (FURS). Information like tax registration number, ID number (i.e. company registration number), taxable person type, name, and address of the taxpayer, and the information whether the partner is liable for Slovenian VAT or whether it has special handling based on 76.a article of ZDDV-1 can be recorded in the list.

For the import of taxpayers, it is necessary to insert the URLs of the documents on the FURS web page. Links to the adequate documents are available in the document, linked below. After confirming, taxpayers are imported to Slovenian taxable persons. Upon using the feature, users can also choose, whether they want already imported information to be overwritten or only new taxable persons information should be imported. Additionally, this feature also allows for Tax exempt numbers table to be populated with the VAT IDs of the taxable persons, imported with the full taxable person list from the Slovenian tax authority. 

[Detailed documentation](/Help/Extended-Localization/Tax-package-features/Import-of-Slovenian-taxable-persons-SI)

-----

# Update customer information based on Tax exempt number (SI)

This extended localization feature enables users to default data when creating new customers, based on the entered tax identification number.

If Slovenian taxpayers have been imported from the database provided by the Slovenian tax authority (FURS), it is possible to select the imported Sales tax numbers/VAT IDs when creating new customers. When creating a new customer, Tax exempt number (Sales tax number/VAT ID) must be chosen from the drop-down menu. Customer’s Name and Primary address are automatically updated from SI taxpayers entity. 

[Detailed documentation](/Help/Extended-Localization/Tax-package-features/Update-customer-information-based-on-Tax-exempt-number-SI)

-----

# Validate Tax exempt numbers (VIES database)

This extended localization feature makes it possible to validate values entered in “Tax exempt number” field on customer and vendor accounts and through the Tax-exempt numbers form with an online VIES database.

VIES is an electronic means of transmitting information related to VAT registration of companies registered in the European Union.  When the user needs to verify the VAT number of companies from another Member State through VIES on the web, this request will be sent, to the relevant national database to check if the given number is valid. If yes, the "Valid" status will be displayed. If not, the "Invalid" status will be displayed.


[Detailed documentation](/Help/Extended-Localization/Tax-package-features/Validate-Tax-exempt-numbers-VIES-database)