# Exercise 2: Register the custom extension for dynamic approval
To request assignment to the *SAP BTP Developer* group, an access package is created that uses an existing logic app to find the approver based on the request context. You will use the Microsoft Entra admin center with a preview feature flag enabled for *dynamic approval* to configure the access package, starting with the registration of the logic app as a custom extension in your catalog. 

**Duration:** 5 minutes.

| Step   | Description     | Screenshot          |
| :----- | :-------------- | :-----------------: |
| 2.1    |Use the existing browser window to sign-in to [Microsoft Entra admin center](https://aka.ms/EMApprovalExtensibility) (use the link [https://aka.ms/EMApprovalExtensibility](https://aka.ms/EMApprovalExtensibility)!) with your user user\<41..70\>@bestruncorp.onmicrosoft.com. |<a href="./img/2-1.jpg" target="_blank"><img src="./img/2-1.jpg" width="250"/></a>|
| 2.2    |You are prompted for MFA to login to the Entra Admin Center.|<a href="./img/2-2.jpg" target="_blank"><img src="./img/2-2.jpg" width="250"/></a>|
| 2.3    |Enter the number in your Microsoft Authenticator.|<a href="./img/2-3.jpg" target="_blank"><img src="./img/2-3.jpg" width="250"/></a>|
| 2.4    |Select **Catalogs** from the navigation menu. In the search bar, enter your *Student*-number. Select the catalog **Student\<41..80\>** with the number assigned to you from the list.|<a href="./img/2-4.jpg" target="_blank"><img src="./img/2-4.jpg" width="250"/></a>|
| 2.5    |Select **Custom extensions** from the navigation menu.<br><br>Click **+ Add a custom extension**.|<a href="./img/2-5.jpg" target="_blank"><img src="./img/2-5.jpg" width="250"/></a>|
| 2.6    |On the first page **Basics** of the wizard, provide a name (*DynamicApprover*) and description.<br><br>Click **Next: Extension Type**.|<a href="./img/2-6.jpg" target="_blank"><img src="./img/2-6.jpg" width="250"/></a>|
| 2.7    |Keep the default selection and click **Next: Extension Configuration**.|<a href="./img/2-7.jpg" target="_blank"><img src="./img/2-7.jpg" width="250"/></a>|
| 2.8   |Select **Launch and wait** for the *Behaviour* of the new extension, and **Approval Stage (Preview)** for the *Response data*. Keep the expiration to 5 minutes.<br><br>Click **Next: Details**.|<a href="./img/2-8.jpg" target="_blank"><img src="./img/2-8.jpg" width="250"/></a>|
| 2.9   |Select **No** for the switch to *Create a logic app*. You will use an existing logic app already deployed to the Entra tenant as follows:<br><br>**Subscription**: *Visual Studio Enterprise Abonnement*<br><br>**Resource Group**: *SAPEntra-RG*<br><br>**Logic App**: *DynamicApprover*<br><br>Click **Next:Review + create**.|<a href="./img/2-9.jpg" target="_blank"><img src="./img/2-9.jpg" width="250"/></a>|
| 2.10   |Click **Create**.|<a href="./img/2-10.jpg" target="_blank"><img src="./img/2-10.jpg" width="250"/></a>|
| 2.11   |Go to **Roles and administrators**.<br><br>Click **+ Add access package assignment manager**.|<a href="./img/2-11.jpg" target="_blank"><img src="./img/2-11.jpg" width="250"/></a>|
| 2.12   |In the search bar, enter *DynamicApprover**. Switch to the **Enterprise applications** tab and activate the checkbox for the DynamicApprover enterprise app in the search results.<br><br>Click **Select**.|<a href="./img/2-12.jpg" target="_blank"><img src="./img/2-12.jpg" width="250"/></a>|

Continue with [exercise 3](../ex3/ex3.md), or go back to the [overview](../README.md).
