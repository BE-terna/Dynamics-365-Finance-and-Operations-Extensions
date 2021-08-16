# Public procurement cases

Public procurement cases functionality is used to perform public procurement procedures in D365O.

## **Setup**
---

### Case categories

Case categories are used to distinguish between different public procurement procedures. The required number of case categories, therefore, depends on the types of distinct public procurement processes required to be performed in D365O. For each public procurement procedure (e.g. Low-value order or Open procedure), a unique case category is proposed to be created.

1. Open Organization administration > Setup > Cases > Case categories.
2. New Case categories can be created by clicking »New«, then enter a name and description to an adequate hierarchy node. For each case category, a default case process can be set. Case processes specify the steps for each distinct public procurement process and are further described throughout the following chapter (2.1.2).
3. In the “Public procurement amount limits” section, order value for each public procurement case category can be set. Amounts refer to the total amount of the combined public procurement case parts (RFQ cases), added to the case. However, no amount of validation exists, while these amounts are mainly informational.
 
If the total amount of the combined RFQ cases connected with the public procurement case is lower or exceeds the defined amount limits, the “Amount status” field in the “General” section of the public procurement case displays information about the low or exceeded limit.
 
Additionally, amount limits are checked, if “Propose case categories” function is used when adding RFQ cases to a new public procurement case.
 
### Case processes

The case process is a predefined template, which describes the expected steps in the process of each of the public procurement cases. Case processes can be defined per case category or separately for each public procurement case.
A new case process can be created by clicking “New” and adding responsibilities – a list of all the possible stages within the process.

1. Open Organization administration > Setup > Cases > Case processes.
2. Once Responsibilities are entered, process hierarchy can be defined. This is done by clicking the “Details” button under the “Process” tab.
3. The hierarchy of the entered process steps can be added by clicking “New” - “Level”. A new form opens, where additional information about each of the steps in the process can be entered.
 
### Case Statuses and Stages

When newly created, the public procurement case is in status “Opened”. When users start working with the case, status can be updated to “In process” by clicking the “Change status” button.
 
Additionally, public procurement case stages indicate which part of the public procurement procedure the case currently is. These stages serve only as information for the case users. Thus, no validation connected with each of the case stages exists. The setup of the public procurement case stages is described in the chapter above.
 
Each stage of the case can be started by clicking the »Change stage« and selecting the applicable stage. For example, the »Public procurement members« stage should proceed once, the adequate members have been added to the Public procurement case.
 
NOTE: both – Public procurement case statuses and stages only have the informational value for users - e.g. to get an insight into a stage of the public procurement or easily filter out the desired public procurement cases. However, no validation linked with either specific public procurement case status or stage exists.

## **Create case**
---

Public procurement cases can be created:
1.    Directly from the RFQ case: On RFQ case click on either “Create case” (creates a new public procurement case) or “Add to case” (connects RFQ case with an already existing public procurement case) button.
1.  Through Public procurement cases form: Procurement and sourcing > Public procurement cases > All cases > New > Case.

Following any of the above-described procedures (1 or 2), a new form opens. If action to add RFQ case to an already existing case is selected, a new form opens, where users can select the public procurement case, with which they want to connect the RFQ case. If an action to create a new public procurement case out of the RFQ case is selected, a different form opens, where it is possible to determine additional information about the public procurement case. This information is described below by each section of the public procurement case form: 

GENERAL section:

|**Field**|**Description** |
|--|--|
|Name  |selected from the workers and contractors register (used to ease the filtering of cases)  |
|Case category  |select an adequate public procurement case category from the register  |
|Case ID |generated automatically according to the number sequences setup  |
|Description  |description (content) of the public procurement case can be added  |
|Priority  |can be selected from the register  |
|Parent case  |an existent public procurement case can be selected if applicable  |
|Status  |can be selected from the register  |

PUBLIC PROCUREMENT section: 

|**Field**|**Description** |
|--|--|
|Purchase type  |the desired result of the public procurement case (Purchase agreement, Purchase order or Framework agreement)  |
|Solicitation type  | selected from the register (Constructions, Goods or Services) |
|Expiry date and time  |expiry date of the Public procurement case (final date for the acceptance of vendor quotations)  |
|Subject  |a free text field (e.g. longer description of the public procurement case)  |
|Agreement ID  |link to an associated Framework agreement if it exists.  |

OTHER section:


|**Field**|**Description** |
|--|--|
|Department  |the department responsible for the public procurement case  |
|Employee responsible  |an employee responsible for the public procurement case (selected from the employee's register)  |
|Case process  |populated automatically according to case category (defined in “General” section) – it can still be changed by selecting an adequate value from the register.  |



After all the required information for a specific public procurement case is entered, the case can be created by clicking the »Create« button in the bottom right corner of the form. A public procurement case form opens, where most of the information, entered upon creating the case can still be edited. The public procurement case form and its processing is described throughout the following chapter.

## **Case sections**
---

Throughout the following part of the document, sections of the Public procurement case form, together with their purpose and functionalities are described.

### General

A general section consists of mostly the information, which can already be entered upon creating a new public procurement case (as described in chapter *Create Case*). Additionally, a Primary contact connected with the case can be selected from the contacts register.
 
### Public procurement parts

This section consists of the RFQ cases, related to the public procurement case. If public procurement case has been created directly from the RFQ case (as described in chapter *Create Case*, RFQ number from which public procurement case has been created is automatically displayed in the public procurement parts sections. On the other hand, if public procurement case has been created throughout the Public procurement cases form (as described in chapter *Create Case*), RFQ case(s), which the user wants to associate with the public procurement case need to be manually added. This can be done by clicking on the »New« button. Details about each of the related RFQ cases can be viewed by clicking on the »Details« button, which opens the selected RFQ case. By clicking the “Delete” button, RFQ case(s) can also be removed from the public procurement case.
 
The ID of the connected RFQ case(s), their Title and Net amount are automatically transferred from each RFQ case when they are added to the public procurement case.

Additionally, Expected dates of finality and a checkmark whether quotations in relation to each RFQ are Final can be specified. Their function is described later throughout the document.

### Public procurement members

In this section, it is possible to add members (e.g. of the Expert commission), related to the public procurement case. 

This can be done by clicking »New« and selecting adequate member roles (from the register of roles), then assigning each role to a worker (from the register of workers). For each of the selected members, a Description and duration of their membership in the public procurement case can be defined. Multiple members can be added (as separate lines).
 
### Public procurement attachments

Attachments can also be added to the Public procurement case. This can be done by clicking »New« and selecting the present attachment type from the register. Once a new line is created, desired files to be attached (e.g. service/goods specifications, different documentation) can be added to each line, by clicking the »Attachments« button. A new (standard) form opens where a file type can be selected, uploaded  and other details about the attached file can be filled in. 
 
### Public procurement identifications

Once a public procurement case is officially published on an adequate public procurement portal, Public procurement identifications (št. Javnega naročila) can be entered.
  
### Certifications

Additional enhancement on certifications is added as part of public procurement functionality, and that is the Certification insurance type. Upon certification entry on vendor form, the field Certification insurance type is added to the standard form to ensure the additional classification of vendor certificates. 
 
The values for drop-down selection in this field are entered in the code list at Procurement and sourcing > Setup > Vendors > Certification insurance type. If certifications are applicable for an individual public procurement case, they can be added in this section by clicking “New”, specifying Vendor (it is possible to choose from all the tenderers, co-tenderers or subcontractors specified in “Tenderer registration section” of the public procurement case) and selecting Certification type from the related register. One vendor certificate can only be used for one public procurement case. It is not possible to use the same certificate on multiple cases.

### Proposed vendors

The proposed vendors section is used only for public procurement procedures, connected with a Framework Agreement. If a Framework agreement is linked to a Public procurement case, the Proposed vendors section displays vendors (tenderers) from the related agreement. If public procurement is not linked to a Framework agreement, proposed vendors should not be entered.
 
### Tender registration

Tender registrations section serves for registering tenders, who responded to the specific public procurement request. The following fields are available to be entered for each tender (line):


|**Field**|**Description**|
|--|--|
|Date and time  |Date and Time of the received tender  |
|Vendor’s account  |endor’s account from the vendor’s register (NOTE: if vendors are added to “Proposed vendors” section of the public procurement case, only these specified vendors can be selected when registering tenderers)  |
|Consortium  |should be checked if the line refers to the consortium of vendors  |
|Worker  |who registered the tender is automatically selected from the register upon entering each new tender  |
|Delivery status  |indicates whether tender has been received within the specified public procurement case Expiry date - “Late” or “In time” options are available (NOTE: only tenders from the tenderers who sent their tenders “In time” can be accepted later in the process)  |
|Submission method  |indicates the method by which tenderer has submitted the tender (e.g. by mail or electronically)  |
|Delivered by  |a free text field (e.g. name of the delivery person)  |
|Properly labeled  |indicates whether the received tender is properly labeled (NOTE: only properly labeled tenders can be accepted later in the process)  |
|Number of consignments  |indicates the number of the received consignments connected with the tender.  |


In the bottom part of the form, users can specify to which RFQ case from the “Public procurement parts” each tender reefers to. The bottom part of the form consists of as many lines as there are RFQ cases (public procurement parts) related to the public procurement case.

For example – tender from “Telekom Slovenije, d.d.” refers to the goods/services from the public procurement part “000076”. This is indicated with the “In tender” checkmark:
 
#### Consortium

If the “Consortium” field is marked on the tender registration, the “Co-tenders” function becomes available for the selected record. This function allows entering multiple vendors accounts, associated with one received tender if applicable (e.g. if more vendors together responded to the public procurement request). A new form opens where multiple vendor accounts from the register can be selected.
 
NOTE: all co-tenderers from which the invoices are expected to be received in relation to the Public procurement case outcome document (Purchase order, Purchase agreement or Framework agreement), should be entered since only invoices from the specified vendors can be accepted in terms of the resulting document.  

#### Subcontractors

Similarly to a consortium, subcontractors can be added to each tender, by clicking the “Subcontractors” button. A new form opens, where vendors from the register can be specified as subcontractors.
 
In contrast to co-tenderers, Subcontractors serve only as additional information about the subcontractors involved with each tender, while no limitations in the further documents, related to the specified subcontractors exist.

#### Copy vendors

When successfully selecting public procurement case parts (RFQ cases), tenderers should be transferred to these public procurement case parts (RFQ case), associated with each tender. This can be done by clicking the “Copy vendors” function. Once completed, all the transferred lines are indicated with the “Yes” mark in the “Transferred” field of each tender.

When tenderers are transferred to an adequate RFQ case, an informational message is also displayed. Tenderers are transferred only to public procurement case parts (RFQ cases), marked with “In tender” checkmark, but only if the Delivery status of their tenders is “In time” and the tenders are marked as “Properly labeled”:
 
#### Send

Send functions performs the same action, as the “Send” function on the standard RFQ case form and are meant for sending RFQs to the specified vendors.

While standard D365O functionality requires RFQs to be sent to the specified vendors, in terms of public procurement procedures, RFQs are not actually sent to vendors from D365FO. »Send« action in terms of public procurement procedures is used only to reach the required status of the RFQ cases, which allows entering the tenderer replies.

For that purpose, make sure that »Purchaser can edit vendors bid« checkmark in Procurement and sourcing parameters is set to »Yes«. If this option is not enabled, only vendors to whom RFQs are sent can enter and modify their replies (e.g. actual quantities, prices, details) through Vendor collaboration procedures, which is not applicable in terms of public procurement procedures.
 
1. By clicking “Send” action, a new form opens, where users can specify to which of the connected RFQ case lines each of the tenderers responded:
2. By clicking “OK”, line status of the marked lines on the associated RFQs changes to “Sent”, which is a prerequisite for entering tenderer replies later in the public procurement process.
 
An informational message is also displayed.
 
3. After refreshing the form, a new line appears in the “Tenderer replies” section of the Public procurement case.
 
### Tenderer replies

When RFQ case lines, associated with tenders, listed in the “Tender registration” section of the public procurement case are in status “Sent”, a separate line, associated with each of the registered tenders appears in the “Tenderer replies” section. 

1. By clicking on the “Request for quotation case” link on each line, or by selecting a specific line and clicking “Reply details”, RFQ connected with the tender opens and details about the tenderer replies can be entered.
2. Entering tenderer replies will not be described in detail since it is a standard D365O feature. 
3. Once replies have been managed (tenderer replies are submitted for each of the RFQ cases), the status of each submitted tenderer reply on the associated public procurement case changes to “Received”. “Net Amount” fields display the price, calculated based on the entered tenderer replies.
 
### Public opening of tenders

In this section, the location and time of the public opening of tenders can be specified by clicking »New« and typing in the location and opening date and time.
 
### Administration

This section displays information about the user who created the case and the creation date and time. Additionally, when the case is closed, it also displays information about the closing user, date and time.
 
### Legal protection events

Different legal protection event can also be entered if and when applicable by clicking “New”. Adequate fields then need to be filled in, depending on the legal event type:


|**Field**|**Description**|
|--|--|
|Event type ID  |selected from the register  |
|Applicant  |a worker who filed the request  |
|Date  |  |
|Application complete  |Options Yes if application is complete and No if application is incomplete.  |
|Commission decision  |can be selected from the register|
|Commission decision date  |Date of commission decision|



Additionally, in the bottom part of the form, the user can define which of the RFQs specific legal protection event refers to.
After the legal protection event is completed, a tender accepting process can begin.

## **Accept tenders**
---

Before accepting the tenders, public procurement parts (RFQ cases connected with the public procurement case) should be marked as “Final”. Information about the finality is also transferred to the RFQ case.

Tender replies can be compared by clicking the “Accept tenders” button. A new form opens, consisting of two additional tabs: (1) Request for quotation and (2) Acceptance of quotation.
   - (1) RFQ cases associated with tenders to be accepted;
   - (2) Based on the selected RFQ case in (1), tenderer replies are listed. Users can select tenders to be accepted by adding a checkmark into the “Marked” field.
 
NOTE: if a Purchase type of the public procurement case is “Framework agreement”, multiple vendors can be selected for one public procurement case part (RFQ case).

When the desired tenderer replies are selected, they can be accepted by clicking on the “Accept” button. A new form for Accepting requests for quotation opens, where RFQ, tenderer’s name, and currency are displayed. Transaction date is automatically adjusted to the current system date, but can also be changed.

NOTE: a checkmark in the “Do not transfer inventory dimensions” field signifies that inventory dimensions from the RFQ case line, associated with the tender will not be transferred to the generated document (public procurement case result) and is applicable only if result of the public procurement case acceptance is either purchase agreement or framework agreement.

In the bottoms section of the form, RFQ case lines, associated with the tender replies to be accepted are displayed. By clicking OK, another form for rejecting the remaining tenders opens. The section contains all the received tenderer replies, which have not been accepted in the previous step of the procedure.

When processing is completed, the status of the accepted tenderer replies changes to “Accepted” and of those rejected to “Rejected”. This can be seen in:
   - “Acceptance journal” section of the “Request for quotation acceptance” form or
   - Tenderer replies form, where the selected tender is also indicated.

Additionally, informational messages indicate the public procurement case processing results – created either Purchase order, Purchase agreement or Framework agreement.
 
### Group acceptance journals

An additional parameter is added to procurement parameters that enable a grouping of accepted tenders by vendor account and currency code into a single document when the result of public procurement processing is a purchase agreement.
 
With the “Group acceptance journal” parameter enabled, if the result of the public procurement case acceptance is a purchase agreement when the same vendor is marked as selected for different public procurement parts (different RFQs), a single output document is generated upon clicking Accept. The created purchase agreement contains all lines from accepted RFQs. 
 
## **Resulting document**
---

A decision about the resulting document is defined by the user at the point of Public procurement case creation, by selecting an adequate document in the Purchase type field. This process is described in chapter *Create Case*.
 
NOTE: in case of a chosen tender from a tenderer consortium, multiple documents (purchase agreements) are created because of public procurement case – one for each of the specified co-tenderers and one for a vendor, which defines the vendor consortium. 
   
### Purchase order

If a result of a public procurement case is a purchase order, purchase type “Purchase order” has been defined when generating the case. If any other document had been selected upon the public procurement case creation, these documents would be created instead.
 
It can be accessed through standard D365O forms for accessing purchase orders. All the information (header and line details) about the tenders are transferred from the related tender (RFQ case part associated with the tender) to this newly created purchase order (standard D3565O functionality). Purchase order is created in status “Approved”.
 
### Purchase agreement

If Purchase agreements are created because of a public procurement case, they can be accessed through standard D365O forms for accessing purchase agreements. Header and line information about the accepted tender are transferred from the related RFQ case parts, included in the accepted tender.
 
If tender from a consortium of tenderers has been accepted in public procurement case, then one purchase agreement is created for each of the involved vendor accounts in D365O:

Information about the related purchase agreements, resulting from the accepted tender for a consortium of tenderers can be seen in the “Related agreements” section on each of the related agreements.
    
### Framework agreement

Prior to generating framework agreements, number sequences used for Framework agreements need to be configured in Organizational administration module, with the following settings:


|**Field**|**Value**  |
|--|--|
|Scope  |Shared  |
|Area |Purchase  |
|Reference  |Framework agreement ID  |


If the purchase type “Framework agreement” has been defined when generating the public procurement case, a result of the case process is a generated framework agreement. One framework agreement can consist out of multiple case parts and tenders related to each of these parts (RFQ cases).
 
NOTE: Purchase type “Framework agreement” is displayed as an option also when creating RFQ cases, but cannot be manually selected there.
 
After tenders are accepted, a Framework agreement is created based on the pre-set number sequence. 
 
## **Send decisions**
---

Notifying tenderers about the acceptance or rejection of their tenders can be recorded on the Public procurement case in the “Tender registrations” section. By selecting an adequate tenderer, “Decision sending date” and “Decision delivery” date can be entered. 
This procedure should be repeated for each tenderer, included in the public procurement case.

NOTE: publishing decision about the accepted/rejected tenders can only be indicated in D365O, while it may have to be manually updated on the adequate public procurement portal.

## **Close case**
---

Once the public procurement process is complete, the case can be marked as “Closed”. This can be done by clicking “Change status” and selecting “Closed”.

In the “Administration” section, “Closed by” fields display the name of the user, who closed the case, along with the closed date and time.