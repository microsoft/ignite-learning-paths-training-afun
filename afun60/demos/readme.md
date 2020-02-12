# Technical Demonstrations

* Use https://shell.azure.com 
* Ensure that your kubectl is connected to your AKS cluster : az aks get-credentials -n <aks-name> -g <resource-group>

| [README](/afun60/README.md) | [Slides](/afun60/presentations.md) | [AKS Deployment](/afun60/aks/readme.md) |
|-----------------------------|------------------------------------|-------------------------------------------|

## Demo 1 - ACI (time permittting)

* az container create -n mycontainer --image microsoft/aci-helloworld -g myResourceGroup --ip-address public

## Demo 2 - App Service

[Video - Orlando](https://globaleventcdn.blob.core.windows.net/assets/afun/afun60/demos/AppService-Demo-Ignite-Orlando.mp4)

* Portal : Create New Web App for Containers on Linux
* Location: EASTUS
* FREE Service Plan
* SET microsoft/aci-helloworld as the image

## Demo 3 - AKS

[Video - Orlando](https://globaleventcdn.blob.core.windows.net/assets/afun/afun60/demos/AKS-Demo-Ignite-Orlando.mp4)

Get the deployment.yaml from a running pod

* kubectl get pods
* kubectl get pod <insert-2nd-to-last-pod-name-here> -o yaml 

Talk through the yaml deployment file, addressing the Enviroment variables set and the container image used.

## Before session begins

In order to be ready for prime time, We encourage you to prepare the following just before delivering your session.
The following is only _recommendations_, and not mandatory.

### Clipboard

> We encourage you to use a clipboard manager to have all kind of commands/URLs handy. If you're using Windows 10,
> you can use the built-in clipboard manager with `Win+V` keys.

Clear your clipboard manager, and copy the following items into it. **Ensure any default value is changed if needed**

- `az container create -n mycontainer --image microsoft/aci-helloworld -g myResourceGroup --ip-address public`
- `microsoft/aci-helloworld`
- `spboyer/ignite-afun60`
- `docker run -d -p 8000:80 spboyer/ignite-afun60`

### Browser

Link | Related to demo | Comments
-----|------|------
http://localhost:8000 | 1 - ACI | Shows a locally executed container
https://shell.azure.com | 1 - ACI | Ensure you select the appropriate subscription
https://ms.portal.azure.com/?feature.customportal=false#create/Microsoft.WebSite | 2 - Web App for Container | 
https://hub.docker.com/r/spboyer/ignite-afun60 | 1 & 2 | Shows the source, and that it's public (hence Container Registry)
Azure Portal - Open on the pre-created Web App for container resource | 2 - Web App for Container | Your backup if resource deployment has an issue
http://localhost:8001 | 3 - AKS | Kubernetes Dashboard


### Command line

- In a dedicated window, execute `docker run -d -p 8000:80 spboyer/ignite-afun60`
- In a dedicated window, execute `az aks browse --resource-group myResourceGroup --name myAKSCluster`
- Have a dedicated terminal window for demo 3. Execute `az aks get-credentials -n -g` to ensure kubectl is connected to your AKS cluster.

### Pre-work

We encourage you to pre-deploy a container instance and a web site. So, if there is any latency with the deployment
of these ressources during the session, you can simply switch to pre-deployed resources.
Here is a simple script to deploy demo 1 and demo 2 resources, with `-pre` suffix so you don't get _name not available_
error on stage. Please modify `$city` and `$alias` values before running it.

```powershell
$city = "sydney"
$alias = "chmaneu"
$rgName = "rg-$($city)-afun60-$($alias)"
az group create --name $rgName --location eastus
az container create -n "aci-$($city)-afun60-$($alias)-pre" --image spboyer/ignite-afun60 -g $rgName --ip-address public --dns-name-label "hello-afun60-$($city)-pre"
az appservice plan create --name "asp-afun60-$($city)-pre" --resource-group $rgName --location "East US" --sku S1 --is-linux
az webapp create --resource-group $rgName --name "web-afun60-$($city)-pre" -i spboyer/ignite-afun60 --plan "asp-afun60-$($city)-pre"
```
