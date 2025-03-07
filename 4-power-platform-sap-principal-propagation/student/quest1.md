# Discover your integration target

**[🏠Home](../README.md)** - [ Quest 2 >](quest2.md)

## Step 1: Call the SAP OData API with Basic Authentication on AS ABAP

Navigate to the following URL in your browser to see the metadata of the SAP OData API. You will be prompted for credentials. Use the provided credentials.

```bash
https://microsoftintegrationdemo.com:44300/sap/opu/odata/iwbep/GWSAMPLE_BASIC/$metadata
```

> [!NOTE] later on you will be calling the OData service from API Management, not directly on stack. This is only possible in this setup, because the SAP system is exposed to the internet.

## Step 2: Login on Microsoft Power Automate

Navigate to the following URL in your browser to login to Power Automate. Use the provided credentials.

```bash
https://make.powerautomate.com/environments/Default-85642982-0095-4777-a3e2-147c5c95af60/home
```

## Step 3: See the OAuth and SSO setup

### SAP OAuth Server

We prepared an OAuth client in the SAP system for you authorized for the OData service GWSAMPLE_BASIC with scope `ZGWSAMPLE_BASIC_0001`. That client trusts our bestrun Entra ID tenant.

### Entra ID enterprise app registration (SAP Netweaver)

### Entra ID app registration (API Management)

## Step 4: Login on Microsoft Azure Portal - API Management

Navigate to the following URL in your browser to login to Azure Portal. Use the provided credentials.

```bash
https://portal.azure.com/?feature.customportal=false#@bestruncorp.onmicrosoft.com/resource/subscriptions/48b193a0-2500-45b5-ad41-f09cde1a95cd/resourceGroups/SAPEntra-RG/providers/Microsoft.ApiManagement/service/bestrun-apim/apim-apis
```

Ok, you are all set up to do some principal propagation!

## Where to next?

**[🏠Home](../README.md)** - [ Quest 2 >](quest2.md)

[🔝](#)