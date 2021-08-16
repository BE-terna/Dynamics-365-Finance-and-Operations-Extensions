## **Travel requisition enhancements**
---

This feature enhances standard D365O travel requisition functionality by adding the following functionalities:

### **Fields on Travel requisition header**
Additional fields are added to travel requisition header: 
   - From date and time 
   - To date and time 
   - By order of 
   - Transport type (Company-owned vehicle, Personal vehicle) 
   - Registration number 
   - By order of 
   - Registration number 

### **Date Validation**

The estimated expense date of each travel requisition line must be within a period, entered on the travel requisition header (set with “From” and “To date and time” fields). This feature can be enabled/disabled with parameter in **Expense management parameters > BE-terna (expense) > Ignore Form-To date validation**. If set to No, dates from travel requisition lines will be validated against dates in the document header.   

### **Submit travel requisition without lines into Workflow**
Parameter for submission of Travel requisition is added to **Expense management parameters > BE-terna (expense) > Enable submit to WF w/o lines**. If set to yes, travel requisition can be submitted to  Workflow without lines.


### **Travel requisition report print**
   - Two new travel requisition printouts are added with this feature:
     - Localized print (including details from each expense line) 
     - Localized print without lines (less detailed). 

Note: Localized printouts become available only if option is checked in **Expense management parameters > BE-terna (expense) > Use localized reports**.

### **Generate Expense report from Travel requisition**

It is possible to generate Expense report directly form approved Travel requisition. Function "Create expense report is added to Travel requisition list page and Travel requisition page. If approval status is different from Approved or Reconciliation status is set to Closed, function is disabled. 

### **Link to related Expense report**
Link to related Expense report is added to Travel requisitions list page (**Expense reports > My expenses > Travel requisition >** Column Expense report number)

### **Close requisition when mapping to expense report**
It is possible to automatically force closing of travel requisition after it is mapped to Expense report, even though there is an unreconciled amount left on the travel requisition. With parameter in **Expense management parameters > BE-terna (expense) > Close requisition when mapping to expense report** set to Yes, travel requisition will be closed when it is mapped with expense report. If mapping is removed, status will be reversed back to Open (if reconciled amount exists). If parameter is set to No, status of the travel requisition will be left Open, but only in cases when reconciled amount exists. If reconciled amount equals 0, status will be set to Closed (standard functionality). 