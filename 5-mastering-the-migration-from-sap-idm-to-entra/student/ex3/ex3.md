# Exercise 3: Create the access package and configure the assignment policy
With the custom extension registered in your catalog, you are now ready to create the access package and the assignment policy that uses the custom extension.<br>An assignment policy controls who can request the access package and who can approve it. In this scenario, the approver will be dynamically determined by the results returned from the custom extension. 

**Duration:** 10 minutes

| Step   | Description     | Screenshot          |
| :----- | :-------------- | :-----------------: |
| 3.1    |Navigate to **Access packages**.<br><br>Click **+ New access package**.|<a href="./img/3-1.jpg" target="_blank"><img src="./img/3-1.jpg" width="250"/></a>|
| 3.2    |On the first page of the wizard, provide a **Name** for the new access package, e.g. *BTP Student \<41..70\>.<br><br>Enter a description and click **Next: Resource roles**.|<a href="./img/3-2.jpg" target="_blank"><img src="./img/3-2.jpg" width="250"/></a>|
| 3.3    |Under **Resource roles**, click **+ Groups and Teams**.|<a href="./img/3-3.jpg" target="_blank"><img src="./img/3-3.jpg" width="250"/></a>|
| 3.4    |Activate the **checkbox** to *see all groups*. Enter *SAP BTP* in the search field.<br><br>Activate the **checkbox** for the *SAP BTP Developer* group.<br><br>Click **Select**.|<a href="./img/3-4.jpg" target="_blank"><img src="./img/3-4.jpg" width="250"/></a>|
| 3.5    |From the **Role** drop-down list, select *Member*.<br><br>Click **Next: Requests**|<a href="./img/3-5.jpg" target="_blank"><img src="./img/3-5.jpg" width="250"/></a>|
| 3.6   |Select **For users in your directory** and **Specific users and groups** for *Users who can request access*.<br><br>Click **+ Add users and groups**.|<a href="./img/3-6.jpg" target="_blank"><img src="./img/3-6.jpg" width="250"/></a>|
| 3.7   |Enter *Student \<NN\>* in the search bar.<br><br>Activate the checkbox on your user in the result list<br><br>Click **Select**.|<a href="./img/3-7.jpg" target="_blank"><img src="./img/3-7.jpg" width="250"/></a>|
| 3.8   |Switch **Require requestor justification** to *No*.<br><br>From the **First approver** drop-down list, select the *DynamicApprover* custom extension.<br><br>Switch **Require approver justification** to *No*.<br><br>Switch **Disable assignment emails** to *Yes*.<br><br>Switch **Enable new request** to *Yes*.<br><br>Click **Next: Requestor information**.|<a href="./img/3-8.jpg" target="_blank"><img src="./img/3-8.jpg" width="250"/></a>|
| 3.9   |Under **Questions**, enter *Developer role* for the first *Question*.<br><br>Select *Multiple choice* for the **Answer format**.<br><br>Activate the **Required** checkbox.<br><br>Click **Edit and localize**.|<a href="./img/3-9.jpg" target="_blank"><img src="./img/3-9.jpg" width="250"/></a>|
| 3.10   |Enter *SAP BTP* for the **Answer value**.<br><br>Select *English (United States)* as **Language**, and enter *SAP BTP* for the **Localized text**.<br><br>Click **Save**.|<a href="./img/3-10.jpg" target="_blank"><img src="./img/3-10.jpg" width="250"/></a>|
| 3.11   |Add the next **Question** and enter *Context*.<br><br>Select *Multiple choice* for the **Answer format**.<br><br>Activate the **Required** checkbox.<br><br>Click **Edit and localize**.|<a href="./img/3-11.jpg" target="_blank"><img src="./img/3-11.jpg" width="250"/></a>|
| 3.12   |Add the answer *JAVA* (**Answer value**), *English (United States) (**Language**), and *JAVA* (**Localzed text**).<br><br>Add a second answer *SAPUI5* (**Answer value**), *English (United States) (**Language**), and *SAPUI5* (**Localzed text**).<br><br>Click **Save**.|<a href="./img/3-12.jpg" target="_blank"><img src="./img/3-12.jpg" width="250"/></a>|
| 3.13    |Finally, add the third **Question** *Company code*, **Answer format** *Short text*. Activate **Required**.<br><br>Click **Next: Lifecycle**.|<a href="./img/3-13.jpg" target="_blank"><img src="./img/3-13.jpg" width="250"/></a>|
| 3.14    |Keep all defaults, but switch **Require access reviews** to *No*.<br><br>Click **Next: Rules**.|<a href="./img/3-14.jpg" target="_blank"><img src="./img/3-14.jpg" width="250"/></a>|
| 3.15    |Click **Next: Review + create**.|<a href="./img/3-15.jpg" target="_blank"><img src="./img/3-15.jpg" width="250"/></a>|
| 3.16    |Click **Create**.|<a href="./img/3-16.jpg" target="_blank"><img src="./img/3-16.jpg" width="250"/></a>|


Continue with [exercise 4](../ex4/ex4.md), or go back to the [overview](../README.md).
