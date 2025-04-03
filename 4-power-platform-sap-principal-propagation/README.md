# Secure SAP app integration with Microsoft

Ensuring that SAP authorizations are enforced across all apps that consume from the ERP is key for honoring named user license, staying compliant, and protecting sensitive data. In this workshop, you will learn how to secure your SAP apps that expose OData services with Microsoft Entra ID applying SAP Principal Propagation.

## Introduction

SAP Principal Propagation is a mechanism that allows the mapping of a non-SAP entity (user on Entra ID for example) to a named SAP user. In this workshop we will be using the SAP OAuth server applying the OAuth2SAMLBearer flow. This is ideal for people-facing apps like Power Platform, where the user is authenticated by Microsoft Entra ID and the app needs to call an SAP OData service on behalf of the user.

> [!TIP]
> The concepts applied in this hack can be re-used with other products and services. Take SAP API Management for example.

* Familiarize yourself with the scenario using the provided [Powerpoint deck](../misc/welcome.pptx).

## 📌Buckle up and start your lab [**👉here**](student/README.md)📌

⏱️⩇⩇:⩇⩇⩇⩇:⩇⩇

## Recommended courses and further learning

### YouTube sessions

[Power Platform + SAP OData Services | Step by step guide](https://www.youtube.com/watch?v=AcM67FBIEB4&list=PLvqyDwoCkBXYHECuHw2pKN2DrWjyn3q5f&index=9)
[SSO with SAP APIM and Power Platform | SAP as guest on the show](https://youtu.be/nQplgEHASAI)
[Power Platform & SSO deep dive](https://youtu.be/92jYUT712wY)
[Expanded SSO for SAP Connectors](https://youtu.be/7M0C_-tsa2Q)

### Blogs

* [Perform SAP Principal Propagation with Microsoft Entra ID for SAP SuccessFactors!](https://community.sap.com/t5/technology-blogs-by-members/perform-sap-principal-propagation-with-microsoft-entra-id-for-sap/ba-p/13860532)
* [Integrating low code solutions with Microsoft using SAP Integration Suite has never been easier!](https://community.sap.com/t5/enterprise-resource-planning-blogs-by-members/integrating-low-code-solutions-with-microsoft-using-sap-integration-suite/ba-p/13789298)
* [Hurray🎉 SAP OData connector now supports OAuth2 and SAP Principal Propagation](https://community.powerplatform.com/blogs/post/?postid=c6a609ab-3556-ef11-a317-6045bda95bf0)
* [Enhancing Copilot Studio Extensions for SAP by using Adaptive Cards and Principal Propagation](https://techcommunity.microsoft.com/t5/running-sap-applications-on-the/enhancing-copilot-studio-extensions-for-sap-by-using-adaptive/ba-p/4187096)
* [Entra ID with SAP blog series | by Martin Raepple](https://blogs.sap.com/2022/11/02/principal-propagation-in-a-multi-cloud-solution-between-microsoft-azure-and-sap-business-technology-platform-btp-part-vi-calling-the-microsoft-graph-on-behalf-of-the-sap-authenticated-user/)

## 📢Feedback

This repos encourages contributions and feedback via the [GitHub Issues](https://github.com/MartinPankraz/DSAGTechXChange25/issues/new/choose).
