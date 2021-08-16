Partial Disposal is a functionality that enables user to partially dispose one fixed asset.  With new Partial disposal - scrap transaction type, a fixed asset in disposed for desired disposal percent (e.g. 20%). Partial disposal function generates all needed transactions that affect allready generated transactions.  

## Setup
---

### Fixed asset posting profiles

1. Go to **Fixed assets > Setup > Fixed asset posting profiles** 
1. Select **posting profile** that is used for other transactions
1. Select transaction type **Partial disposal - scrap**
1. Add **new entry** for each of the books that this transaction type will be used with and select **Ledger accounts**
 
### Fixed assets parameters 

This setup is needed to automatically generate Depreciation adjustment transaction in the moment of partial disposal posting.

1. Go to **Fixed assets > Setup > Fixed assets parameters > Fixed assets**
1. Set parameter **Automatically create depreciation adjustment amounts with disposal**  to Yes
 

### Fixed asset book

1. Go to **Fixed assets > Fixed assets > Fixed assets >  Mark specific Fixed Asset > Books**
1. Set parameter **Create depreciation adjustments with basis adjustments** to Yes
1. Set parameter **Allow depreciation when placed in service and disposal are in the same fiscal year** to: 
   - **Yes**: depreciation adjustment transaction will not be posted automatically, if Acquisition and Partial disposal – scrap transactions are within the same Fiscal year.
   - **No**: depreciation adjustment transaction will be posted automatically also in case that Acquisition and Partial disposal – scrap transactions are within the same Fiscal year. 

If you want this parameter to be set to Yes always when new Fixed asset is generated: 
1. Go to **Fixed assets > Setup > Books** 
1. Set parameter **Create depreciation adjustments with basis adjustments** to Yes
1. Set parameter **Allow depreciation when placed in service and disposal are in the same fiscal year** to Yes/No

<br>



## Partially dispose fixed asset
---
 
In order to do partially dispose fixed asset perform following steps: 
1. Go to **Fixed Assets > Journal entries > Fixed assets journal**, 
1. Generate new journal with button **New** from the Action Pane, choose **Journal Name** and then click the button **Lines** from the Action Pane to enter journal lines.  
1. Enter the **date** of partial disposal. 
1. Select the **Partial disposal – scrap** transaction type from the drop-down menu. 
1. Enter **disposal percent** (round number that is greater than 0 and less than 100). If you would like to dispose of fixed asset completely, the Disposal – scrap functionality should be used. 
1. Select the **fixed asset number** you want to partially dispose in the Account field. Other fixed asset information will be automatically entered from the Fixed asset book information. 
1. Click **Post**. 


**Partial diposal transactions overview**
---

1. Go to **Fixed assets > Fixed assets > Fixed assets >  Mark specific Fixed Asset > Books > Transactions** 
1. All transactions that were generated can be checked on each fixed asset. Partial disposal – scrap transaction will reduce amounts for all posted transaction types on the fixed asset by the disposal percent. 

<br>

## Example
---

In the picture below, you can see a simple example for partial disposal. A new fixed asset in the amount of 1.000 USD was acquired on the 1st of January 2019. The fixed asset has 10 depreciation periods and the depreciation method is Straight line service life, which means that monthly depreciation amount is 100 USD. Depreciations for January and February were posted at the end of each month. On 16th of March 2019 the fixed asset was partially disposed for 30%, as it can be seen in the picture. The partial disposal of 30% influenced the change of the depreciation amount in March. The new acquisition value of the fixed asset is now 700 USD and consequently, the new depreciation amount is 70 USD (transaction on the date of 31/03/2019). 

![image.png](/.attachments/image-df5655b0-8f00-467e-9e86-7fb2696d409e.png)