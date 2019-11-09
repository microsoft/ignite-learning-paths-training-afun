# AFUN95 Deployment

## Prerequisites

- Microsoft Azure subscription
- GitHub Account

### Azure Subscription

Having an Azure subscription is mandatory to be able to do the *AFUN95: Figuring Out Azure Functions​*. If you don't own an Azure subscription already, you can create your **free** account today. It comes with 200$ credit, so you can experience almost everything without spending a dime.

[Create your free Azure account today](https://azure.microsoft.com/en-us/free?WT.mc_id=msignitethetour2019-github-afun95)

### GitHub

GitHub is a development platform inspired by the way you work. From open source to business, you can host and review code, manage projects, and build software.  During the *AFUN95: Figuring Out Azure Functions​* demos you will host your code in a GitHub repository, and use it to deploy your Azure Function.

[Create your free account today](https://github.com/)

---

## Demo Environment Deployment Instructions

### Automated Deployment

Simply by pressing the blue "*Deploy to Azure*" button below, will create all the resources required for AFUN95 demos.

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2Fignite-learning-paths-training-afun%2Fmaster%2Fafun95%2Fdeployment%2FdeployAzure.json" target="_blank"><img src="https://azuredeploy.net/deploybutton.png"/></a>



### Post-Deployment Steps

#### OneDrive Connection

From the Azure Portal open the Azure Logic App blade, and click click **Edit** in the top menu. 

There is currently two boxes: an HTTP Trigger, and a OneDrive action. Before we can try it we need to give access to the Azure Logic App to your OneDrive.

> Note that there is a little icon ⚠️ to show that this action required our attention

Click on the second Box, named Connections. There is a message saying: "Invalid connection". It's normal it wasn't configured. Let's fix that. Click on the **Add new** button. This will popup a login window, where you will need to enter your OneDrive credentials.

By default, the Azure Logic App while creates the file into the folder */IgniteDemo*. If you don't have it, create it from your OneDrive or select another folder.

> You should create a */IgniteDemo* folder closer as possible to the Root. Also if you prefer you can use DropBox or another folder online service.

You are now ready to present.



## **IMPORTANT:** When you are done

Be sure to delete the resources when you have completed the presentation. It can be done by the portal or with Azure CLI.

``` az cli
az group delete --name <resource group name> --yes --no-wait
```

It will take several minutes, but by deleting the entire resource group, all resources associated with the demo environment will be destroyed.
