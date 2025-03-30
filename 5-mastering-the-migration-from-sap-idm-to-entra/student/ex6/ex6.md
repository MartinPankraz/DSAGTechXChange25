# Exercise 6: Test access to SAP Business Application Studio
Now that the request has been approved, the user is assigned to the resources specified in the access package, i.e. the *SAP BTP Developer* group.
By accessing SAP Business Application Studio, the user is delegated to the SAP Identity Authentication Service tenant, which proxies the request to the corporate IDP, Microsoft Entra. After successful authentication, Entra emits the user token containing the group membership for *SAP BTP Developer*. The group ID is mapped to the required role in BTP which now permits access. 

**Duration:** 5 minutes.

| Step   | Description     | Screenshot          |
| :----- | :-------------- | :-----------------: |
| 6.1    |Start a new **incognito browser window**.<br><br>Open the URL ```https://4478e7a5trial.ap21cf.trial.applicationstudio.cloud.sap/```.<br><br>Pick your user *user\<41..70\>@bestruncorp.onmicrosoft.com* from the list.|<a href="./img/6-1.jpg" target="_blank"><img src="./img/6-1.jpg" width="250"/></a>|
| 6.2    |Click **Next**.|<a href="./img/6-2.jpg" target="_blank"><img src="./img/6-2.jpg" width="250"/></a>|
| 6.3    |Click **Skip setup**.|<a href="./img/6-3.jpg" target="_blank"><img src="./img/6-3.jpg" width="250"/></a>|
| 6.4    |With the group membership approved and assigned to your user, access to SAP Business Application Studio is now granted.<br><br>**Close** the incognito window.|<a href="./img/6-4.jpg" target="_blank"><img src="./img/6-4.jpg" width="250"/></a>|

Congratulations! You've successfully completed the hands-on session. If you want to explore more IDM workflow and customization options with Microsoft Entra, continue with the optional [exercise 7](../ex7/ex7.md), or go back to the [overview](../README.md).
