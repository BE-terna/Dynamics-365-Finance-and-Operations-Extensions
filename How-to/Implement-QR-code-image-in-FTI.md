QR code is generated as part of Fiscalization package. Below are the instructions for using generated image in Free text invoice printout. 

QR code image in PNG format is saved as binary in container field named FiscalizationQRCode_AdLocFisc.

![image.png](/.attachments/image-605ce1cd-b778-4e81-a783-30fb1a0b7f25.png)

When you refresh report data source you can see this field.

![image.png](/.attachments/image-52ad2039-a9a8-4c53-8e82-cf6063bbabf5.png)

In the report design add image.

![image.png](/.attachments/image-ae99ca10-fe3d-43c6-b152-3eb3291de9c5.png)
 

Set image source as Database and use field from this data source where QR code image is. (e.g. =First(Fields!FiscalizationQRCode_AdLocFisc.Value, "FreeTextInvoiceHeaderFooterDS"))

![image.png](/.attachments/image-5b18e1d4-64e0-4007-acbb-df2ca205249d.png)
 

Keep image size as required (QR kod for Croatian invoices is required to be in size 2x2 cm and empty space arround QR code needs to be at least 2 mm).

The principle is the same for all the other documents, the difference is only in ReportDataProvider and associated temp table. 
