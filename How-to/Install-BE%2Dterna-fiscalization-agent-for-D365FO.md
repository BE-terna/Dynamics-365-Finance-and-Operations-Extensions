BE-terna fiscalization agent is an application that is installed as a windows service under NETWORK SERVICE or user account and it is used as middleware between D365FO and Tring fiscal printer.


# **Installation**
___

**Installation prerequisite:** 
-	.Net Framework version 4.0
-	Application registration on Azure process is finished

Download latest application from:
-	[Fisclization agent release]( https://erp-releases.adacta-group.com/b/adaxreleases?path=adloc%2F10.0%2FAdLocExt%2F) and open **adactafiscalizationagentd365fo.zip**

If direct link doesn’t work, please copy link and paste it into the internet browser. After download make sure that zip file is unblocked:

![image.png](/.attachments/image-85932e1e-a06e-4cb6-b5ea-99b258788064.png)


Unzip downloaded files from AdactaFiscalizationAgentD365FO\AdactaFiscalizationAgent\bin\Release to the installation directory:
-	C:\Adacta\AdactaFiscalizationAgentD365FO
Make sure that installation folder has proper user rights:
![image.png](/.attachments/image-1680c317-b1c8-44cd-a0b3-c7204baf1177.png)

In installation directory you can find **configuration files** that need to be configured for every service instance. Before running **service App.SECRETS.config** should be configured with D365 parameters. Brief config key explanation can be found below.

Config file (AdactaFiscalizationAgentD365FO.exe.config):
-	key="ServiceName" – Name of the service that will be taken in the process of installation
-	key="DisplayName" – Display name of the service that will be taken in the process of installation
-	key="TimerInterval" – Time interval in millisecond between fiscalization process occurs 
-	key="NumOfRows" – number of rows per one cycle of fiscalization process
-	key="TLSVersion" – TLS version, live blank to use default version
-	key="TringFiscalServerPort" – Tring fiscal server port (default 8085)
-	key="TringFiscalServerIP" – IP address of Tring fiscal server (default localhost)
-	key="TringOperator" – Tring operator ID (default 0)
-	key="TringPassword" – Tring operator password (default 0)
-	key=”StaticInvoiceItemNumber” – Invoice item number that will be used when creating invoice using tax transactions (grouped, used in wholesale mode). You can use {0} in string that will be changed with line number and {1} that will be changed with voucher number in runtime. (Default {0})
-	key=”StaticInvoiceItemName” – Invoice item that will be used when creating invoice using tax transactions (grouped, used in wholesale mode). You can use {0} in string that will be changed with the tax value and {1} that will be changed with line number. (Default Stavke po fakturi PDV {0}%)
-	key=”StaticInvoiceUnitOfMeasure” – Unit of measure that will be used when creating invoice using tax transactions (grouped, used in wholesale mode). (Default ko)
-	key=”StaticNapomenaReklamniRacun” – note on the receipt when sending credit note
-	key=” StaticNapomenaRacun” – note on the receipt when sending invoice
-	key=” DefaultMethodOfPayment” – Default method of payment that will be used when creating invoice using tax transactions (grouped, used in wholesale mode) if there is no method of payment set on fiscalization document. Possible values are: Cek, Gotovina, Kartica, Virman; (Default Virman)
-	key=”D365CustInvoiceJourTableId” – Table number for the CustInvoiceJour table from D365FO (Default 2579)
-	key=”D365ProjInvoiceJourTableId” – Table number for the ProjInvoiceJour table from the D365FO (Default 9966)
-	key=”ServiceUserName” – user name if service needs to be installed to run under user credentials
-	key=”ServiceUserPassword” – user password if service needs to be installed to run under user credentials
Config file (App.SECRETS.config), used for secrets:
-	key="ActiveDirectoryResource" – Resource value that is configured in AppRegistration process on Azure portal
-	key="ActiveDirectoryTenant" – Tenant ID as URI  https://login.microsoftonline.com/TenantID
-	key="ActiveDirectoryClientAppId" – Client ID from AppRegistration process on Azure portal
-	key="ActiveDirectoryClientAppSecret" – Client secret value from AppRegistration process on Azure portal
-	key="ServiceUserName" – username that will be used in installation of windows service
-	key="ServiceUserPassword" – password for username that will be used in installation of windows service
-	key="UriString" – URI of environment (like: https://usnconeboxax1aos.cloud.onebox.dynamics.com)

Before you proceed with the installation please **populate needed configuration in App.SECRETS.config** file using text editor (Notepad, Notepad++ etc.) and **configure user** in D365FO that will be used for the communication (see chapter D365 configuration and Application registration process)

Use install or uninstall command to install or uninstall service (install.bat and uninstall.bat script files are included in the zip file):
-	c:\windows\microsoft.net\framework\v4.0.30319\InstallUtil.exe<br> 
"C:\Adacta\AdactaFiscalizationAgentD365FO\AdactaFiscalizationAgentD365FO.exe" **to install**
-	c:\windows\microsoft.net\framework\v4.0.30319\InstallUtil.exe /u<br> 
" C:\Adacta\AdactaFiscalizationAgentD365FO\AdactaFiscalizationAgentD365FO.exe" **to uninstall**

Run script or CMD **as administrator**.

To check if services is installed and running check services on the server:
![image.png](/.attachments/image-636e382c-acf8-428a-b378-ae569fe944f0.png)

Services should be in status: Running to enable fiscalization process. To check logs of the service use windows Event viewer. 

# **Configuration**
---

User that is connected to the Fiscalization agent Client ID needs special permissions:
-	Fiscalization integration agent

ONLY **Default company on D365FO user** is used to retrieve fiscalization data so be sure to configure right company on user level.
Client ID of BE-terna fiscalization agent must be connected to the user account in D365 to enable communication between the fiscalization agent and D365 application (check: Azure Active Directory applications form): 
![image.png](/.attachments/image-61b55297-9ce9-4b64-8f3e-2bf561fb284b.png)

# **Application registration**
---

For the application registration process please refer to the online documentation:
-	[Register an app with Azure Active Directory](https://docs.microsoft.com/en-us/powerapps/developer/data-platform/walkthrough-register-app-azure-active-directory)

For redirect URL use your environment URL and add Dynamics ERP under Microsoft API permissions.
After application registration is finished you will get 
-	Client ID 
-	Client secret

This information is needed to be populated in application configuration file.
You need one Client ID and Client secret to access **TEST environment** and another one to access **PRODUCTION environment** so please take this in to account when creating app registration.
