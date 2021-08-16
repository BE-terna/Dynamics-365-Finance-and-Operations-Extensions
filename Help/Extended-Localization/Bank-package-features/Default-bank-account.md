# Default bank account

This topic includes information about the preferred bank account of the legal entity from which inflows and outflows are preferred to be paid/received.

In terms of inflows (customers), the feature is added so that information about the preferred bank account of the legal entity regarding the expected payments from customers can be defined on the customer group level. When creating a new customer, by entering the Customer group, the default bank account from the customer group is transferred to the newly created customer. When creating sales documents (Sales quotation, Sales order, Sales invoice, and FTI), this company bank account is transferred from the customer to the sales documents. The bank account to which the company wants to receive payments in connection with the document should be specified. This bank account is transferred to the following documents if they exist (e.g. from sales order to invoice), but it can also be manually changed on each sales document. Bank account information can be used  for document printout.

In terms of outflows - each vendor bank account can be mapped to a specific company bank account from which payment should later be proposed. Preferred bank account from which outflows for each specific vendor should be paid can be set on each of the vendor’s bank accounts. Information about the specified bank account can be used during payment proposal preparation.

## **Default bank accounts for Customer payments**


The feature is added so that the information about the preferred bank account can be defined on the document level and later used when printing the document. This way customers are directed to pay to the bank account, preferred by the issuing company. 

## **Setup**
---

### Customer groups

1. Open Accounts receivable - Setup - Customer groups.
2. A new field »Company bank account« is added to the Customer groups table. It is possible to select a default bank account for each customer group, to which a company wants to receive inflows.


### Customers

When creating a new customer, the company bank account is transferred from the specified customer group. If no company bank account is specified on the selected customer group, it can also be manually selected on each customer.

### Vendors

Feature purpose: Each vendor bank account can be mapped to the specific company bank account from which payment should later be proposed. Information is later used during payment proposal preparation. 
For each of the vendor's bank accounts, it is possible to specify a default company bank account, from which the liabilities towards the vendor are expected to be paid.
 
## **Use with Sales documents**
---

1. When creating sales documents (Sales quotation, Sales order, Sales invoice, and FTI), the company bank account is transferred from the customer to the document (field »Company bank account«), where it can still be manually changed. This field identifies the bank account to which the company wants to receive the future inflows connected with the document.
2. After the customer invoice is posted, the Company bank account is transferred to the created open customer transaction.

### **Free Text Invoice (FTI)**

The company bank account is transferred from the customer to FTI.
 
When FTI is posted, the company bank account is transferred to field »Company« on the created open customer transaction.
 
### **Sales quotation**

The company bank account is transferred from customer to the created Sales quotation:
 
### **Sales order**

1. If a Sales order is created from the sales quotation, the company bank account is transferred from the sales quotation (and not customer).
2. If a Sales order is created without the preexisting Sales quotation, the Company bank account is transferred from the customer.

### **Sales invoice**

1. When creating a Sales invoice from a Sales Order, the Company bank account is transferred from sales order (not from customer account) to the invoice.
2. When an invoice is posted, the company bank account from the invoice is transferred to the newly created customer invoice journal and open customer transaction.
 
## **Use with Sales documents**
---
 
### **Vendor invoice**

1. Company bank account from which the liabilities towards vendor are desired to be paid defaults from the vendor to the Vendor invoice based on the selected vendor's bank account specified on the invoice. Both vendor's and company bank account on the invoice can still be manually changed.
2. After the invoice is posted, information about the company bank account from the invoice is transferred to the created open vendor transaction.
 
### **Vendor invoice journal**

Functionality is not supported for invoices generated using the Vendor invoice journal. The company bank account, in that case, will not be transferred to the created open vendor transaction once the vendor invoice journal is posted.

## **Generate Vendor payment journal**
---

Company bank accounts are transferred from open vendor transactions to vendor payment journal if **payment attribute »Third-party bank« is checked** on the payment method, used when generating vendor payment lines via the Payment proposal function.
 
### Payment proposal

1. Open Accounts payable - Payments - Payment journal.
2. When creating a new payment proposal, the company bank account from open customer transactions is transferred to the generated payment journal line as an Offset bank account (via the selected payment method).
An alternate bank account field displays the vendor's bank account to which the payments should be made. The bank account field displays the company bank account (set on the alternate bank account) from which the company will pay the liabilities to the vendor.
 
NOTE: functionality only works if the Payment proposal function is used to create payment journal lines. If payment journal lines are generated manually or with the »Settle transactions« function, the offset bank account will not be changed and has to be adjusted manually.
