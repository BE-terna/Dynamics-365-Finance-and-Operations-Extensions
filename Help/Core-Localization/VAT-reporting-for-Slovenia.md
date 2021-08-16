This topic provides country/region-specific information about how to set up and create the sales tax declaration for legal entities in Slovenia only. In order to comply with the Slovenian legislation, adequate reports regarding the sales tax need are for Slovenia in terms of this localization feature and are further described below.

Sales tax reporting codes for Slovenia are added as part of the Slovenian report Layout and used for reports listed below.

## **DDV-O (Obračun DDV)** ##
-----

is a Slovenian sales tax return report. Every taxable person identified for VAT purposes in Slovenia is obliged to submit a VAT return to the Slovenian tax authority. The DDV-O should include all the required VAT return settings, with the information needed to calculate the sales tax and applicable deduction to be made including the total value of transactions relating to such tax and deductions. Additionally, the value of any exempt transactions should be included. Taxable entities have to submit the tax return to the tax authority by the last business day of the month, which follows the expiry of the tax period, while Slovenian laws also allow multiple exceptions. VAT tax return (DDV-O) needs to be submitted electronically via the eDavki portal of the Slovenian tax authority (FURS).

The DDV-O report is prepared based on Tax transactions and according to the VAT date. The DDV-O report can also be previewed (HTML) and exported to the XML file.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Slovenia/DDV-O-\(Obračun-DDV\))


## **List of incoming (PR) and outgoing (IR) invoices** ##
-----
A taxable person filing a VAT return (DDV-O) for the first time must attach a list of the incoming (PR) and outgoing (IR) invoices that served as the basis for preparing the VAT return. These two lists must also be available to be sent to the Slovenian tax authority if required directly by the authority and therefore need to be available to be extracted from the ERP.

IR and PR reports are prepared based on Tax transactions and according to the VAT date. Both reports can be exported to various formats (e.g. Word, PDF or Excel). A special export in the format, required by the Slovenian tax authority (FURS) is also available for IR and PR. All reports are prepared using Slovenian sales tax reporting codes.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Slovenia/List-of-incoming-\(PR\)-and-outgoing-\(IR\)-invoices)

## **PDO (Poročilo o dobavah)** ##
----- 

is a report required by the Slovenian tax authority regarding the supply of goods and services for which the recipient (and not the provider of goods or services) is a VAT payer according to the 76.a Article of the Slovenian sales tax law (ZDDV-1), where specific services for which this is applicable is also defined – e.g. construction work-related services. Slovenian taxable persons, which perform these activities, must notice the Slovenian tax authority about their activities within 30 days of their occurrence. PDO report needs to be submitted electronically until the last day of the following month after deliveries of such goods or services occurred. Reporting is done through the eDavki portal of the Slovenian tax authority (FURS).

PDO reports sums transactions based on tax exempt numbers. The report consists of A (information about the deliveries for the current period) and B part (information about the corrections for previous periods). PDO report can be previewed (HTML) and exported as an XML file, using the adequate model for reporting to the Slovenian tax authority (FURS) portal eDavki.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Slovenia/PDO-Report)

## **VIES (recapitulative report)** ##
-----

 is a report in which taxable entities, identified for VAT purposes in Slovenia are obliged to report the supplies of goods and services that are delivered to entities, identified for VAT in the other Member States of the European Union during the reporting period (the calendar month). VIES report needs to be submitted to the Slovenian tax authority (FURS) till the 20th in the following month after the occurrence of the reporting events.

VIES (recapitulative report) processes the transactions, considered as intra-community trade transactions based on the delivery address of the documents (Sales invoices, Free text invoices, Project invoices, Vendor invoices) if country code from that address is specified for the EU trade. Selected transactions are then transferred to the EU sales list journal if they meet the predetermined criterion. Additional localized information is available to be added to these transactions (e.g. Customs procedure 42 or 63). In contrary to the standard, localized feature reports transactions based on the VAT (and not transaction) date. VIES report can be exported either to an Excel file (standard) or to an adequate XML file format (localization), accepted by the Slovenian tax authority (FURS) portal eDavki and previewed prior to export. After generating an EU Sales list report for a specific period, it is also possible to mark the records that are included in the report by setting the Reporting status value to Reported and Closed when for example tax authorities have accepted the report.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Slovenia/VIES-\(recapitulative-report\))

<!-- 
[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_SI%20VAT%20Reports%20SI%20docx.docx?d=wb9549c42a47d410a9d9723a851a6df44&csf=1&e=bFzEGW) -->
	
