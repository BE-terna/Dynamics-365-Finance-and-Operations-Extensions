# KEP report

This topic provides country/region-specific information about the locally required KEP report, which is legally required in the retail industry by the Serbian authorities. It uses form prescribed by a rule book in which the entry, exit, and condition of goods in the warehouse need to be financially evidenced. Sources for the report are based on data from calculations, nivelations, invoices, delivery reports, and other documents.

This extended localization feature enables the generation and export of the Serbian legally required report for retail. It includes the KEP report, revelations, and retail calculation. The setup enables the selection of adequate price groups, which should be reported in the KEP report. Based on the adequate transactions querying, the KEP report can be created, finalized and printed. The report can be printed in Excel or Word formats.

The feature is part of the LOC_KEP extended localization packet.

## **Setup**
---

### Price group

It is necessary to indicate which price group will be used for inventory valuation in the KEP report. It is common that this is the same price group that is used in a retail store for which the KEP report is created.

1. Open Retail - Pricing and discounts - Price groups - All price groups.
2. For the appropriate price group, you need to put a checkmark in the KEP field.

### Retail store – price group

1. Selected price group should be linked to retail stores in AX on the following path Retail - Channels - Retail stores - All retail stores.
 
## **Generate report**
---

After setup is completed report can be generated. 

NOTE: It is necessary that there are valid prices existing for all the dates on which inventory transactions are posted, for the price group marked it will be used for KEP.

1. Open Retail - Channels - Retail KEP - KEP.
2. A new report is created by clicking the New button in the upper left corner. In the left part of the form, a new line will appear and in the right part of the form it is necessary to fill out the following:
   - Warehouse – select the one for which the KEP report should be created. By choosing a warehouse, the Store number, Year and Price Group will automatically fill in. These data should not be changed.
   - Date from and Date to – select the period (fiscal year) for which the report is created (e.g., 01/10/2017 to 30/09/2017). In case of generating the first report in the new system (after the transfer of the initial state), the first working date in the new system should be entered as the Date from and the last date of the fiscal year for which the report is created should be entered as the Date to the new date.
3. After completing the data on the header you need to click on the Create transactions button.
4. To date field will initially be populated with the last date entered on the header of the report but can be changed to any date that is within the date range defined at the header of the report. After clicking on the OK button, the report will be created.
 
Explanations for the fields in the KEP transactions part of the form are the following:
   - No. – this field is initially empty. It is filled by the Closing report function, which will be explained below.
   - Transaction date – this field shows the date of the transaction when the stock change occurred.
   - Transaction description – transaction details such as document type, transaction type, document number, and date are visible in this field. For purchase invoices, there are vendor details (name and address) visible.
   - Debit – this column shows the amounts:
     - Initial stock with the positive sign
     - Purchasing and inventory journal – adjustment, transfer, movement, bills of materials, with a positive sign
     - Price leveling with a positive sign (to increase the price) and a negative sign (to reduce the price)
   - Credit – this column shows the amounts:
     - Sales invoices with a positive sign
     - Customer return orders with a negative sign
     - Price differences between the price in the price list and price used on the sales invoice/customer return order, with a positive or negative sign, depending on the direction in which the price difference occurred.
     - Sales discount – with a negative sign in the case of the sale of goods and with a positive sign in the case of the return order.
   - Status – the status of the transaction shown in this field can be the following:
     - Initialized – if the report line is created without error
     - Error – If there are some transactions that do not go through the basic report control (e.g. missing price in the retail price list for the date on which the inventory transactions exist). 
     - Closed – The transaction gets this status after the Closing function is completed. As a result, the transaction line gets a unique transaction number. 
NOTE: In case the rows get the Error status, message with error details will appear. After corrections are completed, it is necessary to start the Delete open transactions option on the document header.
 
Only transactions that do not have an Ordinary number (not closed) will be removed from the report. After that, transactions can be generated again according to the procedure described above.
   - Reference – the source of the transaction in AX is displayed in this field
   - Type – transaction type in AX is displayed in this field
   - Number – this field contains information about the document number from which the transaction expired

### Retail KEP transaction specification

For each transaction shown in the report, there are transaction details available in the middle section of the form.
 
## **Report closing**
---

After all errors have been corrected, the report can be finalized and prepared for printing. The closing option closes the report (after report closing, any further changes are not allowed) and all lines get a unique line number. In addition, the closing function is also a condition for printing the KEP book.

NOTE: Before generating and closing report for a period, it is necessary to determine whether all inventory transactions have been finalized (whether all vendor invoices are posted, whether all the customer invoices are posted, whether all inventory journals are posted completely) in order to be sure that all transactions that occurred during reporting period are included in the KEP report. Once the report is created, closed and printed, any further changes in inventory can no longer be included in the KEP report.

1. For the start of the closing procedure click Close KEP transactions, on the report header.
2. A new form opens. Enter the date by which transactions will be closed. This date should be any day within the period of the KEP book (if it is created during the day, the proposal is to take the previous day as the report closing date).

## **Report printing**
---

1. The print option prints all the lines of the KEP book that are closed (have line number). Printing is started by clicking on the button Print KEP report.
2. Click on the OK button and the report will be generated.
3. The report can be saved in Excel or PDF format.
 
NOTE: Due to the number of the transaction included in the report, it is recommended to create a report for shorter time intervals, and to determine only one (or few) users for creating a report in order to avoid the situation of simultaneous generating of report transactions by multiple users at the same time.
