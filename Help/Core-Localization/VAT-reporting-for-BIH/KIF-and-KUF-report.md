KIF and KUF consist of the receivable and payable tax transactions and provide data about the applicable VAT rates for each of the sales tax transactions. KIF provides such information for the receivable, while KUF for payable transactions.


##**Setup**
----

The main prerequisite: VAT Book reports are available in legal entities with BIH country/region code.

###KUF/KIF format
1. Go to **Tax > Setup > Parameters > General ledger parameters > tab BE-terna localization > Electronic reporting**
2. Select KIF and KUF report electronic reporting format (KIF report csv/KUF report csv)

###Sales tax authorities setup

1. Go to **Tax > Indirect taxes > Sales tax > Sales tax authorities > Report layout**. 
2. Choose Bosnian report Layout.

###Sales tax reporting codes
1. Go to **Tax > Setup > Sales tax > Sales tax reporting codes**.<br>
The generation of reports is based on [BIH reporting codes.xlsx](/.attachments/BIH%20reporting%20codes-5b92fc74-998a-44f6-8b00-f8f4920cb862.xlsx). Reporting code carries information about which field the transaction will be recorded in. Each country has its own reporting codes. Reporting codes can also be imported using Excel add-in.

###Sales tax codes reporting setup
1. Go to **Tax > Indirect taxes > Sales tax > Sales tax codes**.
2. Set up reporting codes from Bosnian report layout, defind on Tax authorities setup. VAT reports are generated according to the setup of sales tax reporting codes.


##**KIF report**
----
1. To generate KIF report for the first time for settlement period go to **Tax > Declarations > Bosnia and Herzegovina > VAT > Generate KIF report lines** and to update lines for already generated report go to **Tax > Declarations > Bosnia and Herzegovina > VAT > VAT book reports > Generate tab > Generate KIF report**
2. Enter reporting parameters such as Sales tax settlement period and VAT date or/and Posting dates and File line count (number of lines per file with size restriction of 5 MB).
3. After confirmation, a report is generated.
4. **Export** of lines in CSV file by using **Tax > Declarations > Bosnia and Herzegovina > VAT > VAT book reports > Export tab > ER export**
5. After export, the report can be **closed for changes** using **Tax > Declarations > Bosnia and Herzegovina > VAT > VAT book reports > Actions tab > Close** option
6. If changes are needed for the closed report, it can be **reopened** by using **Tax > Declarations > Bosnia and Herzegovina > VAT > VAT book reports > Actions tab > Open** option
7.	**Deleting** of report header and lines can be done only for open reports in **Tax > Declarations > Bosnia and Herzegovina > VAT > VAT book reports > Actions tab > Delete** option




##**KUF report**
----
1. To generate KUF report for the first time for settlement period, go to  **Tax > Declarations > Bosnia and Herzegovina > VAT > Generate KUF report lines** and to update lines for already generated report go to **Tax > Declarations > Bosnia and Herzegovina > VAT > VAT book reports > Generate tab > Generate KUF report lines**.
2.	Enter **reporting parameters** such as Sales tax settlement period and VAT dates or/and Posting dates and File line count (number of lines per file with size restriction of 5 MB).
3.	After confirmation, a report is generated.
4.	**Export** of lines in CSV file by using **Tax > Declarations > Bosnia and Herzegovina > VAT > VAT book reports > Export tab > ER export**
5.	After export, the report can be **closed for changes** and new lines generating by using **Tax > Declarations > Bosnia and Herzegovina > VAT > VAT book reports > Actions tab > Close** option
6.	If changes are needed for the closed report, it can be **reopened** by using **Tax > Declarations > Bosnia and Herzegovina > VAT > VAT book reports > Actions tab > Open** option
7.	**Deleting** of report header and lines can be done only for open reports in **Tax > Declarations > Bosnia and Herzegovina > VAT > VAT book reports > Actions tab > Delete** option


