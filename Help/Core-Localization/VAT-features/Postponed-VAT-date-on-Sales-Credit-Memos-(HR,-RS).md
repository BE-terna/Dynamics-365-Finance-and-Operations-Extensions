

Localization functionality allows posting Sales credit memos without VAT date in order to be compliant with Croatian and Serbian legislation. If the feature is enabled, the VAT date on the tax transaction is left empty, and these documents are not included in any VAT reports. Later, when a Credit note is confirmed by Customer, the VAT date can be added manually, directly to Tax transaction, using the VAT date change feature. 

## **Setup**
---

Additional setup is added to General ledger parameters (General ledger > Setup > General ledger parameters > BE-terna localization), which enables posting sales credit memo without VAT date:

|Setup|Value|
|---|---|
|VAT Date pending on credit notes  | set field to post tax transactions without VAT date, which can be changed later. |



Setup affects Credit notes generated from the following documents:  
 - Free text invoice 
 - Sales invoice 
 - Project invoice 

## **Generate Credit memo without VAT date (postponed VAT)** 
---

1. Post Sales credit memo (follow standard procedures).
2. Check tax transactions.

As a result tax transactions are created without VAT date. The date can be entered later using the Change VAT date function, which is also a localization feature.  

## **Change VAT Date**
---

1. Open Posted sales tax transactions.
2. Choose the button Change VAT Date and enter the VAT date.

VAT Date is entered on Posted sales tax. Such document will be included in VAT reporting.



