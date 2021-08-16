# Year end procedure enhancements 

Functionality enables balancing Main account balance with Ledger account balance in order to avoid opening transactions in cases where Ledger account balance equals zero and Main account balance does not. The feature is useful if at the end of the year a different balance on each main account - financial dimension combination s remains, while the balance for the same main account (combining all the dimensions) is zero.

This extended localization feature enables a proposition for balancing General Ledger transactions from the General journal. As a result, journal lines with settlement proposals are generated. After the journal is posted, balance on both, Ledger account and Main account, is zero.

In cases when the Main account balance (ledger account + financial dimension) for a specific combination in a fiscal year is different from zero while Ledger account balance is zero, it is possible to generate a proposal to settle the remaining Main account balances. As a result, such transactions are not included in opening balances for the next year.

## **Generate Closing Account Transactions proposal**
---

1. Open General journal - Lines - Functions - Propose balancing GL transactions.
2. New function »Propose balancing GL transactions« is added as an additional BE-terna feature. In new general journal lines click Functions -> Propose balancing GL transactions. Enter Start and End date (mandatory fields) and the main account that will be included (optional).
   - Start/End date – the period for which transactions will be checked and journal generated
   - Main account – main account/s that will be included. Multiple main accounts can be included. 
3. As result journal lines with settlement proposals are generated. If the Main account that does not allow manual entry is included, the system will throw an error. 
4. Generated lines can be deleted/changed and new lines can be added. If a new line is manually added, it gets a new voucher number.
5. After the journal is posted, balance on both, Ledger account and Main account, is zero.



