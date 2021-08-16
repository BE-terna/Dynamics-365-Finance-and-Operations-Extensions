# Public Holidays

Standard D365O functionality allows adding a calendar to a customer (receipt calendars), vendor (purchase calendars), warehouse, coverage group, resource (work center). Calendars can also be used in payroll, master planning, and manufacturing. They define working times (working days) and allow calculation of capacity for resources of the legal entity. With this feature, the standard functionality is enhanced with an option to add public holidays to working times and payment calendars. The feature is especially useful for entering local public holidays, which are not working days.

The feature is part of  BE-ternaPublicHolidays AdSuite D365O extension.

##**Setup**
---

### Public holidays calendar setup

1. Open Organization administration > Setup > Calendars > Public holiday calendars.
2. Create a new public holiday. Navigate to button Public holidays to enter work-free holidays.
3. Create a new entry, enter Holiday identification and Name. Under tab General enter calculation data. Options for calculation:


|**Parameter**|**Description** |
|--|--|
|None|no calculation is offered for this type of holiday.  |
|Fixed|enter Month and Day on which the holiday always occurs.  |
|First weekday after|define Month and Day, and select Weekday on which holiday occurs.  |
|Easter|allows user to specify offset days (e.g. Easter Monday occurs 1 day after Easter).  |
|Manual|new tab “Dates” is displayed, which allows users to enter any date.  |
   
4. Using button Preview allows users to view which day the selected holiday will fall due on.
5. Enter From date and To date to define a period of interest for the selected holiday.
 
 
### Calculate working calendar

1. Open Organization administration > Setup > Calendars > Calendars. 
2. See Working times for the selected calendar.
3. On the toolbar, select Add public holidays to add holidays to the selected calendar.
4. In the Calendar field, select the name of the calendar to add holidays to. In the From date field, enter the first date to add holidays to. By default, the field contains the current date. In the To date field, enter the last date to add holidays to. By default, the field contains a date that is one year from the current date. In the Holiday calendar field, select the appropriate calendar.
 
Column Holiday is populated with checkmarks whenever there is a holiday day. Notice that holidays are also automatically marked as Closed for pickup days.
 
### Payment calendar

1. Open Accounts payable > Payment setup > Payment calendar or Accounts receivable > Payments setup > Payment calendar.
2. It is also possible to add public holidays to payment calendars. The new button “Add public holidays” is added to tab Exception days. 
3. Add public holidays parameters:
   - Calendar is populated by default with the value of the payment calendar.
   - From date, To date: start year date and end year date for the value in field Filter to the calendar year
   - Holiday calendar: select public holiday calendar
   - Update existing holidays: select Yes if existing holidays are to be updated with new values
   - Update existing business days:  select Yes if an existing business day is to be updated with new values
4. After confirming, public holidays are added to Exception days. 
 
