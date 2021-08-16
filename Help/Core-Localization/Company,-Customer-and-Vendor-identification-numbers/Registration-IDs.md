In order to comply with locally used registration IDs (e.g. tax and identification numbers), additional registration categories are added with this localization feature and need to be set up for the adequate Registration IDs to allow other localized features to work correctly - e.g. REK reporting and eInvoices use Registration IDs with the localized registration categories for validation purposes. If inadequate registration categories are used for the set-up of registration IDs, validation when using other localized features may fail, while the required ID may also be missing from other documents, therefore localized registration categories should be used.

Standard D365 features allow for the validation of Tax exempt numbers formats. However, by standard, format validation is not available for Slovenian or Croatian Tax exempt numbers and is added with this localization feature.


Standard functionality Registration IDs is used for managing different kinds of identification numbers. Some of bullets are included only for user setup help.  

## **Setup**
----

### Registration types 

1. Open Organization administration – Global address book – Registration types – Registration types.
2. Set up registration types for the different types of registration numbers that each party is subject to:


| **Field** | **Description** |
|--|--|
|Name  | The description of the registration type. |
|Description  | The unique identifier of the country/region. |
|Country/region |The unique identifier of the country/region.  |
|Tax authority  | The tax authority that is associated with the registration type.  |
|Restricted to  |The kind of restriction that applies to the tax registration type: None, Person, Organization.  |
|Format |The validation format for the registration type.  |
|Can be updated  |Defines if the registration number for the registration type can be updated after it is entered.  |
|Unique  |Defines if the registration number for the registration type is unique.  |
|Primary for the country  |If a party is associated with one or more addresses in a particular country and the registration ID is valid for all these addresses, you must designate one address as primary for the country. You can only register one ID as primary. Defines if the registration number can be entered only for primary for country address.   |


  ### Registration category 

Registration category is country/region registration identifier approved for using in particular country/region for tax, customs, and other purposes. This category defines validation rules of particular registration ID (including check digits etc.) and inclusion of registration ID in different reports

1. Open Organization administration – Global address book – Registration types – Registration category.
2. Set fields:


| **Field** | **Description** |
|--|--|
|Registration type  |The registration type for a particular country/region.  |
|Restricted to |The kind of restriction applies to the tax registration type: None, Person, Organization.  |
|Registration category  |The unique registration identifier approved for use in the country. As part of localization following Registration categories were added:  |
|| - Tax identification number (AD): Davčna številka for SLO, OIB for CRO and PIB for RS|
|| - Company registration number (AD): Matična številka for SLO|
|| - National identification number (AD): EMŠO for SLO|

Standard Registration category VAT ID is used for ID for VAT purposes. 

Dropdown menu for Tax exempt number (with the filter set to Party) on Vendor/Customer card will show all registration IDs with the VAT ID registration category (standard functionality). 

## **Use registration IDs** 
----

1. Click Registration IDs on forms related to the party, legal entity, vendor, customer, worker to open the Manage addresses page.  
2. On the Registration ID tab, click Add, and enter information about the registration ID. Validation upon format and structure for a registration number that is VAT ID registration category is part of localization functionality. 

**Slovenia** 

### VAT ID, Tax identification number (AD), Company registration number (AD) and National identification number (AD) for Slovenia 

Setup in registration categories: 


| Registration category | Description |Available list|
|--|--|--|
|VAT ID  | ID za DDV |Tax exempt numbers list is opened. Tax exempt number (ID za DDV) from the list is copied to the Registration number field. Pay attention to the setup of the Registration type formatting. Correct formatting should be SI########.|
|Tax identification number (AD) |Davčna številka  |Slovenian taxable person list is opened. The tax registration number (Davčna številka) from the list is copied to the Registration number field.|
|Company registration number (AD)  |Matična številka podjetja  |Slovenian taxable person list is opened. ID number (Matična številka) from the list is copied to the Registration number field.|
|National identification number (AD) |EMŠO  |No list available|
 
  

On the Registration ID tab, enter information about the registration ID. 

  

In other cases, registration numbers must be entered manually. 


**Croatia**

### OIB number for Croatia 

OIB number is entered as Registration type “Tax identification number (AD)”, using standard registration IDs functionality. For VAT purposes VAT ID Registration type is used.  

1. Set up registration categories. 

2. In the case of Registration type with registration category Tax identification number (AD), a dropdown list with Croatian taxable persons opens. A dropdown is available as part of the LOC_core package.  

For the VAT ID registration category, manual entry is required.  

**Serbia**

### PIB number for Serbia 

Registration ID can be used for an ID number, using standard registration IDs functionality. 

1. Set up the Enterprise ID registration category for the ID number. 

2. Click Registration IDs on forms related to the party, legal entity, vendor, customer, worker to open the Manage addresses page and enter registration number for selected registration type. 

## **Registration ID validation** 
----

### OIB validation (CRO) 

New OIB number is entered in Croatian taxable persons (Tax – Declaration – Croatia – Croatian taxable persons). 

Format and structure (11 digits) are validated upon entry – there is a warning in case of an incorrect OIB number. 

### Tax exempt number validation (SI, CRO) 

Validation is performed if the Check tax exempt number is marked in Tax/Setup/Sales tax/Country/region parameters.  

Validation for Slovenia and Croatia is added as part of localization. Validation for other supported countries is performed as part of standard solution. Tax exempt number structure (8 digits for SI and 11 for CRO) is validated upon entry – there is a warning displayed in case of incorrect tax exempt number.    


## **Retrieval priority**
---

REgistration ID's listed above are used for reporting purposes. They can be used in combination with additional identification numbers (see   [Additional identification numbers](/Help/Core-Localization/Company,-Customer-and-Vendor-identification-numbers/Additional-identification-numbers). Therefore retrieval priority is defined:   


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