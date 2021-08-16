Debit and Credit notifications are used in cases when users need more frequent updates regarding bank transactions. Therefore, term Online notifications is also used. Frequency of import is part of setup, which means that it can be adjusted according to specifics of business process.  

## **Setup**
---
 See [Bank statement Import setup](/Help/Standalone-solutions-\(Suite\)/Advanced-Banking/Bank-statement-import)

## **Import and validate debit credit notifications**
---

If SharePoint source is configured for debit credit bank notifications, they can be either **imported** from SharePoint or **entered manually**.

_NOTE: if SharePoint source is not configured, debit credit notifications can also be uploaded directly from PC from Cash and bank management – Bank statement reconciliation – Bank debit credit notifications form_.

To import from configured sources (SharePoint):
1. Go to **Cash and bank management > Periodic tasks > Bank debit credit notification import (ER)**.
2. Specify:
   - **Bank account**
   - **Import notification for multiple bank accounts in all legal entities**:  select if you want to import notifications for multiple bank accounts at once (NOTE: importing notifications to multiple bank accounts in D365FO with same bank account number is not allowed)
   - **Notification format**: select adequate electronic reporting format
   - **Number of files to import**: specify number of bank notification files that you wish to import (if left 0 only 1 will be imported)
 
To import manually: 
1. Go to **Cash and bank management > Periodic tasks > Bank debit credit notification import (ER)**. 
2. Click on **Import notification**
 
To see the list of imported bank notifications: 
1. Go to **Cash and bank management > Bank statement reconciliation > Bank debit credit notifications**
2. List can **viewed**, **edited** and **validated**. 
3. **Manually entered** notification files are marked as **Manual**. 

 
Each bank notification file has a Status defined, which can be also used for filtering:
   - **Reconciled**:  indicates whether bank notification has been reconciled with transaction from the system
   - **Reconciled with bank statement**: indicates whether bank notification has been reconciled with transaction from bank statements
   - **Reversal**: indicates notification transactions, marked as reversals
	 
