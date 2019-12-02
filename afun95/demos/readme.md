# Demos

## Suggested Presentation SetUp
 
 You should have a few things open a ready: 

 - PowerPoint
 - Browser Tab - OneDrive - IgniteDemo Folder
 - Browser Tab - Portal Azure - Dashboard/ home
 - Browser Tab - Portal Azure - Function App (with out any Functions)
 - Browser Tab - Portal Azure - Logic App Overview blade 
 - Browser Tab - GitHub - on the demo page. (https://github.com/microsoft/ignite-learning-paths-training-afun/tree/master/afun/afun95)
 - ZoomIt (or another application that zoom your screen) should be running

---

## Demo 1 - Azure Logic App Demo

> 💡 You must have completed the [deployment](../deployment/README.md) before attempting to do the demo.

In this demo, we will see an Azure Logic App triggered by an HTTP Get command creating a file in a OneDrive folder with dynamic content base on the parameter received via the HTTP call.

### Azure Logic App

> Open the Browser Tab - Portal Azure - Logic App Overview blade 

On the Azure Logic App blade, click the **Logic app designer** from the left panel. Alternatively, you can also click **Edit** in the top menu. We are now in the Designer view. There is currently two boxes: an HTTP Trigger, and a OneDrive action. 

> Explains how the connection are saved in Azure. SO it secure and you don't need to enter any credential while using the Azure Logic App.

### Add an Action

Explain that if we would execute the Logic now the caller wouldn't have any indication of success failure. This is why you will add an HTTP Response. Click the **+ New step** bellow the last step *Create File*. In the search bar type `Response` then select the **Response Request**. Enter `200` as Status Code. 


For the body we will use the **dynamic content**, it's one of the great features about Azure Logic App. Each property of the previous step will be present in a dynamic menu, you just need to click on it to use them. Type `The file `. Then from the dynamic content click on **Display Name** in the OneDrive content (It's the one with the OneDrive logo on the side). Then type ` was created`.

![addResponse][addResponse]

Don't forget to save your work by clicking the **Save** button on the top of the screen.

> Now that your work is saved, switch to the code view and show briefly the code. HAve a look to the Response you just added.

### Testing the workflow

To execute this Azure Logic App we will need the URL to fire the Trigger. This one can be found in the trigger box. Click on the first box and copy the **HTTP GET URL**

![azure logic app url][azurelogicappurl]

Open a new tab in your favorite browser and paste the URL into the address bar. Before taping Enter we need to add a parameter.  To do this add the following code at the end of the URL.

  &salutation=Hello%20Ignite

Now Press Enter.

You should see the response we created: `The file test.txt was created`. Now open the destination folder in OneDrive and open that `test.txt` file...

You can now return to the slide.

---

## Demo 2 - JavaScript Function Demo

> 💡 You must have completed the [deployment](../deployment/README.md) before attempting to do the demo.

In this demo we will show how easy it is to create a new JavaScript Azure Function. We will do it from the Portal.

> Switch to the Browser Tab - Portal Azure - Dashboard/ home

Click the "+" sign on the top left corner and select **Function App**. Fill the creation form while explaining your choices.
* **Resource Group**: create a new one (ex: AFUN95demo).
* **Hosting plan:** Consumption Plan. 
  > Explain the difference between *Consumption Plan* pay for the time you run vs. *App Service Plan* where it's a monthly fee because the resources are always there.. but can be share with other services (ex: other function, website)
* **Runtime:** Node.js 

> ⚠ Don't click on the create button! ⚠ 
Show the script/ ARM template that could be generated... Mention that we will see more of this in the third demo.

Just like on TV shows you already have one created.

> Switch to the Browser Tab - Portal Azure - Function App (with out any Functions)

Do a quick tour of the screen, very short... show the tab **Platform feature** mention there tons of information over there... but we don't need it in this demo (we don't have enough time).

A Function App is like a container with multiple functions. Click the "**+**" beside Function to create our first Function. There is many different ways to create Function, but right now let's do it In-Portal; click **In-Portal**, and the **Continue** button. Click **More templates**

> Take a few second to show different templates, and briefly mention scenario where it could be use. 

Click on **HTTP trigger**.  Change the name for `SimpleHttpTrigger`, and the *Authorization level* to `Anonymous`. Of course in a real situation, we would probably use a different configuration, but in this demo context, those will be just perfect.

> Using the name `SimpleHttpTrigger` will simplify things for demo3. However is you decide, you can change it.

### Let's Examine the code

As you can see at line 4 the function is expecting a parameter `name`

```javascript
   if (req.query.name || (req.body && req.body.name)) {
```
If you pass it it return a greeting message, otherwise it response with a message explaining that you should pass a parameter.

### Executing the Azure Function 

To get started, let's test the Azure Function directly from the Azure portal. 
    * Expand the **Test** panel on the right
    * Click the Run button, read the answer. It's working! 
    * Now delete the Request body to see the error message. Click the Run button... Notice the error message.

### Update the Azure Function     

Because the Azure Function is in JavaScript we can edit it directly in the portal. Change `Hello ` by `Hello Ignite I'm `. And click the **Save** button. 

Click on **</> Get function URL**, at the right of the buttons

![Part of the portal to get the Function Url][functionUrl]

Copy-Paste the URL in a new Browser tab, notice the error message. This is there is no parameter. When we test the Function earlier we pass the parameter in the body. Let's pass it via the querystring this time. Add `?name=YOUR_BANE` at the end of the URL, and hit Enter.

Creating, updating and using Azure Function is that easy. You are now ready to create your own! Visit [Azure Functions](https://azure.microsoft.com/en-us/services/functions/?WT.mc_id=msignitethetour2019-github-afun95) web pages to get more details, different scenarios.

> You have successfully finish your second demo!

> Take a few moment to introduce the next demo.
> In the previous demo, we saw how easy it is to use the Azure Portal to create some Azure Function. That might be fantastic for a first experience, but in a development environment that won't scale very well. Since you probably use a Git (or another repository), let's see how to deploy the same Azure Function from an online git: GitHub. 

---

## Demo 3 - Deploying from GitHub Demo

> 💡 You must have completed the [deployment](../deployment/README.md) before attempting to do the demo.

In this demo you will deploy an Azure Function directly from the GitHub using Azure Resource Manager (ARM) template.

> Switch to : Browser Tab - GitHub - demo afun59 page

> Mention that you will start the deployment right now and explain how it works while it's deploying. Also mention that the folder you are using **IS** the repository that can use and they saw in the bottom of every slides.

> In the bottom of the page in the section **[Deploy the Azure Function](https://github.com/microsoft/ignite-learning-paths-training-afun/tree/master/afun95/demos#deploy-the-azure-function)** click on the Deploy to Azure Button. Once more fill the form explaining your choices and this time click the deployment button. Click the notification in the top right corner to see easily when the deployment is done. 

> Now let's get back in GitHub

### The Function Code

Inside the folder **functionapp-demo** there is information related to the FunctionApp like host environment, packages list and more. There is also a folder **SimpleHttpTrigger**, this is the code of our function. Open it and then open the file `index.js`. 

You should recognize this code, it's our Function with a little difference in the message: "Hello, it's still me " instead of "Hello".

### Deployment pieces

Open the **deployment** subfolder. It contains two Azure Resource Manager (ARM) template. The first one was use to setup the environment for this session, deploy the half-done Azure Function, and Azure Logic App. In this demo we will focus on `deployAzure-afun95-demo3.json`.

The ARM template uses a formatting really close to JSon, and it's used to create the Azure instances for our solution. Not the binaries, only the infrastructure.

Open the file `deployAzure-afun95-demo3.json`, this is the file we will use for this demo. There are four major sections to an ARM template: parameters, variables, resources, and outputs. 

> Show those lists.

### Parameters and Variables

Parameters and Variables are very useful to create a more dynamic content. Have a look at the few parameters and variables name, we will get back to them later.

### The Resources

There it is the core of the ARM template the list of resources to create. To create an Azure Function we need a few resources: a functionapp (aka.Web/sites), an storageAccounts to save the code, and a Service Plan or "serverfarms" that describe the physical resources that will be useful and some billing options. Try to find those in elements in the template, and examine the properties. 

There is a sub-resource inside the functionApp that starts at line 88

```json
{
    "apiVersion": "2015-08-01",
    "name": "web",
    "type": "sourcecontrols",
    "dependsOn": [
        "[resourceId('Microsoft.Web/sites/', variables('funcAppName'))]"
    ],
    "properties": {
        "RepoUrl": "[variables('repoURL')]",
        "branch": "[parameters('GitHubBranch')]",
        "publishRunbook": true,
        "IsManualIntegration": true
    }
}
```

Like mentioned previously an ARM template doesn't contain any binaries. In this **sourcecontrols** resource we tell Azure to get the code into the repository defined by the variable `repoURL`. Looking back to the top of the template we can see the variable value `"https://github.com/microsoft/ignite-learning-paths-training-afun.git"`.

What will append is Azure will create the list of resources and then synchronize git repository inside Azure Function to that GitHub. And this is how Azure will have our code!

### Deploy the Azure Function

To deploy the Function we will send the ARM template to define in the deployment folder to the Azure portal `#create` feature. This is done by appending the absolute path of our template to the URL of the portal. The result looks like this.

```html
https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2Fignite-learning-paths-training-afun%2Fmaster%2Fafun95%2Fdeployment%2FdeployAzure-afun95-demo3.json
```
A frequent way to ease the process is to put that composed URL in an anchor. Click the Deploy to Azure anchor (or button) to start the deployment.

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2Fignite-learning-paths-training-afun%2Fmaster%2Fafun95%2Fdeployment%2FdeployAzure-afun95-demo3.json" target="_blank"><img src="https://azuredeploy.net/deploybutton.png"/></a>

> The deployment should be done now, return to the Azure Portal and execute the Function, check the code....



---

## Demo 4 - Using Azure Function with Azure Logic App

> 💡 You must have completed the [deployment](../deployment/README.md) before attempting to do the demo.

After you deployed the Azure Function, during demo 3, let's go back to Azure portal in the Azure Logic App. We will use the freshly deployed Function to change our Logic App output.

Open the Logic App in Edit mode. To make the call to the Azure Function, add an action between the Trigger and the *Create File*.

![AddAzFunction][AddAzFunction]

In the Search bar type "Function" and select the function App you just deployed, then select **SimpleHttpTrigger**.

![SelectHttpTrigger][SelectHttpTrigger]

Remember the Azure Function required a parameter `name`. In the **Request Body** section enter a simple JSON like this.

```json
{"name":""}
```

Now, while your cursor is placed between the two double-quotes, use the *Dynamic Content* menu to add the Trigger's **Queries**. Click the Save button.

![AddQuery][AddQuery]

The *Trigger Queries* contains a full JSON, and we only need the value of "salutation". We need to fix this.  Switch to the **Code View**.  Locate `SimpleHttpTrigger`.

```json
 "SimpleHttpTrigger": {
    "inputs": {
        "body": {
            "name": "@{triggerOutputs()['queries']}"
        },
        "function": {
            "id": "/subscriptions/....."
        }
    },
    "runAfter": {},
    "type": "Function"
}
```

The change required is very simple. We need to specify witch value we need by adding `['salutation']` at the end of our *body* value. 

```json
 "SimpleHttpTrigger": {
    "inputs": {
        "body": {
            "name": "@{triggerOutputs()['queries']['salutation']}"
```

Click the Save button and switch back to the **Designer** view

Great, now that the Azure Function is properly called we will update the text save in the file to use this output.  Expend the **Create file** action. Delete the text in the of **File Content**. Use the *Dynamic Content* menu to add the **Body** of the **SimpleHttpTrigger**. 

> You will probably need to click the "See more" button to see that option.

![completedAzLogicApp][completedAzLogicApp]

Save your work. You can now test your updated version of the Azure Logic App.

The message in the text file should be something like: `Hello, it's still me Frank`

---

> Congrats all demos are done.

---

## Teardown Instructions

Navigate to the Azure Portal and delete the Azure Resource Group (ex: AFUN95demo) you created earlier. Deleting the Resource Group will delete all resources within. Once the command is started you don't need to way, the command is been executed in Azure. 

> Note: It's always a good idea to check again after a few hours or the next day to be sure you didn't forget a Resource Group.


[allResources]: assets/all-afun95-resources.png
[deployafun95]: assets/deployafun95.png
[azurelogicappurl]: assets/azurelogicappurl.png
[addResponse]: assets/addResponse.png
[functionUrl]: assets/functionUrl.png
[AddAzFunction]: assets/AddAzFunction.png
[SelectHttpTrigger]: assets/SelectHttpTrigger.png
[AddQuery]: assets/AddQuery.png
[completedAzLogicApp]: assets/completedAzLogicApp.png