# Demos

**Note:** Make sure you're using the "public" view of the Portal and not the Preview. This is the Public Portal URL https://portal.azure.com/?feature.customportal=false#home

## Demo 1: Browse the Azure Portal's Networking Section

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

* Walk through the portal. Show the new design and focus on the Networking features. You show the options available in the Azure Marketplace, as well as first-party features.


---


## Demo 2: Attach a CDN to an Existing Storage Account

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

1. Access the previously-created storage account in the AFUN30 resource group (or whatever resource group you're using)
2. Click on the Azure CDN menu underneath "Blob service"
3. In the section that says "New Endpoint," enter a new endpoint name in the field under "Create New" -- name it something like "twt-[CITY]"
4. Under pricing tier, choose the Standard Microsoft tier, but click the link that says "view full pricing details" to show the other options.
5. Leave the hostname alone, but show how it can be altered  
6. Click Create
7. After the endpoing is created, click it. 
8. Go through each of the settings tabs, showing what different options are and explaining how it works
9. Explain how you can export an ARM template with those settings if you want to redeploy the same type of setup later.