## Demo Preparation / Setup

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
