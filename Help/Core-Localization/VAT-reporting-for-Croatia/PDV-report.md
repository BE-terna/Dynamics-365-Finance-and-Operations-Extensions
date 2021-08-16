# Create a PDV form 

PDV report is a Croatian sales tax return report. Every taxable person identified for VAT purposes is obliged to submit a VAT return to the Croatian tax authority. The report consists of sums of sales tax from both payable and receivable transactions, according to different sales tax rates. Taxable entities must submit the PDV report electronically via the ePorezna portal of the Croatian tax authority.

## **Setup**
----

### Legal Entity - Tax reporting number 
Go to Organization administration > Legal entities > open specific Legal entity > Tag reporting tab. 
**Enter OIB** in Tax registration number field. **Important**: Do not enter VAT ID in this field since all reports use this field as OIB.

### Legal Entity - Address
Go to Organization administration > Legal entities > open specific Legal entity > Address. Enter Legal entity address. Information is used for reporting purposes. 

###Sales tax authorities - report layout

To generate a VAT declaration in the correct format for the appropriate tax authority, you must set up the **report layout** for the sales tax authorities. On the **Sales tax authorities** page, in the **Report layout** field, select **Croatian report layout**. Select the same sales tax authority for the sales tax settlement period that will be used in the sales tax codes. 

###Sales tax authorities - responsible person
When generating XML, it is mandatory to report **responsible person** for the preparation of report. Setup exists on Tax authorities form. Currently fields Responsible person first name and Responsible person last name need to be added to the form using personalization. 

####Sales tax reporting codes

The generation of reports is based on reporting codes. Reporting code carries information about which field the transaction will be recorded in. 

1. Open **Tax > Setup > Sales tax > Sales tax reporting codes**:
   - Enter the list of **reporting codes for Croatia**. Reporting codes can also be imported using Excel add-in. 
2. Open **Tax > Indirect taxes > Sales tax > Sales tax codes**:
   - VAT reports are generated according to the setup of sales tax reporting codes on sales tax codes.  

####Configure Electronic reporting 

First make sure, that BE-terna localization ER configurations are imported. In case they are missing, you will need to import them first. Instructions are available on [**this link**](/How-to/Import-BE%2Dterna-ER-configurations). 

Open Electronic reporting formats setup in General ledger > General ledger parameters > BE-terna localization. To generate PDV form, electronic reporting formats need to be configured first. Two formats are available for PDV form: 
   - (1) PDVXmlFormatVer8 electronic reporting format is used to report Sales tax transactions up to (including) 31.12.2014 
   - (2) PDVXmlFormatVer9 electronic reporting format is used to report Sales tax transactions from (including) 1.1.2015 

## **Generate VAT statement (PDV form)** 
----

Sales tax calculation according to VAT date is part of the BE-terna localization pack, while standard sales tax calculation is performed according to the posting date. Standard Sales tax calculation form is used, and it can be found in **Tax > Declarations > Sales tax > Report sales tax for the settlement period**.


| **Field**                 | **Description**                                                                                                                                                                                                     |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Settlement period         | Period for which calculation is performed                                                                                                                                                                           |
| From date                 | first day of the period for which calculation should be performed                                                                                                                                                   |
| Transaction date          | Datum for settlement posting                                                                                                                                                                                        |
| Sales tax payment version | _Original_ – is used when no settlement posting for the chosen period exists. _Latest corrections_ – is used when a settlement for the existing period is already posted. Only Tax Transactions that were created after the last settlement posting are included.  |


 
As a result of the Sales tax calculation process PDV form is created (CRO localization feature). It can be viewed in **Tax > Declarations > Croatia> VAT > PDV forms**. 

####Export to XML
The report can be exported to XML by choosing a button **Export**. 



 

 

 

 
