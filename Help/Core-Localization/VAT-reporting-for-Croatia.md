This topic provides country/region-specific information about how to set up and create the sales tax declaration for legal entities in Croatia only. In order to comply with the Croatian legislation, adequate reports regarding the sales tax need are for Croatia in terms of this localization feature and are further described below.

## **PDV report** ##
-----
is a Croatian sales tax return report. Every taxable person identified for VAT purposes is obliged to submit a VAT return to the Croatian tax authority. Report consists of sums of sales tax from both payable and receivable transactions, according to different sales tax rates. Taxable entities must submit PDV report electronically via the ePorezna portal of the Croatian tax authority.

PDV report is prepared based on Tax transactions  and according to VAT date. PDV report can be exported as  XML file in the format, accepted by the Croatian tax authorities.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Croatia/PDV-report)

## **IRA and URA reports** ##
-----
IRA and URA consist of the receivable and payable tax transactions and provide data about the applicable VAT rates for each of the sales tax transactions. IRA provides such information for the receivable, while URA for payable transactions. These two lists have to be available to be extracted from D365, in case the adequate Croatian tax authority requires so.

IRA and URA reports are prepared based on Tax transactions and according to VAT date. IRA and URA reports can be exported to various format (e.g. Word, PDF or Excel).

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Croatia/IRA-and-URA-reports)

## **PPO form** ##
-----
PPO form is legally required form in Croatia, according to the Croatian sales tax Law, Article 75., Section 1., Point 3. - Official gazette 73/13, 99/13, 148/13, 153/13, 143/14, 115/16). PPO consists of the overview of non-taxable deliveries - e.g. transferred tax liability to the recipient made in Croatia (domestic transfer of tax liability). It has to be submitted on a 3-month basis to Croatian tax authorities, with the values in Croatian national currency (HRK). It consists of transactions regarding the goods and services, determined by the local legislation, for which their recipient is a sales tax payer. Form is submitted electronically via ePorezna portal of the Croatian tax authority.

PPO report is prepared based on the tax transactions. In order for tax transaction to be included in PPO report, adequate setup must exist on each of the sales tax codes. Report can be created, overviewed and exported to various formats, including the XML format, accepted by ePorezna portal of the Croatian tax authority.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Croatia/PPO-report)

## **PDV-S and ZP (Zbirna Prijava) report - VIES** ##
-----
PDV-S and ZP (Zbirna Prijava) report is a recapitulative report in which taxable entities, identified for VAT purposes in Croatia are obliged to report the supplies of goods or services to (ZN report) and from (PDV-S) legal entities from other EU member states, which are identified for VAT in Member States of the European Union during the reporting period. Along with entities, registered in the VAT system, buyers who are not eligible (do not charge) for VAT – but have had an acquisition of goods of value, higher then the legally required threshold, also have to submit both forms. Both – ZN and PDV-S reports have to be submitted to the Croatian tax authority.

PDV-S and ZP (Zbirna Prijava) report processes the intra-community transactions based on the delivery address of the documents (Sales invoices, Free text invoices, Project invoices, Vendor invoices) if country code from that address is specified for the EU trade. Selected transactions are transferred to EU sales list journal, if they meet the predetermined criterion. Additional localized information are available to be added to these transactions (e.g. Customs procedure 42 or 63). In contrary to the standard, localized feature allows reporting transactions based on the VAT (and not transaction) date. Two separate reports – PDV-S and ZP report can then be generated. Both reports can be printed or exported to an adequate XML file format, required by the Croatian tax authority. All transactions can be also manually marked as included, reported or closed.

[Detailed documentation](/Help/Core-Localization/VAT-reporting-for-Croatia/PDV-S-and-ZP-report)

