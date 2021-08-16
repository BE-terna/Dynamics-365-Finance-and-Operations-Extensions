# eSettlement

In Slovenia, it is legally required (IV. Chapter of the ZPreZP-1) from debtors to report their overdue liabilities to vendors, with a goal to settle multilateral sett-offs. Reporting of the liabilities is done electronically via ePobot application of AJPES (Agency of the Republic of Slovenia for Public Legal Records and Related Services). Slovenian eSettlement offers a fast, safe, efficient and affordable way of settling the mutual liabilities between the legal entities, business entities registered in the Business Register of Slovenia (PRS). This system allows for monthly multilateral set-offs of reported mutual liabilities between legal entities, which can then be settled in the process.

This localization feature (SI) allows users to set up, process and export the generated eSettlement (ePobot) files. Transactions to be included in eSettlement are prepared through vendor payment journal from where they can be exported in an adequate XML file, supported by the ePobot application. When results of the e-settlement are known the non-compensated transactions from vendor payment journal should be deleted, while customer entries with which vendors’’ transactions have been settled should be entered before posting the journal.

## **Setup**
---

This topic provides country/region-specific information about how to set up, create and process multilateral set-offs in the scope of the Slovenian localization.

### Export format configuration

1. Open Workspaces – Electronic reporting -> Reporting configurations.
2. Choose Exchange -> Load XML file on any configuration. Based on file content it will automatically upload to correct configuration.
3. Click “Browse” and choose ePobot (S).xml file attached below (before upload, check the latest version of this file with developer).
4. After the file has loaded, click OK to upload it to configuration.
5. Search for configuration “Payment model” and expand it to find ePobot (SI). Check for status “Completed” in tab Versions.
 
### Method of payment

1. Create a new payment method with Period “Invoice” and Payment type “Electronic payment”. Navigate to tab File formats and enable “Generic electronic reporting”. In the field, Export format configuration choose “ePobot (SI)”.
2. Navigate to Payment specification and create entries for mandatory and voluntary set-off. The export format is defined by payment specification parameters for each settlement type as shown below:
   - 1 – mandatory set-off
   - 2 – voluntary set-off of outstanding liabilities
   - 3 – voluntary set-off of due liabilities
 
### Mandatory set-off periods

1. Open Accounts payable – Payment setup – Mandatory set-off periods.
2. Insert periods from the Ajpes schedule in the form. 
 
### Fictive back account

1. Open Cash and bank management – Bank accounts – Bank accounts.
2. For the purposes of exporting entries for e-settlement create a fictive bank account “AJPES”. 
 
## **Generate eSettlement**
---

1. Open Accounts payable – Payments – Payment journal -> Payment proposal  Create payment proposal for mandatory set-off.
2. Automatic proposal of liabilities that have fallen due but have not been paid is enabled in the Vendor payment journal. It is necessary to define the mandatory set-off period in the proposal. “From date” and “To date” fields are automatically transferred upon choosing period. Note: dates populated are shifted one day back (if the period is defined 1.1.-31.1., dates populated are 31.12.-30.1.). “Total payment date” is also automatically transferred from the mandatory set-off period (defined as Settlement date). 
3. Define the smallest amount payable (250€). Additional filters can be entered in tab Records to include if needed. In case of enabling “Change method of payment” choose Method of payment created for eSettlement and Payment specification that defines settlement round (1-mandatory, 2-voluntary of outstanding liabilities, 3-voluntary of due liabilities). Upon creating the proposal, these data will accordingly change on transactions, included in the proposal. 
 
   Method of payment and Payment specification can also be subsequently changed using “Multiple change” functionality in the proposal.
 
4. Before transferring payments to the payment journal make sure to check if all transactions have Method of payment for e-settlement and adequate Payment specification (important for export format).
5. After confirming, transactions are transferred to payment journal lines.
6. ESettlement proposal is exported to file using standard functionality “Generate payments. Define payment method for e-settlement, file name, and bank account, created for settlement purposes.
7. After confirming parameters for payment generation, it is necessary to choose the Mandatory set-off period. 
8. The system displays Infolog about the file – define the location to save the XML to. 
 
When the results of e-settlement are known, delete the transactions that have not been compensated from the vendor payment journal. Enter customers’ entries in which vendors’ transactions were settled with and post the journal. 

Check [Test Scenario](eSettlement-Test-scenario.xlsx)