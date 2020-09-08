# AFUN60 (Tailwind Traders AKS Deployment)

| [README](/afun60/README.md) | [Slides](/afun60/presentations.md) | [Demos](/afun60/demos/readme.md) | [AKS Deployment](readme.md) | 
|--------|-------|------------|-----------|

## Prerequisities

If you do not already have accounts with each, please register first.

### Service Principal Requirement

Part of the demo environment uses Kubernetes. 

As a result, a service principal is required in order to provision all of the necessary pieces of infrastructure.

If you have already generated a service principal ID, you do **NOT** need to do it again. Use the same ID and password as before.

If you have never created a service principal, run the following command from [Cloud Shell](https://shell.azure.com):

``` az cli
az ad sp create-for-rbac
```

The output should look similar to this:

``` az cli
{
  "appId": "2ddb2923-88c6-45cc-98zz-36717cq35001",
  "displayName": "azure-cli-2019-09-04-17-35-58",
  "name": "http://azure-cli-2019-09-04-17-35-58",
  "password": "3c371136-dafd-4b1f-a793-50885537e9a7",
  "tenant": "72f988bf-86f1-41af-91ab-2d7cd011db47"
}
```

>See [az ad sp create-for-rbac](https://docs.microsoft.com/en-us/cli/azure/ad/sp?WT.mc_id=none-github-nepeters&view=azure-cli-latest#az-ad-sp-create-for-rbac) for more information.

### Provider registration

The Tailwind Traders application uses many Azure services. In some cases, if a service has not yet been used in your subscription, a provider registration may be needed. The following commands will ensure your subscription is capable of running the Tailwind Traders application.

``` az cli
az provider register --namespace Microsoft.OperationalInsights
az provider register --namespace Microsoft.DocumentDB
az provider register --namespace Microsoft.DBforPostgreSQL
az provider register --namespace Microsoft.OperationsManagement
az provider register --namespace Microsoft.ContainerService
az provider register --namespace Microsoft.Sql
az provider register --namespace Microsoft.ContainerRegistry
```

## Instructions

### Automated Deployment

To deploy the demo environment used for AFUN60 - Responding To Incidents, [use the instructions found in the official deployment repository](https://github.com/microsoft/ignite-learning-paths-training-afun/tree/main/afun60) or just press the blue "Deploy to Azure" button below.

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fneilpeterson%2Ftailwind-reference-deployment%2Fmain%2Fdeployment-artifacts-aks%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

[Video of the process is available here](https://globaleventcdn.blob.core.windows.net/assets/ops/ops20/video/00_Deployment.mp4)

Once the deployment has completed and you have verified that you can access the Tailwind Traders site, your next step is to deploy an additional Logic App that will be used in the first technical demonstration ([Demo One](demos/01/README.md)) of this presentation.

>**Presenter Note:** This step should be automated soon and the Logic App will be deployed with the rest of the resources.

---

## **IMPORTANT:** When you are done

Be sure to delete the resources when you have completed the presentation.

Run the following command from [Cloud Shell](https://shell.azure.com) to delete the entire resource group.

``` az cli
az group delete --name <resource group name> --yes --no-wait
```

It will take several minutes, but by deleting the entire resource group, all resources associated with the demo environment will be destroyed.

---

## Next Step After Deploying

[Go here to deploy the Logic App needed in demo 1 (to be automated)](../deployment/logic_apps/README.md)

---

## Source Repositories

https://github.com/microsoft/TailwindTraders

https://github.com/neilpeterson/TailwindTraders-Backend

https://github.com/neilpeterson/TailwindTraders-Website
