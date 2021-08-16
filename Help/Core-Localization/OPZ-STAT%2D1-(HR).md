# OPZ STAT-1 report

In order to comply with the Croatian legislation (Pravilnik o obvezujućim mišljenjima, ispravku prijave, statističkim izvješćima i poreznoj nagodbi (NN 78/15). OPZ STAT 1 is a mandatory statistical report, required by the Croatian tax authority. OPZ STAT 1 includes the overdue, but uncollected claims which legal entity has towards its customers. The report must be submitted to the Croatian tax authority in the prescribed XML file format on a quarterly basis. It is important to note that taxpayers must report only the overdue but uncollected receivables, which are not older than 6 years on the day of the reporting. The taxpayer is therefore not obliged to hand over OPZ STAT 1 report if there are no overdue but uncollected receivables in one of the above-mentioned periods. Transactions need to be reported in Croatian local currency (HRK) no matter the original currency of the document. Realized FX differences are also taken into consideration within the report.

This localization feature allows the preparation generation of the OPZ STAT 1 report. The report includes outgoing invoices from goods and services, but not also advances and credit notes. The report can be exported only as an XML file format, required by the Croatian tax authorities.

## Legal notes

OPZ STAT 1 is a mandatory statistical report for the Croatian tax authority and it must include overdue but uncollected claims towards customers.  
The report is submitted to the Tax authority in XML format. 

The form must be delivered on a quarterly basis as follows:
1. Until May 20th for all overdue but uncollected receivables with the balance as of March 31st of the current financial year which has not been settled until April 30th of the current financial year
2. Until August 20th for all overdue but uncollected receivables with the balance as of June 30th of the current financial year which has not been settled until July 31st of the current financial year
3. Until November 20th for all overdue but uncollected receivables with the balance as of September 30th of the current financial year which has not been settled until October 31st of the current financial year
4. Until February 20th for all overdue but uncollected receivables with the balance as of December 31st of the previous financial year which has not been settled until January 31st of the current financial year

It is important to note that taxpayers must report only the overdue but uncollected receivables which are not older than 6 years on the day of the report.

The taxpayer is not obliged to hand over OPZ STAT 1 report if there are no overdue but uncollected receivables in one of the above-mentioned periods.
 
Following documents are included:
   - Outgoing invoices for goods and services
   - Interests

Following documents are not included: 
   - Advances
   - Credit notes

Transactions need to be reported in Croatian kuna (HRK) no matter the original currency of the document. Realized FX differences are also taken into consideration within the report.
 
## **Setup**
---

### Company setup (standard fields)

1. Open Organization administration/Organizations/Legal entities.
2. For reporting purposes following setup needs to be done (no localized fields needed): 
   - Name of the taxpayer
   - OIB number
   - Address of the taxpayer
   - E-mail address

### Customer setup

1. Open Accounts receivable/Customers/All customers.
2. Following customer data is needed for reporting purposes: 
   - Name 
   - OIB (LOC field)/Tax exempt number
   - Sales tax group

### Sales tax group setup (standard)

1. Open Tax/Indirect taxes/Sales tax/Sales tax groups.
2. If the value of EU trade is Yes, transactions with this Sales tax group will be printed in group 2 of the report. If the value is set to No, transactions will be printed in group 3. Valid only for customers with tax exempt numbers entered. In the case of customers with OIB, this setup is irrelevant.

### Responsible person setup (standard fields)

1. Open Human resources/Workers/Employees.
2. For reporting purposes following Employee data from the Contact information detail is needed (no localized fields added):
   - First and last name
   - Phone number
   - FAX number
   - E-mail address

### Electronic reporting setup

1. Open General ledger/Ledger setup/General ledger parameters/BE-terna localization/Electronic reporting.
2. If report configuration is changed following steps need to be done: 
   - Delete OPZ STAT-1 configuration
   - Reimport OPZ STAT-1 configuration
 
We need to wait for a message from the system, which says that import is complete. After that new configuration is available in General ledger parameters/Electronic reporting. 

### OPZ STAT-1 Opening balance setup

1. Open Accounts receivable/Customers/All customers/Transactions.
2. Two localized fields are added to customer transactions for OPZ STAT-1 reporting purposes:
   - Original Invoice amount
   - Original VAT amount

They need to be populated only in case of importing Customer open balances, that was partially closed before import. This means that open amount is different from the original amount. Amounts need to be entered in HRK (even if the original was different).
 
For reporting purposes, field Document date (standard field) also needs to be populated with the original Invoice date. 
For all other transactions, generated in the system (not part of opening balances import) original amounts are used for reporting and described fields do not need to be populated.

## **Generate OPZ STAT-1 report**
---

1. Open Accounts receivable/Inquiries and reports/Croatia/Generate OPZ-STAT-1.
2. The report can be generated only in XML format (no print is available). To generate the report following fields need to be populated: 
   - Filename: Name under which report will be saved. 
   - Authority: Tax authority for reporting. Value is chosen from the list. 
   - From date/To date: Reporting period
   - Not closed until: last settlement date to be considered. If the settlement date is later than the date entered, the document will be considered as open. 
   - Reported by: Name of the responsible person. Value is chosen from the list. 
   - Separate persons: 
      - Yes: Customer transactions of the customers without OIB or Tax exempt code will be generated in section 3 of the report.
      - No: Customer transactions of the customers without OIB or Tax exempt code will not be included in the report.
3. The following message appears after a click on the OK button. 
4. Save the document. The document is generated in XML and XLS formats. 
 
Additional explanation of some values: 
   - Transaction marking (column 2 in section II) is based on Customer tax data setup (Tax exempt number, OIB and Sales tax group): 
     - Mark 1– domestic customers with an OIB number
     - Mark 2 – foreign customers with Tax exempt number and Sales tax code with EU Sales set on Yes 
     - Mark 3 – customers with Tax exempt number and Sales tax code with EU Sales set on No
   - Number of overdue days calculation example: Due date is 15.4. and reporting balances are per 31.07. The calculation period is 16.4.-31.07., the calculated number of days is 107. 

## **Control report (standard report)**
---

1. Open Accounts receivable/Inquiries and reports/Open transactions report.
2. Control report can be generated to compare open customer transactions and OPZ STAT-1 report. The standard report is used. 
 

 
