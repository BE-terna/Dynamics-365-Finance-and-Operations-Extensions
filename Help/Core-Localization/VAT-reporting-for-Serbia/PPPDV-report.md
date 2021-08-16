# Create PPPDV Form (VAT Statement report)

PPPDV is a Serbian sales tax return report. Every taxable person identified for VAT purposes in Serbia is obliged to submit a VAT return to the Serbia tax authority. 

Sales tax calculation according to VAT date is part of the BE-terna localization pack, while standard sales tax calculation is performed according to the posting date. 
 
## PPPDV Form

1. Standard Sales tax calculation form is used and it can be found in Tax/Declarations/Sales tax/Report sales tax for the settlement period.
2. Results of “Report sales tax for settlement period” are:
   - Report preview of PPPDV form (Poreska prijava) which can be printed/saved in PDF, Excel format.
   - Appropriate XML file which can be submitted by tax representative and uploaded on the Tax Authority portal (http://www.poreskauprava.gov.rs/en.html).
3. Field explanation:
   - Settlement period: Period for which calculation is performed. Usual setup of Salax tax settlement period in Serbian legal entities:
      - One settlement period code which is related to sales tax transactions which should be reported to VAT authority (MONTH)
      - One settlement period code which is related to sales tax transactions which should be reported to VAT authority (NE_U_PDV)
   - From date: first day of the VAT period for which calculation should be performed 
   - Transaction date (visible only on Settle and post sales tax form): Posting date for settlement posting 
   - Sales tax payment version:
      - Original – is used when no settlement posting for the chosen period exists.
      - The latest corrections – is used when a settlement for an existing period is already posted. Only Tax Transactions that were created after the last settlement posting are included.

## PPPDV report format configuration

1. Open Setup - Export format configuration. 
2. OpenWorkspaces – Electronic reporting -> Reporting configurations
3. Choose Exchange -> Load XML file on any configuration. Based on **[file content](PPPDV.xml)** it will automatically upload to correct configuration. Before upload, check the latest version of these files with the developer. 
4. Click “Browse” and choose the attached files (be sure to upload the data model first (PPPDV.xml file) because the format is dependent on it). After the file has loaded, click OK to upload it to configuration.
5. The next step is uploading of **[PPPDVXmlFormat.xml](PPPDVXmlFormat.xml)** file. 
6. Search for configuration “PPPDV” and expand it to find PPPDVXmlFormat. Check for status “Completed” in tab Versions.
 
##	General ledger parameters

1. Open General ledger – Ledger setup – General ledger parameters – BE-terna localization.
2. To define export format navigate to BE-terna localization and section Electronic reporting. Select “PPPDVXmlFormat” in the field “PPPDV electronic reporting format".
3. Set additional settings for export XML file for PPPDV for on General ledger – Ledger setup – General ledger parameters – Sales tax such as Responsible person and contact e-mail address.
4. The tax identification number for Serbian companies (PIB) can be entered on legal entity detail (tab Registration numbers). PIB should be displayed on the PPPDV report and exported in the PPPDV.xml file.
 
