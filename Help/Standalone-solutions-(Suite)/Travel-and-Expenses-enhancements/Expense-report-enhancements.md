## **Expense report enhancements**
---

This feature enhances standard D365O Expense report functionality by adding the following functionalities.

### **Fields on Expense report header**

Additional fields are added to the Expense report header.

Open Expense report header:
   - From date and time 
   - To date and time 
   - By order of 
   - Transport type (Company-owned vehicle, Personal vehicle) 
   - Registration number 
   - By order of 
   - Registration number 

### **Date Validation**
   
Validation is executed upon expense report dates: “Transaction date” entered for each expense line has to be within an entered period in expense report header localization fields From and To date and time.

Validation is optional and can be enabled/disabled in **Expense management > Setup > General > Expense management parameters > BE-terna (expense) > Ignore From-To date validation**. 


|**Value**  | **Behavior** |
|--|--|
|Yes |Validation is not performed. There is no warning and the document can be submited to Workflow even if transaction is out of date range defined on the header of the document.  |
|No  |Validation is performed. Warning appears if transaction is out of date range defined on the header of the document and the document cannot be submited to Workflow. |

###**Disable Pre-authorisation of manually added lines**
With standard functionality manually added lines need to be pre-authorised (Pre-authorised node on Travel expense line is set to Yes). With this extension pre-authorisation of such lines can be avoided. 

1. Go to **Expense management > Setup > Expense management parameters > BE-terna (expense)**
2. Find setup "**Default Pre-Authorised field to No**". If set to Yes, value of Pre-authorised node on Travel expense line will be automatically set to No and pre-authorisation won't be demanded. If set to No, value of Pre-authorised node on Travel expense line will be automatically set to Yes and pre-authorisation will be demanded.

### **Expense report Localized print**


1. Open **Expense management > Setup > General > Expense management parameters > BE-terna (expense > Use localized reports**.
2. when set to Yes, localized reports are available under Print section of Travel requisitions and Expense reports.  
1. Choose Print > **Localized print** on an expense report to generate the report. 

_Note: if localized reports are not enabled in expense management parameters, the option “Localized print” is not available._ 
 

### **Map to travel requisition**

This feature also enables Expense reports to be mapped with Travel requisitions. Upon mapping information from mapped Travel requisition header and lines are transferred to Expense report. The feature works only if **“Copy data from requisition” option is checked in Expense management parameters**, while only travel requisitions in Reconciliation status “Open” and Approval status “Approved” can be mapped to an Expense report.


### **Automatic Cash advance return line**

If mapping Travel requisition with an applied cash advance (in status “Paid), upon transferring information from Travel requisition to mapped Expense report, additional expense line with expense type “Cash advance return” will be automatically created on an Expense report. The transaction amount and date for this newly generated line are transferred from cash advance (mapped to Travel requisition).

To enable this function:  
1. Go to **Expense management parameters > BE-terna (expense) > Apply cas advance return**.
2. Set field Apply cash advance return to Yes.



### **Set up posting dates for group Expense report transactions posting**

This feature allows defining date for posting expenses in case of transaction grouping. Posting date setup is applicable only when a standard grouping of transactions based on the offset account (specified on payment method) is enabled. Using this functionality, expenses can be posted based on: (1) The earliest transaction date within the group; (2) The latest transaction date within the group; (3) Last date in a month of the transaction line with the latest date.

#### Posting date of group transactions

1. Open **Expense management > Setup > General > Expense management parameters > BE-terna (expense) > Per diem transaction date on last day**.
2. The feature allows defining the date to post expenses on in case of enabled transaction grouping. Posting date setup is applicable only when a standard grouping of transactions based on the offset account specified in the payment method is enabled. 
 
Possible options are:


|**Value**  |**Description**  |
|--|--|
|First of group  |Transaction is posted on a date that is the earliest of all transaction dates.  |
|Last of group  | Transaction is posted on a date that is the latest of all transaction dates. |
|Last in month |Transaction is posted on the last date of the month of the line with the latest date. |

 
Check **[Test Scenario](Travel-and-Expenses-Test-Scenario.zip)**.