## Purchase requisition and request for quotation enhancements

The procurement process usually begins with Purchase requisitions (PRs) – a standard D365O feature. However, some enhancements in connection with PRs are made for the purpose of the more efficient procurement process. These enhancements are described throughout the following chapters.

### Allow change of purchase type
---

When RFQ cases are created from PRs, their purchase type is “Purchase requisition” and cannot be changed. The purchase type on RFQs is important, as it defines the outcome (document) that is to be created at the end. Since standard D365O functionality does not allow the change of purchase type on RFQ cases, which were created from PRs, the below-described functionality has been added to allow that.

Open Procurement and sourcing - Setup - Procurement and sourcing parameters.
 
By enabling the “Allow change of purchase type” setting, purchase type on RFQs created from PRs can be manually changed, as long as PR is in status “In review”. Available values in the field:
   - Purchase order
   - Purchase agreement
   - Framework agreement  
 
If “Allow change of purchase type” is enabled, standard Purchase type field on RFQ header is always locked for editing (greyed out):
 
Changing purchase type on RFQ case manually is not allowed if:
   - standard D365O conditions for locking the field are met or
   - RFQ is connected with the public procurement case (available only in AdSuite_Public Procurement package)

 
### Auto approve the purchase requisition
---

Using this setting, when creating RFQ(s) out of PR(s) with purchase type either “Purchase order” or “Purchase agreement”, after accepting/rejecting all the PR lines, PR is auto-approved – PR header and line status automatically changes to “Closed”. Auto-approval is generated in the name of the user, who performed the acceptance/rejection of the last remaining unprocessed PR line. Auto-approval can be enabled in:

Open Procurement and sourcing - Setup - Procurement and sourcing parameters -> tab Request for quotation, field Auto approve purchase requisition.
 
Reason for using this functionality is to avoid leaving PRs, related to RFQ(s), in review, but instead closing them once all the lines have been either accepted or rejected. When vendor tenders related to all lines from PR are either accepted or rejected, PR status (header and lines) changes to “Closed”.
 
This feature prevents releasing already accepted/rejected PR lines to a purchase order through the standard “Release approved purchase requisitions” functionality and therefore prevents duplicated purchase orders or purchase orders referring to the same PR lines.
