# 4. Challenge 3: Change data in SAP
[< Quest 2](Quest2.md) - **[Quest 4 >](Quest4.md)**

In this challenge you will learn how to:
* The difference between Actions and Topics.
* Create a topic to handle more complex tasks like updating data in SAP.
* How topics will be activated with the right trigger phrases.
* Call flows from topics.
* Use other entities of the SAP OData Connector
* Handle special situations (e.g. no product found)
* Parse JSON and assign values to topics variables

For the sake of time and simplicity, we keep the hand-on session simple and only provide the possibility to update the price.

## 4.1 Create necessary flows in advance
### 4.1.1 Create flow to read SAP Product Details
Go to the browser window with Power Automate.

We now create a flow called “SAP Product Details” as a copy of the first flow “List SAP products of a category” you have already created. 

Create another flow with the “Save as” procedure.
 
 
Refresh the page and “Turn on” the flow.

This flow will retrieve all detailed information about the product from the SAP system.
 
The first node has just the input:
 
The SAP OData Connector uses the Query OData entities with the following required by SAP to filter on the relevant Product ID:
````javascript
concat('ProductID eq ', '''', triggerBody()['text'], '''')
````

The action Respond to Copilot looks like this and sends back the product details as string:
````javascript
string(outputs('Query_OData_entities')?['body']['data'])
````

Save the flow and publish.

### 4.1.2 Create flow Update SAP Product Price
Create another flow called Update SAP Product Price as a copy of the first flow List SAP products of a category.
 
Refresh the page and “Turn on” the flow.
 
At the first position, add the required Flow Parameters. (Note: Price is a number):
 
At second position, delete the existing action called Query OData entities. And add a new action of type “SAP OData Connector” with the Entity “Update OData entity”. Set the ProductID Input as shown:
 
 
In the advanced parameters mark those where we want to allow updates. To keep this lab simple, only select Price:
 
Update the “Update Odata entity” Actions with the relevant variables in the corresponding fields (remember we are only updating Price in this lab):
 
Update the last action in the flow with a success message:

  Save the flow and publish.

### 4.2 Create a Topic “SAP Product Data”
Go to Copilot Studio --> Topics

Create a new topic from blank.
 
In the section “Describe what the topic does” Enter the following:

You can copy/paste the following in the Description box:

This topic will fetch details of a product in SAP and allows the user to update SAP product information.

Typical queries are like these:

Update / change or edit product price in SAP.

Save the Topic
 
Open the Topic Details and add the following text to Description:

Show and update information about a product in the SAP system.
 
Go to the Input tab.

Create a new variable called ProductID.

Add following text to the Description box:

Product ID. Example: HT-1000.
 
Save again.

Add a node of type Ask a question for the Product ID.

Add following text:

Which product do you want to update? Please provide the Product ID. Example: HT-1000.
 
In the Identify field choose User’s entire response:
 
Make sure the response will be saved in the variable ProductID:
 
> [!Note]
> With GenAI feature enabled the question might not be asked when the ProductID is already known within the context of the conversation, which is very convenient. For this the variable must have the “receive values from other topics” check box activated.
 
## 4.3 Add the flow to read SAP product details
Add the flow after clicking on Add node
 
Next choose Call an action and add the relevant Flow SAP Product Details:
 
 
## 4.4 Parse the data returned by the Flow
As a next step, add a node that will parse the data and assign all values to a table variable with the name “Product”:
 
The Input to the Parse node is the Output from previous node which is the data with all product information returned from SAP. We store the data in a Variable of type “Table” that we call “Product”.

Set the Parse Value Input string to the Output (from previous node) and set the data type to Table:
 
Create a new variable:
 
Go into the Var1 “View details” to change the name to “Product”
 
 
The schema needs to be generated or provided. Here, we are providing it to speed up the hands-on session.

Copy/paste the following text into the “Edit schema” box.
```text
        kind: Table
        properties:
         Category: String
         ChangedAt: String
         CreatedAt: String
         CurrencyCode: String
         Depth: Number
         Description: String
         DescriptionLanguage: String
         DimUnit: String
         Height: Number
         MeasureUnit: String
         Name: String
         NameLanguage: String
         Price: Number
         ProductID: String
         SupplierID: String
         SupplierName: String
         TaxTarifCode: Number
         ToSalesOrderLineItems:
           type:
            kind: Record
            properties:
              AssociationLinkUrl: Blank
              IsCollection: Boolean
              Name: String
              Url: String

         ToSupplier:
          type:
           kind: Record
           properties:
              AssociationLinkUrl: Blank
              IsCollection: Boolean
              Name: String
              Url: String

         TypeCode: String
         WeightMeasure: Number
         WeightUnit: String
         Width: Number
```

## 4.5 Add Question about required change
Add a node “Ask a question” and enter all product details as shown below with the final question what the user wants to change. In this lab with limited time we have limited the functionality to the possibility to change only the price.
 
Add a question node like this with:
* Question text: Placeholder, we'll add details via code editor. The details of the question will be added using the code editor subsequently.
* Identify “User’s entire response” and
* Save users response as variable “ChangeRequest”:
 
Use the code editor to enter the formulas to show the product details and ask the question:
 
In the code editor, search for the text Placeholder, we'll add details via code editor and replace the selected text with this block of text:
 
 ```text
      |-
        The product information in SAP are as follows:
        - **Product ID:  {Topic.ProductID}**
        - **Name:**  {LookUp(Topic.Product, ProductID = Topic.ProductID).Name}
        - **Description:**  {LookUp(Topic.Product, ProductID = Topic.ProductID).Description}
        - **SupplierID:**  {LookUp(Topic.Product, ProductID = Topic.ProductID).SupplierID}
        - **SupplierName:**  {LookUp(Topic.Product, ProductID = Topic.ProductID).SupplierName}
        - **Category:**  {LookUp(Topic.Product, ProductID = Topic.ProductID).Category}
        - **Price:**  {LookUp(Topic.Product, ProductID = Topic.ProductID).Price}
        - **Currency:**  {LookUp(Topic.Product, ProductID = Topic.ProductID).CurrencyCode}

        What do you want to change?
```

Your code editor should look like this, the newly inserted text being highlighted in yellow:  

Finally, the question should look like this:
 
Save the topic for now. We’ll create another action to change the price and finish the topic afterwards:  

## 4.6 Create another action to update the product price
Go to “Actions” and create a new action with following details:
 
Chose the prepared flow “Update SAP Product price”:  

If the UI feels stuck, then click Back and try again.
 
 
The flow we reference here has 2** input parameters**. Therefore, this action will need to provide them. Verify correct configuration of the 2 Inputs as follows (Product ID and Price):
 
 
You can leave the Output unchanged.

Save the action.

## 4.7 Add a plugin action to update the price
* Go back to the Topic “SAP Product Data and add another node at the end.
* Add Call an action and choose in Plugin (preview) the Action Update SAP Product price that you created in previous step.
 
 
In the plugin action you don’t need to provide an input because Gen AI will automatically fill in the details into the action input based on the last user input and conversation context.

Save and publish.

## 4.8 Test the price update in Copilot Studio
 
## 4.9 Publish the final version to Microsoft Teams
 
Restart the agent if necessary:
 
## 4.10 Final test in Teams
 
 
 
 
# Where to next?

**[Quest 2](Quest2.md) - [ Quest 4 >](Quest4.md)

[🔝](#)