# Intrastat enhancements

Intrastat is the system for collecting information and generating statistics about the trade of goods among countries/regions of the European Union (EU). Intrastat reporting is required whenever a product crosses the border of another EU country/region, whereas, in several countries/regions, Intrastat reporting also applies to services. Mandatory and optional elements can be collected in Intrastat reporting. Most of the Intrastat functionality consists of standard D365 features. Some features, however, are added in order to comply with the requirements of the Slovenian and Croatian local authorities. These localized enhancements are described in the following section.



###**Exchange rate**

 
In Croatia it is legally required to report foreign currency transactions converted into Croatian local currency (HRK), using the first valid exchange rate of Croatian national bank for the month in which Intrastat is required to be reported. This localization feature allows users to specify the adequate Exchange rate type in order to include the exchange rate calculation. When transferring transactions in foreign currency (other than HRK) to Intrastat journal, values are recalculated to accounting currency, using the specified Intrastat exchange rate.
ELECTRONIC REPORTING FORMATS Localization provides adequate Intrastat report file mappings (for Slovenia and Croatia), which enable users to generate Intrastat reports in accordance with the Slovenian and Croatian legislation, whereas the reporting format is standard.


### **Intrastat journal line status**

Another localized feature is the line status of transactions included in the Intrastat journal. With the localization added status allows lines in Intrastat journal to be available for editing until line status remains “Open”. Additionally, transactions can be filtered based on this status.


### **Reporting history**

The feature enables reviewing historically created Intrastat declaration (and in these declarations included transactions). Additionally, it enables a generation of replacement declarations regarding past reporting periods, for which Intrastat declarations have already been submitted. Status of the reported transactions can be set back to “Open”, and then replacement declaration can be created for each of the reports from reporting history. This can be useful if changes have been made in connection with transactions, which have already been declared through Intrastat. In this case, replacement declarations can be created, with the updated transactions reporting period.


### **Intrastat archive**

Enables users to review transactions, which have been compressed by parameters (compression is a standard feature, while the review of compressed transactions is localized feature). Localization functionality also ads option to transfer the compressed transactions back to the Intrastat journal in their original state (before compression) when applicable.

### **Weight change on product receipt**
Information about weight can be manually changed on product receipt line. 

### **Weight validation moved from Item to Product receipt**
Standard validation (weight on Item) is removed and enabled only validation of weight on product receipt. If weight is missing on Item and entered on product receipt, document can be posted.   

### **Statistical adjustment value according to delivery terms** 
With additional setup on Delivery terms, statistical value adjustment can be calculated. Different setup can be applied to each delivery term. 


## **Setup**
---

### Transaction codes

1. Open Tax – Setup – Foreign trade – Transaction codes.
2. Set up the nature of the transaction according to your country’s requirements. For each transaction code that you set up, you must set up the rules for calculating invoice amounts and statistical amounts for transfer orders and sales/purchase orders.
3. For transfer orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:
   - Empty – The amount will be 0 (zero).
   - Financial cost amount – The amount will be equal to the financial cost.
   - Total cost – The amount will be equal to the total cost of the transaction.
   - Manual – The amount will be equal to the amount that is manually specified on the transfer order line.
4. For sales orders and purchase orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:
   - Empty – The amount will be 0 (zero).
   - Invoice amount – The amount will be equal to the amount that is invoiced for the commodity.
   - Base amount – The amount will be equal to the amount that would be invoiced before any discount is applied.
 
### Transport method

1. Open Tax – Setup – Foreign trade – Transport method.
2. Set up the transport mode according to your country’s requirements. 
 
For each mode of delivery (Procurement and sourcing – Setup – Distribution – Modes of delivery), you can set up a default transport method on the Foreign trade tab.

### Port

1. Open Tax – Setup – Foreign trade – Port.
2. Set up the port/airport of loading/unloading if this information is collected by your country.
 
### Delivery terms - Intrastat code

1. Open Accounts payable – Setup – Terms of delivery.
2. If a country collects delivery terms information, it is necessary to set them up. Define the Intrastat code for each of the terms.

### Delivery terms - statistical value adjustment

1. Open Accounts payable > Setup > Terms of delivery.
2. Set Intrastat dispatch statistical value percent adjustment if needed: Statistical amount on the dispatch transaction will be adjusted according to setup
3. Set Intrastat arrival statistical value adjustment percent if needed: Statistical amount on the arrival transaction will be adjusted according to setup

 
### Statistics procedure

1. Open Tax – Setup – Foreign trade – Statistics procedure.
2. Set up the statistical procedure if this information is collected by your country.
 
### Compression of Intrastat

1. Open Tax – Setup – Foreign trade – Compression of Intrastat.
2. Here, you can select the fields to use for compression. All transactions that have the same combination of values for the selected fields in the Intrastat journal will be compressed into a single transaction when you run the Compress function in the Intrastat journal.
 
### ISO codes for countries/regions

1. Open Organization administration – Global address book – Addresses – Address setup.
2. Set up the International Organization for Standardization (ISO) codes for countries/regions.
 
### Commodity codes

1. Open Product information management – Setup – Categories and attributes – Category hierarchy role associations
2. Set up a category hierarchy of type “Commodity code”.
3. Open Product information management – Setup – Categories and attributes – Category hierarchies.
4. Enter all commodity codes according to the combined nomenclature list. For each commodity, set up the following information:
   - The name of the commodity and the commodity code
   - The friendly name and/or translated name
   - Settings for reporting additional (supplementary) units on the Foreign trade tab. You can select the additional unit in the unit list. You can also specify whether the weight of commodities must be reported in addition to the selected additional unit.
5. Created commodity codes will be available in the Selected view when you select a commodity code in the released product details, and on the sales order, purchase order, and transfer order lines.

### Electronic reporting

Set up electronic reporting configurations to export Intrastat data in an electronic file that has the format that is requested by the relevant authorities.
 
### Foreign trade parameters

1. Intrastat 

Open Tax – Setup – Foreign trade – Foreign trade parameters - Intrastat:
   - General – Specify the following information:
      - The default transaction codes for sales orders, purchase orders, credit notes, and transfer orders. The transaction code that is set up for credit notes is also used as the code for physical goods return and is used for deviating physical returns versus correction credit notes.
      - The employee that is responsible for preparing Intrastat reports.
    - Minimum limit – Specify the settings for updating transactions that are below the threshold:
      - The threshold amount and weight
      - The commodity code to apply to transactions that are under the threshold
    - Transfer – Specify the criteria for transferring transactions to the Intrastat journal. You can specify that transactions are transferred only when the items meet one or all of the following criteria:
      - The items are not service items.
      - The items have a commodity code.
      - The items have a weight.
      - The items have additional units.
    - Check setup – Specify the rules for validating the completeness of the transactions in the Intrastat journal. Transactions that aren’t completed will be marked as not valid. You can select which data is validated.
    - Exchange rate (LOC) – localization allows you to specify Exchange rate type if needed. Upon transferring transactions in foreign currency to the Intrastat journal, the value in field Invoice amount is calculated to accounting currency, using selected Intrastat exchange rate. 
In particular, this is used in Croatia, since it is required to report foreign currency transactions converted into HRK at the first valid exchange rate of Croatian national bank for the month in which Intrastat is reported. <br>
Exchange rate type for Intrastat is manually created in Cost accounting – Ledger setup – Currencies – Exchange rate types. Specify “From currency” and “To currency” and add the exchange rate.
 
    - Rounding rules – Specify the following settings for rounding amounts and weights in Intrastat reporting:
      - The rounding rule (precision)
      - The rounding method: up, down, or normal
      - The number of decimal places for amounts and weights
      - Instructions for rounding weights that are less than 1 kilogram (kg): up to 1 kg, normal, or no rounding
     - Electronic reporting format (LOC) – Specify references to electronic reporting configurations, so that you can generate an electronic file and report. Intrastat (SI) for SI and Intrastat (HR) for HR file format mapping is part of localization, whereas Report format mapping is standard. 
    - Commodity code hierarchy – Specify the category hierarchy of the Commodity code type that represents the Intrastat commodity code. 
 
2. Agent: Specify the agent's contact information: name, address, tax exempt number, telephone number, and fax number.
 
3. Country/region properties: Set the country/region of the current legal entity to Domestic. Set the country/region of EU countries/regions that participate in EU trade with the current legal entity to EU. For each country/region, you also identify country/region intrastate code which transfers to report.
	
4. Number sequence: Specify the number sequence for the Intrastat journal.
 
### Legal entity setup

1. Open Organization administration – Organizations – Legal entities
2. Set up tax exempt numbers for import/export, and the Intrastat code that is assigned to the legal entity (company’s tax registration number).
 
### Released products setup

1. Open Product information management – Products – Released products
2. Set up the following foreign trade data for released products.
   - Commodity code – Select from either the list of selected commodities that is retrieved from assigned product categories or the full list of Intrastat commodity codes.
   - Statistical charges percentage
   - Country/region of origin – Select the default country/region where the goods were completely obtained or produced.
   - State/province of origin/destination – Select the default state/province of destination for arrivals and the state/province of origin for dispatches.
   - Net weight in kg
 
### Customer/Vendor setup

1. Set up the customer/vendor delivery address in the EU country/region.
2. Set up customer/vendor’s tax exempt number. Optionally, enter delivery data which is transferred to purchase/sales order and invoice.
 
### Miscellaneous charges

1. Open Accounts payable – Charges setup – Charges codes.
2. Set up the miscellaneous charges code to include in the invoice amount, the statistical amount, or both. On the Charges codes page, on the Foreign trade tab, enable Intrastat invoice value to include the amount of the charge in the invoice value, and enable Intrastat statistical value to include the amount of the charge in the statistical value.

## **Document entry**
---

When you create a sales order, free text invoice, purchase order, vendor invoice, project invoice, or transfer order, some fields that are related to foreign trade have default values in the document header or on the line:
   - The default transaction code is taken from the corresponding field on the Foreign trade parameters page. 
   - The default commodity code, country/region of origin, state/province of origin and weight are taken from the item. 
You can change the default values and can also fill in other foreign trade-related information: the statistics procedure, transport method, and port.

Upon document entry, Intrastat data can be adjusted in Line details, on the Foreign trade tab. 

As part of localization solution, fields unit weight, Total weight and unit of measure are added to **product receipt line**. If unit wight information exists on the item level it is automatically transferred to document. It can also be manually removed or changed. If wight is changed, new amount is transferred to intrastat reporting line. If weight is removed, the action depends on setup in Foreign trade parameters > Check setup > Weight. If value is set to yes, blank walue is not allowed. In such case, system will throw error at the moment of posting product receipt. If value is set to No, empty value in wigts field is allowed. In such case weight will be transferred from item setup. 
 
Intrastat data can also be edited in the Intrastat journal before export. 

## **Generate Intrastat journal**
---

1. Open Tax – Declarations – Foreign trade – Intrastat.
2. Intrastat transactions are created using the button “Transfer”. Mark adequate documents that need to be transferred and confirm.
3. According to marked parameters, transactions are transferred to the Intrastat journal. 

A customer invoice, free text invoice, purchase invoice, project invoice, customer packing slip, vendor product receipt, or transfer order is transferred to the Intrastat journal only if the country/region type of the destination (on dispatches) or consignment (on arrivals) is EU.
 
More information about the selected transactions can be found on the tab General.

In cases when statistical value adjustment percent is set on Terms of delivery, **Statistical value adjustment amount** is populated. 
 
4. Review transferred data, including country/region of destination/dispatch, country of origin, weight, quantity, quantity in additional units, commodity, transaction code, invoice amounts, and statistical amounts. You can modify data if necessary as long as line status is Open. Line status (LOC) is a localization feature.
5. Click to “Validate” to execute validation of transactions in the Intrastat journal according to Check setup in Foreign trade parameters. 
6. Transactions that are not completed will be marked as not valid. Manually modify the necessary data.
 
### Intrastat reporting

1. Generate an Intrastat report by clicking on “Output” -> “Report”. 
2. Define Intrastat reporting parameters:
   - From date, To date: enter monthly reporting period
   - Generate file: enable if XML file for download should be generated 
     - File name: name of the XML file for download
   - Generate report: enable if Excel report (list of transactions included in reporting) should be generated (please note, that XML and excel file generation cannot be enabled at the same time since only excel file will be created in that case)
     - Report filename: name of Excel report file
   - Direction: select whether the report should be generated for Arrivals or Dispatches
“File format mapping” section of reporting parameters is localization (LOC):
   - Type of Intrastat declaration: 
     - Nil declaration: if no dispatches or arrivals of goods to/from EU member states (depending on which flow the company is obliged to report) is recorded in the reporting period, nil declaration is provided
     - Original declaration: report which is first reported for the selected period
   - Testing purposes: export file is generated for test purposes; it is not recorded in the history
3. After confirmation, you are asked to open or save the file you have enabled to generate.
4. Status of transactions included in the report changes to “Reported”. 
 
Localization allows lines in the Intrastat journal to be filtered by reporting status (LOC).
 
#### Reporting history

Another localization feature in the Intrastat journal is “Reporting history” (LOC).
 
1. Here, information about past reporting is available. It is possible to change the status of reported transactions back to “Open” using the button “Open reported transactions”. 
2. After confirming, the status of reported transactions in the Intrastat journal is changed back to “Open”.<br>
   For each of the entries in Reporting history, it is possible to view transactions included in the report.
3. Replacement declaration can be created in Intrastat reporting history. The reporting period is automatically set to the reporting period of the original report from which replacement is being made. Type of Intrastat declaration is automatically set to “Replacement declaration”. Enter a new file name and confirm.
4. The creation of a replacement declaration is recorded in reporting history. 
 
According to Slovenian standard deleting previously sent report is also enabled. The reporting period is automatically set to the reporting period of the report for which deletion is being made. Type of Intrastat declaration automatically sets to “Deletion of sent declaration”. Enter the new file name, confirm, and save.
 
The deletion of the sent declaration is recorded in reporting history. 
 
#### Intrastat archive

1. Intrastat archive (LOC) is another localization feature that allows you to review transactions that have been compressed by parameters, selected in Tax – Setup – Foreign trade – Compression of Intrastat.
2. Compress data in the Intrastat journal.
3. Dates are automatically populated. Localization allows you to add Active remark (LOC) and enable “Archive uncompressed data”. <br> 
   Note the compressed (summed) Intrastat lines. 
4. Check the Intrastat archive after compression. Choose an archive name.
5. Review transactions that have been compressed. 
6. Use “Delete archive” to delete lines and “Transfer” to return the transactions in the Intrastat journal to their original state (before compression).
 


