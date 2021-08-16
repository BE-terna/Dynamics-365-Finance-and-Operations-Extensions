

As part of localization, an additional “Reporting” tab is added to Tax transactions. It displays information, such as Customer/Vendor, Address, Tax exempt number, Document, Document date, and Document receipt date. This information is used for VAT reporting.

## **Reporting Tab data sources**
----
Go to **Tax > Inquiries and reports > Sales tax inquiries > Posted sales tax > Reporting tab**

Following information, needed for VAT reporting purposes is added to the tab:

**Customer/Vendor** 


|Source document| Source field |
|--|--|
| Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice  | Vendor/Customer in the document header |
| Journal with Vendor/Customer line | Customer/Vendor field on journal line |



 **Address** 

|Source document| Source field |
|--|--|
|Vendor Invoice  | Vendor account in the document header |
|Sales Invoice, Free text invoice  | Invoice Address in the document header |
|Project Invoice  | Address from funding sources in the document header |
| Journal with Vendor/Customer line | Address field on journal line |

 
 
**Tax exempt number**: 

|Source document| Source field |
|--|--|
| Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice  |Tax exempt number/ Tax registration number from the original document |
| Journal with Vendor/Customer line | Tax reporting number field on journal line |

 

**Document** 

|Source document| Source field |
|--|--|
| Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice  | |
| Journal with Vendor/Customer line |Document field if fields Invoice and Document are populated / Invoice field if only field Invoice is populated on the journal line. |

  

 **Document date** 
|Source document| Source field |
|--|--|
| Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice  |Invoice date on the original document |
| Journal with Vendor/Customer line | Invoice date field on journal line |



**Document receipt date** 

|Source document| Source field |
|--|--|
| Vendor Invoice |Document receipt date on the original document|
| Journal with Vendor/Customer line | Document receipt field on journal line |


## **Reporting Tab data on Journals**
----

When Journals are used, **reporting data is defaulted** from Vendor/Customer line to other lines within the same Voucher. This is useful in cases, when journals are used for posting invoices. Without dafaulting user would have to populate the fields, used for reporting (these are fields that get transferred to Reporting tab on Tax trandasction) manually on all the lines that generate tax transactions. 

New field, **Tax reporting number**, is added to journal. There is no validation on this field. It is **filled automatically** from the fields in following order: 
1. VAT ID on Vendor/Customer
1. Tax registration number on Vendor/Customer
1. Registration ID of type VAT ID
1. Registration ID of type Tax registration number


Functions **Post** and **Simulate posting** trigger copying the data from Vendor/Customer line to other lines. Only empty fields will get populated by copying from Vendor/Customer line.  

Following data gets transferred from Vendor/Customer line to other lines within the same Voucher: 
- Customer/Vendor 
- Address 
- Tax exempt number 
- Tax reporting number 
- Document 
- Document date 
- Document receipt date 
- Invoice
