# Exercise 4: Test the new dynamic approval workflow
You are now ready to test the approval workflow by initiating a new request for the access package. You will also verify the execution of the *DynamicApprover* Logic App and the response from
the IAM OData service in S/4 HANA by using the available monitoring and troubleshooting tools.  

**Duration:** 10 minutes.

| Step   | Description     | Screenshot          |
| :----- | :-------------- | :-----------------: |
| 4.1    |Select **Overview** from the navigation menu. (Select Access Package -> Overview) <br><br>Click **Copy to clipboard** for the *My Access portal link*.|<a href="./img/4-1.jpg" target="_blank"><img src="./img/4-1.jpg" width="250"/></a>|
| 4.2    |Open a **new browser tab**.<br><br>Paste the *My Access portal URL* into the address bar and hit enter.<br><br>Login with *user\<41..70\>@bestruncorp.onmicrosoft.com.*<br><br>Click **Continue** for starting a new request for the *BTP Student \<NN\>* access package.|<a href="./img/4-2.jpg" target="_blank"><img src="./img/4-2.jpg" width="250"/></a>|
| 4.3    |Provide the answers to the questions as defined in the *Dynamic approver* policy.<br><br>* Select *SAP BTP* for **Developer role**.<br>* Select *JAVA* or *SAPUI5* for **Context**.<br>* Enter ***DE***, followed by the ***number*** you are assigned to (41..70), for **Company Code**.<br>* Provide a *Business justification*.<br><br>Click **Submit request**.|<a href="./img/4-3.jpg" target="_blank"><img src="./img/4-3.jpg" width="250"/></a>|
| 4.4    |Wait until your new request has been processed.|<a href="./img/4-4.jpg" target="_blank"><img src="./img/4-4.jpg" width="250"/></a>|
| 4.5    |Go back to the first browser tab.<br><br> Select **Identity Governance \| Catalogs** from the breadcrumb navigation.|<a href="./img/4-5.jpg" target="_blank"><img src="./img/4-5.jpg" width="250"/></a>|
| 4.6    |Select **Catalogs** from the navigation menu. Enter *Student*, followed by the ***number*** you are assigned to (41..70).<br><br>Click on your **catalog** in the search results.|<a href="./img/4-6.jpg" target="_blank"><img src="./img/4-6.jpg" width="250"/></a>|
| 4.7   |Select **Custom extensions** from the navigation menu.<br><br>Click on the link **DynamicApprover** to navigate to the *Logic app* extension.|<a href="./img/4-7.jpg" target="_blank"><img src="./img/4-7.jpg" width="250"/></a>|
| 4.8   |Select **Run history** from the **DynamicApprover** logic app navigation menu.|<a href="./img/4-8.jpg" target="_blank"><img src="./img/4-8.jpg" width="250"/></a>|
| 4.9   |Click on the most recent entry from the list of runs.|<a href="./img/4-9.jpg" target="_blank"><img src="./img/4-9.jpg" width="250"/></a>|
| 4.10   |The execution history of the selected run is shown.<br><br>Click the **Get company code from request** action which extracts the company code entered by the user in the request from the input values passed to the logic app.<br><br>On the right panel you can see the value entered by the user. Verify that this is the same value you entered when you've created the request.<br><br>*Note: You may have selected a run of another student in the previous step. In this case, go back an try again with another entry from the list.*|<a href="./img/4-10.jpg" target="_blank"><img src="./img/4-10.jpg" width="250"/></a>|
| 4.11   |Click the **Call IAM OData Service** action from the run history. On the **OUTPUTS** section, click **Show raw outputs** to view the raw response data from the IAM OData service in S/4 HANA.|<a href="./img/4-11.jpg" target="_blank"><img src="./img/4-11.jpg" width="250"/></a>|
| 4.12   |Verify that the returned value for **ApproverEmail** corresponds to the account with your number for your approver user, i.e. *approver\<41..70\>@bestruncorp.onmicrosoft.com*.|<a href="./img/4-12.jpg" target="_blank"><img src="./img/4-12.jpg" width="250"/></a>|

Continue with [exercise 5](../ex5/ex5.md), or go back to the [overview](../README.md).
