# Exercise 6: Test access to SAP Business Application Studio
Now that the request has been approved, the user is assigned to the resources specified in the access package, i.e. the *SAP BTP Developer* group.
By accessing SAP Business Application Studio, the user is delegated to the SAP Identity Authentication Service tenant, which proxies the request to the corporate IDP, Microsoft Entra. After successful authentication, Entra emits the user token containing the group membership for *SAP BTP Developer*. The group ID is mapped to the required role in BTP which now permits access. 

| Step   | Description     | Screenshot          |
| :----- | :-------------- | :-----------------: |
| 6.1    |Lorem Ipsum      |<a href="./img/6-1.jpg" target="_blank"><img src="./img/6-1.jpg" width="250"/></a>|
| 6.2    |Lorem Ipsum      |<a href="./img/6-2.jpg" target="_blank"><img src="./img/6-2.jpg" width="250"/></a>|
| 6.3    |Lorem Ipsum      |<a href="./img/6-3.jpg" target="_blank"><img src="./img/6-3.jpg" width="250"/></a>|
| 6.4    |Lorem Ipsum      |<a href="./img/6-4.jpg" target="_blank"><img src="./img/6-4.jpg" width="250"/></a>|

Congratulations! You've successfully completed the hands-on session. If you want to explore more IDM workflow and customization options with Microsoft Entra, continue with the optional [exercise 7](../ex7/ex7.md).