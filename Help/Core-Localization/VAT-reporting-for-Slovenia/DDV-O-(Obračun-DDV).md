# VAT statement (DDV-O) details for Slovenia

DDV-O is a Slovenian tax return report. Every taxable person identified for VAT purposes in Slovenia is obliged to submit a VAT return to the Slovenian tax authority. DDV-O should include all the required VAT return settings, with the information needed to calculate the sales tax and applicable deduction to be made including the total value of transactions relating to such tax and deductions. Additionally, the value of any exempt transactions should be included. Taxable entities have to submit the tax return to the tax authority by the last business day of the month, which follows the expiry of the tax period, while Slovenian laws also allow multiple exceptions. VAT tax return (DDV-O) needs to be submitted electronically via the eDavki portal of the Slovenian tax authority (FURS).

DDV-O is prepared based on Tax transactions and **according to the VAT date**. DDV-O can also be previewed (HTML) and exported to the XML file.

## **Setup**
----

####Legal entity - Tax registration number
1. Go to **Organization information > Organizations > Legal entities > Tab Tax registration > Tax registration number**
2. Enter Tax registration for the Legal entity (Davčna številka!)

####Sales tax authorities

To generate a VAT declaration in the correct format for the appropriate tax authority, you must set up the report layout for the sales tax authorities. On the **Sales tax authorities** page, in the **Report layout** field, select **Slovenian report layout**. Select the same sales tax authority for the sales tax settlement period that will be used in the sales tax codes. 

####Sales tax reporting codes

The generation of reports is based on reporting codes. Reporting code carries information about which field the transaction will be recorded in. 

1. Open **Tax > Setup > Sales tax > Sales tax reporting codes**:
   - Enter the list of **[reporting codes for SI](Reporting-codes.zip)**. Reporting codes can also be imported using Excel add-in. 
2. Open **Tax > Indirect taxes > Sales tax > Sales tax codes**:
   - VAT reports are generated according to the setup of sales tax reporting codes on sales tax codes.  

####Configure Electronic reporting 

First make sure, that BE-terna localization ER configurations are imported. In case they are missing, you will need to import them first. Instructions are available on [**this link**](/How-to/Import-Adacta-ER-configurations). 

Open **Electronic reporting formats setup in General ledger > General ledger parameters > BE-terna localization**. To generate DDV-O, electronic reporting formats need to be configured first. Two formats are available for DDV-O: 
   - (1) DDV-O electronic reporting format is used to report Sales tax transactions up to (including) 31.12.2019 
   - (2) DDV-O (version 11) electronic reporting format is used to report Sales tax transactions after (including) 1.1.2020. 

## **Generate VAT statement (DDV-O)** 
----

Sales tax calculation **according to VAT date** is part of the BE-terna localization pack, while standard sales tax calculation is performed according to the posting date. Standard Sales tax calculation form is used, and it can be found in **Tax > Declarations > Sales tax > Report sales tax for the settlement period**.


| **Field**                 | **Description**                                                                                                                                                                                                     |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Settlement period         | Period for which calculation is performed                                                                                                                                                                           |
| From date                 | first day of the period for which calculation should be performed                                                                                                                                                   |
| Transaction date          | Datum for settlement posting                                                                                                                                                                                        |
| Sales tax payment version | _Original_ – is used when no settlement posting for the chosen period exists. _Latest corrections_ – is used when a settlement for the existing period is already posted. Only Tax Transactions that were created after the last settlement posting are included.  |


 
As a result of the Sales tax calculation process DDV-O form is created (SI localization feature). It can be viewed in **Tax > Declarations > Slovenia > VAT > DDV-O forms**. 

####Preview report
Tax report can be previewed. Preview is generated based on generated XML, using transformation from eDavki. This means that in preview report is visible in identical way is it will be visible on eDavki. 

####Export to XML
The report can be exported to XML by choosing a button Export to XML. If the Sales tax reporting date is before 1.1.2020, the old version of DDV-O form is generated instead. 

_**NOTE**: Field TaxNumber in XML is populated with Tax registration number (Davčna številka) and not VAT number (ID za DDV). When XML is imported into eDavki, this number is transformed (SI prefix is added as part of transformation in eDavki)._ 

## **DDV-O Correction** 
----

DDV-O corrections are enabled in Self report  -> Correction tab. Tax amount and interests can be reported. Correction is visible on the DDV-O report preview and is also included in exported XML.  

