# HCalculate interest for a day (Actual year)

Standard D365O feature in terms of the interest calculation allows calculating daily interests but does not account for the leap years, as it considers all years equally long.

This localization feature enables an additional interest calculation type “Day (Actual year)”, which recalculates the interest amount. It considers the actual number of days in each year, including the leap years. Calculation type ”Day (Actual year)” calculates interest according to the following formula:

interest rate = amount * (annual interest rate / number of days in a calendar year) * number of overdue days

## **Interest calculation formula**
---

As BE-terna localization feature new interest calculation type “Day (Actual year)” is added, which also includes leap years.  
 
The interest calculation formula for this period:

Amount x Annual interest rate / Actual Calendar days x Days overdue.

If this calculation is selected, it is important that the interest code **effective dates for one version start and end within the same year**. Otherwise, the calculation of interest returns an error about the start and end date.
 
Check **[Test Scenario](Interest-calculation-type-test-case.xlsx)**.
 
