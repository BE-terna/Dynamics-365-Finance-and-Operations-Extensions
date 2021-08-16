With this functuionallity users can import Vendor invoice lines for specific Vendors. Currently import of invoices for following Vendors is supported: 
- Petrol
- OMV
- Elektro Energija
- Telekom
- A1

##**Setup**
---

###**Transformation setup**

1.	Go to **System administration > Workspaces > Data management**
2.	Click »Import« and create a **new import project**. 
3.	Specify **Group name** and click on “Add file” to **add a file**, which defines structure, required to import vendor invoice lines to D365O. _NOTE: to obtain the entity, you can first create an export project and download “Import invoice lines” entity._

|Field|Action|
|--|--|
|Entity name| Entity to which files will be imported: »Imported invoice lines«;|
|Source data format| File format structure: “XML-Element”|
|Upload data file|“Imported invoice line” D365O entity – the required structure for importing invoice line to D365O, which can be obtained by exporting »Imported invoice lines« entity.|
4.	When upload is completed, close the dialog, and click on **View map** icon to see mapping between the source and staging files
5.	Then click on**Transformations** ribbon to upload and apply the XML transformation between the structure of external invoice file and invoice lines structure in D365O. Make sure to use the actual transformation files (ask developer for an adequate versions) or use the ones provided in this link.
6.	Create a new line, click on »Upload file« and select the transformation file from your PC. When upload is completed click on **Apply transforms**, to apply the uploaded transformation!
_NOTE: Procedure described throughout this chapter needs to be repeated for each specific invoice transformation (e.g. A1, Telekom, and OMW). Separate import projects have to be created for each specific invoice format, desired to be imported to D365O._

###**Import identification group**
Prior to importing vendor invoice lines, Identification groups have to be set. Allowed vendors for each group can be specified - e.g. group »Telecom« for vendors SLO-001 (Telekom Slovenije, d.d.) and SLO-002 (A1 Slovenija, d.d.) for telecommunication services. This way product groups for each vendor are defined. Additionally, it is possible to select the Default (Item) sales tax group for each Import identification group.
1.	Go to **Accounts payable > Setup > Invoice specification import > Import identification group**
2.	Add new Import identification group with button **New**
3.	Enter Identification group name, description and add allowed vendors.

##**Import and processing**
---

###**Import vendor invoice lines**
1.	Go to System administration > Workspaces > Data management > Import projects.
2.	Select an adequate project, and click on **Run project**
3.	Click on **Upload file**, browse for the invoices to be imported and click **Upload**. When upload is completed click **Import** to start the import process. Once completed, Execution summary indicates how many lines were added/updated and whether any errors exist. Informational messages connected with the import process are also displayed.
4.	Clicking on **View staging data** a list of uploaded lines can be viewed. If import process has been completed with errors, by clicking **View execution log**, details about the errors can be overviewed.

###**View imported invoice lines**
1.	Go to **Accounts payable > Inquiries and reports > Imported invoice lines**

Uploaded invoice lines are matched with vendor's account in D365O according to the VAT ID information from the imported vendor invoice and “Tax exempt number” from vendors register in D365O.

Button **Update parameters** uses the same processing as when importing invoices through Data management project. It is recommended in cases when any information has been added to D365O, after invoice lines had been imported. For example: 
- if Tax exempt number on vendor has been changed after importing the invoice lines for that vendor;
- after configuring consumer definitions to transfer Service definition groups defined in the consumer definition form to the imported invoice lines;
- prior to setting up Service definitions, to transfer Service IDs from the imported invoice lines to the Service definition form.

###**Consumer definition**
1.	Go to **Accounts payable > Setup > Invoice specification setup > Consumer definition**

By selecting Vendor account, Consumer ID values from imported invoice are automatically transferred to the list below. In case of invoices from Telekom and A1, consumer is represented by his phone number, which is displayed in »Consumer ID« field for each invoice line.

It is possible to define Worker and/or Project for each of the imported invoice lines. This is applicable, e.g. if legal entity has vehicles opened as projects and would like to record maintenance costs per vehicle. Additionally, default financial dimensions for each Consumer ID can be set. This data is then later defaulted to the vendor invoice lines in D365O.

In field **Identification group** an adequate group should be selected for each Consumer ID when uploading an invoice for the first time.
After Identification groups for each Consumer ID are entered, “Imported vendor invoices form” should be updated. This applies adequate Service identification groups to each of the imported lines and can be done by clicking on **Update parameters** button in: **Accounts payable > Inquiries and reports > Imported invoice lines**

###**Service definition**
Service definitions represent the content of each invoice line - define goods/services from the imported invoice lines. New Service definitions can be created by clicking “New” and selecting an adequate vendor.
1.	Go to **Accounts payable > Setup > Invoice specification import > Service definition**

To obtain the adequate Service IDs, »Service ID« field can be updated with values from the imported invoice lines, which can be done by clicking **Update parameters** button in the Imported invoice lines form. This feature transfers all the existing Service IDs from imported vendor invoice lines to “Service ID” column in the Service definitions form, according to the matching vendor account from both forms (e.g. SLO-002).

Each Service ID can then be connected with an adequate Procurement category, which will be transferred to the vendor invoice lines, once the imported lines are transferred to the invoice. In addition to Procurement category, default Unit and Item sales tax groups can be entered for each Service ID.
The "Create Missing" button adds the remaining Identification groups, existent for a specific vendor. Newly created records are created with the Item tax group value, Specified as default on the Identification group.

##**Create vendor invoice lines**
---

To import invoice lines, it is necessary to create the header of the invoice with the correctly specified vendor from D365O register and invoice number from the imported vendor invoice.
By clicking **Import lines** and then **Related lines** in Lines section of the invoice, based on the Invoice account and Invoice number, imported vendor invoice lines will be transferred to the invoice.
Lines can be transferred to the invoice in two ways:
-	**Summary**: if there are more services, which are linked with the same Procurement category, invoice lines will be summarized based on the following criterion: Procurement category, Financial dimensions, Item sales tax number, Project (Project ID) and Sign of the amount (+/-)
-	**Detailed**: for each line from the specification (imported vendor invoice), one invoice line in D365O will be created

In case of a large number of lines, that need to be transferred to the invoice it is also possible to set Batch processing.

When line transfer is completed, informational message about the number of transferred lines and lines with errors is displayed. Lines are transferred to the invoice.

Item sales tax group is transferred from the Service definitions form for the invoicing vendor.

Lines, which are already transferred to an existing vendor invoice in D365O cannot be transferred again. If the transfer procedure is required to be repeated, existing lines need to be deleted first. 
After invoice lines are posted, it is no longer possible to transfer them to vendor invoice in D365O.



