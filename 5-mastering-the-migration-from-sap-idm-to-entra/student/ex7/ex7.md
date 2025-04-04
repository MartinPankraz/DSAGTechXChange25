# Exercise 7 (**optional**): Inform the SOC team via Microsoft Teams
In this optional exercise, you can further enhance your skills in IAM worklow design with Entra ID Governance. To inform BestRun's Security Operations Center (SOC) team about any changes in priviledged roles such as developer access, a notification to the SOC's channel in Microsoft Teams should be send. 
You will implement this new workflow requirement with another Logic App that will be called by the corresponding events (access request approved, and access assignment removed).

**Duration:** 15 minutes.

| Step   | Description     | Screenshot          |
| :----- | :-------------- | :-----------------: |
| 7.1    |Go back to the **first browser tab**.<br><br>Click **Student\<NN\> \| Custom extensions** from the breadcrumb naviation.|<a href="./img/7-1.jpg" target="_blank"><img src="./img/7-1.jpg" width="250"/></a>|
| 7.2    |Click **+ Add a custom extension**.|<a href="./img/7-2.jpg" target="_blank"><img src="./img/7-2.jpg" width="250"/></a>|
| 7.3    |Enter a name for the new extension, for example **SendTeamsNotification**, and enter a description.<br><br>Click **Next: Extension Type**.|<a href="./img/7-3.jpg" target="_blank"><img src="./img/7-3.jpg" width="250"/></a>|
| 7.4    |Select **Request workflow** for the *Extension Type*.<br><br>Click **Next: Extension Configuration**.|<a href="./img/7-4.jpg" target="_blank"><img src="./img/7-4.jpg" width="250"/></a>|
| 7.5    |Select **Launch and continue** for the *Behavior* of the new logic app.<br><br>The entitlement management governance process is not required to wait for the response from the new extension and can continue immediately.<br><br>Click **Next: Details**|<a href="./img/7-5.jpg" target="_blank"><img src="./img/7-5.jpg" width="250"/></a>|
| 7.6    |Leave the switch to **Yes** because you will create a new logic app for the extension. Select *Visual Studio Enterprise Abonnement* for the **Subscription**, *SAPEntra-RG* for the *Resource Group*.<br><br>Enter *SendTeamsNotification\<NN\>* as the **Logic app name**. Replace *NN* with the number you are assigned to.<br><br>Click **Create a logic app**.|<a href="./img/7-6.jpg" target="_blank"><img src="./img/7-6.jpg" width="250"/></a>|
| 7.7    |Wait for the message that your new logic app has been deployed successfully.<br><br>Click **Next: Review + create**.|<a href="./img/7-7.jpg" target="_blank"><img src="./img/7-7.jpg" width="250"/></a>|
| 7.8    |Review the setting for the new custom extension, then click **Create**.|<a href="./img/7-8.jpg" target="_blank"><img src="./img/7-8.jpg" width="250"/></a>|
| 7.9    |From the list of custom extensions, select the newly created logic app **SendTeamsNotification\<NN\>**.|<a href="./img/7-9.jpg" target="_blank"><img src="./img/7-9.jpg" width="250"/></a>|
| 7.10   |Go to the **Logic app designer** in the navigation menue.<br><br>*Right-click** on the *Condition* action in the logic app, and select **Delete** from the context menu.|<a href="./img/7-10.jpg" target="_blank"><img src="./img/7-10.jpg" width="250"/></a>|
| 7.11   |Click **+** and select **Add an action**.|<a href="./img/7-11.jpg" target="_blank"><img src="./img/7-11.jpg" width="250"/></a>|
| 7.12   |In the *Search Bar*, filter for *Teams*.<br><br>Click the **See more** link for **Microsoft Teams** actions in the search results.|<a href="./img/7-12.jpg" target="_blank"><img src="./img/7-12.jpg" width="250"/></a>|
| 7.13   |Select the **Post *card* in a chat or channel** action from **Microsoft Teams**.|<a href="./img/7-13.jpg" target="_blank"><img src="./img/7-13.jpg" width="250"/></a>|
| 7.14   |Click on the title and change it, for example *Post notification in SAP IAM Events channel*.<br><br>Select **Channel** from the **Post In** drop-down list.|<a href="./img/7-14.jpg" target="_blank"><img src="./img/7-14.jpg" width="250"/></a>|
| 7.15   |Select **SAP IAM Events** from the **Channels** drop-down list.|<a href="./img/7-15.jpg" target="_blank"><img src="./img/7-15.jpg" width="250"/></a>|
| 7.16   |In the **Adaptive Card** entry field, copy and past the content from the file [teamsAdaptiveCard.json](../files/teamsAdaptiveCard.json).<br><br>Click **Save**.<br><br>This [*Adaptive Card*](https://adaptivecards.io/) template takes the values received from the **manual** trigger event, such as the name of the access package or the user name, and sends this information nicely rendered to the selected Teams channel.|<a href="./img/7-16.jpg" target="_blank"><img src="./img/7-16.jpg" width="250"/></a>|
| 7.17   |Select **Student\<NN\> \| Custom Extensions** from the breadcrumb navigation.|<a href="./img/7-17.jpg" target="_blank"><img src="./img/7-17.jpg" width="250"/></a>|
| 7.18   |Select **Access packages** from the navigation menu. Select the **BTP Student \<NN\>** package from the list.|<a href="./img/7-18.jpg" target="_blank"><img src="./img/7-18.jpg" width="250"/></a>|
| 7.19   |Select **Policies** from the navigation menu. Select the **Initial Policy** assignment policy from the list.|<a href="./img/7-19.jpg" target="_blank"><img src="./img/7-19.jpg" width="250"/></a>|
| 7.20   |In the **Policy details** section, clicL **Edit**.|<a href="./img/7-20.jpg" target="_blank"><img src="./img/7-20.jpg" width="250"/></a>|
| 7.21   |Switch to the **Custom extensions** tab.<br><br>Select *Request is approved* for the **Stage**.|<a href="./img/7-21.jpg" target="_blank"><img src="./img/7-21.jpg" width="250"/></a>|
| 7.22   |Select *SendTeamsNotification* for the **Custom Extension**.<br><br>On the second line, select *Assignment is removed* for the **Stage**.|<a href="./img/7-22.jpg" target="_blank"><img src="./img/7-22.jpg" width="250"/></a>|
| 7.23   |Select *SendTeamsNotification* for the **Custom Extension**.<br><br>On the second line, select *Assignment is removed* for the **Stage**.|<a href="./img/7-23.jpg" target="_blank"><img src="./img/7-23.jpg" width="250"/></a>|
| 7.24   |Again, select *SendTeamsNotification* for the **Custom Extension**.<br><br>Click **Update**.|<a href="./img/7-24.jpg" target="_blank"><img src="./img/7-24.jpg" width="250"/></a>|
| 7.25   |Select **Assignments** from the navigation menu.<br><br>Activate the checkbox for the existing assignment to your *Student user \<NN\>*.<br><br>Click **Remove**. This will trigger the new logic app to send a notification into the SOC team's event channel.|<a href="./img/7-25.jpg" target="_blank"><img src="./img/7-25.jpg" width="250"/></a>|
| 7.26   |Verify that the event information has been sent.<br><br>Open a *new incognito windows**.<br><br>Login to [Microsoft Teams](https://teams.microsoft.com/) with user *sapsentinel@bestruncorp.onmicrosoft.com*.<br><br>Click **Next**.|<a href="./img/7-26.jpg" target="_blank"><img src="./img/7-26.jpg" width="250"/></a>|
| 7.27   |Click **Skip for now**.|<a href="./img/7-27.jpg" target="_blank"><img src="./img/7-27.jpg" width="250"/></a>|
| 7.28   |Click **Next**.|<a href="./img/7-28.jpg" target="_blank"><img src="./img/7-28.jpg" width="250"/></a>|
| 7.29   |Select **SAP Sentinel** from the account list.|<a href="./img/7-29.jpg" target="_blank"><img src="./img/7-29.jpg" width="250"/></a>|
| 7.30   |Select **Skip for now**.|<a href="./img/7-30.jpg" target="_blank"><img src="./img/7-30.jpg" width="250"/></a>|
| 7.31   |Select **Skip setup**.|<a href="./img/7-31.jpg" target="_blank"><img src="./img/7-31.jpg" width="250"/></a>|
| 7.32   |Click **Yes**.|<a href="./img/7-32.jpg" target="_blank"><img src="./img/7-32.jpg" width="250"/></a>|
| 7.33   |In Microsoft Teams, switch to **Teams** on the left-side navigation. Expand the *bestruncorp* team, and select the **SAP IAM Events** channel from it.<br><br>Verify that the adaptive card has been sent by your new custom extension and informs about the removal of the assignment.|<a href="./img/7-33.jpg" target="_blank"><img src="./img/7-33.jpg" width="250"/></a>|
