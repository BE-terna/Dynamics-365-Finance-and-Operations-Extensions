# Compensations (Set-off)

The feature enables settlements between receivable and payable amounts for a company that is registered as both – a customer and a vendor in the system need to be done. This settlement process uses a legal procedure that is known as compensation or netting.

The creation of a compensation proposal is enabled, where it is possible to select a customer, a vendor, and transactions to be compensated – credit notes can also be used in the procedure. Compensations can be posted to the specified general journal, customer and vendor posting profiles. Compensation proposal can be printed.

This custom-developed feature is part of the BE-ternaSuiteCompensations AdSuite D365O extension packet.

## **Setup**
---

### Number sequence

The number sequence needs to be set up. This can be done in Organization administration - Number sequences - Number sequences. The number sequence needs to be referenced to area Compensations. 
 
### Journal name

A separate journal name needs to be generated. Since one voucher posting is not allowed, the offset account (type is not important, but usually Bank or Ledger are used) needs to be defined for this journal. This way two separate vouchers will be generated during the posting process.
 
## **Generate compensation proposals**
---

Compensation proposals are generated in Accounts Payable - Compensations - Generate compensations. Two types of compensations can be generated: 
   - Internal: between Customer and Vendor that are connected to the same Party in Global Address book
   - Chain: between Customer and Vendor that are connected to different Partys in Global Address book.  
According to Type, different options are available. 

To generate compensations proposal, following parameters need to be defined: 

| **Parameter** |**Description**|
|--|--|
|Type  |Two options are available: Internal and Chain. When choosing Type Chain, fields Customer account and Vendor account are enabled. In this field, the user can manually choose Vendor and Customer for comepansation.  With option Internal compensation proposals will be created for all candidates with the same Party ID and open receivable and payable amounts. Fields Customer account and Vendor account are disabled. |
|Date  |The date field defines the date of the compensation proposal.   |
|Due date  |With Due date, a user defines transactions to be compensated. Due date is checked for Vendor and Customer transactions.  All Vendor/Customer transactions that have a due date before or on the date defined, will be candidates for compensation.  |
|Currency  | Currency defaults from legal entity currency since compensations are usually processed in domestic currency.  The user can also change the currency to generate compensations in foreign currency if needed. In this case, the currency of the Vendor and Customer transaction needs to be in the same currency. |

 
After confirming with OK button Compensation proposals that fit the criteria are generated. A list of Compensation proposals can be found in Accounts Payable > Compensations > Compensations.
 

Compensation proposals are assigned a certain status, according to phase: 


|Status|Description  |
|--|--|
|Open  |When compensation proposals are generated, they get status Open. This status allows editing and deleting a document. Status can be manually changed into Active.  |
|Active  |When in status Active, no changes are allowed anymore. Status can be manually changed into Open. Only Active status allows posting of the document.  |
|Closed  |When compensation proposal is posted, status is automatically changed to Closed  |
|Rejected  |If the proposal is rejected by Customer/Vendor, status can be changed to Rejected. With this status, all connections to original transactions are deleted, which means, that transactions can be included in the payment process again.  |

 
In compensation proposal details all transactions, that fit the criteria, are listed. There is a separate tab for Customer and Vendor transactions. If the transaction will be compensated the amount in field Compensation amount is populated. The amount can be lower than the original transaction open amount. All proposed transactions can be manually reorganized, which means that transactions can be added (from open transactions list), removed or edited (change of compensation amount). 


Additional Display fields are available at the bottom of the transactions list: 


|**Field**|**Description**|
|--|--|
|Open amount  |Shows open amount that is available for compensation  |
|Transaction sum  |Shows the sum of compensation amounts for a specific transaction. This number is useful in cases where one transaction is split into several compensations.  |
|Compensation amount  |the sum of all amounts listed in the column Compensation amount.  |

###Credit notes
If credit notes are included in the compensation proposal, they get a negative compensation amount. If this amount is edited manually,  the negative sign needs to be set manually. 

###Foreign currency
Compensation proposal can also be prepared for documents in foreign currency, but only in cases where vendor and customer documents are posted in the same foreign currency. Currency for compensation proposal is defined in the “Generate proposal” form. 

###Compensation proposal print
Compensation proposal can also be printed. Print can be generated regardless of Change status.


###Compensation amount and Payment proposal


All transactions that are included in the compensation proposal, will be excluded from the payment proposal. They are still visible in the Open transactions list but are blocked for payment. If the transaction is only partially included in the compensation proposal, only the remaining open amount will be included in the payment proposal. If the payment journal is prepared by using Settle transactions function, only warning with information about the compensation amount will be displayed. However, the total open amount will be transferred to the payment journal line. 

Amounts included in compensation are listed in a separate column on Settle transactions form. 


 
## **Post compensations**
---

Post button is enabled only if Compensation status is set to Active. This needs to be done manually. With click on Post button, new form opens, where following posting parameters need to be defined: 

|**Parameter**|**Description**  |
|--|--|
|Journal Date | Date of compensation posting. Transactions will be settled with this date.  |
|Journal Name  |Journal name, that is used for compensation posting. |
|Customer posting profile  |Posting profile that will be used for closing customer transactions from compensation |
|Vendor posting profile  |Posting profile that will be used for closing Vendor transactions from compensation |

 
Customer and Vendor transactions are generated as a result of the compensation proposal posting. Journal can be opened from the Compensation proposals List using the Voucher transactions button.

**In case of error**, Journal is generated, but not posted. Posting error is displayed. Information about generated journal is visible in compensation header in field Journal batch number. User can open generated journal and manually adjust it or delete it. If Journal is deleted, Journal batch number is deleted from Compensations header. 
 
