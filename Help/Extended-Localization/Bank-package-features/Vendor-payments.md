# Use Vendor Payments

This section summarizes the Vendor payment features, developed in the scope of the Bank extended localization package.

## **Central bank purpose code on vendor payments**
---

The four-digit code for the purpose of payment replaces the textual description of the payment purpose. Its use is recommended for payments that follow the principles of the SEPA scheme, which allows, along with a structured reference, automatic closing of claims. 

This extended localization feature enables the transfer of Central bank purpose code from a vendor to pending vendor invoice header and then to vendor transaction. If there is no Central bank purpose code on the vendor when the vendor invoice is created, the value is transferred from Accounts payable parameters. Value in field “Central bank purpose code” on vendor payment journal line can be edited before generating the export files for the bank. If the purpose code is missing on vendor transaction upon transfer to payment journal, it is populated with Central bank purpose code value from the Vendor, if it is defined there. If not, it is transferred from Accounts payable parameters. This code is then used when generating a Vendor payment file. 

1. Open Accounts Payable – Setup – Accounts payable parameters.
2. Setup for default Central bank purpose code is added in Accounts Payable Parameters -> Setup à General -> Payments. This setup is used when creating a vendor payment export files for payment journal lines where the Central bank purpose code field is empty.  
3. Central bank purpose codes are part of standard solution setup and are defined in Cash and Bank Management – Setup – Payment Purpose Codes.  
4. Setup for default Central bank purpose code on the Vendor level can be done on the Vendor card in tab Payment.  

As part of the extended localization feature, the value from this field is transferred to: 
   - Pending vendor invoice header and then to vendor transaction (if there is no Central bank purpose code on the vendor when the vendor invoice is created, the value is transferred from Accounts payable parameters) 

Value in field “Central bank purpose code” on vendor payment journal line can be edited before generating the export files for the bank. If the purpose code is missing on vendor transaction upon transfer to payment journal, it is populated with Central bank purpose code value from the Vendor, if it is defined there. If not, it is transferred from Accounts payable parameters.  

When creating a payment journal line with Settle transactions function, Central bank purpose code (CBPC) is populated with the value from Accounts payable parameters if central bank purpose codes on marked transactions are different or from Vendor card if CBPC is missing. Some cases:  
   - CBPC on Transaction 1 equals SUPP and CBPC on Transaction 2 equals LOAN, vendor payment transaction will be created with CBPC value OTHER (setup on Accounts payable parameters) 
   - CBPC on Transaction 1 and Transaction 2 equals SUPP, the vendor payment transaction will be created with CBPC value SUPP 
   - CBPC on Transaction 1 equals SUPP and CBPC on Transaction 2 is empty, the vendor payment transaction will be created with CBPC value from Vendor. If there is no value set up on the Vendor, the value will default from setup on Accounts payable parameters. 

When creating a payment journal line with the Payment proposal function, CBPC is populated with the value from the Vendor if there is no value on the transaction (standard functionality). If the value is missing on Vendor, transactions will be generated using the CBPC setup on Accounts payable parameters.  



## **Payment purpose description**
---

This extended localization feature allows field “Payment purpose” on payment order to be populated with the value from field “Note” on vendor payment journal line. This way, users do not need to populate the payment purpose field manually, when generating vendor payments.

Localization allows field “Payment purpose” on payment order to be populated with the value from field “Note” on vendor payment journal line.  

The field can be populated manually, or automatically (with standard feature Default descriptions1). In this case set up for Vendor – payment, the vendor is needed in Organization administration - Setup - Default descriptions. 



## **Vendor payments - Export format configuration**
---

Standard electronic payment formats are enhanced with additional formats, which are commonly used in banks from the Adriatic region. 

This extended localization feature enables the setup (Methods of payments), adequate transformations and export of the locally used electronic vendor payment formats. Transformations for the following bank formats are part of this extended localization feature:
   - Slovenia – ISO 20022 (SEPA, VP70)
   - Croatia – FINA, ISO 20022
   - Serbia – Halcom, Halcom Foreign - GWS

### **Slovenia (SEPA and VP70)**

#### Export format configuration

1. Open Workspaces – Electronic reporting  Reporting configurations.
2. Choose Exchange -> Load XML file on any configuration. Based on file content it will automatically upload to correct configuration.
3. Click “Browse” and choose ISO20022 Credit transfer (SI).XML (before upload, check the latest version of this file with the developer). 
4. After the file has loaded, click OK to upload it to configuration.
5. Search for configuration “Payment model” – “ISO20022 Credit transfer” and expand it to find “ISO20022 Credit transfer (SI)”. Check for status “Completed” in tab Versions.
 
#### Payment format code sets

1. Open Accounts payable – Payment setup – Payment format code sets.
2. For correct export format, it is necessary to create exact code sets as defined below which are then chosen on methods of payment for SEPA and VP70.
 
#### Methods of payment

1. Open Accounts payable – Payment setup – Methods of payment.
2. Create separate payment methods for SEPA and VP70. Payment type has to have value “Electronic payment”. Navigate to tab File formats and enable “Generic electronic reporting”. In the field, Export format configuration chooses “ISO20022 Credit transfer (SI)”.
   - For SEPA payment order fill in the fields in tab General with the following values:
     - Local instrument: SEPA
     - Charge bearer: SLEV
     - Service level: SEPA
   - For VP70 populate fields with the following values:
     - Local instrument: VP70
     - Charge bearer: SHAR/CRED/DEBT
     - Service level: leave empty
 
Default Method of payment which carries information about payment order format and charge bearer can be set up on Vendor card in tab Payment. Method of payment is transferred to Pending vendor invoice and from there to vendor transaction and Payment journal line.
 
### **Serbia (Halcom, Halcom Foreign – GWS)**

#### Halcom domestic

1. Open Accounts payable – Payment setup – Methods of payment.
2. Create a new method of payment for Halcom domestic payments. There should be two different methods of payments for payment per invoice and for a total payment.
   - HALCOM P – payment per invoice payment order:  fill in the fields with the following values:
     - Method of payment: HALCOM P
     - Period: Invoice
     - Payment type: Electronic payment
     - Export format: Halcom (RS)
    - HALCOM Z – total payment order: fill in the fields with the following values:
     - Method of payment: HALCOM Z
     - Period: Total
     - Payment type: Electronic payment
     - Export format: Halcom (RS)
 
Default Method of payment which carries information about payment order format is set up on Vendor card in tab Payment. Method of payment is transferred to Pending vendor invoice and from there to vendor transaction and Payment journal line.
 
#### Halcom foreign GWS

In order to be able to use Halcom foreign GWS payment format, the following setup should be completed on the Method of payment.

1. Open Accounts payable – Payment setup – Methods of payment.
2. For HALCOM_FOR payment order fill in the fields with the following values:
   - Method of payment: HALCOM_FOR
   - Period: Total
   - Payment type: Electronic payment
   - Export format: HalcomForeignGWS(RS)


### **Croatia (SEPA)**


## **Payment ID validation for vendor invoice and payment journal (SI, HR)**
---

This topic provides country/region-specific information about the locally used Payment IDs, which are often mandatory information when making payments in Slovenia in Croatia. Payment IDs need to be generated according to local formats. In order to validate the payment ID form to comply with the local requirements, this extended localization feature enables adequate validation.

This extended localization feature allows the validation of payment ID for vendor invoice and payment journal is executed upon saving. Control for Payment ID on vendor invoice is additionally triggered upon document saving when the vendor bank account has country code for which validation is implemented (standard validation!). Validation can be enabled or disabled by authorized users.

1. Open **Accounts payable > Setup > Accounts payable parameters > General**.
2. **Validation** of payment ID for **vendor invoice** executed upon **saving** if “Validate payment ID” is enabled. In case of invalid Payment ID **Warning** is thrown. User can continue with Vendor entry and document can be posted.
2. **Validation** of payment ID for **payment journal** is executed upon Payment ID **entry** if “Validate payment ID” is enabled. In case of invalid Payment ID **Error** is thrown. User can not continue with process until correct Payment ID is entered or Payment ID is deleted. If Validation is disabled, Payment ID is not validated at the moment of entry. <br>
_Note: (1) Standard validation is performed when Validate or Simulate posting function is run and when journal is posted. In all those cases standard Warning is thrown, journal can be posted. (2) Custom validation is performed only when journal line is entered manually. When lines are generated with Payment proposal function, custom validation is not performed._
3. Control for Payment ID on vendor invoice is additionally triggered upon document saving when the vendor bank account has country code for which validation is implemented (standard validation!). 
4. Control in vendor payment journal is executed if “Validate payment ID” is enabled regardless of the vendor bank account. 
 
A payment ID is entered manually in purchase documents or on vendor payment journal line before posting. As part of extended localization **controls are added for models** SI00, SI01, SI02, SI03, SI04, SI05, SI06, SI07, SI08, SI09, SI10, SI11, SI12, SI18, SI19, SI28, SI38, SI40, SI41, SI48, SI49, SI51, SI55, SI58, SI99, HR01, HR02, HR03, HR04, HR05, HR06, HR07, HR08, HR09, HR10, HR11. If the entered value is wrong, the system will generate a warning.<br>
For other (foreign) models standard validations are used.<br>

Check **[Test Scenario](Vendor-Payments-Test-Scenario.zip)* for vendor payments.



## **Payment reference generation**
---

This topic provides country/region-specific information about the locally used Reference numbers, which are often mandatory information when making payments. Reference numbers need to be generated according to locally accepted formats. In order to simplify and automate Payment reference generation in an adequate form, this extended localization feature has been developed.

This extended localization feature enables the automatic generation of payment references for vendor payments through vendor payment journal. The payment reference number is generated upon XML creation and captured in the “Payment reference” field of each of the payment journal lines. The payment reference form depends on the XML export format.

Upon generating payments from the vendor payment journal, the payment reference number is generated upon XML creation and written to field “Payment reference”

### SEPA (SI)

For SEPA payment orders, payment reference for regular payments is generated in the following form:
   - RF + control number + RI + Record ID of payment line
 
“Referenca plačnika” field in e-banking is populated with this value.
 
Batch booking (MP SEPA)

In case “Batch booking is used”, Payment reference is generated for all lines in the batch in the following form:
   - RF + control number + RIMP + Record ID of first payment line in batch
 
### VP70 (SI)

If the VP70 payment order is used, payment reference is generated in the following form:
   - Record ID of the payment line
 
Field “Referenca uporabnika” in payment order is populated with this value upon XML upload.
 
Check **[Test Scenario](Vendor-Payments-Test-Scenario.zip)** for payment reference.
 

