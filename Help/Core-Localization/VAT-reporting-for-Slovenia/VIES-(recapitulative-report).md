# VIES Report (EU Sales list) 

VIES report is a report in which taxable entities, identified for VAT purposes in Slovenia are obliged to report the supplies of goods and services that are delivered to entities, identified for VAT in the other Member States of the European Union during the reporting period (the calendar month). VIES report needs to be submitted to the Slovenian tax authority (FURS) till the 20th in the following month after the occurrence of the reporting events.

VIES (recapitulative report) processes the transactions, considered as intra-community trade transactions based on the delivery address of the documents (Sales invoices, Free text invoices, Project invoices, Vendor invoices) if country code from that address is specified for the EU trade. Selected transactions are then transferred to the EU sales list journal if they meet the predetermined criterion. Additional localized information is available to be added to these transactions (e.g. Customs procedure 42 or 63). In contrary to the standard, localized feature reports transactions based on the VAT (and not transaction) date. VIES report can be exported either to an Excel file (standard) or to an adequate XML file format (localization), accepted by the Slovenian tax authority (FURS) portal eDavki and previewed prior to export. After generating an EU Sales list report for a specific period, it is also possible to mark the records that are included in the report by setting the Reporting status value to Reported and Closed when for example tax authorities have accepted the report.

## **Setup** 
------

### Legal entity 

1. Open **Organization administration > Organizations > Legal entities.**
2. The **primary address** of the legal entity must be in an **EU member state**. On the Legal entities page, select your legal entity. On the Addresses, FastTab, create an address, select a country/region and other address components, and mark the address as Primary.  
3. On the **Tax registration FastTab**, in the “Tax registration number” field, specify the **tax registration number** for your company. 

### Tax exempt identification parameters 

1. Open **Tax > Setup > Sales tax > Country/region parameters**.
2. Set up **tax exempt identification parameters** on the Country/region parameters page. For each country/region where you have counterparties, create a record on the page, and specify the following information: 


|**Parameter**|**Description**|
|--|--|
|Country/Region |Select a country/region to associate with a tax exempt identification.  |
|Sales tax  |Enter the tax exempt identification number (that is, the tax exempt number prefix) for the selected country/region.  |
|Check tax exempt number  |Select this checkbox to validate the tax exempt identification for the selected country/region.  |

  
### Tax exempt numbers 

1. Open **Tax > Setup > Sales tax > Tax exempt numbers**.
2. Create **tax exempt numbers** for your counterparties on the Tax exempt numbers page. For each tax exempt number, create a record on the page, and specify the following information: 

|**Parameter**|**Description**|
|--|--|
|Country/Region |Select the country/region of the tax registration of the counterparty. |
|Tax exempt number  |Enter the tax exempt number of the counterparty.  |
|Company name  |(optional) Enter the name of the counterparty. |

 
3. Navigate to All Customers or All Vendors, and **select a customer/vendor record**. On the Invoice and delivery FastTab, in the “Tax exempt number” field, **select the tax registration number**. 

### Sales tax 

#### Sales tax codes 

1. Open **Tax > Indirect taxes > Sales tax > Sales tax codes**.
2. Set up the **tax codes to include** on the EU Sales list report. On the Report setup FastTab, for each sales tax code that should be included in the report, **clear the “Excluded” checkbox**.  

#### Item sales tax groups 

1. Open **Tax > Indirect taxes > Sales tax > Item sales tax groups**.
2. Set up sales tax parameters for items on the Item sales tax groups page. For each item sales tax group, **select a value in the “Reporting type” field**. The value that you select determines the ESL amount column that the line amount will be included in:


|**Value**|**Description**|
|--|--|
|Blank |The line amount is included in the “Not assigned” value column.  |
|Item  |The line amount is included in the “Items” value column.  |
|Service  |The line amount is included in the “Services” value column.   |
|Investment  |The line amount is included in the “Investment” value column. NOTE: This column is relevant only for Belgium.  |


#### Electronic reporting configuration 

1. Open **Workspaces > Electronic reporting > Reporting configurations**.
2. Search for model “EU Sales list model” and expand it to find **“EU Sales list AD”**. Check for status “Completed” in tab Versions. 

#### Foreign trade parameters 

1. Open **Tax > Setup > Foreign trade > Foreign trade parameters**.
2. Set up ESL reporting parameters on the Foreign trade parameters page. Specify the following parameters on EU sales list tab on Transfer part:


|**Parameter**|**Description**|
|--|--|
|Report cash discount  |Select this checkbox if a cash discount should be included in the value when a transaction is included in the ESL.  |
|Transfer purchases  |Select this checkbox to include purchases on the ESL.  |


3. Set up **ESL reporting parameters** on the Foreign trade parameters page. Specify the following parameters on EU sales list tab on **Rounding rules** part:

|**Parameter**|**Description**|
|--|--|
|Rounding rule  |Specify a real number to use for rounding. ESL amounts will be rounded to multiples of this number. |
|Use minimum value  |Select this checkbox if you want amounts that are less than the Rounding rule number to be rounded up to the Rounding rule  |
|Rounding method  |Select the rounding method to use when ESL amounts are rounded (Normal, Downward, or Rounding-up).|
|Number of decimals |Specify the number of decimal places to show in ESL amounts (both in electronic files and on the ESL preview report).|
 
4. Set up **ESL reporting parameters** on the Foreign trade parameters page. Specify the following parameters on EU sales list tab on the **Electronic reporting** part:

|**Parameter**|**Description**|
|--|--|
|File format mapping |Select the electronic reporting format to use when an export file is generated for the ESL. The export format is localized since it is specific for each of the countries.|
|Report format mapping  |Select the format to use when a preview report is generated for the ESL. |

  
5. Set the following parameters on the **Country/region properties** tab. **Identify EU member states**. For each EU member state, create a record on the page, and specify the following information:  

|**Parameter**|**Description**|
|--|--|
|Country/region |Select a country/region.|
|Country/region type|If the Country/region value is the country that your company is registered in, select “Domestic”. If it is an EU member state other than the country that your company is registered in, select “EU”. If the Country/region value is not an EU member state, select “Third country/region”. |

6. Set the following parameters on the **Number sequences** tab: 
   - Select a number sequence code for the EU sales list reference. 

7. Select **report mapping** in **Electronic reporting**  tab: 
   - Select File format mapping. Choose **EU Sales list * (SI)**. Other options ignore localized specifics.
   - Select Report format mapping. Choose **EU Sales list * (SI)**. Other options ignore localized specifics.

     
          

### Warehouse for consignment setup 

This setup is needed in case the client needs to report sections C to G and A17 from the EU Sales list report. 

1. Open **Inventory management > Setup > Inventory breakdown > Warehouses**.
2. Following setup is added to **Warehouse**:  

|**Parameter**|**Description**|
|--|--|
|Customer account |Customer that owns the warehouse|
|EU Sales list/Excluded|If set to No, transactions to/from this warehouse will be included in VIES reporting in the Consignment part of the report.|

  

For VIES reporting purposes **Address** also needs to be set on Warehouse. If Address is outside EU, transactions will be excluded from VIES reporting, regardless of the setup described above.  

# **Working with the EU Sales list** 


### EU Sales list transactions 
---

Transactions of the **following types** can be considered intra-community trade transactions: 
   - Sales invoices  
   - Free text invoices  
   - Project invoices  
   - Vendor invoices 
   - Transfer orders (SI localization) 
   - Transfer journals (SI localization) 

Additionally, consignment transactions need to be reported when goods are transferred to/from consignment warehouse that is in another EU member state. For this purpose, **additional types** of documents are added to reporting as part of Slovenian localization.  

A transaction is considered an intra-community trade transaction if the delivery address of the transaction is in a member state of the EU. For such countries, a record of Country/region type “EU” should exist on the Country/region parameters tab of the Foreign trade parameters page.  

Intra-community trade transactions are marked in the “List code” field. If the delivery address is one of the Countries/regions with Country/region type “EU”, specified in Country/region parameters of the Foreign trade parameters page, then the value in this field is automatically set to “EU trade”. Using this field, you can also separate general intra-community trade transactions from triangular trade transactions. Localization added option is “Customs procedure 42 or 63”. 

<br>

### Collect EU sales list transactions 
---

1. Open **Tax > Declarations > Foreign trade > EU Sales list**.
2. You can collect information about intra-EU trade transactions on the EU Sales list page by using the **“Transfer”** function. This function lets you include transactions of different reporting types (i.e., items or services), according to the item sales tax groups that are specified on transaction lines.  
The Transfer function creates a record on the EU Sales list journal for each transaction that corresponds to selected parameters. Counterparty account number, country/region, tax exempt number, and invoice number and date are transferred. The list code value is copied from the transaction. You can manually change the list code for a transaction on the EU Sales list page. Additional localization value is “Customs procedure 42 or 63”. 
3. The **Transfer function** creates records with the **Reporting status** value set to **Included**. 

You can validate the information that is collected on the EU Sales list page by using the **“Validate”** function. 

<br>

### Collect EU sales list Consignment transactions - Consignment reporting 
---

Transfers to/from consignment warehouses located in another EU member state are collected in Consignment Tab.  They are generated by using the Transfer consignment function.

1. Open **Tax > Declarations > Foreign trade > EU Sales list > Consignment**.
2. “From” or “To” Warehouse nedds to have following parameters set:  
   - The **customer field** must be populated.
   - **EU Sales list Excluded** parameter must be set to NO.
   - **Warehouse Address** needs to be in the EU.
3. Following transaction types can be generated:  

|**Transaction Type**|**From warehouse > To warehouse**  | **Action** |
|--|--|--|
| Issue |non-consignment warehouse > consignment warehouse  |Shipment  |
| Return |consignment warehouse > non-consignment warehouse  |Receive  |
| Transfer |consignment warehouse > consignment warehouse  |Shipment and Receive  |


<br>

### **Generating EU sales list report** 
-----

EU Sales list transactions are reported **according to VAT date** in localization (contrary to invoice date in standard). You can generate report by using the **“Reporting”** function on EU sales list.  Open **Tax > Declarations > Foreign trade > EU Sales list > Reporting**  and Insert following parameters:  


| **Parameter** |**Description**|
|--|--|
|**Reporting period** |Select the type of reporting period from the following options:<br> - _Not selected_ – The reporting period is not specified.<br> - _Monthly_ – The EU sales list report is generated monthly.<br> - _Quarterly_ – The EU sales list report is generated quarterly.|
|**From date** |Select the starting date of the reporting period to include in the report.  |
|**To date**  |Select the ending date of the reporting period to include in the report.  |
|**Generate file**  | Select this check box to generate the EU sales list as an export **XML file**. |
|**File name**  |Enter the file name and file path of the EU sales list export file.  |
|**Generate report**  |Select this check box to generate **preview report**.  |
|**Report name**  |Enter the file name and file path of the EU sales list preview file.   |
|**Send electronically**  |Localization feature. For this to be enabled, you need to select the “Generate file” first. The file name is a mandatory field. This option creates a record in **Tax > Declarations > Slovenia > VAT > VIES recapitulative forms**, which can be previewed  or exported to the XML file.  |
|**Worker**  | Select the worker who is responsible for filing the report |



#### Reporting status 

After you generate an EU Sales list report for a specific period, you can mark the records that are included in the report by setting the Reporting status value to **Reported**. To set this status, use the **“Mark” > “Mark as reported”** function on the EU Sales list page. 

When you have completed the reporting process for a specific period (for example, when tax authorities have accepted the EU Sales list report), you can mark the records as **Closed**.  

Setting the Reporting status value to **“Included”** will revert the closing of the period. These records can then be included on EU Sales list report again. You can select to view transactions according to their status.  

#### Corrections 

Localization allows users to **report corrections** for previous periods. Standard feature enables marking corrected transaction (field “Corrected” in the EU sales list transaction line). Localization feature changes this logic with marking correcting transactions, opposite to standard functionality where corrected transactions are marked.   

Additionally Date of original document is added. This information is needed for **section B reporting**. 

Reporting date determines the period in which the correction is reported. 

All documents marked as correction are reported in section B of the report. Cases listed below, are supported:  
   - One credit note, one invoice; Invoice value > credit note value. Expected result: New value is the difference between reported summarized value for the corrected period for selected VAT ID and summarized value of corrections for the reporting period for selected VAT ID.  
   - One credit note, multiple invoices from different periods; Invoice value in last period > Credit note value. Expected result: New value is the difference between reported summarized value for the corrected period (period of last settled invoice) for selected VAT ID and summarized value of corrections for reporting period for selected VAT ID.  
   - One credit note, multiple invoices from different periods; Invoice value in last period < Credit note value. Expected result: New value is the summarized value of corrections for reporting period for selected VAT ID. Value needs to be adjusted manually. 
   - Credit note without the settlement. Expected result: New value is the summarized value of corrections for reporting period for selected VAT ID. The value needs to be adjusted manually. 

#### Corrections – Consignment transactions 

Corrections of consignment transactions need to be entered manually. Process description:  
1. Enter new line.
2. Enter new line to Consignment Tab and enter correct data that needs to be reported.
3. Go to Consignment correction tab and Set “Corrected” tab to Yes.
4. From dropdown list pick original consignment that is being corrected 
5. Enter Correction type.

Correction transactions will be then reported in sections F or G of the report.  

 