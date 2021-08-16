# KRD report

KRD stands for the SKV part of the report on short-term receivables and liabilities from doing business with non-residents according to the financial instruments specified by the Bank of Slovenia. Legal entities obliged by the report are informed about the obligation by the Bank of Slovenian based on the importance of their business activities with the non-residents. If obliged to report, legal entities must submit the report until the 20th day in the current month for the past month, electronically in an adequate XML format.

This localization feature enables the preparation and export of the report to the adequate localized XML file format. The report can be prepared for transactions within the specified period. Transactions are summed up by the ISO numeric code of each country and currency.

## **Setup** 
---

### **Electronic reporting** 

1. Open **Workspaces > Electronic reporting > Reporting configurations.**
2. Choose **Exchange > Load XML file** on any configuration. Based on file content it will automatically upload to correct configuration. 
3. You can upload **[files](KRD.zip)**. Before upload, check the latest version of these files with the developer. 
4. Click “**Browse**” and choose the attached files (be sure to upload ERKRDKIPOModel.xml first because the format file is dependent on it). After the file has loaded, click OK to upload it to configuration. 
5. Search for configuration “KRD/KIPO” and expand it to find the KRD report. Check for status “Completed” in tab Versions. 

### **General ledger parameters** 

1. Open **General ledger > Ledger setup > General ledger parameters**.
2. Navigate to BE-terna localization, tab Electronic reporting, and select KRD report in field “KRD electronic reporting format”. 

### **Country/region setup for KRD report** 

1. Open **Country/region code** at the partner’s address. 
2. ISO and numeric ISO country code in **Organization administration > Global address book > Addresses > Address setup**. 

### **Financial instruments for KRD report** 


1. Open **General ledger > Inquiries and reports > Slovenia > KRD report > Settings > Financial instruments**.
2. Enter the list of financial instruments. The financial instrument "T" will be linked to the KRD groups in order to generate the report in the (former) SKV range, while other financial instruments serve to manually add report lines. 

### **Groups** 

1. Open **General ledger > Inquiries and reports > Slovenia > KRD report > Settings > Groups**.
2. Navigate to Action Pane, tab General, section Settings, and button Groups to set up groups.  
3. Enter the group name and a description of the capital relationship between the debtor and the creditor. In the FI Code field, add the financial instrument "T", which allows the automatic transfer of relevant transactions to the report. As mentioned earlier, do not link other financial instruments with groups because they serve for manual creation of report lines.<br>
_**Note: Group name must include Group label (A,B) and number that represents Capital connection between debtors and creditors (one of the following numbers: 11,12,21,22,3). For instance A11, B11, A12 etc). This is important for generating XML, since this value is used for populating field AffiliationType in XML file. If Group name is A11, field AffiliationType will be populated with value 11. If group name is 11, field AffiliationType will be populated with value 1, which is not correct.**_ 
4. Enter Customer and Vendor criteria through buttons “Customer/Vendor criteria”.  

### **Sector codes** 

1. Open **General ledger > Inquiries and reports > Slovenia > KRD report > Settings > Sector codes**.
2. Navigate to Action Pane, tab General, section Settings, and button Sector codes to define sectors. This table allows you to enter the sector code and its description, and below, allocate the code to the individual customer, vendor. 
3. It is possible to allocate sector code directly on the Customer/Vendor card. 

## **Generate KRD report** 
---

1. Create a new reporting period. Select either date from the calendar lookup or enter “Period start” in form month.year. “Period end” value is automatically populated. Enter the date of preparing the report in the field “Date”.  
Some of the “Reporter” tab fields are automatically populated after creation of the period: Reporter (legal entity’s name); in the "Report prepared by" section, the details of the worker who created the report and his contact details are filled in (if they exist on the worker's card). 
2. The report is generated through the button “Read transactions”. In the "Transactions" section, all transactions within the period are recorded, while in the "Sums, data for printout" section they are summed up according to the ISO numeric code of the country and currency. Through the connection with the group, "FI code" is set to "T" for all totals. The final state of the previous report (column "Sum") is considered as the Opening balance of the report for the next month. 

   - It is possible to manually correct and update values in the “Sums” area fields. If you correct the data only in the report, but not at the source, the manually edited values will be reset each time the report is generated. 
   - It is also possible to manually add report lines (manually adding data for other financial instruments that are not included in automatic generation). The manually added line is automatically marked upon creation by a checkmark in the Field Manual, and will not be deleted when you re-generate the report. 

If fields "Principal other" or "Interest other" are populated, field “Note” must offer an explanation for the entered amount.  

Validation if the Note exists for the value in fields Other is executed upon export to XML. 

## **Export KRD report to XML** 
---

Navigate to “Export to XML file” to export the report to XML form for Bank of Slovenia reporting. 

