# Advance invoices

Local tax authorities require VAT eligible companies that receive/give prepayments and will not deliver/receive products or services within the same tax period to report VAT from the received/given prepayment transactions in the same period as the prepayment has been given/received. In order to comply with local legislation, the purpose of this functionality is to enable posting the VAT from the received/given prepayments as soon as payments are posted.

This localized functionality allows for the sales or purchases advance invoice generation, processing and posting based on the posted received/given prepayments. Posting advance invoice post only the calculated VAT amount from the prepayment transactions to both - general ledger and VAT entry. When the final (original) invoice is posted, VAT from with the invoice settled advance invoice is automatically reversed and VAT of the final (original) invoice is posted. If only a partial amount of prepayment is applied, a proportional share of the Advance invoice will be reversed. Advance invoices can be either settled with sales or purchase documents or manually. VAT reversal occurs with the settlement.

# Received prepayment invoices

## **Setup**
---

### Vendor posting profiles

1. Open **Accounts payable > Setup > Vendor posting profiles**.
2. Setup a specific vendor posting profile for posting prepayments (please note, the content of the setup is country-related). Selecting the main account in the “Sales tax prepayments” field is mandatory if the option “Sales tax on prepayment in payment journal” in Accounts payable parameters are marked. Otherwise, the payment of prepayment cannot be posted in the payment journal. 
 
### Advance invoice journal

1. Open **Accounts payable > Payment setup > Prepayment journal names**.
2. Create a new entry, enter the name, and select journal type “Prepayment to vendors”. Define voucher series for posting advance invoices, and select Amounts in the journal include sales tax (amounts, including VAT, are entered on the advance invoice).

### Accounts payable parameters

1. Open **Accounts payable > Setup > Accounts payable parameter**s.
2. BE-terna localization: Navigate to the BE-terna localization section and enable prepayments by selecting “Yes” in the Use prepayments field. Select advance invoice journal name for reversal transaction in the field “Reversal journal name”. If advance invoices functionality is used as shown in the test case “Purchase order and prepayment invoice” then reversal of advance invoice uses the voucher set up on this journal. 
3. Ledger and sales tax: Navigate to Ledger and sales tax section, tab Payment, and select Posting profile for payment journal with prepayment. When the payment journal line is marked as prepayment, posting profile changes to the selected one. Mark “Yes” for sales tax on prepayment in payment journal included in the amount. In this case, the posting profile should have the main account for “Sales tax prepayments” (see Chapter 1.1). 
4. On the tab Prepayment invoice, select the Posting profile with which prepayment invoices will be posted. This setup will be used only in cases when posting definitions are not in use. Otherways setup from posting definitions is used for posting prepayment invoices.  
 
### Procurement category for prepayments

1. Open **Procurement and sourcing > Procurement categories**.
2. If prepayments will be recorded in connection with purchase orders and prepayment invoices, create a new procurement category.
 
#### Posting setup for procurement category

1. Set up the main account for posting liability for payment of prepayment.
 
### Ledger posting groups

1. Open **Tax > Setup > Sales tax > Ledger posting groups**.
2. If sales tax from prepayment should be posted on the separate main accounts, create a new Ledger posting group with a sales tax receivable account and settlement account. 
3. Select this ledger posting group in the localization field Ledger posting group for tax in prepayments. 
4. If no separate ledger posting group is specified, sales tax from prepayments will be posted with the sales tax receivable main account from the used ledger posting group.

### Sales tax code

1. Open **Tax > Indirect taxes > Sales tax > Sales tax codes**.
2. Some countries might wish to record separate sales tax codes for advance invoices (e.g. Serbia). In this case, create a separate sales tax code.


 
## **Generate Prepayment invoice**
---

1. Open **Accounts payable > Payments > Prepayment invoice.**
2. Create **New** journal and Click on **Lines** to enter the journal.
3. Navigate to **Functions > create prepayment proposal**.   
4. Enter **“From date”** and **“To date”** to filter out payment transactions marked as prepayment. Optionally, enter the **Posting date** and **VAT date** that Prepayment invoices will be generated with. Confirm the date parameters.<br>
_Note: in case of prepayment invoice, the date for the filter is the posting date of liability (posting date of prepayment invoice) and not the payment date of the prepayment invoice._
6. **Prepayment invoice header** is generated in the upper section of the journal. If the prepayment was generated as part of the purchase order the invoice line is generated automatically. If there is no purchase order or the payment of prepayment was not linked to one, the line is not generated. Infolog appears: “Prepayment is not completely allocated to orders.” In this case, manually add the line: 
   - If there is no purchase order, add a line with Item type “Text” and insert necessary data (quantity, amount, and sales tax group are populated automatically, enter item sales tax group). 
   - If there is a purchase order that has not been linked, select item type “item”, select purchase order and order line – quantity, amount, and sales tax data will transfer automatically. <br>

7. Upon saving the line, the Voucher amount/Line amount and Voucher VAT/Line VAT fields are calculated. For countries that use separate sales tax codes for the advance invoice (e.g. Serbia), it is necessary to change the item sales tax group after the line generation. **Sales tax** for individual prepayment invoice line can be checked before posting by navigating to **Inquiries > Sales tax**.
8. **Enter** Document receipt date, Document date, VAT date, and advance invoice number.
10. **Post** Prepayment journal. Posting the journal posts only VAT. 


##**View Prepayment invoice information**
---
To see the list of posted Prepayment invoices and their reversals based on generated final Invoices: 
1. Go to **Accounts Payable > Invoices > Prepayment invoice**
2. **List** of all generated prepayment invoices will open
3. To see **Voucher** select Prepayment invoice and go to Tab Prepayment invoice > Voucher
4. To see **Posted sales tax** select Prepayment invoice and go to Tab Prepayment invoice > Posted sales tax
5. To **reverse** Prepayment invoice (only in cases when Prepayment invoice needs to be reversed manually and it won't be settled with final Invoice) select Prepayment invoice and go to Tab Prepayment invoice > Reverse.
6. To **Print** Prepayment invoice select Prepayment invoice and go to Tab Prepayment invoice > **Print journal** or Use **print management** Print journal is used when you just want to preview and print Prepayment invoice. In cases, when you need some additional rules eg. sent to emali, print to file, use separate print layout for separate customers etc. it is recommended to use print management option. 


##**Prepayment invoice and Final invoice**
---
When Final invoice is linked to prepayment, Prepayment invoice is automatically reversed. 

1.  If the final invoice is linked to the purchase order that was settled against prepayment, reversal happens upon posting the invoice.
14. If there was no purchase order, reversal happens upon manually settling the posted invoice and payment of prepayment. 
    - Navigate to “Settle transactions” on the Vendor account.
    - Mark the transaction of prepayment and final invoice and select “Post”. The message about reversal appears.

 
## **Test cases**
---

### Purchase order and prepayment invoice
 
Steps:
1. Purchase order: Create a purchase order.
2. Prepayment: Define prepayment value on the purchase order.
3. Prepayment invoice: Record and post prepayment invoice.
4. Pay prepayment invoice: Transfer transaction of prepayment invoice to payment journal and post with general posting profile.
5. Advance invoice: Create an advance invoice (the line is automatically generated because of the connection of prepayment to the purchase order) and post the VAT amount.
6. Final invoice: Generate a final invoice.
7. Apply prepayment: Apply prepayment invoice. Upon posting the final invoice, advance invoice (and with it the posted VAT amount) is reversed.

Note: if posting definitions are active, the functionality of the prepayment invoice is standardly not available. Localization enables the usage of prepayment invoice even when posting definitions are active. 

Check [Test Cases](Advance-Invoice-Test-scenario.zip).

### Reverse generated Prepayment invoice
Prepayment invoice, generated based on issued prepayment, can be also reversed. With Reverse function, new Prepayment invoice journal with negative amount is created, but it needs to be posted manually. After that prepayment is again available for issue of new Prepayment invoice.

To create Prepayment invoice reversal: 
1. Go to **Accounts payable > Invoices > Prepayment invoice** 
1. Choose Prepayment invoice that needs to be reversed 
1. Go to tab **Prepayment invoice > Reverse**
1. Enter parameters and click **OK**. Prepayment journal is generated.
1. Go to **Accounts payable > Payments > Prepayment invoice**
1. Go to journal that was generated in step 4 and click **Post**. Prepayment invoice is reversed and prepayment available for new Advanced invoice. 

### Settle prepayment against the purchase order
 
Steps:

1. Payment of prepayment: Create a payment journal with a new payment. Mark the payment as a prepayment – posting profile changes to the prepayment posting profile. Post the prepayment.
2. Settle prepayment against purchase order: Settle the prepayment against the purchase order – on the Action Pane, use Settle transactions and mark prepayment transaction.
3. Advance invoice: Create advance invoice – line is automatically generated because of the connection of prepayment to the purchase order. Posting the advance invoice posts only VAT amount.
4. Final invoice: Create a final invoice with a link to purchase order. Upon posting, the advance invoice is reversed.

Check [Test Cases](Advance-Invoice-Test-scenario.zip).

### Manually settle prepayment and final invoice
 
Steps:

1. Payment of prepayment: Create a payment of prepayment – mark the payment as a prepayment to post it with posting profile for prepayment.
2. Advance invoice: Create an advance invoice – manually add the line. Posting the advance invoice posts only VAT amount.
3. Final invoice: Create and post the final invoice.
4. Manually settle open transactions: Settle transaction of prepayment payment against the invoice. Upon posting, the advance invoice is reversed.

Check [Test Cases](Advance-Invoice-Test-scenario.zip).

### Reverse VAT charge (article 76.a ZDDV-1)

The process can be any from the above. The only difference is that VAT posted with the advance invoice (and later reversed by posting the final invoice) is both – sales tax receivable and sales tax payable.

Check [Test Cases](Advance-Invoice-Test-scenario.zip).
 
# Issued prepayment invoices

## **Setup**
---

### Customer posting profiles

1. Open **Accounts receivable > Setup > Customer posting profiles**.
2. To use the prepayment functionality, you need to set up a specific customer posting profile. Selecting the main account in the “Sales tax prepayments” field is mandatory if the option “Sales tax on prepayment in payment journal” in Accounts receivable parameters are marked. Otherwise, the received payment of prepayment cannot be posted.
 
### Prepayment invoice journal

1. Open **Accounts receivable > Payment setup > Prepayment journal names**.
2. Create a new entry, enter a name, and select journal type “Customer’s prepayment”. Define voucher series for posting advance invoices, and select Amounts in the journal include sales tax (amounts, including VAT, are entered on the advance invoice).
 
### Accounts receivable parameters

1. Open **Accounts receivable > Setup > Accounts receivable parameters**.
2. BE-terna localization: Navigate to BE-terna localization and enable prepayments functionality in the field “Use prepayments”. 
3. Ledger and sales tax: Navigate to Ledger and sales tax section and select a posting profile to use for posting prepayments in payment journals. Select “Yes” in the field “Sales tax on prepayment journal voucher”. In this case, the posting profile should have the main account for “Sales tax prepayments” (see chapter 2.1.1).
 
### Ledger posting groups

1. Open **Tax > Setup > Sales tax > Ledger posting groups.**
2. If sales tax from received prepayment should be posted on the separate main account, create a new Ledger posting group with a sales tax payable account and settlement account. 
3. Select this ledger posting group in the localization field Ledger posting group for tax in prepayments. 
 
If no separate ledger posting group is specified, sales tax from received prepayments will be posted with sales tax payable main account from used ledger posting group.

### Print management setup (Optional)

Print management option is also enabled for prepayment invoices. It is not mandatory to use Print management.
1. Open **Accounts receivable > Setup > Forms > Form setup > General > Print management > Documents > Prepayment invoice**
2. Create new Default form with needed setup (different destination etc.).

## **Generate Advance invoice from received prepayments** 
---

1. Open **Accounts payable > Payments > Prepayment invoice**.
2. Create **New** journal and Click on **Lines** to enter the journal.
3. Navigate to **Functions > create prepayment proposal**.   
4. Enter **“From date”** and **“To date”** to filter out payment transactions marked as prepayment. Optionally, enter the **Posting date** and **VAT date** that Prepayment invoices will be generated with. Confirm the date parameters.<br>
5. **Prepayment invoice header** is generated in the upper section of the journal. If the received payment of prepayment was settled against sales order through Settle open transactions (see test case), the invoice line is generated automatically.If there is no sales order or the payment of prepayment was not linked to one, the line is not generated. Infolog appears: “Prepayment is not completely allocated to orders.” In this case, manually add the line: 
   - If there is no sales order, add a line with Item type “Text” (quantity, amount, sales tax group – if it is defined on the customer – are automatically populated, add item sales tax group). 
   - If there is a sales order that has not been linked to received prepayment, select item type “item”, select sales order and order line – quantity, amount, and sales tax data will transfer automatically. 
6. Upon saving the line, the Voucher amount/Line amount and Voucher VAT/Line VAT fields are calculated. In cases where separate sales tax codes for the advance invoice is needed, it is necessary to change the item sales tax group after the line generation. **Sales tax** for individual prepayment invoice line can be checked before posting by navigating to **Inquiries > Sales tax**.
8. **Enter** Document date, VAT date, and advance invoice number.
10. **Post** Prepayment journal. Posting the journal posts only VAT. 


##**View Prepayment invoice information**
---
To see the list of posted Prepayment invoices and their reversals based on generated final Invoices: 
1. Go to **Accounts Receivable > Invoices > Prepayment invoice**
2. **List** of all generated prepayment invoices will open
3. To see **Voucher** select Prepayment invoice and go to Tab Prepayment invoice > Voucher
4. To see **Posted sales tax** select Prepayment invoice and go to Tab Prepayment invoice > Posted sales tax
5. To **reverse** Prepayment invoice (only in cases when Prepayment invoice needs to be reversed manually and it won't be settled with final Invoice) select Prepayment invoice and go to Tab Prepayment invoice > Reverse.
6. To **Print** Prepayment invoice select Prepayment invoice and go to Tab Prepayment invoice > **Print journal** or Use **print management** Print journal is used when you just want to preview and print Prepayment invoice. In cases, when you need some additional rules eg. sent to emali, print to file, use separate print layout for separate customers etc. it is recommended to use print management option. 



### Reverse generated Prepayment invoice
Prepayment invoice, generated based on received prepayment, can be also reversed. With Reverse function, new Prepayment invoice journal with negative amount is created, but it needs to be posted manually. After that prepayment is again available for issue of new Prepayment invoice.

To create Prepayment invoice reversal: 
1. Go to **Accounts receivable > Invoices > Prepayment invoice** 
1. Choose Prepayment invoice that needs to be reversed 
1. Go to tab **Prepayment invoice > Reverse**
1. Enter parameters and click **OK**. Prepayment journal is generated.
1. Go to **Accounts receivable > Payments > Prepayment invoice**
1. Go to journal that was generated in step 4 and click **Post**. Prepayment invoice is reversed and prepayment available for new Prepayment invoice. 
 

##**Prepayment invoice and Final invoice**
---
When Final invoice is linked to prepayment, Prepayment invoice is automatically reversed. 

1.  If the final invoice is linked to the sales order that was settled against prepayment, reversal happens upon posting the invoice.
14. If there was no sales order, reversal happens upon manually settling the posted invoice and payment of prepayment. 
    - Navigate to “Settle transactions” on the Customer account.
    - Mark the transaction of prepayment and final invoice and select “Post”. The message about reversal appears.




## **Test cases**
---

### Prepayment linked to sales order

Check [Test Cases](Advance-Invoice-Test-scenario.zip).
 
### Manually settling received prepayment and FTI

Check [Test Cases](Advance-Invoice-Test-scenario.zip).
 

