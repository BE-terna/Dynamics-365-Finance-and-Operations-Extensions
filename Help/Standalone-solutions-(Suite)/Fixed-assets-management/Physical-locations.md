The purpose of functionality is to enable hierarchy among locations, which is not supported by standard functionality. 

The benefit of physical locations is that they have hierarchical structure, meaning that each location can have its parent location and sublocations, which is not possible with standard locations. In addition, physical locations functionality allows adding locations which are a part of a tree structure only and do not represent actual physical location. Physical locations can also be activated and deactivated multiple times.  

## **Setup**
---

### Activate Physical locations

First, Physical locations need to be enabled. 
1. Go to **Fixed assets > Setup > Fixed assets parameters > Fixed assets tab**
1. Set **Activate physical locations** to **Yes** to enable physical locations.
_Note: If user enables Physical location, standard locations are not available any more._ 


## **Use physical locations**
---

### Enter physical locations

1. Go to **Fixed assets > Setup > Fixed asset attributes > Physical locations**
1. Add new Physical location with **New**. Following fields are available. 

|**Field**  | **Description** |
|--|--|
| **Physical location** |ID of the Physical location.  |
| **Physical location name**  | Description of the Physical location |
| **Active** | Defines whether location is available or not. When Physical location is deactivated it is no longer available for use.  |
| **Parent location** |Parent location of the physical location.  |
| **Location** |Indicates whether this location represents a physical location or not. Only physical locations marked with Yes can be selected on Fixed asset, Lending Form or Asset Counting. If a physical location marked with No is selected, warning message is shown.  |
| **ID path**  | Is generated automatically |
|  **Name path**  |Is generated automatically  |

Tree structure of the created physical locations can be seen in the left menu. Above the tree structure, there is a drop-down menu that shows a list of all physical locations. 

### Select physical locations on Fixed Asset

1. Go to **Fixed assets > Fixed assets > Fixed assets > select specific Fixed asset**
1. Open **Location fast tab**.
1. Select **Physical location** from drop-down menu. Physical location path will be populated automatically.

_Note: Physical location drop-down menu offers only **active physical locations**. If **Activate physical location** in Fixed asset parameters is set to No, standard location field will be shown in the Location fast tab instead of Physical location field._ 

### Select physical locations on Lending record

1. Go to **Fixed assets > Fixed assets > Fixed assets > select specific Fixed asset > Lend**
1. Add **new** lending record
1. Select **Physical location** from drop-down menu

_Note: Selection of Physical location on Lending record **does not affect Physical location on Fixed asset card**, which has to be changed **manually**. Physical location drop-down menu offers only **active physical locations**. If **Activate physical location** in Fixed asset parameters is set to No, standard location field will be shown in the Location fast tab instead of Physical location field._ 


### Select physical locations on Fixed asset counting form

1. Go to **Fixed assets > Periodic tasks > Fixed asset counting > Asset counting**
1. Generate **new** Asset counting record with button New
1. **Suggest** new counting lines (recommended) or **Add lines** manually
1. Each line is populated with **Original location from Fixed asset**. If the physical location field on the fixed asset is blank, original location is also left blank.
1. **Counted location** is populated as result of fixed asset counting process - manually or with import

_Note: Physical location drop-down menu offers only **active physical locations**. If **Activate physical location** in Fixed asset parameters is set to No, standard location field will be shown in the Location fast tab instead of Physical location field._ 

