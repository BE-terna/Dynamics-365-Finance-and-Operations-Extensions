
Mass asset lending functionality is used to automate and simplify the standard D365O Fixed asset lending. Functionality adds the Mass asset lending feature, which among others enables users to lend several fixed assets at once, based on the specified critera.

With the new lending functionality, responsible employee and/or location can be added/changed, and the last open lending record is closed. In addition, it is also possible to transfer financial dimension values of newly assigned employee to the fixed asset. It is important to emphasize that based on the setup in the system, this functionality can use physical locations (additional feature) instead of standard locations. 

## **Setup**
---

### Physical locations 
Mass asset lending functionality can use either standard or physical locations. To use physical locations:
1. Go to **Fixed assets > Setup > Fixed assets parameters > Fixed assets** tab 
1. Set **Activate physical locations** to Yes. If this option is set to No, standard locations will be used.

### Mass asset lending dimension attributes

With this setup user defines financial dimensions that will be transferred from employee to fixed asset when mass asset lending action is performed. 

1. Go to **Fixed assets > Setup > Fixed asset parameters > Mass asset lending**
1. From the list of available dimensions (attributes) **select attributes** that will be transferred **from employee to fixed asset**. On the left side, there is a list of all available attributes, while on the right side is the list of selected attributes, which will be transferred during mass asset lending, if the **Financial dimensions of the borrower option is set to Yes** when running the Mass asset lending job.
 

## **Perform Mass asset lending**
---


###Apply processing parameters<br>

1. Go to **Fixed assets > Periodic tasks > Mass asset lending** 
1. Specify the following **parameters**:


|**Parameter**| **Description** |
|--|--|
|**Transfer date**  | Date that will be assigned to a new lending record as **Lending date**. Transfer date also affects the **Actual return date** of the previous opened lending record. Actual return date is recorded as one day prior to the Transfer date.  New lending cannot be created for fixed assets that have open lending with a later date in comparison to transfer date. If a fixed asset fulfills all filtering criteria, but has an open lending with the later date then the transfer date, Error message will appear. Transfer date must be at least 1 day after the current open lending.|
|**From worker**  |ID of a worker (from the register) **from which assets should be transferred**. If left blank,  all acquired fixed assets from the fixed asset register will be processed, unless one of the other filters is selected. In this case a warning is displayed upon mass asset transfer generation. All active and inactive workers are available for selection.   |
|**To worker**  |ID of the **borrowing worker**. Only active workers are available for selection. If the field is left empty, field To location must be populated, otherwise error will occur.|
|**Financial dimensions of the borrower**  |Indicates whether financial dimensions from the borrower’s primary position **should be transferred** to the fixed asset book when Mass lending action is performed or not.<br>  - **Set to Yes**: Dimensions will be transferred. In case of different dimensions, transfer transaction will be generated. If dimensions stay the same, only lending record is generated.<br>  - **Set to No**: Dimensions will not be transferred. Only lending record is generated. <br> _Note:  Only dimensions, selected in Mass lending parameters will be transferred. Financial dimensions will be changed on all fixed asset books that have Post to general ledger - Yes and Posting layer – Current._|
|**From location**|Location from which fixed asset will be transferred. **Standard or Physical** locations are available in this list, depending on setup in Fixed asset parameters. All fixed assets with the selected location in the last open lending record will be considered for creating a new lending transaction.  If From location is selected as well as the From worker, only fixed assets that meet both criteria will be selected for creating a new lending.|
|**Include hierarchy**|This option is available only when **physical locations are used** in the system.<br>  - **Set to Yes**: all subordinate physical locations of selected location will be taken into account. Example: Physical location 1 is selected in the field From location. It has subordinate physical locations 1.1 and 1.2. If Include hierarchy is set to Yes, all fixed assets with open lending in physical locations 1, 1.1 and 1.2 will get a new lending.<br>  - **Set to No**: New transaction will be generated only for the fixed assets with opened lending in the selected physical location. |
|**To location**|Location, to which fixed asset will be transferred. **Standard or Physical** locations are available in this list, depending on setup in Fixed asset parameters. If location selected, this location will be defined in a new lending record in the field Location or Physical location, based on which locations are used in the system. If field To location is left empty, location from the last open lending will be copied to the new lending record. If To location field is left empty, field To employee must be populated, otherwise warning will be displayed. |


When multiple filters are defined (eg. From worker and From location), only corresponding fixed assets that match all criteria will be processed. 

3. Use standard **filtering and batch processing options** if needed. 
1. Click OK to **run the mass asset lending**.
1. **Info message** with the details about the lent fixed asset(s) is available in the Action center

<br>

### Mass asset lending results<br>





Following transactions are created as **result** of As result of Mass asset lending process:
1. **Lending record on the Fixed asset level**: This transaction is recorded always when Mass asset lending is performed for the selected records. It indicates tat some kind of change on the Fixed asset level happened. This could be the change of responsible worker, Location or financial dimensions. 
1. **Transaction in Fixed asset Book**: In cases when financial dimensions change (eg. Asset is transferred from worker A to worker B, and worker A works on position in Business unit 1 and worker B works on position in Business unit 2), also transaction on the Book level is generated. This means that this kind of change also affects General ledger. _Note: Only remaining value gets transferred._


**To see generated lending records:** 
1. Go to **Fixed asset > Lend**
1. List of all **lending transactions** is available. New line is created in the “Lending” form of the selected fixed asset. If a lending line for a fixed asset without the specified “Actual return date” existed, prior to generating the Mass asset lending, then the “Actual return date” is automatically set on the previous day of the newly generated lending line.

**To see generated Fixed asset Book transactions:** 
1. Go to **Fixed asset > Books > Select a Book**
1. List of all generated **Book transactions** is available. This is only valid for Books that have Post to General ledger setup set to Yes. In this case all transactions are also posted to General ledger.

## **Asset transfer transaction reversal**
---

Asset transfer transaction can be reversed by clicking the button Reverse transaction in Fixed asset transactions form: 
1. Go to **Fixed asset > Books > Select a book > Transactions > Reverse button**
1. Select transaction
1. Click **Reverse**

Reverse transaction functionality will reverse postings that occurred with Asset transfer transaction and it will return financial dimensions on fixed asset book that were assigned on the fixed asset prior to the mass asset lending.  **However,** the record in the Lending form will not be removed automatically. It has to be **deleted manually**