# Send Sales Documents to fiscalization

Fiscalization is fiscal law designed to avoid retailer fraud in Slovenia and Croatia. Fiscal law about cash registers has been introduced in countries to control the grey economy by enforcing all mandatory transaction reporting to the authorities. According to fiscal law, an appropriate fiscal receipt has to be printed and given to the customer.

The feature allows the generation of the number sequence on sales documents (Sales Order, Free text invoice, Project Invoice, Prepayment invoice, FTI corrections, Credit notes, Collection letters, Interest notes, and Advance invoices) according to the Fiscal law. The fiscal number can be seen in the field “Invoice” on Customer transactions. After posting, the transaction is displayed in Fiscalization documents. QR code is also generated as result. 

The feature is part of the LOC_FISCALIZATION extended localization package.

## **Setup**
---

### **Legal entity setup**
1. Open **Organization administration > Organizations > Legal entities**
2. Navigate to tab **General**:
3. Go to **Time zone**: Select your current time zone. This time zone will be used as time when fiscal document is sent to tax authority and also as time when fiscal document is created (for Croatia and Slovenia select appropriate GMT+1 time zone).



### **General ledger parameters**

1. Open **General ledger > Ledger setup > General ledger parameters**.
2. Navigate to BE-terna localization, tab Fiscalization:
   - **Fiscalization**: enable functionality to use fiscalization of outbound documents
   - **Separator**: define delimiter that identifies the distinction between different sets of fiscal numbers; allowed characters are \ / * - _|. : ; 
   - **Fiscalization document**: enable documents that need to use fiscalization numbering (note: standard numbering is replaced with fiscal numbering; voucher numbering remains standard!)
   - **Fiscalization job**: Fiscalization job setup is used used to setup Batch processing and recurrence to send fiscalization documents to the fiscalization service. Set recurrence for batch processing. _Note: The same fiscalization process will be triggered with print of fiscalization documents to ensure that fiscalization process is triggered before printing_
 
### **Fiscalization – locations**

1. Open **General ledger > Fiscalization > Locations**.
2. An integral part of the fiscal number is the company’s location. Create a new entry and identify the location.
3. **Enable Fiscalization** for those **locations** for which fiscalization number sequence should be used.
4. **Enable Tax authority fiscalization** for those locations eligible for full fiscalization (document needs to receive JIR/EOR and ZKI/ZOI).

 
### **Fiscalization – terminals**

1. Open **General ledger > Fiscalization > Terminals**.
2. **Create a new terminal** and select an adequate location.
3. **Add workers** which will create invoices for defined terminal and location

### **Fiscalization methods of payment**
1.	Open **General ledger > Fiscalization > Fiscalization methods of payment** > Create new fiscalization method of payment and enter adequate Code
2.	Open **Accounts receivable > Payments setup > Methods of payment** > Navigate to Method of payment, tab Fiscalization > Choose needed Method of payment defined for fiscalization

 
### **Fiscalization number sequence setup**

1. Open **General ledger > Fiscalization > Fiscalization number sequence setup**.
2. The third part of the fiscal number is invoice number which is determined by fiscalization number sequence. 
3. Create a new entry, specify effectively and expiration dates, and define Location and Terminal. Create a number sequence code to select in the Fiscalization sequence field. Be careful to select Continuous numbering.
 
### **Worker’s tax identification number**

The worker who creates outbound documents should have a valid tax identification number defined.
 
If the tax identification number is not defined on Worker, the error is thrown upon document posting.

In order to create valid tax identification number for worker, following setup is needed: 
1.	Go to **Organization administration > Global address book > Registration types > Registration types** and generate appropriate **Registration type**.
2.	Go to **Organization administration > Global address book > Registration types > Registration categories** and **link** Created Registration type with Registration category Tax identification number (AD) 
3.	Add Tax identification number for worker
4.	Go to **System administration > Users > Users** and **link user with Person** (worker with defined tax identification number)

 
## **Fiscalization documents**
---

1. Open **General ledger > Inquiries and reports > Fiscalization > Fiscalization documents**.
2. Overview of all transactions with fiscal number contains all the data that are sent to tax authority. 
3. Using the button “Open document” in section Fiscalization, source document data is displayed for the selected transactions. 

### **Sales invoice**

Posting sales invoice standardly does not generate infolog with information about the posted invoice.<br>
The fiscal number can be seen in the field “Invoice” on Customer transaction.<br>
After posting, the transaction is displayed in Fiscalization documents. 
 
### **Free text invoice**

Upon FTI posting, infolog with information about the fiscal number is generated.<br> 
Field “Invoice” on Customer transactions is populated with the generated fiscal numbers.
 
#### Correct FTI

1. Correcting FTI generates a new fiscal number.
2. To correct a free text invoice that has already been posted, select the posted free text invoice. On the Invoice page, in section Cancel, select “Correct invoice”. Define a reason code, add comments, and select the date for the new corrected invoice. Modify the corrected invoice, and post it.
3. After posting, fiscal numbers are generated for canceling and corrected invoices.
4. Field “Invoice” on Customer transactions is populated with the fiscal number of posted invoices.
5. Fiscal numbers of canceled and corrected invoices can be seen in the list of all fiscalization documents.
 
### **Credit note**

The fiscal number is generated after posting a credit note.<br>
It can be seen in field “Invoice” on Customer transaction.<br>
The posted document can be seen in the list of all fiscalization documents.
 
### **Advance invoice**

1. Posting advance invoice generates a fiscal number that is recorded in the field “Invoice”.
2. Reversing advance invoices also generates a fiscal number.
3. The posted document can be seen in the list of all fiscalization documents.
 
### **Project invoice**

1. Posting invoice proposal generates a fiscal number that is recorded in the field “Invoice”.
2. Check all project invoices to find a fiscal number in the field “Invoice”.
3. A posted document can be seen in the list of all fiscalization documents.
 
### **Collection letter**

1. Collection letters are generated with fiscal numbers. 
2. Right after creation, they can be seen in Fiscalization documents form.
3. Posting collection letters generate a fiscal number. 
4. Field “Invoice” on Customer transactions is populated with a fiscal number.
 
### **Interest note**
Created interest notes have fiscal numbers.
 
Transactions can be seen in the Fiscalization documents list.
 
The posted transaction is generated with a fiscal number.
 
Customer transaction has a fiscal number in field Invoice.

### **Use generated QR code in printouts**

Generated QR code can be used in printouts. Here is the [example of implementation](/How-to/Implement-QR-code-image-in-FTI) of QR code on Free text invoice. Principle is the same for all the other documents. 
 
## **Test cases**
---
                           
Check **[Test Scenaio](Fiscalization-Test-Scenario.zip)** for fiscalization.