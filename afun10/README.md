# AFUN10: Discovering Microsoft Azure

 ![Learning Path](https://img.shields.io/badge/Learning%20Path-AFUN-fe5e00?logo=microsoft)
 
 # AFUN10 Train the Trainer Resources

 ## Video Asset Links

 Create VM Demo - [Link](link)


 ## PowerPoint Asset Links

 PowerPoint Deck - [Link](link)

 ## Demo Notes

 Before performing the demos, make sure you have set your account/machine to the correct Azure subscription. By default, the Azure CLI/Cloud Shell will default to your Visual Studio account, if you want to use a different subscription (like "Ignite the Tour") be sure to set this subscription in your browser/shell BEFORE starting the demos. Otherwise, if the proper resource groups are not present, the demo will fail.

 The following command sets the Azure subscription, replace ```"Ignite the Tour"``` with your own subscription name if you are not using that subscription.

 ``` az account set --subscription "Ignite the Tour"```

 It will be helpful to use a text-expander tool (on macOS you can use the built-in [text-replacement tool](https://support.apple.com/guide/mac-help/replace-text-punctuation-documents-mac-mh35735/mac) and on Windows the free [AutoHotKey](https://www.autohotkey.com/) is excellent -- third-party apps such as [TextExpander](https://textexpander.com/) are also wonderful) to store some of the commands you will be using.

 For example, I have a snippet named ```twtssh``` that expands to a public SSH key I auto-generated for this project.

 I have another snippet ```vmtwt``` that expands to 
 ```shell 
 az vm create \
   --resource-group AFUN10 \
   --name myVM \
   --image UbuntuLTS \
   --admin-username azureuser \
   --generate-ssh-keys 
   ```

   If you choose to use text-snippets (highly recommended), follow the instructions [here](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/mac-create-ssh-keys) to create your SSH key BEFORE your demos and save that resulting public SSH key to a snippet that can be used later/


 ## Demo 1: Browse the Azure Portal

 * Walk-through the portal. Show the new design (including where the sidebar is now hidden by default) and show different resources and resource types.

 * Click on the Cloud Shell icon and show the Azure Cloud Shell and how it can be used with Bash or PowerShell. Show ```code .``` if you want to show off the very basic Monaco integration (not to be confused with VS Online)

 * You can also choose to show the Azure CLI using the Windows Terminal (Cloud Shell or via the PowerShell Az extension) or on macOS/Linux (using the Azure CLI package)

 **Note:** Make sure you're using the "public" view of the Portal and not the Preview. This is the Public Portal URL https://portal.azure.com/?feature.customportal=false#home

 ## Demo 2: Create a VM in the Portal and in the Cloud Shell

 1. Load the Azure Portal
 2. Click on "Create a Resource"
 3. Choose Ubuntu 18.04 LTS
 4. Choose the proper subscription (most-likely, "Ignite the Tour)
 5. Choose the existing resource group, "AFUN10" -- if this resource group does not exist for some reason, create it now.
 6. Give the VM a unique name i.e. twt-[CITY] or ignite-tour-[CITY]
 7. Choose the region, select US East US (this is the region of the AFUN10 resource group)
 8. Select the Ubuntu LTS Image -- scroll through the options to show other image choices
 9. For size, allow the default D2s v3 Option to exist -- you can show the other sizes available if you want
 10. For auth type, you can choose a password or an SSH key, I prefer an SSH key. Enter in whatever username you want.
 11. In the SSH field, enter in an SSH public key pre-generated (if you're using a snippet) OR fill out the password field instead
 12. Choose your public inbound ports. By default, port 22 (SSH) is selected, I often select Port 80 and Port 443 for HTTP and HTTPS
 13. Click Next and go to the Disks section
 14. In Disks, select either Premium or Standard SSD (leaving the default is fine)
 15. Click Next: Networking
 16. Keep the Networking settings as default -- show that you could choose an existing virtual network if you wanted
 17. Click Next:Management
 18. Again, keep all options as default
 19. Click Next: Advanced
 20. Keep all default options -- at your discretion, show off the Extension options and the cloud-init options
 21. Click Next:Tags
 22. Explain how tagging works, do not fill out tags
 23. Click Next: Review + Create
 24. Ensure settings are correct, show how to download the ARM template, click the create button

 While the VM is being created in the Portal, click on the CloudShell button at the top of the Portal

 1. Login, ensure you are in the same subscription as where you created your last VM
 2. Choose "Bash" if you are given an option
 3. Type in the following command (using a text snippet is highly recommended) 
 ``` shell 
 az vm create \
   --resource-group AFUN10 \
   --name myVM \
   --image UbuntuLTS \
   --admin-username azureuser \
   --generate-ssh-keys
   ```
   4. Execute the snippet, explain what each command does -- i.e., creates a VM in resource group AFUN10, with the name myVM using the UbuntuLTS image with an admin username of azureuser and a generated SSH key
 5. Watch as the VM is created
 6. After the VM is created, go to the Azure Portal and show the resources in AFUN10, showing that both virtual machines now exist.


 