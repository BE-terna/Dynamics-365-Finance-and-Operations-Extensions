# Set default VAT date and VAT payable date

As part of the localization package VAT date is added to some documents (for more details check Localization features) and can be entered manually. With tax package, the user is able to setup defaulting rules for VAT date calculations. It is possible to set up a VAT date and VAT payable date defaulting. 

## Additional fields

For VAT reporting purposes following dates are added:
   - VAT date
   - VAT Payable date
   - Document Receipt date

VAT date is also added on Tax transactions and is generated automatically when posting following documents with sales tax:
   - Pending Vendor Invoices (VAT date, VAT Payable date, Document Receipt date)
   - Invoice Journal (VAT date, VAT Payable date, Document Receipt date)
   - Free Text Invoice (VAT date)
   - Sales Invoice (VAT date)
   - Project Invoice (VAT date)
   - Intercompany Invoice (VAT date)
   - General Journal (VAT date, VAT Payable date)
   - Collection letter (fee with sales tax)
   - Interest letter (interests with sales tax)

Additional setup is available for VAT date and VAT Payable date calculation. VAT date validation is added. If the VAT date is missing, posting such a document is disabled.  

## Defaulting VAT date and VAT payable date


In order to facilitate the posting, there is a possibility to set up VAT date and VAT payable date defaulting. Options for defaulting are:
   - None: VAT date has to be entered manually
   - Posting date: VAT date defaults from posting date (field “Date” in journals and FTI, “Invoice date” on Sales invoice)
   - Document date: field “Invoice date” on the vendor invoice 
   - Document receipt date: applicable only for inbound documents

## **Setup**
---

VAT date defaulting setup is added to the following modules: 
1. Open General Ledger > Setup > General Ledger Parameters > General.<br>
    VAT date defaulting from the setup above is applicable in the General journal. If general journal entry has account type “Vendor” or “Customer”, setup from Accounts payable/Accounts receivable is active.
2. Open Accounts Payable > Setup > Accounts Payable Parameters > General.<br>
    VAT date defaulting from Accounts payable is implemented on Pending vendor invoice and Vendor invoice journal.
3. Open Accounts Receivable > Setup > Accounts Receivable parameters > General.<br>
    There is no “Default VAT payable date” setup at accounts receivable parameters and no “Document receipt date” option in the selection. 
 
VAT date defaulting from Accounts receivable is implemented on the Sales invoice, Free text invoice, and Project invoice. 

Check **[Test Scenario](VAT-Date-Test-Scenario.zip)** for default dates.
