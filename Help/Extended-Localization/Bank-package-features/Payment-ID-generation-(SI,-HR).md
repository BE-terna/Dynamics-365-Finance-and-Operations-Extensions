# Generate Payment ID

This topic provides country/region-specific information about the locally used Payment IDs, which are often mandatory information when making payments in Slovenia in Croatia. Payment IDs need to be generated according to local formats. In order to simplify and automate Payment ID generation in an adequate form, this extended localization feature has been developed.

Payment ID can be generated for outgoing documents if enabled so in Accounts receivable parameters. This extended localization feature also enables users to set different rules for generating payment IDs for all customers, customer groups, or individual customers; for different types of transactions and billing classifications. For documents, issued in Slovenia, the calculation of reference number is supported for the following models: SI00, SI01, SI02, SI03, SI04, SI05, SI06, SI07, SI08, SI09, SI10, SI11, SI12, SI18, SI19, SI28, SI38, SI40, SI41, SI48, SI49, SI51, SI55, SI58, and SI99. After invoice posting, the model is simply copied from the settings, the control number is calculated depending on the model. The control number for the RF model for invoices within the EU is also calculated upon invoice posting. It depends on the reference number, which is allocated after the invoice posting.

## **Setup**
---

On the sales side, payment ID is generated based on the settings specified in accounts receivable parameters.

1. Open Accounts receivable – Accounts receivable parameters – General.
2. A checkmark in the field “Generate payment ID” enables the generation of Payment ID. Button “Rules for payment ID generation” opens set up for generation rules. It is possible to set different rules for generating payment IDs for all customers, customer groups, or individual customers; for different types of transactions and billing classifications. 
 
For documents, issued in Slovenia, the calculation of the reference number is supported for the following models: 
   - SI00, SI01, SI02, SI03, SI04, SI05, SI06, SI07, SI08, SI09, SI10, SI11, SI12, SI18, SI19, 
   - SI28, 
   - SI38, 
   - SI40, SI41, SI48, SI49, 
   - SI51, SI55, SI58,
   - SI99. 

## **Post Invoice**
---

1. After invoice posting, the model is simply copied from the settings, the control number is calculated depending on the model. <br>
2. The control number for the RF model for invoices within the EU is also calculated upon invoice posting. It depends on the reference number, which is allocated after the invoice posting.
3. Payment ID for collection letters and interest notes is generated upon the creation of documents. 

Note: setup %2 (voucher) in field Payment ID is not an adequate setting for collection letter and interest note since it is generated before posting.
 
Check **[Test Scenario](Payment-ID-generation.zip)** for Payment ID generation.