# Import bank statement

This topic includes information about two options for bank statement import: 
- Bank statement transformations, used for mapping D365 fields with the information from bank statements (**Data management** - Option 1).
- **Electronic reporting formats** for bank statement import (Option 2). 

Following bank statement formats are supported as part of this package: 

   - Slovenia – ISO 20022 (HalcomSI)
   - Croatia – FINA
   - Serbia – Assecco (Pexim) and HalcomRS

After import, bank statements can be processed using standard D365 bank reconciliation feature or additional bank statement processing features that this package is offering.

## **Setup**

### **Setup of Data management (Option 1)**
---

### **Data management setup**

#### Create Source data format

<br>Open System administration > Workspaces > Data management > Configure data source.

It is necessary to create a new Source data format. Setup depends on the type of import file. 

Example of XML file import setup:  

|**Source name**| **Operations** | 
|--|--|
|**Source name** |XML-Element  |
|**Description**  |XML Element  |
|**Type**  |File  |
|**Default dextension**  |XML  |
|**File format**  |XML |
|**XML style**  |Element  |
|**Root document**  |Document  |
|**Language locale**  |*pick local language that you want to use  |
|**Time zone preference**  | Company or Manual |


 
### **Bank statement import setup** 

## Set up the import of HalcomSI (ISO20022) bank statements

First, you must define the bank statement format processing group for HalcomSI bank statements by using the data entity framework.
1.	Go to **Workspaces** > **Data management**.
2.	Click **Import**.
3.	Enter a name for the format, such as **BankStatementImport_SI**.
4.	Set the **Source data format** field to **XML-Element**
5.	Set the **Entity name** field to **Bank statements**.
6.	To upload the import files, click **Upload**, and then browse to select the **[SampleBankCompositeEntity.xml](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)** file that you saved earlier.
7.	After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.
8.	The Bank statements entity is a composite entity that consists of four separate entities. In the list, select **BankStatementDocumentEntity**, and then click the **View map** action.
9.	On the **Transformations** tab, click **New**.
10.	For sequence number 1, click **Upload file**, and select the **Halcom_SI.xslt** file that you saved earlier.
11.	Click **Apply transforms**

Transformations for the supported formats can be found on [**this link**](https://ad365o.visualstudio.com/AdSuite/_versionControl?path=%24%2FAdSuite%2FBankStatements%2FMain%2F10%2FMetadata%2FAdactaSuiteBankStatements%2FAdactaSuiteBankStatements%2FAxResource%2FResourceContent%2FData). 

After the format processing group is set up, the next step is to define the **bank statement format** rules for HalcomSI bank statements.
1.	Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**.
2.	Click **New**.
3.	Specify a statement format, such as **HalcomSI**.
4.	Enter a name for the format.
5.	Set the **Processing group** field to the group that you defined earlier, such as **BankStatementImport_SI**.
6.	Enable XML file option.



##Set up the import of FINA (ISO20022) bank statements

First, you must define the bank statement format processing group for FINA bank statements by using the data entity framework.

1.	Go to **Workspaces > Data management**.
2.	Click **Import**.
3.	Enter a name for the format, such as **BankStatementImport_HR**.
4.	Set the **Source data format** field to **XML-Element**
5.	Set the **Entity name** field to **Bank statements**.
6.	To upload the import files, click Upload, and then browse to select the **[SampleBankCompositeEntity.xml](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)** file that you saved earlier.
7.	After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.
8.	The Bank statements entity is a composite entity that consists of four separate entities. In the list, select **BankStatementDocumentEntity**, and then click the **View map** action.
9.	On the **Transformations** tab, click **New**.
10.	For sequence number 1, click **Upload file**, and select the **FINA_TxtToXML_HR.xslt** file that you saved earlier.
11.	For sequence number 2, click **Upload file**, and select the **FINA_XMLToRecon_HR.xslt** file that you saved earlier.
12.	Click **Apply transforms**

Transformations for the supported formats can be found on [**this link**](https://ad365o.visualstudio.com/AdSuite/_versionControl?path=%24%2FAdSuite%2FBankStatements%2FMain%2F10%2FMetadata%2FAdactaSuiteBankStatements%2FAdactaSuiteBankStatements%2FAxResource%2FResourceContent%2FData). 

After the format processing group is set up, the next step is to define the **bank statement format** rules for FINA bank statements.
1.	Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**.
2.	Click **New**.
3.	Specify a statement format, such as **FINA**.
4.	Enter a name for the format.
5.	Set the **Processing group** field to the group that you defined earlier, such as **BankStatementImport_HR**.
6.	Disable XML file option, enter File type = txt




##Set up the import of HalcomRS bank statements

First, you must define the bank statement format processing group for HalcomRS bank statements by using the data entity framework.
1.	Go to **Workspaces > Data management**.
2.	Click **Import**.
3.	Enter a name for the format, such as **BankStatementImport_RS**.
4.	Set the **Source data format** field to **XML-Element**
5.	Set the **Entity name** field to **Bank statements**.
6.	To upload the import files, click **Upload**, and then browse to select the **[SampleBankCompositeEntity.xml](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)** file that you saved earlier.
7.	After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.
8.	The Bank statements entity is a composite entity that consists of four separate entities. In the list, select **BankStatementDocumentEntity**, and then click the **View map** action.
9.	On the **Transformations** tab, click **New**.
10.	For sequence number 1, click **Upload file**, and select the **Halcom_TxtToXML_RS.xslt** file that you saved earlier.
11.	For sequence number 2, click **Upload** file, and select the **Halcom_XMLToRecon_RS.xslt** file that you saved earlier.
12.	Click **Apply transforms**

Transformations for the supported formats can be found on [**this link**](https://ad365o.visualstudio.com/AdSuite/_versionControl?path=%24%2FAdSuite%2FBankStatements%2FMain%2F10%2FMetadata%2FAdactaSuiteBankStatements%2FAdactaSuiteBankStatements%2FAxResource%2FResourceContent%2FData). 

After the format processing group is set up, the next step is to define the **bank statement format** rules for HalcomRS bank statements.
1.	Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**.
2.	Click **New**.
3.	Specify a statement format, such as **HalcomRS**.
4.	Enter a name for the format.
5.	Set the **Processing group** field to the group that you defined earlier, such as **BankStatementImport_RS**.
6.	Disable XML file option, enter File type = txt
7.	Enable Halcom RS option 



There is an additional column “Halcom RS” available, which is **specific for Serbian bank statements import**. Halcom_RS is special in a way that it generates two files for one bank statement which is then imported as .zip file. For that purpose, Halcom_RS has a checkmark in the field “Halcom RS”.

##Set up the import of AssecoRS (Pexim) bank statements

First, you must define the bank statement format processing group for AssecoRS bank statements by using the data entity framework.
1.	Go to **Workspaces > Data management**.
2.	Click **Import**.
3.	Enter a name for the format, such as **BankStatementImport_Asseco**.
4.	Set the **Source data format** field to **XML-Element**
5.	Set the **Entity name** field to **Bank statements**.
6.	To upload the import files, click **Upload**, and then browse to select the **[SampleBankCompositeEntity.xml](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)** file that you saved earlier.
7.	After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.
8.	The Bank statements entity is a composite entity that consists of four separate entities. In the list, select **BankStatementDocumentEntity**, and then click the **View map** action.
9.	On the **Transformations** tab, click **New**.
10.	For sequence number 1, click **Upload file**, and select the **Asseco_RS.xslt** file that you saved earlier.
11.	Click **Apply transforms**

Transformations for the supported formats can be found on [**this link**](https://ad365o.visualstudio.com/AdSuite/_versionControl?path=%24%2FAdSuite%2FBankStatements%2FMain%2F10%2FMetadata%2FAdactaSuiteBankStatements%2FAdactaSuiteBankStatements%2FAxResource%2FResourceContent%2FData). 

After the format processing group is set up, the next step is to define the **bank statement format** rules for AssecoRS bank statements.
1.	Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**.
2.	Click **New**.
3.	Specify a statement format, such as **AssecoRS**.
4.	Enter a name for the format.
5.	Set the **Processing group** field to the group that you defined earlier, such as **BankStatementImport_Asseco**.
6.	Enable XML file option.


### **Setup of Electronic reporting formats** 
---

### Import Electronic reporting configurations
<br>

1. Go to **Organization administraton > Workspaces > Electronic reporting**
2. Open **Adacta repository**
3. Click **Add** and **create** new configuration repository by choosing **BE-terna Suite (Bank Statements)**
4. Select repository, created in previous bullet and **Open**. 
5. **Import** all **Bank statement models**

Imported transformation files are then displayed in Electronic reporting configurations as: 
- **Camt.053 Format (AD)** for bank statements 
- **Camt.054 Format (AD)** for bank debit credit notifications


### Bank statement format setup
1. Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**
2. **Add** new **Bank statement import configuration**
3. Specify a **statement format**, such as **Camt.053**.
4. Enter a **name for the format**.
5. Enable **XML** file option.
6. Mark **Generic Electronic import format field** 
7. Select **Import configuration format**

### Bank account setup
---

Import is enabled only for bank accounts that have a checkmark in field “Advanced bank reconciliation”.
 
Once this option is enabled on a bank account it cannot be reversed (button turns inactive, grey). The optional setup is the definition of Statement format. 

### Configuration of import sources
---

It is possible to configure different sources (e.g. SharePoint) for importing bank debit credit notifications and statements to D365FO. Configuration of SharePoint is optional – they can also be entered manually or imported from PC.

To **configure SharePoint** as a statement/notification source: 
1. Go to **Organization administration > Document management > Document types**.
2. Create Document type **Inbox** for each file type (bank statement or/and notification)
2. Create Document type **Completed** for each file type (bank statement or/and notification)
2. Create Document type **Error** for each file type (bank statement or/and notification)
  
![image.png](/.attachments/image-f7e7cef3-851b-48e8-98ab-b18e70b83e63.png)

Same number of folders should be created on the **connecting SharePoint**. Each of the newly created Document types then needs to be **mapped** with the **related SharePoint folder**. To do that, enter URL address of each SharePoint folder in the **Sharepoint Address field** of the Document type setup.

Finally, **mapping of Electronic reporting sources** with **Document types** needs to be configured. 
1. Go to **Organization administration > Electronic reporting > Electronic reporting source**. 
2. Create a **new source** for each file type (one for bank statements and one for notifications). 
3. In field “**Format**” configure **Camt.054 Format (AD)** as bank notification and **Camt.053 Format (AD)** as bank statements source.
4. On each newly created Electronic reporting source **add a new File source**, enter adequate name (bank statement or notification)
5. Click on Settings  
6. Enable **SharePoint** and connect **Document types** with adequate **document categories** 

![image.png](/.attachments/image-9111f5aa-8841-4d1d-b72a-9dbad06ff1c2.png)

## **Import Bank statement**
---

Bank Statement is imported in **Cash and Bank management > Bank statement reconciliation > Bank statements > Import statement**.

At import, system checks for an **unique combination** of bank account number, SWIFT code, routing number, IBAN and currency between bank account records in D365FO and information from the statement. Therefore, import for multiple bank account records in D365FO with same bank account number, but different currencies is possible.

_NOTE: No validation exist to avoid duplicated bank statements in D365FO - same bank statement can be imported several times._

If adequate setup exists, bank statements can also be imported directly from the configured sources (SharePoint) through **Cash and bank management > Periodic tasks > Bank statements import (ER)**.


_NOTE: For Serbia, bank statement files should be zipped before import._ 
 
1. Set **Import statements for multiple bank accounts in all legal entities** to yes if you want to import statements for multiple bank accounts at once. NOTE: importing statements to multiple bank accounts in D365FO with same bank account number is not allowed. 
1. Select **Bank account** from list of bank accounts.
1. Select **Statement format**. If the format is already defined on Bank account, this field is populated automatically after choosing Bank account. During import, the system will recognize bank account based on IBAN number if it is not defined in parameters.
1. Click **Upload** 
1. Click **OK**

Bank Statement is imported when it is shown in the list of bank statements. After import, the bank statement can be validated and reconciled. 


Check **[Test Scenario](Bank-statement-import.xlsx)** for Slovenian bank statement import.
 
