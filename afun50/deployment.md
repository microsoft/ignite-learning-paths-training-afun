# Demo Preparation / Setup

 The demo requirement for this session are fairly light. For those presenters who don't want to deploy any Azure resources, videos are embedded into slides #19 and #28.

 ## Demo #1

 For the first demo, the Azure Storage Account will be created from scratch so no preparation is needed. Make sure you are deploying into a subscription that has access to deploy resources into the region you want to use, but any subscription should work. 

 In the original version of this demo we ended by actually mapping the file system we created to the local device, and opening it up live to copy files in, before switching back to the Azure portal to view those files. I cut that section because of time, but it's an effective end to the demo if you can make it work.

 ## Demo #2

 This demo can be run against _any_ Cosmos DB, as there are no specific requirements for which API is being used or any need for the database to have any data in it. The demo will work just fine with a fresh Cosmos DB instance deployed directly from the Azure portal with all the defaults.

 If you want to use something relevant to the Ignite Tour, there is a standalone version of the TT app that can be deployed directly into Azure. 

 https://github.com/microsoft/TailwindTraders-Website/tree/master/Source/Tailwind.Traders.Web/Standalone

 Please follow the instructions under the Deploy to [Azure App Service](https://github.com/microsoft/TailwindTraders-Website/tree/master/Source/Tailwind.Traders.Web/Standalone#deploy-to-azure-app-service-automatic-deployment) section of the README, and you'll end up with the same Cosmos DB instance that was used to create the demo video. 

The only pointer I'd offer for this demo is to _not_ click ```"Save"``` at the end of the section where you select new regions for replication so you don't have to sit through the validation process of that step. If you _do_ click save, use that as the last step when you end the demo.