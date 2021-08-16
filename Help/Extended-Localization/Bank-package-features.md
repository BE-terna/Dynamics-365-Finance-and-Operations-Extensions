This section summarizes the additionally developed bank features, in scope of the LOC_BANK extended localization package.

----

# Vendor payments

This section summarizes the Vendor payment features, developed in the scope of the Bank extended localization package.

[Detailed documentation](/Help/Extended-Localization/Bank-package-features/Vendor-payments)

----

# Payment ID generation (SI, HR)

This topic provides country/region-specific information about the locally used Payment IDs, which are often mandatory information when making payments in Slovenia in Croatia. Payment IDs need to be generated according to local formats. In order to simplify and automate Payment ID generation in an adequate form, this extended localization feature has been developed.

Payment ID can be generated for outgoing documents if enabled so in Accounts receivable parameters. This extended localization feature also enables users to set different rules for generating payment IDs for all customers, customer groups, or individual customers; for different types of transactions and billing classifications. For documents, issued in Slovenia, the calculation of reference number is supported for the following models: SI00, SI01, SI02, SI03, SI04, SI05, SI06, SI07, SI08, SI09, SI10, SI11, SI12, SI18, SI19, SI28, SI38, SI40, SI41, SI48, SI49, SI51, SI55, SI58, and SI99. After invoice posting, the model is simply copied from the settings, the control number is calculated depending on the model. The control number for the RF model for invoices within the EU is also calculated upon invoice posting. It depends on the reference number, which is allocated after the invoice posting.

[Detailed documentation](/Help/Extended-Localization/Bank-package-features/Payment-ID-generation-\(SI,-HR\))

----

# IBAN control numbers

The feature allows the Bank group and data from Bank group defaulting upon entering IBAN.

This extended localization feature enables additional localization fields “IBAN control number” and “SWIFT code” on bank group form. Entering IBAN on partner, employee or company bank account enables automatic transfer of data from related bank groups. After entering IBAN code on the bank account, fields Name, Bank groups, SWIFT code, and Address are automatically populated with data from the corresponding bank group (if entered in bank group form).

[Detailed documentation](/Help/Extended-Localization/Bank-package-features/IBAN-control-numbers)

----

# Default bank account

This topic includes information about the preferred bank account of the legal entity from which inflows and outflows are preferred to be paid/received.

In terms of inflows (customers), the feature is added so that information about the preferred bank account of the legal entity regarding the expected inflows from customers can be defined on the customer group level. When creating a new customer, when entering the Customer group, the default bank account from the customer group is transferred to the newly created customer. When creating sales documents (Sales quotation, Sales order, Sales invoice, and FTI), this company bank account is transferred from the customer to the sales documents. The bank account to which the company wants to receive inflows in connection with the document should be specified. This bank account is transferred to the following documents if they exist (e.g. from sales order to invoice), but it can also be manually changed on each sales document. Bank account information is also transferred to the document printout and open customer transaction when documents are posted.

In terms of outflows - each vendor bank account can be mapped to a specific company bank account from which payment should later be proposed. Preferred bank account from which outflows for each specific vendor should be paid can be set on each of the vendor’s bank accounts. Information about the specified bank account can be used during payment proposal preparation in the presence of an adequate setup.

[Detailed documentation](/Help/Extended-Localization/Bank-package-features/Default-bank-account)


----
# Additional exchange rate providers

As standard D365 functionality does not support some of the locally used exchange rate providers, often requested by local companies, this extended localization feature enables the most commonly used providers within the region.

The following additional exchange rates providers are available as part of this localization package: Bank of Slovenia, Croatian national bank, National bank of Serbia and National bank of Macedonia. Exchange rates from the listed providers can then be imported and used throughout D365 using standard features.

[Detailed documentation](/Help/Extended-Localization/Bank-package-features/Additional-exchange-rate-providers)

