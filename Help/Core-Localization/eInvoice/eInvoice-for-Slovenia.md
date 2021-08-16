# eInvoices for Slovenia

This topic provides country/region-specific information about how to set up, create and export eInvoices in order to comply with Slovenian legislation. eInovices can be generated for folowing docuemnt types: 
- Free text invoice / Credit note
- Sales invoice / Credit note
- Project invoice / Credit note
- Advance invoice / Credit note (only for SI)

Supported providers: 
- SI: UJP, Halcom, ZZI
- CRO:  

## **Setup**
---



### Export format configuration

1. Open **Workspaces > Electronic reporting > Reporting configurations**.
2. Choose **Exchange > Load **[XML file](e-Invoices-SI.zip)**** on any configuration. Based on file content it will automatically upload to correct configuration. Before upload, check the latest version of these files with the developer.
3. Click **Browse** and choose the attached files (be sure to upload the Customer invoice model (AD).xml first because the following ones are dependent on it). After the file is loaded, click OK to upload it to configuration.
4. Search for configuration “Customer invoice model (AdLoc)” and expand it to find Project invoice – eSlog 2.0 (SI) and Sales invoice – eSlog 2.0 (SI). Check for status “Completed” in tab Versions.
 
### Electronic invoice parameters

1. Open **Accounts receivables > Setup > Slovenia > E-Invoices > Electronic invoice parameters**.
2. Following eInvoice parameters are set up under tab **General**:

|Parameter|Description|
|--|--|
|**Create envelope**|enable or disable to generate envelope upon eInvoice export or sending.|
|**Automatic sending of eInvoices**| When enabled, zip/XML file will automatically be downloaded, after XML is created (function Create XML). When disabled, zip/XML file will be downloaded with seperate action (Send).|
|**Bank account**|Company bank account for received customer payments (validation upon SWIFT and IBAN is executed in eInvoice registry), that will be used for eInvoices.  |
|**Default unit of measure**|Value in this field is transferred to eInvoice when the unit is not defined on customer invoice. There is no field “Unit” on Free text invoice so in this case the value in this field is always transferred to eInvoice).|
|**Download eInvoice as archive**|If set to Yes, ZIP file will be generated with eInvoice files (invoice, envelope, and customized visualization). Important: visualization of the document is not part of this localized feature and needs to be implemented during project implementation.  |
|**Electronic signature**|**Mandatory**: created eInvoices need to be signed with electronic signature using an appropriate valid certificate. <br>**Optional**: if a valid certificate is available, eInvoices are automatically signed if “Automatic electronic signing of eInvoice” is enabled. Otherwise, the user manually signs eInvoice in the registry. EInvoice can also be sent without a signature. <br>**Disabled**: eInvoice can be sent without an electronic signature.  |
|**Automatic electronic signing of eInvoices**|If set to Yes, eInvoice will be automatically signed. If Electronic signature option Disabled is chosen, this parameter is disabled. |
  
  
   
3. Go to **Profile** section, create Profile ID and choose adequate Electronic reporting configurations for Sales and Free text invoice, Sales and Free text credit note, Project invoice, Project credit note, Advance invoice and Advance invoice Credit note.

4. Go to **Number sequences** section and define number sequence code for eInvoice unique file name. 
 
 
 
### External codes

1. Open **Organization administration > Setup > Units > Units > Choose unit of measure > External codes**.
2. In Overview segment add Code=eRacun, external code definition=eRacun; Mark field Standard code
2. In Value segment **Map** standard **eInvoice units** of measure to D365FO units that will be used on customer invoices (e.g. D365FO unit “pcs” is defined in eInvoice documentation as “pce”). This is done through External codes, where External code definition and Code both have to be named “eRacun” in order for validation to be successful.
 

 
###  Certificate

1. Open **Accounts receivable > Setup > Electronic signature certificates**.
2. **Add** Electronic signature certificate. For testing purposes, it is possible to define a certificate for the electronic signature of eInvoices.
 
### Customer setup - profile ID

1. Go to Accounts receivable > Customers > All customers > Open specific customer > go to Invoice and delivery tab > Profile ID. 
2. Choose “Profile ID” from list. Profile ID defines eInvoice structure.   
2. **Mandatory data** such as name, address, tax exempt or tax registration number, ID number, and default bank account (and IBAN and SWIFT for that bank account) are being validated in the eInvoice registry upon creating XML (more on that below).

_Note: **Leave** parameters **eInvoice** and **eInvoice envelope** set to **No**, since these parameters enable standard eInvoice functionality._

### Customer setup - Taxable person type
 
1. Go to **Accounts receivable > Customers > All customers > Select Customer > Invoice and delivery tab**
1. Select **Taxable person type** from drop-down menu. Available options: 
   - Legal entity
   - Sole proprietor
   - Natural person

_Note: This setup **affects validation** of **Tax registration number** (Davčna številka) and **Registration number** (Matična številka), when eInovice is generated. When Type Natural person is selected, those two are optional. When Sole proprietor or Legal entity is selected both, Tax registration number and Registration number are mandatory._ 

## **eInvoice registry**
---

### **Electronic customer invoices**

1. Open **Accounts receivable > Invoices > E-Invoices > Electronic customer invoices**.
2. **Posting** Sales or Free text invoices for customers with Profile ID **automatically generates eInvoice**.
3. Go to **Accounts receivable > Invoices > E-Invoices > Electronic customer invoices** where all generated einvoices can be found. Created eInvoice can be found in customer eInvoices registry with status “New”. 
4. With action **Create XML**, file is generated. With action **Sign**, file can be signed and with action **Send**, file is downloaded. 
5. Create XML function executes **validation** of the following parameters:
   - LEGAL ENTITY ACCOUNT INFORMATION (name, a bank account with IBAN and SWIFT; address with country, city and ZIP code)
   - INVOICING AND DELIVERY CUSTOMER ACCOUNT INFORMATION (name, a bank account with IBAN and SWIFT; address with country, city and ZIP code)
   - Tax exempt or tax identification number and company identification number on both customer and legal entity (NOTE: adequate registration categories must be selected for each of the required registration IDs: Tax identification number (AD), Company registration number (AD), VAT ID (if VAT ID is entered in Registration IDs)
   - Invoice ID
   - Unit of measure for on invoice used units or a default unit of measure with adequate set up external codes (value for external code must be “eRacun” or validation fails) 
   - Purpose code (either on customer transaction or on legal entity
   - External codes for on invoice used Units of measure or Default unit of measure
   - Currency code

   If any of the listed parameters are missing, the system throws an error and XML is not created. 
 
6. If validation is successful, status is changed to **Created**, eInvoice unique file name is generated as defined in the number sequence. 
7. The XML file is created and stored in the field **Outgoing XML** in **tab Details**. Here, more information about eInvoice is displayed, including a unique file name, details about the user, creating date, and signature data. 
8. If **Automatic electronic signing of eInvoice** is enabled in eInvoice parameters, eInvoice is automatically signed after XML creation. 
9. After XML has been created, buttons **Create signature** and **Send** are enabled. **Status** is changed to **Created** or **Sent**, depending on Automatic sending of eInvoices parameter. If parameter is set to Yes, status is changed to Sent. If parameter is set to No, status is changed to Created. 
10. Using **Create signature** changes status to **Signed** (applicable only if Automatic sending of eInvoices parameter is set to No). With action **Send** status is changed to **Sent**.  
11. **Multi select** is also enabled for actions. Mark multiple eInvoices with a checkmark and select appropriate action.
12. Using the action **Export** or **Send**, envelope (if enabled in parameters) and eInvoice are downloaded to the selected directory (first, select location for the envelope and save, then the select location for eInvoice and save). If **Export** action is used, status stays the same. Status is changed to Sent after using the action **Send**.
13. eInvoice can be exported only after creation of XML (e.g. status must be higher then **New** or **Not ready**).
 
Check **[Test Scenario](e-Invoices-SI.zip)**.
 
### **Electronic project invoices**

1. Open **Accounts receivable > Invoices > E-Invoices > Electronic project invoices**.
2. **Posting** invoice proposal for customers with Profile ID **automatically generates eInvoice**.
3. Go to **Accounts receivable > Invoices > E-Invoices > Electronic project invoices** where all generated einvoices can be found. Created eInvoice can be found in Project eInvoices registry with status “New”. 

Project eInvoices are subject to the same procedures and actions as described in chapter Electronic customer invoices. 

Check **[Test Scenario](e-Invoices-SI.zip)**.

###**Electronic Advance invoices**

1. Open **Accounts receivable > Invoices > E-Invoices > Electronic advance invoices**.
2. **Posting** Advance invoices for customers with Profile ID **automatically generates eInvoice**.
3. Go to **Accounts receivable > Invoices > E-Invoices > Electronic advance invoices** where all generated einvoices can be found. Created eInvoice can be found in Advance eInvoices registry with status “New”. 
4. With action **Create XML**, file is generated. With action **Sign**, file can be signed and with action **Send**, file is downloaded. 
5. Create XML function executes **validation** of the following parameters:
   - LEGAL ENTITY ACCOUNT INFORMATION (name, a bank account with IBAN and SWIFT; address with country, city and ZIP code)
   - INVOICING AND DELIVERY CUSTOMER ACCOUNT INFORMATION (name, a bank account with IBAN and SWIFT; address with country, city and ZIP code)
   - Tax exempt or tax identification number and company identification number on both customer and legal entity (NOTE: adequate registration categories must be selected for each of the required registration IDs: Tax identification number (AD), Company registration number (AD), VAT ID (if VAT ID is entered in Registration IDs)
   - Invoice ID
   - Unit of measure for on invoice used units or a default unit of measure with adequate set up external codes (value for external code must be “eRacun” or validation fails) 
   - Purpose code (either on customer transaction or on legal entity
   - External codes for on invoice used Units of measure or Default unit of measure
   - Currency code

   If any of the listed parameters are missing, the system throws an error and XML is not created. 
 
6. If validation is successful, status is changed to **Created**, eInvoice unique file name is generated as defined in the number sequence. 
7. The XML file is created and stored in the field **Outgoing XML** in **tab Details**. Here, more information about eInvoice is displayed, including a unique file name, details about the user, creating date, and signature data. 
8. If **Automatic electronic signing of eInvoice** is enabled in eInvoice parameters, eInvoice is automatically signed after XML creation. 
9. After XML has been created, buttons **Create signature** and **Send** are enabled. **Status** is changed to **Created** or **Sent**, depending on Automatic sending of eInvoices parameter. If parameter is set to Yes, status is changed to Sent. If parameter is set to No, status is changed to Created. 
10. Using **Create signature** changes status to **Signed** (applicable only if Automatic sending of eInvoices parameter is set to No). With action **Send** status is changed to **Sent**.  
11. **Multi select** is also enabled for actions. Mark multiple eInvoices with a checkmark and select appropriate action.
12. Using the action **Export** or **Send**, envelope (if enabled in parameters) and eInvoice are downloaded to the selected directory (first, select location for the envelope and save, then the select location for eInvoice and save). If **Export** action is used, status stays the same. Status is changed to Sent after using the action **Send**.
13. eInvoice can be exported only after creation of XML (e.g. status must be higher then **New** or **Not ready**).
 

### **Subsequent creation of eInvoices**

1. Open **Accounts receivable > Invoices > E-Invoices > Electronic customer/project invoices > button “Select”**
2. **EInvoices** can be subsequently generated according to selected filters for already posted invoices or invoices deleted from eInvoice registry for the customer with adequate Profile ID. Navigate to button **Select** and define Criteria for the subsequent creation of eInvoices. 
 
3. After confirming, subsequent eInvoices are **created** with status **Not ready**.
 
4. Proceed with the same steps and actions as described in the chapters above. 

Check **[Test Scenario](e-Invoices-SI.zip)**.

## **Additional information regarding Tax number and VAT number recording in XML file**
--- 
Following rules regarding Tax and VAT number of receiver and issuer are implemented, according to National forum for e-invoice: 

###**Case 1: Issuer is identified for VAT purposes (has VAT number)**
VAT number (Tax exempt number/ID za DDV) is recorded under BT-31 and BT-32<br>
![image.png](/.attachments/image-1c7aa7cb-4553-4865-9200-7b1d2339b845.png)

###**Case 2: Issuer is NOT identified for VAT purposes (has only Tax number)**
Tax number (Davčna številka) is recorded under BT-32<br>
![image.png](/.attachments/image-3d06d57c-db77-46c9-95f9-892bcf27cc33.png)

###**Case 3: Receiver is identified for VAT purposes (has VAT number)**
VAT number (Tax exempt number/ID za DDV) is recorded under BT-48 and NBT-013<br>
![image.png](/.attachments/image-9caa1ca4-1233-4f64-80da-bf5217fe39f6.png)

###**Case 4: Receiver is NOT identified for VAT purposes (has only Tax number)**
Tax number (Davčna številka) is recorded under BT-32<br>
![image.png](/.attachments/image-fd3a5cd9-da6e-4de3-aeb8-93cc130690f2.png)