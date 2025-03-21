# 🤖 2. Challenge 1: Setup Copilot
[🏠Home](../README.md) - [🔌 Quest 2 >](Quest2.md)

In Challenge 1, you will be setting up a Copilot (and connecting it to Microsoft Teams). This involves creating a new Copilot with a specific name, adding a detailed description and instructions that will guide the Copilot's behavior, especially when the Generative AI feature is active.

## 2.1 Create the Copilot
Login to Copilot Studio [https://copilotstudio.microsoft.com/](https://copilotstudio.microsoft.com/) witht he provided user, e.g. ```userXXX@bestruncorp.onmicrosoft.com``` where XXX is the number assigned to you. 
![Sign in to Cpilot](../images/SignInToCopilot.jpg)

> [!Note]
> If you are promted to provider "More information", click on *Next*
> 
> ![More information](../images/MoreInfo.jpg)
> 
> and click on *Skip setup*
> 
> ![Skip Setup](../images/SkipSetup.jpg)
> 

When asked to *Stay signed in* click on *Yes*

![Stay Signedin](../images/StaySignedIn.jpg)

When asked about your region, select "Germany"

<Platzhalter Screenshot>

Skip the *Welcome to Copilot Studio* screen
![Welcome to Copilot Studio](../images/WelcometoCopilotStudio.jpg)

and click on Create to Create your first *Copilot Studio Agent*
![Create Agent](../images/CreateAgent.jpg)

Click on *New agent*
![New Agent](../images/NewAgent.jpg)

and create a Copilot with the name SAP Product Copilot
 

Provide a **Name**: ```SAP Product Copilot```

**Description**: 
```text 
This Copilot Agent enables users to lookup information about Products in the SAP System
````

and **Instructions**. The instructions are important as they influence the behavior of the copilot when Generative AI feature is active:
````text
You are a copilot that checks available products in a SAP system. You provide the product details as a HTML table for better readability.
````

Then click on **Create**
![New Agent](../images/CreateSAPProductCopilot.jpg)



 
## 2.2 Activate “Generative AI” Feature
Now that the *Copilot Studio Agent* is created, open the Settings
![Open Settings](../images/OpenSettings.jpg)

Select *Generate AI* on the left, then *Generative (preview)* and click on *Save*
![Enable Generative AI](../images/EnableGenAi.jpg)


## 2.3. Ask a first questions
Now *Close* the Settings screen and use the *Test your agent* to interact with your new Agent. 
![First Questions](../images/FirstQuestion.jpg)

>[!Note]
> Obviously at the moment it is a generic Agent and does not have access to any external data (like your SAP system)

 


# Where to next?

**[🏠Home](../README.md)** - [🔌 Quest 2 >](Quest2.md)

[🔝](#)
