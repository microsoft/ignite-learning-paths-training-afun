
## Demo 1 - Storage Account Demo

We are going to go into the web portal for this demo, but everything we are going to do in the portal we could do in multiple different ways. We could use the Azure APIs to create the storage account, we could use an ARM template, which is the Azure native Infrastructure as Code option, or we could even use a command line. Yes, in case you haven’t gotten to play around with it, Azure has a command line that you can launch from a web browser, or even directly from your OS. You can also use tools like Visual Studio and VScode to configure them.

But, for us, we choose the portal. We log in and you can see the home screen here. For most things in Azure if I want to create a new resource I start here, and click Create a Resource. This takes us to the Marketplace, and you can see our most popular options. You’ll notice that each of these services on the right has a “Quickstart Tutorial” link available, which will take you directly to the documentation for that service. There, you’ll find everything you need to get up and running quickly. They are usually 5-minutes articles, sometimes videos as well, that go over how to deploy and configure the service you have selected. You’ll also see specific help depending on the method you are using to create the resource. Here we have the portal, PowerShell, The Azure CLI, and help if you are using the .NET, Java, Python or JavaScript SDKs. We’ve spent so much time and energy on making it so you don’t have to dig very far to find the information you need to get started, and all of these documentation pages are able to be edited by customers directly, so if there’s something else you need, or if something doesn’t work as expected, you can contact the documentation teams directly to get it updated.

Here we go and create a new storage account.

We have to add some information in, and it’s basically the same for any new Azure services you deploy. You need to choose the subscription you want to use, and you need to either choose an existing resource group or create a new one. Resource groups are collections of different kinds of resources and you can choose how you want group things. Some customers group them by project, some group them by physical location, some customers who are spinning up environments for testing will use the name of the test run to keep things simple. Whatever you choose it goes here. 

You can choose from any Azure Region, and the type of performance level needed. Under “Replication” we can see all the types available. We can see that in the region we have selected we do have the option to use zone-based replication!

Finally we can choose which access tier we need for this dataset. Once we are done, we click “review and create”. On the next screen we can review our choices and start the account creation.

After it’s complete we can look at the overview. We can see the status of the primary and secondary copies and which region they are deployed into and the replication type we selected. We can see each of the storage types we have the ability to deploy and some performance graphs that are automatically.

To the left, we have a couple of the places we can use the things we talked about earlier. We can see the access keys that are used for programmatic access to the account, and rotate them as needed. Under encryption we can see that data at rest is always encrypted, and we have the option of using our own keys if we want to. We can also do interesting things like leverage a storage account to create a static website. All you have to do is enable it and you’ll get a public URL and SSL encryption for whatever content you want to upload.

Let’s go back to the overview and we’ll create a basic file share. Since we just created the account, we can confirm that there aren’t any existing shares, and click the plus sign to create a new one. We’ll give it a name and a quota, and in short order we can see it’s done. If we open it up, we see the options we have. We can enable backups, we can view or create snapshots, and we can look at how to connect the file system to an operating system. Since SMB supports Windows, Linux and MacOS, we have each of the commands you’d need to use to connect right here. If we look at the Windows section specifically, we can pick a drive letter we’d like to map, and then see the PowerShell command we’d use to connect and map the folder to the host. Now, multiple endpoints can see and make changes to a shared set of files. 


## Demo 2 - Cosmos DB Demo

[More to come...]