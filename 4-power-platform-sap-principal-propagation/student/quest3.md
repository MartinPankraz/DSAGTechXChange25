# Setup your Power Automate flow to perform a business partner change

[< Quest 2 ](quest2.md) - **[🏠Home](../README.md)**

In this quest you will conclude your journey and experience yourself what it takes to perform a business partner change using SAP Principal Propagation.

## Adjust the SAP OData connection on Power Automate to use Entra ID via Azure APIM

* Enhance your existing Power Automate flow to use Entra ID via Azure API Management authentication scheme. This is a prerequisite for the SAP Principal Propagation.

![Screenshot of oauth with APIM auth in PowerAutomate](assets/3-1.png)

* Add an **OData Read entity** operation for the entity set `BusinessPartnerSet` and an individual business partner to your existing flow. You can pick any of the business partner ids outputted from the previous flow run.

> [!IMPORTANT]
> Be aware that you are using a shared tenant and other users might have changed the same business partner data in the meantime.

```bash
/BusinessPartnerSet('0100000000')
```

The prior read ensured the retrieval of an ETag to ensure concurrency of the OData operations.

* Add another OData action to update the email address of the business partner.

## Test your flow

* Execute the flow and verify the run history. You should see a successful run of the OData update action.

## Where to next?

[< Quest 2 ](quest2.md) - **[🏠Home](../README.md)**

[🔝](#)