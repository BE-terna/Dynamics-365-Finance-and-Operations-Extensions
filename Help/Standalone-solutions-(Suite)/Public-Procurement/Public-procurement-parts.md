# Public procurement parts


Public procurement parts refer to requests for quotation (RFQ) cases, which are used as input documents to successfully perform public procurement procedures. Throughout the following chapter, required setup, prerequisites, and additionally developed functionalities, required for an adequate RFQs creation for the purpose of public procurement procedures are presented.

## **Request for quotation case enhancements**
---

RFQ cases are used as inputs (parts) of public procurement cases, described separately. Although RFQ cases are standard D365O functionality, some additional enhancements are added for the purpose of public procurement procedures. These enhancements are described throughout the following paragraphs.

Public procurement functionality adds the “Public procurement” section in the RFQ case header. This section contains »Case ID« and »Description« fields, which are populated with the public procurement case ID and description once the RFQ case is connected with the procurement case. Additionally, information in the »Expected date of finality« and »Final« checkmark display information about the connected case finality:
 
Once created, RFQ cases can be added to either a new or an existing public procedure case, using the “Create case” or “Add to case” actions: 
 
If RFQ case is to be connected to a public procurement case, its purchase type should be either “Purchase order” or “Purchase agreement”, depending on the desired document, created because of the related public procurement case.
 
For the purpose of public procurement procedures in D365O, RFQ cases should only contain lines with the ordering goods/services. Proposed vendors should not be defined directly on each RFQ case, but directly on public procurement case, which is described later throughout this document (chapter 2.4.8). 
All other processes (e.g. sending RFQs or entering vendor replies to RFQ cases) are also performed directly from the public procurement case and are not supposed to be performed through RFQ case form.