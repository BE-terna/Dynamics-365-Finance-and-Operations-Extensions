# PDO report

PDO report is a report required by the Slovenian tax authority regarding the supply of goods and services for which the recipient (and not the provider of goods or services) is a VAT payer according to the 76.a Article of the Slovenian sales tax law (ZDDV-1), where specific services for which this is applicable is also defined – e.g. construction work related services. Slovenian taxable persons, which perform these activities, must notice the Slovenian tax authority about their activities within 30 days of their occurrence. PDO report needs to be submitted electronically until the last day of the following month after deliveries of such goods or services occurred. Reporting is done through eDavki portal of the Slovenian tax authority (FURS).

PDO reports sums transactions based on tax exempt numbers. The report consists of A (information about the deliveries for the current period) and B part (information about the corrections for previous periods). PDO report can be previewed (HTML) and exported as an XML file, using the adequate model for reporting to the Slovenian tax authority (FURS) portal eDavki.

## **Setup** 
--- 

### Export format configuration 

1. Open **Workspaces > Electronic reporting > Reporting configurations**.
2. Choose **Exchange > Load XML** file on any configuration. Based on file content it will automatically upload to correct configuration. 
3. **[Files for upload](PDO-Report.zip)** are available. Before upload, check the latest version of these files with the developer.  
4. Click **“Browse”** and choose the attached files (be sure to upload the model first (PDO.xml file) because the format is dependent on it). After the file has loaded, click OK to upload it to configuration. 
5. Search for **configuration** “PDO” and expand it to find PDO format. Check for status “Completed” in tab Versions. 

### General ledger parameters

1. Open **General ledger > Ledger setup > General ledger parameters**.
2. To **define export format** navigate to BE-terna localization and section Electronic reporting. Select “PDOXmlFormat” in the field “PDO electronic reporting format". 

### Sales tax code 

1. Open **Tax > Indirect taxes > Sales tax > Sales tax codes**.
2. Sales, liable under article 76a of ZDDV-1, need to be monthly reported in the PD-O report. Define which sales are reported on sales tax code by enabling field “Include in PDO”.  

## **Generate PDO report** 
---

1. Open **Tax > Declarations > Slovenia > VAT > PDO report**.
2. Using the button **“New”** new reporting period is created where it is necessary to choose reporting Month and define Year. 
3. Click the button **“Prepare transactions for PD-O report”** to transfer transactions to tab Current period transactions. Transactions are summed by Tax exempt number. 
4. Check tab **Transactions** for detailed information about summed transactions. Click on the voucher number to open the invoice journal. 
5. Navigate to Action grid and click **“Preview”**. The report is generated according to section A and section B transactions.
6. Data can be exported to XML using the button **“Export to XML”**.  

Check **[Test Scenario](PDO-Report.zip)** for PDO report.