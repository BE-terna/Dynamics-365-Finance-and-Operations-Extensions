# Create PDV-S and ZP report 

PDV-S and ZP (Zbirna Prijava) report is a recapitulative report in which taxable entities, identified for VAT purposes in Croatia are obliged to report the supplies of goods or services to (ZN report) and from (PDV-S) legal entities from other EU member states, which are identified for VAT in the Member States of the European Union during the reporting period. Along with entities, registered in the VAT system, buyers who are not eligible (do not charge) for VAT – but have had an acquisition of goods of value, higher than the legally required threshold, also have to submit both forms. Both – ZN and PDV-S reports have to be submitted to the Croatian tax authority.

## Setup

### Country/Region Parameters (standard) 

1. Open **Tax > Setup > Sales tax > Country/Region parameters**.
2. VAT number prefix and Country/Region need to be mapped In order to recognize candidates for reporting. Additionally, validation of tax exempt number can be enabled. This is a standard setup.  

Only transactions with vendors/customers that have country/region type set to the EU will be included in the report. This is why Country/Region properties need to be setup.  

3. Open **Tax > Setup > Foreign trade > Foreign trade parameters > Foreign trade properties**.

### Item Sales tax group setup 

1. Open **Tax > Indirect taxes > Sales tax > Item sales tax groups**.
2. Reporting type which defines if particular item sales tax group represents service, item or investment needs to be defined on Item Sales tax group. 

### Sales tax code setup 

1. Open **Tax > Indirect taxes > Sales tax > Sales tax codes**.
2. Only Sales tax codes that have “EU sales list - Excluded” marked as No, will be included in the report.  

### Electronic reporting configuration 

1. Open **Workspaces > Electronic reporting > Reporting configurations**.
2. Choose **Exchange > Load XML** file on any configuration. Based on file content it will automatically upload to correct configuration. 

As a result, ZP and PDV-S report (HR) and EU Sales list (HR) must appear on the list.  

### Foreign trade parameters 

1. Open **Tax > Setup > Foreign trade > Foreign trade parameters > EU sales list**.
2. In parameters **“Transfer purchases”** must be marked as Yes in order to include purchase transactions in EU sales list reports. If not, only sales transactions will be included.  

To be able to generate both (PDV-S and ZP) reports, an Electronic reporting setup needs to be enabled. Report configurations from the previous paragraph need to be setup.  

## Generate EU sales list reports 

When creating documents that are potential candidates for EU sales list reporting, the system will set the List code (for EU Sales list) based on selected customer/vendor country/region setup. 

If the customer/vendor EU, the system will automatically set List code as EU trade in the header. If the customer/vendor is domestic or from third countries, the system will automatically set the document header as Not included. 

Code can be manually changed to one of the following: 
   - EU Sales: used for sales and purchase of both goods and services (PDV-s and ZP reports). 
   - Triangular/Prod on toll: used only for sales of goods in the EU (ZP report). With third-party purchase transactions, the EU trade option is used since there is no additional column for third-party transactions in the PDV report.   
   - Customs procedures 42 and 63: valid only for sales of goods in EU which are imported to Croatia from Third countries and where we apply for exemption from VAT payment (ZP report). 
   - Not included – if this field is chosen, the transaction will be excluded from the report.  

1. Open **Tax > Declarations > Foreign trade > EU Sales list**.
2. To generate a report, the new header needs to be created.  
3. After that transactions need to be transferred to the report. 
4. After transactions are transferred, both reports can be exported to XML or printed. 

All transactions can be manually marked as included, reported or closed.  

 