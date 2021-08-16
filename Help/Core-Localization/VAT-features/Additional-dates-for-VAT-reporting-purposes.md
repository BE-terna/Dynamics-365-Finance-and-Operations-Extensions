

All VAT reporting for Slovenia, Croatia, and Serbia needs to be performed according to VAT date and not Transaction date (which is how standard functionality for Tax reporting works). For VAT reporting purposes following dates are added to several documents: 

* VAT date
* VAT Payable date
* Document Receipt date (used for defaulting VAT date)

VAT date and VAT Payable date (when populated) are transferred to a VAT date field (additional localized field) on Tax transactions as a result of document posting. This date is then used for VAT calculation and reporting.

List of documents where additional VAT date fields are enabled:


|**Document**| **Available dates** |
|--|--|
|Pending Vendor Invoice |VAT date, VAT Payable date, Document Receipt date  |
|Invoice Journal |VAT date, VAT Payable date, Document Receipt date  |
|Free Text Invoice | VAT date  |
|Sales Invoice |VAT date  |
|Project Invoice | VAT date |
|Intercompany Invoice  |VAT date  |
|General Journal |VAT date, VAT Payable date  |
|Collection letter  | VAT date |
|Interest letter  |VAT date  |


VAT date validation is also added. If the VAT date is missing, posting such a document will result in an error.  

  
