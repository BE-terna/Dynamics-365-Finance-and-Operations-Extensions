
**Extended Localization** is a combination of custom developed features, meant to cover the Slovenian, Croatian and Serbian local specifics that are not mandatory, but are helpful. In this section, Extended Localization features are summarized through several sub-sections, based on the business context.

NOTE: a prerequisite for using Extended Localization features is installed Core Localization package.



## Tax package:
---
|**Tax Package Features _(LOC_TAX)_**| **SI** |**CRO**  | **RS** | **Description** | **Note** |
|--|--|--|--|--|--|-|--|
|[Import SI taxable persons](/Help/Extended-Localization/Tax-package-features/Import-of-Slovenian-taxable-persons-SI)  | • |  |  |Import of SI taxable persons  | |
|[Validate Tax exempt numbers](/Help/Extended-Localization/Tax-package-features/Validate-Tax-exempt-numbers-VIES-database)  |•  | • | • | It is possible to validate  VAT numbers with VIES checker. |   |
|[Update customer information](/Help/Extended-Localization/Tax-package-features/Update-customer-information-based-on-Tax-exempt-number-SI) | • |  |  |It is possible to generate new customer based on VAT number.  |   |
|[Settlement period closing](/Help/Extended-Localization/Tax-package-features/Closing-of-Settlement-period) | • | • | • |It is possible to close Settlement periods for posting  |   |
|[Defaulting VAT date and VAT payable date](/Help/Extended-Localization/Tax-package-features/Defaulting-VAT-date-and-VAT-payable-date)  |•  | • | • |It is possible to default VAT payable and receivable dates according to setup.  |   |

<br>

## Bank package
---

|**Bank Package Features _(LOC_BANK)_**| **SI** |**CRO**  | **RS** | **Description** | **Note** |
|--|--|--|--|--|--|-|--|
|[Vendor Payments export](/Help/Extended-Localization/Bank-package-features/Vendor-payments)  |•  |•  |•  | - Additional export formats: ISO20022 SI (Domestic, VP70), ISO20022 HR, Pexim, Halcom, Halcom foreign.<br> - Payment reference is generated when generating export formats<br> -  Central bank purpose code setup is added to AP parameters and can be used when generating vendor payments.<br> - Payment purpose<br> - Payment ID validation  |   |
|[Payment ID in Accounts receivable](/Help/Extended-Localization/Bank-package-features/Payment-ID-generation-\(SI,-HR\))  |•  | • |  |Payment ID can be generated for outgoing documents. Rules for structure can be defined.  |   |
|[Bank Groups](/Help/Extended-Localization/Bank-package-features/IBAN-control-numbers)  | • | • |•  |Defaulting of Bank group and data from Bank group  upon entering IBAN  |  |
|[Company Bank Account](/Help/Extended-Localization/Bank-package-features/Default-bank-account)  | • |•  |•  |Company bank account for payments can be defaulted  on Customer and Vendor side.<br> Customer: Bank account for received payments can be defaulted on customer. Information can be used for generating Invoice printouts<br>Vendor: bank account for vendor payments can be defaulted on Vendor Bank Accounts. Each Vendor Bank Account can have defaulted Bank Account from which payment will be performed.  |  |

<br>

## Additional Exchange rate providers package
---

|**Additional Exchange rate providers _(LOC_EXCHANGE RATES)_**| **SI** |**CRO**  | **RS** | **Description** | **Note** |
|--|--|--|--|--|--|-|--|
|[Exchange rates import providers](/Help/Extended-Localization/Additional-exchange-rate-providers)  |•  |•  |•  |Following exchange rates providers are available as part of loc features: Bank of Slovenia,  Croatian national banka and National bank of Serbia  |  |

<br>

## Additional General Ledger package
---

|**Additional General Ledger Features _(LOC_LEDGER)_**| **SI** |**CRO**  | **RS** | **Description** | **Note** |
|--|--|--|--|--|--|-|--|
|[Journalize tax as parent line](/Help/Extended-Localization/General-Ledger-features/Journalize-tax-as-parent-line)  | • | • | • |Functionality enables posting tax to the same offset account as the line from which the tax is derived.  ||  |
|[Year-end procedure enhancements](/Help/Extended-Localization/General-Ledger-features/Year-end-procedure-enhancements)  |•  |•  | • |Functionality enables balancing Main account balance with Ledger account balance in order to avoid opening transactions in cases where Ledger account balance equals zero and Main account balance does not.    | |

<br>

## Fiscalization package
---

|**Fiscalization _(LOC_FISCALIZATION)_**| **SI** |**CRO**  | **RS** | **Description** | **Note** |
|--|--|--|--|--|--|-|--|
|[Fiscal number sequence](/Help/Extended-Localization/Fiscalization-\(SI,-HR\))  |•  |•  |  |Generating number sequence on sales documents (Sales Invoice, Free text invoice, Project Invoice, Prepayment invoice) according to the Fiscal law.   |  |
|[Communication with Tax authority](/Help/Extended-Localization/Fiscalization-\(SI,-HR\))  |  |•  |  |Communication with Tax Authority (Porezna) to exchange fiscal numbers for sales documents (Sales Invoice, Free text invoice, Project Invoice, Prepayment invoice) according to the Fiscal law.   |  |

<br>

## KEP package (only for Sebia)
---

|**KEP _(LOC_KEP)_**| **SI** |**CRO**  | **RS** | **Description** | **Note** |
|--|--|--|--|--|--|-|--|
|[KEP report](/Help/Extended-Localization/KEP-report,-nivelations-and-retail-calculation-\(RS\)) |  |  | • |Legally required report for retail. It includes KEP report, nivelations and retail calculation.   |    |

<br>

## Cash Register package (depricated)
---

|**Cash Register _(LOC_CASH)_**| **SI** |**CRO**  | **RS** | **Description** | **Note** |
|--|--|--|--|--|--|-|--|
|[Cash Management](/Help/Extended-Localization/Cash-Management)  |   | | |Cash register is opened as a Cash account. For Cash account is possible to setup cash posting profile and posting slip journal for cash inflows and outflows. There is possible to setup the responsible person > the main cashier, which can be printed on cash reports (Cash receipts and Cash disbursements).  |  |Not available for versions after 7.3  |