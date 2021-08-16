## Purchase agreement enhancements

### Requester
---

An additional field “Requester” has been added to the purchase agreement header to allow the specification of an employee who has requested the creation of a specific purchase agreement. Field Requester allows the selection from the list of all employees.
 
This additional field allows for the person in the field to be included in the vendor invoice review process if adequate participant provider is selected in the workflow configuration.

### Purchase agreement type
---

For further differentiation of purchase agreements an additional field “Purchase agreement type” has been implemented to determine whether an agreement is an Annex or a stand-alone agreement. Possible values for selection in the field are Agreement and Annex. 
 
If Annex is selected, a new field "Related to agreement" activates (more in the next chapter).
 
### Related to agreement
---

In relation to the “Purchase agreement type” field, an additional one – Related to an agreement – has been added to the purchase agreement header. This feature allows establishing a relation between an original purchase agreement and its annex. 

Related to the agreement field is active only when the Purchase agreement type selected is “Annex”. It allows the selection of all existing purchase agreements from all legal entities that are of type “Agreement”. 
 
### Disable editing of effective purchase agreements
---

Standard functionality allows for data on the purchase agreement to be edited regardless of document status. To prevent changes in Effective status, additional functionality is implemented. 

Navigate to Procurement and sourcing - Setup - Procurement and sourcing parameters – tab General -> Select Yes in the Disable editing of effective purchase agreements field.
 
When this parameter is set to Yes, a purchase agreement is locked for editing when in status Effective.
 
When the status is set to On hold, the agreement fields become active for editing.
 
### Change classification
---

Standard functionality does not allow for purchase agreement classification to be changed (once the record is saved, the field becomes unavailable for editing).
 
With procurement enhancements, it is possible to change the classification if no related Invoice lines or Release order lines exist. Navigate to action pane, button Change classification.
 
Select the desired purchase agreement classification from the drop-down.
 
Confirm the selection.
 
The value in field Purchase agreement classification is changed.
 
Once the related Invoice lines or Release order lines exist, the button Change classification is no longer available.
 
The ability to change classification is also affected by the Disable editing of effective purchase agreements parameter (if the parameter is set to Yes and the agreement is in status Effective, the button to change classification is locked for selection even though there are no related Invoice lines or Release order lines). 