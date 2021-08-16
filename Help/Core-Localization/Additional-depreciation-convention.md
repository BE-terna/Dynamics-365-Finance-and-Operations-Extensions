# Additional depreciation convention

This topic provides country/region-specific information about additional depreciation convention, added with a purpose to comply with the local legislation. According to the local accounting standards, depreciation calculation for fixed assets has to start with the first date of the following month after an asset has been put in use, or when it is available for use.

Localization feature offers an additional depreciation convention “Next month”, which enables automatic setup of depreciation calculation run date at the first month after the fixed asset has been acquired (acquisition posting date is considered) or placed in service (placed in service date is considered). For example, if an asset has been acquired (or put in use) on the 10th of July, using this localized feature, the depreciation run date will be set on the last day of the following month (August 31st).

## **Setup**
---

### Depreciation convention
1. Go to Fixed assets > Setup > Fixed asset groups > Books > Depreciation convention.
2. Additional  Depreciation convention type »Next month« is added. 


### Create depreciation adjustment with basis adjustment setup on FA Book
This setup affects only transaction type Acquisition adjustment. 
1. If set to Yes: Next month convention is ignored. Transaction is included in calculation of base amount for depreciation in the month of transaction date (transaction posted on 1.1. will be included in depreciation calculation for january)   
2. If set to No: Next month convention is taken into account. Transaction is included in calculation of base amount for depreciation the next month after transaction date (transaction posted on 1.1. will be included in depreciation calculation for february)   

## **Usage**
---
Transactions taken into consideration: 
 - Acquisition
 - Acquisition adjustment
 - Write up adjustment
 - Write down adjustment

When this type is set on a Fixed asset book, the depreciation run date will be set in the moment of acquisition posting and will be set to the following month. Placed in service month is determined by the acquisition posting date and the Depreciation run date will be set to the following month. 

Effect of Next month convention in case of **Write up/ Write down transactions**: 
Once the Write up adjustment or Write down adjustment transaction is posted, the adjustment is considered in the following month (e.g. Write up/Write down adjustment is posted in April, a new depreciation amount is calculated for May).
 
Example: Straight line service life depreciation method, 10 depreciation periods
 

| Transaction date |Transaction type  |Amount  |Note  |
|--|--|--|--|
|01.01.2020  |Acquisition  |1000  |  |
|28.02.2020  |Depreciation  |-100  |Convention Next month – Acquisition in January, first depreciation in February  |
|31.03.2020 |Depreciation  |-100  |  |
|01.04.2020  |Write up adjustment  |500  |  |
|30.04.2020  |Depreciation  |-100  |  |
|31.05.2020  |Depreciation  |-150  |Convention Next month – Write up/Write down adjustment in April, new depreciation amount calculated for May. (1000+500) / 10 = 150|

Effect of Next month convention in case of **Acquisition adjustment transaction type**:
Depreciation calculation after posting Acquisition adjustment transaction depends on the **Create depreciation adjustments with basis adjustments setup** on the Fixed asset book:
- If Create depreciation adjustments with basis adjustments is **set to No**, the depreciation calculation works in the same way as for Write up adjustment and Write down adjustment transactions - the adjustment is considered in the following month (e.g. Acquisition adjustment is posted in April, a new depreciation amount is calculated for May).

Example: Straight line service life depreciation method, 10 depreciation periods:
| Transaction date |Transaction type  |Amount  |Note  |
|--|--|--|--|
|01.01.2020  |Acquisition|1000  |  |
|28.02.2020  |Depreciation|-100  |Convention Next month – Acquisition in January, first depreciation in February  |
|31.03.2020 |Depreciation|-100  |  |
|01.04.2020  |Acquisition adjustment|500  |  |
|30.04.2020  |Depreciation|-100  |  |
|31.05.2020  |Depreciation|-150  |Convention Next month – Write up/Write down adjustment in April, new depreciation amount calculated for May. (1000+500) / 10 = 150|

- If Create depreciation adjustments with basis adjustments is **set to Yes**, the adjustment is considered in the same month (e.g. Acquisition adjustment is posted in April, a new depreciation amount is calculated already for April). 
In this case the system automatically posts Depreciation adjustment transaction with Acquisition adjustment. Depreciation adjustment transaction corrects all prior posted depreciations, in a way that all depreciation amounts from the beginning include Acquisition adjustment transaction. Consequently, a new depreciation amount is already calculated in the same month when acquisition adjustment is posted.

Example: Straight line service life depreciation method, 10 depreciation periods:
| Transaction date |Transaction type  |Amount  |Note  |
|--|--|--|--|
|01.01.2020  |Acquisition|1000  |  |
|28.02.2020  |Depreciation|-100  |Convention Next month – Acquisition in January, first depreciation in February  |
|31.03.2020 |Depreciation|-100  |  |
|01.04.2020  |Acquisition adjustment|500  |  |
|30.04.2020  |Depreciation|-100  |The system automatically posts Depreciation adjustment transaction. New depreciation amount calculation: (1000+500) / 10 = 150. Prior depreciations were equal to 100, meaning the system increases each posted depreciation amount for 50. 2 x (-50) = -100  |
|31.05.2020  |Depreciation|-150  |Consequently, a new depreciation amount is already calculated in the same month when acquisition adjustment is posted.|