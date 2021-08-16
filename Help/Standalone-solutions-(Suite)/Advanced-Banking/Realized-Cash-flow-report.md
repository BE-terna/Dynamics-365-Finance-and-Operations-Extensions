# **Realized cash flow**	

The cash flow functionality by direct method enables the collection of all posted banking transactions in a joint overview. Each bank transaction is enriched with information about the customer, vendor, and the GL account to which the bank inflow or outflow is posted. In cases when one bank transaction settles multiple customer or vendor transactions, such inflow or outflow is split into several lines in the report.  In addition to the above, it is also possible to include data from unposted bank statements, if the user selects this option during the preparation.

In case of subsequent transfers between customers/vendors and GL accounts that are not posted through a bank statement, these are not reflected in the realized cash flow report. If we want to include such transfers in the cash flow overview, it is necessary to post them through transitional bank account (with transitional GL account). The same applies to compensations between customers and vendors. Such transactions will be included in cash flow report only if they will be posted through transitional bank account. 


## **Setup**
---
### **Cash flow groups**

Cash flow transactions can be sorted into optional Cash fow groups, which can later be used for reporting purposes. 
1.	Go to **Cash and bank management > Setup > Cash flow groups**
2.	Generate new cash flow groups into which cash flow transactions will be sorted
3.	Define associated offset **Debit and/or credit Main accounts**. Multiple Main accounts can be selected. Each Main account can appear twice, once as debit and once as credit main account. Main accounts listed under credit, will show outflow transactions. Main accounts listed under debit, will show inflow transactions.



## **Generate realized cash flow report**
---
1.	Go to Cash and bank management > Realized cash flow > Realized cash flow report
2.	Enter report parameters 

|Field|Description  |
|--|--|
|Calculate as of | Two options are available <br> **Todays date**: only today's transactions are included<br> **Date range**: Report can include transactions for selected date range|
|From date| Begining date of the report|
|To date | End date of the report|
|Include untransferred bank statements| **Yes**: transactions from untransferred Bank statements will also be included<br> **No**: Only transactions from transferred bank statements will be included.  |


As result, report is generated. 

## **Supported scenarios**
---
1. Payment closing one customer transaction
2. Payment closing one Vendor transaction
3. Payment closing multiple Customer transactions
4. Payment closing multiple Vendor transactions
5. Payment with different currency than  customer/vendor transaction
6. Compensated amounts between customer and vendor (only when posted through bank account)




