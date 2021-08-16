Following fields are added to Customer and Vendor: 
- Tax registration number
- Taxable person type
- Company ID

## **Setup**
---

## Tax registration number
 Davčna številka in Slovenian localization and OIB in Croatian localization. 

1. Go to **Accounts receivable > Customers > All customers > Select customer > Invoice and delivery tab > Tax registration number field** or **Accounts payable> Vendors > All Vendors > Select Vendor > Invoice and delivery tab > Tax registration number field**
1. Enter **Tax registration number** manually or select from drop-down list
1. Drop-down list shows information from SI Taxable persons
1. _Valid only for SI_: If value is selected from SI Taxable persons list (Slovenia), values in the field Taxable person type, Company ID and Tax exempt code (if Customer/Vendor is liable for VAT) are **populated automatically**.


## Taxable person type (SI only) 

1. Go to **Accounts receivable > Customers > All customers > Select Customer > Invoice and delivery tab > Tax registration number field** or **Accounts payable> Vendors > All Vendors > Select Vendor > Invoice and delivery tab > Tax registration number field**
1. Select **Taxable person type** from drop-down menu. Available options: 
   - Legal entity
   - Sole proprietor
   - Natural person
1. Filed can be populated **automatically** when selecting Tax registration number.

_Note: This setup **affects validation** of **Tax registration number** (Davčna številka) and **Registration number** (Matična številka), when eInovice is generated. For more details go to [eInvoices](/Help/Core-Localization/eInvoice/eInvoice-for-Slovenia)._ 


## Company ID (SI only)
Matična številka
1. Go to **Accounts receivable > Customers > All customers > Select Customer > Invoice and delivery tab > Tax registration number field** or **Accounts payable> Vendors > All Vendors > Select Vendor > Invoice and delivery tab > Tax registration number field**
1. Enter the number manually. 
1. Filed can be populated **automatically** when selecting Tax registration number.


## **Retrieval priority**
---

Identification numbers listed above are used for reporting purposes. They can be used in combination with Registratin ID's (see   [Registration ID's](/Help/Core-Localization/Company,-Customer-and-Vendor-identification-numbers/Registration-IDs). Therefore retrieval priority is defined:   


### Customer/vendor entity 
**Tax registration number** (Davčna številka or OIB): 

1. Tax registration number on customer or vendor
2. Registration IDs

**Company ID** (Matična številka) 
1. ID number on customer or vendor
2. Registrations IDs 


### Legal entity:
**Tax registration number** (Davčna številka or OIB):
1. Tax registration number on legal entity
2. Registration IDs

**VAT ID** (ID za DDV)
1. VAT exempt number export on legal entity
2. Registrations IDs 