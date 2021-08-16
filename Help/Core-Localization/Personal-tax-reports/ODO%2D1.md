ODO-1 report needs to be generated in case of payment to non-residents. 



## **Setup**
---

### General ledger parameters

1. Open **General ledger > Ledger setup > General ledger parameters > BE-terna localization**.
2. Select **ODO1 report** configuration in ODO 1 electronic reporting format field. 
 
 
### Sales tax authorities

1. Open **Tax > Indirect taxes > Sales tax > Sales tax authorities**.
2. Create new **Tax authority** for personal tax reporting purposes.
3. In the **Vendor account** field select vendor FURS. Tax payments will be later posted to this account.
4. In the field **Report layout** select value **Default**.

### Sales tax settlement periods

1. Open **Tax > Indirect taxes > Sales tax > Sales tax settlement periods**.
2. Create new **Tax settlement period** for ODO-1 reporting. 
3. In the **Authority** field select authority that was created for personal tax reporting purposes. 
4. In the **Period interval unit** select interval that will be used for reporting.  

### Ledger posting groups

1. Open **Tax > Setup > Sales tax > Ledger posting groups**.
2. Create new **Ledger posting group** for posting tax transactions (main account defined in field “Sales tax receivable”). There is no need to set up a Settlement account since closing the period will post ODO-1 entries to the vendor, defined as tax authority on sales tax settlement period for ODO-1. 


### Income types 

1. Open **Tax > Setup > Adriatic > Personal tax > Income types**.
2. Create new ODO-1 reporting **Income type** 

### Sales tax codes

1. Open **Tax > Indirect taxes > Sales tax > Sales tax codes**
2. Create new **Sales tax code**
2. Select **Settlement period** and **Ledger posting group** for ODO-1 reporting
3. Select ODO-1 value in **Pesonal tax reporting** field
4. Select appropriate **Income type**

Sales tax codes are created for **deductions**, calculated from gross amount, as well as for **contributions** to gross. For correct calculation of deductions from gross the functionality of negative tax is used on those sales tax codes that define deductions from gross. Enabling field “Allow negative sales tax percentage” allows the entry of negative sales tax code value.  


When entering the value for income tax it is important to enter also potential **personal exemption**, **tax allowances**, and **contributions** that reduce the basis for calculation.  There are additional fields in form Value (“Personal tax” part) that are considered for the calculation for income tax percentage.  
 
**“Personal tax” section**: 
- field **Value** should be entered in negative amount for income tax; 
- fields **Personal exemption**, **Tax allowances** and **Contributions**  are left empty. 

  

#####	Payment setup

Payment section of the BE-terna localization tab on sales tax codes enables entry of **payment data**, such as Vendor account (Slovenian tax authority FURS, in our case), Bank account to which the payment of personal tax will be executed, Payment ID, and Central bank purpose code. Entered data are transferred to the **vendor journal payment** line using the Payment proposal.
 
### Sales tax groups

1. Open **Tax > Indirect taxes > Sales tax > Sales tax groups**.
2. Add adequate sales tax codes to sales tax groups.
 
### Item sales tax groups

1. Open **Tax > Indirect taxes > Sales tax > Item sales tax groups**.
2. Create item sales tax group for each ODO-1 income type and add adequate sales tax codes. 
 
### Procurement categories

1. Open **Procurement and sourcing > Procurement categories**.
2. Create a **Procurement category** for each income type and define the **Item sales tax group**. 
3. Go to **Inventory management > Setup > Posting > Posting** and set **Ledger accounts** for new Procurement categories.   
 
If the cost of contract work is posted via the vendor invoice, the ledger account setup is done under “Purchase expenditure for expense” transaction type. In case product receipts are used, posting setup also needs to be done in the “Purchase expenditure, un-invoiced” section.

### Vendor Tax identification number
Tax identification number is needed when ODO-1 report is generated. If the number is missing, error message will appear. To enter Tax identification number: 
1. Go to **Accounts payable > Vendors > All Vendors** and select specific vendor
2. Go to **Registration** section and select **Registration ID's** option.
3. When Registration ID's form opens, go to **Registration ID tab** and enter **Tax registration ID**. Make sure that appropriate registration type is available.

_Note: Field Tax registration number exists on Vendor account, but it can be used only for Slovenian Vendors/Persons, since it is validated against Slovenian rules for Tax registration number structure. In case of foreign Tax registration number validation will fail. This is why Registration ID's option is applicable in these cases._   
 

### Vendor certifications

1. Certificates regarding reliefs or international conventions are entered on **Vendor card > button Certifications**. 
2. Mandatory fields to enter are: 
   - Certification type and Certification number,
   - Certifying organizations (e.g. Slovenian tax authority or Ministry for culture),
   - Certification date. 
3. If Certification type is chosen on sales tax code and a certificate for the same certification type is entered on the vendor, then the certificate number is recorded in REK-2 field D11. 

## **Generate ODO-1 report**
---

Tax transactions with ODO-1 setup are used for ODO-1 reporting. To generate report: 
1. Go to **Tax > Declarations > Slovenia > ODO reporting > ODO-1 > ODO-1 forms** or **Tax > Declarations > Slovenia > ODO reporting > ODO-1 > ODO-1 reporting > Read transactions** to prepare transactions for specific period.
2. Select **Reporting parameters**: 
   - From date: Starting date of reports
   - To date: Ending date of reports
   - Include transactions from unposted journals:  Yes to include unposted journals / se No to exclude unposted journals
3. Go to **Tax > Declarations > Slovenia > ODO reporting > ODO-1 > ODO-1 reporting** to see generated reports

## **Export ODO-1 report**
---

1. Go to **Tax > Declarations > Slovenia > ODO reporting > ODO-1 > ODO-1 reporting > Export to XML** to generate XML file that can be later imported into eDavki. Enter **parameters**: 
   - Document type: Select one of the values from the list
   - Receiver type: Select one of the values from the list
1. **Generate XML** with **OK**.
1. Go to Details tab > Preview** to see specific report details. 


   - 