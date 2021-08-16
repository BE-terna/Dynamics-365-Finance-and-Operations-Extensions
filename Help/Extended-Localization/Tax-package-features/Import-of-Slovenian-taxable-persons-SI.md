# Import of Slovenian taxable persons (SI)

This extended localization feature enables the import of Slovenian taxpayers from the Financial Administration of the Republic of Slovenia (FURS). Information like tax registration number, ID number (i.e. company registration number), taxable person type, name, and address of the taxpayer, and the information whether the partner is liable for Slovenian VAT or whether it has special handling based on 76.a article of ZDDV-1 can be recorded in the list.

For the import of taxpayers, it is necessary to insert the URLs of the documents on the FURS web page. Links to the adequate documents are available in the document, linked below. After confirming, taxpayers are imported to Slovenian taxable persons. Upon using the feature, users can also choose, whether they want already imported information to be overwritten or only new taxable persons information should be imported. Additionally, this feature also allows for Tax exempt numbers table to be populated with the VAT IDs of the taxable persons, imported with the full taxable person list from the Slovenian tax authority. 

## **Import**
---

1. Open Tax – Declarations – Slovenia – Slovenian taxable persons.
2. For import of taxpayers, it is necessary to insert the URLs of the documents on the FURS web page: <br>

   *[DURS zavezanci PO](http://datoteke.durs.gov.si/DURS_zavezanci_PO.zip)*<br>
   *[DURS zavezanci DEJ](http://datoteke.durs.gov.si/DURS_zavezanci_DEJ.zip)* <br>
   *[DURS zavezanci FO](http://datoteke.durs.gov.si/DURS_zavezanci_FO.zip)* <br>

   - If “Synchronize tax exempt number table” is marked, the register of tax-exempt numbers (ID za DDV) will also be imported simultaneously (Tax/Setup/Sales tax/Tax exempt number).  
   - If “Keep history” is marked, the history for each tax number will be kept in the database. New records will overwrite existing ones, if “Keep history” is not enabled.  

3. After confirming, taxpayers are imported to Slovenian taxable persons. It might take a while to process all data.  
Because of a checkmark in the field “Synchronize tax exempt number table” Tax exempt numbers table was also updated upon import. 
4. Open Tax – Setup - Sales tax- Tax exempt numbers.
5. Tax exempt number on partner (Vendor/Customer) can be selected from the register that was imported. 
