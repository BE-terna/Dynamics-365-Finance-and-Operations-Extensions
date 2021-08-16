

Purpose of Fixed assets counting functionality is the automation of the Fixed assets counting process. With standard functionality, this process is performed manually, while with this feature it is possible to generate filtered counting lists, export them (to use with readers), later import the results and later perform needed actions (write off, reallocation).

The feature enables users to perform fixed asset counting. Fixed asset counting list (a list of assets from D365 to be counted), a list of counting locations (from D365 fixed asset locations register) and list of counting users (list of responsible person for all fixed assets from D365 register) can be exported from D365O as a TXT file. After the scanning procedure is done, a list of scanned fixed assets can be imported from the reader back to D365 and adequately processed.

Upon the import, information about the counting user, time, location, fixed asset name and bar code are transferred to each fixed asset from the counting list. Additionally, surpluses and assets checked for write-off are automatically marked, while missing assets have to be marked manually. Lines can also be added manually, while imported lines can also still be edited, while inadequate status. When counting status is completed, locations from the scanned locations of each fixed asset are updated on the D365O fixed asset register for each fixed asset. Additionally when in status “Completed”, write-off journal can be created automatically from a fixed asset counting list. Assets marked either as “Missing” or “Write off” will be automatically added to the write off the journal.


The feature is part of custom development in the scope of the BE-ternaSuiteFixedAssetManagement AdSuite D365O extension packet.

## **Setup**
---

### Fixed asset import/export configurations

The configuration defines a mapping for a specific data model. Separate configurations are used for import and export purposes. In the case of a Fixed asset counting feature, 5 configurations were developed. They are used for export of Fixed assets, locations and users that will be performing counting and for import of counting results.  

1. Open Organization administration - Workspaces - Electronic reporting.
2.The latest fixed asset counting format mappings need to be imported (starting with »ERAssetCountingModel_AdFAM«):
   - ERAssetCountingModel_AdFAM,
   - ERAssetCountingAssetsExportDefault_AdFAM,
   - ERAssetCountingAssetsImportDefault_AdFAM,
   - ERAssetCountingLocationsDefault_AdFAM,
   - ERAssetCountingUsersDefault_AdFAM.

### Fixed assets parameters - import/export mapping

1. Open Fixed assets > Setup > Fixed asset parameters > Electronic reporting.
2. Import/exort mappings should be selected for each reporting type. In the case of missing ER setup, an error message will appear during the process of export or import. 

### Fixed assets parameters - Barcode setup

1. Open **Fixed assets > Setup > Fixed asset parameters > Fixed asset.**
2. Go to **Barcode tab**
3. Set **Bar code equals fixed asset number** to **Yes** if Bar codes are not generated another way

## **Exports**
---

### Fixed asset counting list

1. Open Fixed assets - Periodic tasks - Fixed asset counting - Asset counting.
2. To perform the process of Fixed asset counting, the Asset counting list needs to be generated. This list is later used for export (to use with readers), matching with counting results and processing of results. 
3. Clicking »New« Fixed asset counting list is created. Fixed asset counting ID and date can then be entered.
4. »Suggest« assets open query with different filters based on which fixed assets are added to the fixed asset counting list. Filters can be used to generate separate counting lists for different sets of Fixed Assets based on location, Type, etc.
5. Fixed assets are then added to the fixed asset counting list to section Lines.
6. Fixed assets can also be added/removed manually.<br>

A date validation exists: on a specific date, each fixed asset number can exist only in one fixed asset counting list. If the condition is not met, a warning is displayed:
 
7. A fixed asset counting list can be exported to a ».txt« file which can be used with barcode scanners. File structure depends on the scanner type and software, which means that the export/import configuration might need some modifications to align file structure with a specific scanner. 
8. Once exported, fixed asset counting list status changes from »Draft« to »In progress«. Fixed assets cannot be added to the list and the list cannot be re-exported while in this status. Status can be manually changed in the »Status« section (not recommended).
 
### Fixed asset locations

1. Open Fixed assets - Periodic tasks - Fixed asset counting - Export asset locations.
2. A list of fixed asset locations can be exported to the ».txt« file. Locations can also be filtered.
 
#### Fixed asset counting users

1. Open Fixed assets - Periodic tasks - Fixed asset counting - Export asset counting users.
2. It is possible to export a ».txt« file containing fixed assets counting users. Filtering can be done by User ID and/or Worker name. Only users linked with workers can be exported.

## **Import and processing**
---

While fixed asset counting list is in status »In progress«, files with counting results can be imported. Import configuration might need some modifications, depending on the scanner type and software. <br>
Importing is performed by clicking on the »Import« button and choosing a file to be imported. After import, counting list status changes to »Partially counted«. 

Fields: counted location, counted asset barcode, Name, counted (date and time), User and Write off are populated at the time of import. All counted Fixed Assets are marked as Counted.
 
If all the assets from the list were counted, counting list status can be manually changed to »Fully counted«.
 
If »Counted location« from the imported file does not exist in the D365 register of fixed asset locations, a warning is displayed, and an additional warning icon is displayed in the source line.
 
Button »Show log« displays all warnings and errors.
 
If a fixed asset has been scanned on a different location (existing in the system), a new location is displayed in the “Counted location” field. This information is transferred to the fixed asset record once the fixed asset counting list is in status »Completed«.
 
In case when an imported fixed asset cannot be connected (via Barcode) with an existing asset from D365, it is marked as a surplus (checkmark in the “Surplus” column). Fixed assets are also marked as a surplus if it does not exist on the fixed asset counting list prior to data import (even if it exists in D365 FA register).
 
In case of a missing fixed asset, a checkmark in the “Missing” column should be manually entered. Information about the missing asset is transferred to the fixed asset record in D365 once the fixed asset counting list reaches status »Completed«. Fields »Counted« and »User« are populated with a User ID of the user who marked fixed assets as missing and date & time of the marking.

If it is decided that a certain fixed asset is to be written off, a checkmark in the field »Write off« should be selected. For fixed assets with this checkmark, a write off journal can then be created directly from the counting list, by pressing the button »Create journal«. Write off procedure is described in the last chapter.
A fixed asset list can be manually edited. Upon entering information to each line, fields »User« and »Counted« are populated with the information about the user, who manually adjusted the line and date and time of entering changes.
 
## **Write off journal**
---

After processing the list, a responsible person has the ability to overview the list. When done, the status of the counting list should be manually changed to »Overviewed«. After fixed asset counting is completed, status should be manually changed to »Completed«. At this point, a write off journal can be created by pressing the button »Create journal«. The counting list number is automatically filled out when creating the journal. Additionally - journal name, posting profile and date should be specified. 

A message, with the created journal number, is displayed. Additionally, the Created journal number is displayed in the »Created journal« field in the counting list header.

 Lines from the list, marked as »Write off« are then automatically transferred to a newly created journal. The created journal can be accessed:
   - with a click on the journal number (FA counting list header) opens the journal, created for that counting list or
   -  through the standard Fixed asset journal form as any other fixed asset journal.

A fixed asset write off journal can then be overviewed and posted.

 
In case if the journal is deleted, the journal batch number on the fixed asset counting header in the field »Created journal« is also deleted.