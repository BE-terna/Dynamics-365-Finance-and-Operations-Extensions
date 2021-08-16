# Validate Tax exempt numbers (VIES database)

This extended localization feature makes it possible to validate values entered in “Tax exempt number” field on customer and vendor accounts and through the Tax-exempt numbers form with an online VIES database.

VIES is an electronic means of transmitting information related to VAT registration of companies registered in the European Union.  When the user needs to verify the VAT number of companies from another Member State through VIES on the web, this request will be sent, to the relevant national database to check if the given number is valid. If yes, the "Valid" status will be displayed. If not, the "Invalid" status will be displayed.

## **Validation** 
---

It is possible to validate values entered in “Tax exempt number” field on customer and vendor accounts and through the Tax-exempt numbers form. 

Entered Tax exempt number can be validated by clicking on the “Check VIES online” button. After the checking: 
   - “Check status” field is populated with validation result (valid/Invalid); 
   - “Last check” field displays the information about the last checking performed; 
   - An informational message with the checking results is displayed. If the number has been identified in the VIES database, Status: Valid, name and the address of the customer are displayed. 

In case of a Tax exempt number, nonexistent in the VIES database, Check status is displayed as “Invalid”. Additionally, a warning is displayed as shown in the photo below. 



The testing procedure, added fields, and display messages are the same for customer and vendor accounts. 

## Tax exempt numbers form 

Tax exempt number form displays Tax exempt numbers from the VIES database. Three columns are available: 
   - Country/region, 
   - Tax exempt number,
   - Company name. 

Selecting each line and clicking on the “Check VIES online” will perform the same Tax exempt number validity check as if the checking is performed through the Vendor/Customer account:
   - If Tax exempt number is valid than Status is shown as Valid.
   - In case of a Tax exempt number, nonexistent in VIES database Status is shown as Invalid.