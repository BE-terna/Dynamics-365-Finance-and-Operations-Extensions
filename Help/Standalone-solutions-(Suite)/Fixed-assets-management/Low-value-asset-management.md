Low value asset functionality can be used when low value assets are managed through inventory. In that case, companies can track issues, transfers, returns, and write-offs of low value assets in a clear and transparent way.  


# **Setup**
---

### **Posting**

1. Go to **Inventory management > Setup > Posting > Posting** 
2. Select **transaction type**. Posting setup is expanded to include new section Low value assets, where it is possible to define postings for the following transaction types:
   - Issue
   - In use
   - Depreciation
   - Correction
3. Setup for Issue and Depreciation types is **mandatory**. Setup for other types is optional and depends on process specifics. 

### **Journal names**

1. Go to **Inventory management > Setup > Journal names > Inventory**
2. Create a **new journal name** for each journal type and specify the needed parameters. Inventory journals include **additional journal types**:
   - Low value asset – Release
   - Low value asset – Return
   - Low value asset – Transfer

Selection in field **New voucher** by has been **expanded** to include additional option: Worker (waiting for extension point!).

If the journal is of Low value asset – Return type, **additional tab Low value asset** is displayed, where it is possible to set up the **default value for Write-off** (Yes or No). This value is defaulted to Low value asset – Return journal line. If value is set to **Yes**, Low value asset write-off transaction will be generated at the moment of posting transaction with this journal. If value is set to **No** write-of transaction will not be generated. 

After the journal names are created, navigate to **Inventory and warehouse management parameters > Journals tab**, to select default journal names for each low value asset journal type.

### **Low value asset locations**

1. Go to Inventory management > Setup > Low value assets > Low value asset locations

Low value asset locations are used when **low value assets are returned** to indicate that they have already been **used**. Instead of returning them to inventory (site or warehouse from where they were released), the functionality supports return to Low value asset location from where they can **again be assigned to workers** or **transferred to another low value asset location**. 

2. Create as many Low value asset locations as desired by specifying Location ID and Description and adding default financial dimensions. 

### **Number sequence for low value asset adjustment voucher**

1. Go to **Inventory management > Setup > Inventory and warehouse management parameters > Number sequences**
2. Create a new **number sequence** for the low value assets adjustment postings and set it up **under Low value asset adjustment voucher**. This number sequence is used when adjustment transactions are posted upon running the low value asset adjustment processing (see more in Low value asset adjustment chapter).

# **Working with low value assets**
---

## **Supported cases**

With low value assets functionality, the following test cases are supported:
1.	Low value asset issue from inventory.
2.	Low value asset issue from low value asset location.
3.	Low value asset transfer from one responsible person to another.
4.	Low value asset transfer from one low value asset location to another.
5.	Low value asset return to low value asset location.
6.	Low value asset return with write-off.
7.	Low value asset return proposals. 
8.	Overview of low value asset assignments.
9.	Low value asset adjustment.

## **Low value asset Issue**
Release journal is used to release low value asset from its physical location (inventory or low value asset location) and assign it to a worker.
1. Go to **Inventory management > Journal entries > Low value assets > Low value asset – Release**.  
2. Create **new journal** by clicking New and selecting journal Name. **Other parameters** such as description, voucher policy, details level etc. are defaulted from journal name and can be changed, if needed. 
3. **Add journal lines** for low value asset release. Available columns to populate:

|Field|Description  |
|--|--|
|**Date**  | transaction date |
|**Item number**  |select desired item that represents low value asset.  |
|**Low value assignment**  |if release is done from low value asset location, select open low value asset location assignment; if release if done from inventory (site or warehouse), skip this field.  |
|**Responsible worker**  |elect Worker to whom the assignment is to be made; financial dimensions are defaulted from worker’s employment.  |
|**Assigned person**  |defaults from selected Responsible person; if needed, change to other Party ID  |
|**Quantity**  |assigned quantity  |
| **Storage/Tracking/Product dimensions** |Displayed through Display dimension. Select according to information that is tracked on product; usually Site and Warehouse from where the low value asset will be released.  |

4. **Post** the journal.
5. Low value asset **assignment is created** for selected responsible worker which can be viewed through **Low value asset assignment button** on journal line action pane or through **Inventory management > Low value assets > Low value asset assignment/Open low value asset assignment**. 

General ledger posting that is created for low value asset release **depends on the posting setup**: 
- If low value asset assignments **are not tracked on off-balance-sheet accounts** (In use and Correction posting types are not set up), then only Low value asset, Depreciation (debit) and Low value asset, Issue (credit) postings happen. 
- If low value asset assignments **are tracked also on off-balance-sheet accounts**, then Low value asset, In use (debit) and Low value asset, Correction (credit) transactions are posted along with Depreciation and Issue. 


## **Low value asset Transfer**
Transfer journal is used to transfer low value assets from one responsible person to another or from one low value asset location to another. 
1. Go to Inventory management > Journal entries > Low value assets > Low value asset – Transfer
2. Create new journal by clicking New and selecting journal Name. Add journal lines for low value asset transfer. Available columns to populate:

|Field|Description  |
|--|--|
|**Date**  |Transaction date  |
|**Item number**  |Select low value asset item to transfer (records in field Low value asset assignment will be filtered by the selected value).  |
|**Low value asset assignment**  |Select open low value asset assignment. If no item number was selected, it will be populated with the item from assignment selection.  |
|**Responsible worker** |If the selected low value asset assignment is of type Worker, select Worker to whom the transfer is to be made; financial dimensions are defaulted from worker’s employment. If the selected low value asset assignment is of type Location, field Worker is not available for selection. |
|**Assigned person** |Defaults from selected Responsible person; if needed, change to other Party ID. |
|**Low value asset location** |If the selected low value asset assignment is of type Location, select new location for the asset to be transferred to; financial dimensions are defaulted from selected location. |
|**Quantity** |Transfer quantity defaults from assignment, can be changed to lower quantity. |

3. **Post** the journal.
4. Low value asset **transfer is created** for selected worker or location which can be viewed through **Low value asset assignment button** on journal line action pane or through **Inventory management > Low value assets > Low value asset assignment/Open low value asset assignment**. 

General ledger posting that is created for low value asset transfer **depends on the posting setup**: 
- If low value asset assignments **are not tracked on off-balance-sheet accounts** (In use and Correction posting types are not set up), then no general ledger posting is created. 
- If low value asset assignments **are tracked also on off-balance-sheet accounts** and the low value asset transfer resulted in the change of financial dimensions that are tracked on ledger accounts for this setup, then 
  - **Original assignment is cancelled** for off-the-balance-sheet accounts (Low value asset, In use ( - debit) and Low value asset, Correction ( - credit) transactions are posted, using financial dimensions from the original assignment).
  - Low value asset, In use (debit) and Low value asset, Correction (credit) **transactions are posted** with financial dimensions from new worker/location.

## **Low value asset Return**

Return journal is used to indicate the return of low value assets. The returned low value asset can either be in good shape for further use – in this case the item is returned to low value asset location from where is can be assigned to another worker; or it might be ruined and needs to be written off. Returns to inventory are not supported. 

1. Go to **Inventory management > Journal entries > Low value assets > Low value asset – Return**
2. Create **new journal** by clicking New and selecting journal Name. Add journal lines for low value asset transfer. Available columns to populate:


|Field|Description  |
|--|--|
|Date  |Transaction date. |
|Item number |Select low value asset item to return (records in field Low value asset assignment will be filtered by the selected value).  |
|Low value asset assignment  |Select open low value asset assignment. If no item number was selected, it will be populated with the item from assignment selection.  |
|Write-off  |If **Yes**: field Low value asset location is not available. <br>If **No**: field Low value asset location is mandatory.  |
|Low value asset location  |If field Write-off is set to No, select low value asset location for the asset to be returned to; financial dimensions are defaulted from selected location.  |
|Quantity  |Return quantity defaults from assignment, can be changed to lower quantity.  |

3. **Post** the journal.
4. Low value asset transaction can be **viewed** through **Low value asset assignment button** on journal line action pane or through **Inventory management > Low value assets > Low value asset assignment/Open low value asset assignment**.

General ledger posting that is created for low value asset return **depends on the posting setup**: 
- If low value asset assignments **are not tracked on off-balance-sheet accounts** (In use and Correction posting types are not set up), then no general ledger posting is created, regardless of selection in the Write-off field.
- If low value asset assignments **are tracked also on off-balance-sheet accounts** (In use and Correction posting types are set up), and 
  - **If write off is Yes**, then 
    - Low value asset, In use (credit) and Low value asset, Correction (debit) transactions are posted using original transaction’s financial dimensions.
  - If **write off is No**, then 
    - Low value asset, In use ( - debit) and Low value asset, Correction ( - credit) transactions are posted, using financial dimensions from the original assignment.
    - Low value asset, In use (debit) and Low value asset, Correction (credit) transactions are posted with financial dimensions from selected location.

### **Return proposals**

Low value asset – Return journal enables return proposals with which we can perform mass low value asset returns (or write-offs). 

1. In journal’s action pane navigate to **Functions > Return proposals**. Available **parameters**:
Responsible worker: mandatory field; select worker for which to perform return/write-off

|Field| Description |
|--|--|
|**Responsible worker**  |Mandatory field. Select worker for which to perform return/write-off  |
|**Item number**  |Select item for return/write-off. If left empty, return/write-off proposal will be created for all open low value  |
|**Journal**  |Defaults from journal number  |
|**Return date**  |Defaults to session date. Change if needed.  |
|**Records to include**  |Specify additional parameters  |
|**Write-off**  |Select Yes or No to indicate the default value for write-off (if set to No, Low value asset location needs to be specified)  |
|**Low value asset location (Location ID)**  |Specify value if Write off is set to No.  |

2. After confirmation, **journal lines are created** according to selected parameters.  


## **Low value asset assignments overview**

Each low value asset assignment is tracked in Low value asset assignment form.

1. Go to **Inventory management > Low value assets > Low value asset assignment/Open low value asset assignment** 

Here, you can **view the data related to each low value asset assignment** as well as voucher transactions for each record. On the left side, low value asset assignments are displayed in the list, on the right side the details for each record as well as low value asset return information are displayed. The overview enables personalization of additional columns to the left side of the form. 
It is possible to switch to list form, using button Switch to list form.

In the list form, the data is displayed in columns. 


# **Low value asset adjustment**

If the posting of low value assets includes **setup for posting types In use and Correction**, then Low value asset **adjustment will need to be run** after the inventory recalculation process is complete to create adjustments also on In use and Correction ledger accounts (inventory recalculation creates adjustment for Issue and Depreciation ledger accounts).

1. First, **run inventory recalculation** to successfully create adjustment transaction for Issue and Depreciation ledger accounts. You can check Voucher for each inventory recalculation to see the posting results. You can also **view Settlements** to see posted Adjustments for each transaction. 
2. **After the inventory recalculation** is successfully run, navigate to **Inventory management > Low value assets > Low value asset adjustment**. Available **parameters**:

|Field|Description  |
|--|--|
|**From and To date**  |Define period for calculation  |
|**Posting type**  |**Validate**: Expected adjustment transactions for each item will be displayed in infolog <br>**Post**: adjustment transactions will be posted|
|**Posting date** |the date with which the adjustments will be posted to general ledger |
|**Detail level** |**Details**: adjustments are posted for each transaction in detail <br>**Summary**: adjustments are summed by ledger dimension (ledger account and financial dimensions). |

**Posted adjustment transactions** can be **viewed from Low value asset assignment page**, for each assignment in field Adjustment or through Cost adjustment form.

# **Data entities**

With the following data entities, low value asset journals can be **exported/imported using data management**:
- Low value asset – Release (InventInventoryLVAReleaseJournalEntity_AdFAM)
- Low value asset – Transfer (InventInventoryLVATransferJournalEntity_AdFAM)
- Low value asset – Return (InventInventoryLVAReturnJournalEntity_AdFAM)






 
