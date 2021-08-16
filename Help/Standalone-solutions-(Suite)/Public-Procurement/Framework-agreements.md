# Framework agreements

## **Form description**
---
Open Procurement and sourcing > Purchase agreements > Framework agreements.

The creation of Framework agreements is discussed throughout the chapter Framework agreement. Once created, the Framework agreements list displays all the generated framework agreements.

Framework agreement consists of following sections: 


|**Section**|**Description**  |
|--|--|
|General  |Information in section General is transferred directly from the public procurement case, from which framework agreement has been created (indicated in the “Case ID” field).  |
|Selected parts and vendors  |Section displays all the accepted tenders from the originating public procurement case.   |
|Lines  |Section displays information about the lines, from the accepted tenders, while in Line details section more information about each of the lines is displayed throughout multiple tabs, as described below.  |


| **Line Tab** |**Available information**  |
|--|--|
|General  | <ul><li>Agreement line product (Procurement category or Item) and procurement category/item name</li><li>Agreement ID (ID of the framework agreement to which each line belongs to)</li><li>Part (public procurement case part – the originating RFQ case)</li><li>Project ID (if the referring RFQ line is linked to a project)</li></ul>|
|Price and discount  |information about Quantity, Price, Units, Amounts, and Currency|
|Fulfilment  | <ul><li>Remaining (total remaining amount, left to be released in terms of framework agreement line)</li><li>Released to request for quotations</li><li>Released to purchase agreements</li><li>Released to request purchase orders</li></ul>|


Releasing from framework agreements can be done by linking the RFQ case directly with the framework agreement and connecting them with a public procurement case, as described throughout the following chapter.

## **Releasing from a framework agreement**
---

###Connect Framework agreement and RFQ

A public procurement case, which refers to a framework agreement, is created by creating RFQ cases. Firstly, an adequate framework agreement needs to be selected in the RFQ case header section, and then adequate RFQ case(s) need to be connected to a public procurement case.

NOTE: only RFQ cases associated with the same framework agreement can be connected to the same public procurement case.

1. Framework agreements can be selected directly on each RFQ case by clicking “Select framework agreement” button
1. A new form opens where it is possible to select applicable framework agreement to be associated with the RFQ case (“Framework agreement parts” section) and mark lines from the agreement, which will be released throughout the RFQ case. If one framework agreement consists of multiple parts (tenders), separate records on the list display all the existing framework agreements and part combinations.
 
NOTE: only framework agreements in Status “Effective” are displayed on the list.
In the “Actions” section, a connection between the lines from the RFQ and framework agreement are defined.
 
**Actions** work in the following way:
   - If none of the (two) checkmarks are checked, no connection will be created between the framework agreement and RFQ case – only headers of both documents will be connected. In the case of a framework agreement with multiple parts, only parts on which we are positioned before clicking “Ok” will be connected.
   - If “Automatically match existing lines” is checked, a new connection between the existing framework agreement and RFQ case lines will be created:
     - In case of Procurement categories: if same Procurement category is selected on both – framework agreement and RFQ case line or a procurement category, subordinate to the one from the framework agreement is selected on the RFQ case line;
     - In the case of Items:
       - If the same Item is specified on the framework agreement and RFQ case line;
       - If Item from the RFQ case, a line is connected with the procurement category on the framework agreement or is connected to its subordinate procurement category.
NOTE: manually connecting lines, described in the following part of this section uses the same principle for connecting the framework agreement and RFQ case lines as described above.
   - If “Create lines from selection” is checked, lines on the RFQ case are created based on the selected lines from the framework agreement (selected before clicking “Ok”). Subsequently, a connection between the newly generated RFQ case lines and framework agreement lines will be automatically created.

If connecting framework agreement to RFQ case prior to entering RFQ case lines, these lines need to be manually connected with an adequate framework agreement part. This can be done by clicking on the “Update line” and “Create link”. A new form opens with lines from the selected framework agreement part, which match with the procurement category or item from the RFQ case line. The same rules for matching the framework agreement and RFQ lines, as described above when describing the “Release from framework agreement” actions apply if lines are connected manually.

Attached (connected) framework agreement lines, connected with each line of the RFQ can also be viewed.

###Remove link between Framework agreement and RFQ

A link between the RFQ and framework agreement can also be removed – on both the header and the line level.


A new public procurement case can then be created directly from the RFQ case. This newly generated public procurement case is automatically connected with the framework agreement (or its part), connected with the originating RFQ case. All lines from the RFQ cases, connected with the same public procurement case need to be connected to a framework agreement. If connecting multiple RFQ cases to the same public procurement case, lines from all these RFQs need to be connected to the same framework agreement. Trying to add RFQ cases, connected with different framework agreements to one public procurement case will result in an error.

When RFQ(s), connected with a framework agreement is added to a public procurement case, the framework agreement is displayed in the Agreement ID field on the case.

In the “Proposed vendors” section of the public procurement case, vendors from each part (RFQ case) of the connected framework agreement are displayed. When registering tenders, connected with the public procurement case, only vendors from the “Proposed vendors” section can be registered as tenderers.
 
The rest of the public procurement procedure is the same as for any other public procurement cases and is described throughout previous sections of this document.

When tenders are accepted, the fulfilment of the referring lines from the framework agreement is updated, according to the Purchase type from the public procurement case.