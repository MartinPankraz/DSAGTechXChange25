# 🔌 3. Challenge 2: Setup Flow + SAP OData Connector
[< 🤖 Quest 1](Quest1.md) - **[🔧 Quest 3 >](Quest3.md)**

In Challenge 2, we will setup a Power Automate flow and connect it to an SAP OData Connector. This involves creating a new flow, where we will add an SAP OData action, specifically choosing to query OData entities in SAP.

## 3.1 Create the Power Automate Flow
In Copilot Studio, go to Actions and create a New Power Automate flow.
 
Name your new flow as List SAP products of a category and make a note of it.
 
Add an input variable to the trigger action:
 
Add an SAP OData action.
 
Choose Query OData entities:
 
Configure the connection
PM0 OData Base URI: https://microsoftintegrationdemo.com:44301/sap/opu/odata/iwbep/GWSAMPLE_BASIC

|SAP PM0 Credentials ||
|-----|-----|
| Username| devxchange |
|Password|xxx|

> [!Note]
> If you are using SAP's Public Demo system *ES5*, then OData Base URI: https://sapes5.sapdevcenter.com/sap/opu/odata/iwbep/GWSAMPLE_BASIC

 
Enter the OData Entity “Product Set”:
 
Click “Show all” to enter a filter in the advanced parameters:
 
In $Filter we’ll enter a Power FX expression that will filter on the provided Category.
Add this expression: concat('Category eq ', '''', triggerBody()['text'], '''')
 
The final action Respond to Copilot will return the list of products from SAP.
 
Add an output variable
 
In the output add a Power FX expression:
Add this expression: string(body('Query_OData_entities'))
 
Finally, the action should look like this:
 
Make sure you give your flow a name: List SAP Products of a Category

 
Now save your Power Automate Flow.


## 3.2 Test the flow
Choose Manually and enter product ID Keyboards
 
 
 
From the successful run one would normally take out the output body for later use in the copilot studio as input schema for the JSON parsing. In this lab, however, we provide the schema directly to save some time.
 
## 3.3 Connect the Copilot with the Flow
Go back to the Copliot Studio window. Add an action:
 
Chose the previously created Flow:
 
Next:
 
Edit the Input:
 
In the Input tab, add the following text into the Description box so that Gen AI knows how to set the input for the flow:

````text
Product Category. Only one single category can be chosen as input from this list. It is case-sensitive and must be written exactly like below: Accessories, Notebooks, Laser Printers, Mice, Keyboards, Mousepads, Scanners, Speakers, Headsets, Software, PCs, Smartphones, Tablets, Servers, Projectors, MP3 Players, Camcorders
```` 

Edit the Description of the action output in the same way.
And add the following text into the Description box:

````text
Products found in SAP of a given category. Present the result as HTML table including following information: ProductID; Name; Category; Description; Supplier; Price; Currency.
````

Now Save your agent.

## 3.4 Test the Copilot in the test pane
Open the Test pane and give it a try:
 
For the first test you need to connect with the SAP OData Connector:
 
Now you should get the response in the chat window:
 
## 3.5 Test the Copilot in Microsoft Teams
As a next step we also want to test the updates in Microsoft Teams.
Therefore, publish the changes:
 
Sometimes it can take a while for the changes to become active in Teams. You can force immediate update by asking for restart or start over:
 
Now test again:
 
## 3.6 Optionally, bypass connection requests in the chat window.
Only for testing purposes, you may also specifically set the SAP connection as default in the Flow edit pane to avoid any connection requests within Copilot Studio.
 
# Where to next?

**[🤖 Quest 1](Quest1.md) - [🔧 Quest 3 >](Quest3.md)

[🔝](#)
