
## **Per Diem enhancements**
---

Additional features regarding per diems are added:

   - In terms of standard D365O functionality meal reduction for each meal in connection with per diem need to be entered as a percentage of the full per diem. This feature, however, enables that if field "Include percent" is marked, meal deductions will be calculated according to the value entered in field Meal percent. Otherwise, the deduction has to be entered as a percentage of full per-diem (e.g.  15% breakfast reduction for half per diem is calculated from the amount representing 75% of the full per diem).
   - Per diem transaction date on Expense reports can be defaulted from the last per diem day if the option is enabled in Expense management parameters.

### **Per diem rate tiers: Include percent setup**

1. Open **Expense management > Setup > Calculations and codes > Per diems > Per diem rate tiers**.

2. Localization column “Include percent” is added to the form for per diem rate tiers setup. 

| **Value** | **Description** |
|--|--|
| field "Include percent" is marked |meal reductions will be calculated according to the value entered in field Meal percent, which represents the percentage of full daily allowance, defined in field Meals (e.g. 15% breakfast reduction for half perdiem is calculated from the amount representing 75% of the full perdiem).  |
| field “include percent” is not marked|it is necessary to adjust the percentages of meal reductions in relation to the full perdiem – reductions for meals have to be entered as percentages of full perdiem (e.g. reduction for breakfast for half perdiem represents 11.25% of the full perdiem).  |

 
 
Check **[Test Scenario](Travel-and-Expenses-Test-Scenario.zip)**. - Depricated!
 
### 	**Per diem transaction date on last day**

#### Expense management parameters

1. Open Expense management > Setup > General > Expense management parameters > BE-terna (expense).
2. Per diem transaction date can be set up on the last per diem day by enabling the feature in Expense management parameters. 
 
#### Transaction date on an expense report

1. Open Expense management > My expenses > Expense reports.
2. Upon saving the expense line “Per diem”, the Transaction date is automatically populated with the value from the field “Per diem to date”. 