This topic provides country/region-specific information about the localized VAT features, developed with a purpose to comply with the local legislation and tax authorities of Slovenia, Croatia, Serbia, and Northern Macedonia. According to the adequate local legislation (e.g. ZDDV-1 in case of Slovenia), a taxable event occurs when goods/services are received/delivered or when goods are imported in case of goods from other EU countries, while multiple exceptions exist. 

As part of standard D365FO tax transactions are posted and reported according to transaction posting date, which is not aligned with the local legal requirements, by which the VAT reporting date can be different from the Transaction date. Therefore, additional VAT features were added.



## **Additional dates for VAT reporting purposes** ##
-----

All VAT reporting for Slovenia, Croatia, and Serbia needs to be performed according to VAT date and not Transaction date (which is how standard functionality for Tax reporting works). For VAT reporting purposes following dates are added to several documents: 

* VAT date
* VAT Payable date
* Document Receipt date (used for defaulting VAT date)
<br/><br/>

VAT date and VAT Payable date (when populated) are transferred to a VAT date field (additional localized field) on Tax transactions as a result of document posting. This date is then used for VAT calculation and reporting.

List of documents where additional VAT date fields are enabled:

1.	_Pending Vendor Invoice_:  VAT date, VAT Payable date, Document Receipt date
2.	_Invoice Journal_:   VAT date, VAT Payable date, Document Receipt date
3.	_Free Text Invoice_:  VAT date
4.	_Sales Invoice_:  VAT date
5.	_Project Invoice_:  VAT date
6.	_Intercompany Invoice_:  VAT date
7.	_General Journal_:  VAT date, VAT Payable date
8.	_Collection letter_:  fee with sales tax
9.	_Interest letter_:  interests with sales tax


Additional setup is available for VAT date and VAT Payable date calculation. VAT date validation is also added. If the VAT date is missing, posting such a document will result in an error.

[Detailed documentation](/Help/Core-Localization/VAT-features/Additional-dates-for-VAT-reporting-purposes)

<!-- [Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_VAT%20features.docx?d=w42e2c5023dca417b9b1c9c691af0e3bf&csf=1&e=91Mb4E) 
 -->

## **VAT Date change** ##
-----

VAT date can be manually changed on posted Sales tax transactions by using the function “Change VAT date”. VAT date is then changed on both - Tax transaction and Invoice journal. VAT date change for the period that is closed for posting is not possible and will result in an error.

[Detailed documentation](/Help/Core-Localization/VAT-features/VAT-date-change)


## **Reporting Tab on Tax transaction** ##
-----
As part of localization, an additional “Reporting” tab is added to Tax transactions. It displays information, such as Customer/Vendor, Address, Tax exempt number, Document, Document date, and Document receipt date. This information is used on VAT reports. 

[Detailed documentation](/Help/Core-Localization/VAT-features/Reporting-Tab-on-Tax-transaction)

## **Informative VAT calculation** ##
-----

An option to calculate informative VAT is added. It is used in cases when VAT value is zero, but informative VAT value needs to be calculated and later added to invoice printout or other documents.

[Detailed documentation](/Help/Core-Localization/VAT-features/Informative-VAT-calculation)


## **Taxable persons list (Slovenia, Croatia)** ##
-----

A taxable person list is added in the scope of Slovenian and Croatian localization. Slovenian list stores information, such as tax registration number, company registration number, taxable person type, name, address, and special handling (e.g. 76.a ZDDV-1) checkmark, while Croatian list stores the following information: OIB, identification number, type, and name. This list can later be used when adding VAT ID to Vendor or Customer.

[Detailed documentation](/Help/Core-Localization/VAT-features/Taxable-persons-list-\(SI,-HR\))

## **DDV-O (Obračun DDV) (Slovenia)** ##
-----

is a Slovenian sales tax return report. Every taxable person identified for VAT purposes in Slovenia is obliged to submit a VAT return to the Slovenian tax authority. DDV-O should include all the required VAT return settings, with the information needed to calculate the sales tax and applicable deduction to be made including the total value of transactions relating to such tax and deductions. Additionally, the value of any exempt transactions should be included. Taxable entities have to submit the tax return to the tax authority by the last business day of the month, which follows the expiry of the tax period, while Slovenian laws also allow multiple exceptions. VAT tax return (DDV-O) needs to be submitted electronically via the eDavki portal of the Slovenian tax authority (FURS).

DDV-O is prepared based on Tax transactions and according to the VAT date. DDV-O can also be previewed (HTML) and exported to the XML file.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Slovenia/DDV-O-\(Obračun-DDV\))

## **List of incoming (PR) and outgoing (IR) invoices (Slovenia)** ##
-----

A taxable person filing a VAT return (DDV-O) for the first time must attach a list of the incoming (PR) and outgoing (IR) invoices that served as the basis for preparing the VAT return. These two lists must also be available to be sent to the Slovenian tax authority if required directly by the authority and therefore need to be available to be extracted from the ERP.

IR and PR reports are prepared based on Tax transactions and according to the VAT date. Both reports can be exported to various formats (e.g. Word, PDF or Excel). A special export in the format, required by the Slovenian tax authority (FURS) is also available for IR and PR. All reports are prepared using Slovenian sales tax reporting codes.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Slovenia/List-of-incoming-\(PR\)-and-outgoing-\(IR\)-invoices)

## **PDO (Poročilo o dobavah) (Slovenia)** ##
----- 

is a report required by the Slovenian tax authority regarding the supply of goods and services for which the recipient (and not the provider of goods or services) is a VAT payer according to the 76.a Article of the Slovenian sales tax law (ZDDV-1), where specific services for which this is applicable is also defined – e.g. construction work-related services. Slovenian taxable persons, which perform these activities, must notice the Slovenian tax authority about their activities within 30 days of their occurrence. PDO report needs to be submitted electronically until the last day of the following month after deliveries of such goods or services occurred. Reporting is done through the eDavki portal of the Slovenian tax authority (FURS).

PDO reports sums transactions based on tax exempt numbers. The report consists of A (information about the deliveries for the current period) and B part (information about the corrections for previous periods). PDO report can be previewed (HTML) and exported as an XML file, using the adequate model for reporting to the Slovenian tax authority (FURS) portal eDavki.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Slovenia/PDO-Report)

## **VIES (recapitulative report) (Slovenia)** ##
-----

 is a report in which taxable entities, identified for VAT purposes in Slovenia are obliged to report the supplies of goods and services that are delivered to entities, identified for VAT in the other Member States of the European Union during the reporting period (the calendar month). VIES report needs to be submitted to the Slovenian tax authority (FURS) till the 20th in the following month after the occurrence of the reporting events.

VIES (recapitulative report) processes the transactions, considered as intra-community trade transactions based on the delivery address of the documents (Sales invoices, Free text invoices, Project invoices, Vendor invoices) if country code from that address is specified for the EU trade. Selected transactions are then transferred to EU sales list journal if they meet the predetermined criterion. Additional localized information are available to be added to these transactions (e.g. Customs procedure 42 or 63). In contrary to the standard, localized feature reports transactions based on the VAT (and not transaction) date. VIES report can be exported either to Excel file (standard) or to an adequate XML file format (localization), accepted by the Slovenian tax authority (FURS) portal eDavki and previewed prior to export. After generating an EU Sales list report for a specific period, it is also possible to mark the records that are included in the report by setting the Reporting status value to Reported and Closed when for example tax authorities have accepted the report.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Slovenia/VIES-\(recapitulative-report\))


## **PDV report (Croatia)** ##
-----
is a Croatian sales tax return report. Every taxable person identified for VAT purposes is obliged to submit a VAT return to the Croatian tax authority. The report consists of sums of sales tax from both payable and receivable transactions, according to different sales tax rates. Taxable entities must submit the PDV report electronically via the ePorezna portal of the Croatian tax authority.

PDV report is prepared based on Tax transactions and according to the VAT date. PDV report can be exported as an XML file in the format, accepted by the Croatian tax authorities.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Croatia/PDV-report)

## **IRA and URA reports (Croatia)** ##
-----
IRA and URA consist of the receivable and payable tax transactions and provide data about the applicable VAT rates for each of the sales tax transactions. IRA provides such information for the receivable, while URA for payable transactions. These two lists have to be available to be extracted from D365, in case the adequate Croatian tax authority requires so.

IRA and URA reports are prepared based on Tax transactions and according to the VAT date. IRA and URA reports can be exported to various formats (e.g. Word, PDF or Excel).

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Croatia/IRA-and-URA-reports)

## **PPO form (Croatia)** ##
-----
PPO form is legally required form in Croatia, according to the Croatian sales tax Law, Article 75., Section 1., Point 3. - Official gazette 73/13, 99/13, 148/13, 153/13, 143/14, 115/16). PPO consists of the overview of non-taxable deliveries - e.g. transferred tax liability to the recipient made in Croatia (domestic transfer of tax liability). It has to be submitted on a 3-month basis to Croatian tax authorities, with the values in Croatian national currency (HRK). It consists of transactions regarding the goods and services, determined by the local legislation, for which their recipient is a sales taxpayer. The form is submitted electronically via ePorezna portal of the Croatian tax authority.

PPO report is prepared based on the tax transactions. In order for tax transactions to be included in the PPO report, the adequate setup must exist on each of the sales tax codes. The report can be created, overviewed and exported to various formats, including the XML format, accepted by the ePorezna portal of the Croatian tax authority.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Croatia/PPO-report)

## **PDV-S and ZP (Zbirna Prijava) report - VIES (Croatia)** ##
-----
PDV-S and ZP (Zbirna Prijava) report is a recapitulative report in which taxable entities, identified for VAT purposes in Croatia are obliged to report the supplies of goods or services to (ZN report) and from (PDV-S) legal entities from other EU member states, which are identified for VAT in Member States of the European Union during the reporting period. Along with entities, registered in the VAT system, buyers who are not eligible (do not charge) for VAT – but have had an acquisition of goods of value, higher than the legally required threshold, also have to submit both forms. Both – ZN and PDV-S reports have to be submitted to the Croatian tax authority.

PDV-S and ZP (Zbirna Prijava) report process the intra-community transactions based on the delivery address of the documents (Sales invoices, Free text invoices, Project invoices, Vendor invoices) if country code from that address is specified for the EU trade. Selected transactions are transferred to the EU sales list journal if they meet the predetermined criterion. Additional localized information is available to be added to these transactions (e.g. Customs procedure 42 or 63). In contrary to the standard, the localized feature allows reporting transactions based on the VAT (and not transaction) date. Two separate reports – PDV-S and ZP report can then be generated. Both reports can be printed or exported to an adequate XML file format, required by the Croatian tax authority. All transactions can be also manually marked as included, reported or closed.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Croatia/PDV-S-and-ZP-report)

This topic provides country/region-specific information about how to set up and create the sales tax declaration for legal entities in Serbia only. In order to comply with the Serbian legislation, adequate reports regarding the sales tax need are for Serbia in terms of this localization feature and are further described below.

## **KIF and KUF report (Serbia)** ##
-----
KIF and KUF consist of the receivable and payable tax transactions and provide data about the applicable VAT rates for each of the sales tax transactions. KIF provides such information for the receivable, while KUF for payable transactions. 

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Serbia/KIF-and-KUF-report)


## **PPPDV report (Serbia)** ##
-----
PPPDV is a Serbian sales tax return report. Every taxable person identified for VAT purposes in Serbia is obliged to submit a VAT return to the Serbia tax authority. 

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Serbia/PPPDV-report)


## **POPDV report (Serbia)** ##
-----
VAT taxpayer is obliged to, pursuant to Article 46, paragraph 1 of the Law on VAT, and in order to properly calculate and pay VAT, keeps records in a way that allows you to control the calculation and payment of VAT in each tax period. In that records are required to provide records of transactions, activities, respectively other business changes, in particular data relating to the circulation of goods and the service performed by the VAT taxpayer, that is, which was provided to him, by invoices or other documents which serve as invoices in accordance with the Law, respectively documents confirming a business change (e.g., insurance contract, lease agreement concluded with a natural person, copyright contract, contract on the part, etc.), as well as other information relevant to the correct calculation of VAT.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Serbia/POPDV-report)
