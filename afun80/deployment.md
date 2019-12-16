# Deployment

Introduction. With these preparation steps, you will deploy the necessary environment that will allow you to perform the demo exercises present in the AFUN80 video.
1.	When signed in to a newly created Azure subscription, create the prime.admin account. Assign this account global administrator permissions. Make a note of the yoursubscription.onmicrosoft.com suffix and substitute where appropriate when running the setup code below.
2.	Create a secondary.administrator account. Also assign this account global administrator permissions. Make a note of the yoursubscription.onmicrosoft.com suffix and substitute where appropriate when running the setup code below.
3.	Navigate to portal.azure.com and sign into the demo Azure tenancy with the prime.admin@yoursubscription.onmicrosoft.com account.
4.	To create the VMs and users used in this session’s labs, open Cloud Shell and enter the following commands at the prompt, pressing Enter after each line:

    ```bash
    adminPassword=88Tailwind88Tailwind
    ```

    ```azcli
    az group create --name TT-VMs --location southeastasia
    ```

    ```azcli
    az network vnet create \
        --name TTVirtualNetwork \
        --resource-group TT-VMs \
        --address-prefixes 10.0.0.0/16
    ```

    ```azcli
    az network vnet subnet create \
        --vnet-name TTVirtualNetwork \
        --resource-group TT-VMs \
        --name TTSubnet \
        --address-prefix 10.0.0.0/24 
    ```

    ```azcli
    az network vnet create \
        --name NewVNet \
        --resource-group TT-VMs \
        --address-prefixes 192.168.0.0/16
    ```

    ```azcli
    az network vnet subnet create \
        --vnet-name NewVNet \
        --resource-group TT-VMs \
        --name public \
        --address-prefix 192.168.10.0/24 
    ```

    ```azcli
    az vm create \
        --resource-group TT-VMs \
        --name TT-2019-A \
        --image win2019datacenter \
        --vnet-name TTVirtualNetwork \
        --subnet TTSubnet \
        --admin-username prime \
        --admin-password $adminPassword
    ```

    ```azcli
    az ad user create \
        --display-name “TT-VM-ADMIN” \
        --password $adminPassword \
        --user-principal-name tt-vm-admin@yoursubscription.onmicrosoft.com \
        --force-change-password-next-login false	
    ```

    ```azcli
    az ad user create \
        --display-name “TT-2019-A-Admin” \
        --password $adminPassword \
        --user-principal-name tt-2019-A-admin@yoursubscription.onmicrosoft.com \
        --force-change-password-next-login false	
    ```

5.	In the Azure AD Blade, upgrade the subscription to an Azure AD P2 trial.
