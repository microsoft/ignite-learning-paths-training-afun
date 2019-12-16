# Demos

The labs associated with the AFUN 80 Governance in Azure session can be completed in a trial Azure subscription. If you want to perform the lab related to management groups, you’ll need multiple Azure trial subscriptions and to associate them with the same Azure AD instance. A method of describing how to do this is provided in the appropriate lab, but given the challenges around deploying multiple trial subscriptions, you probably won’t do this lab and will just watch the video instead.


## Demo 1 - VM RBAC

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will apply RBAC at the VM and resource group level to control access to virtual machines. To complete this demonstration, perform the following steps:
1.	Sign on to the Azure portal with the prime.admin account.
2.	On the Azure Portal home page, click the virtual machine node
3.	Verify that VMs TT-2019-A and VM-2019-B are visible.
4.	Sign out of the Azure portal and sign in as TT-VM-ADMIN
5.	In the virtual machine node, verify that no virtual machines are present.
6.	Sign out of the Azure portal, and sign in as TT-2019-A-ADMIN
7.	In the virtual machine node, verify that no virtual machines are present.
8.	Sign out of the Azure portal, and sign in as prime.admin.
9.	In the VMs node, select VM TT-2019-A.
10.	In the Access control (IAM) node of TT-2019-A’s properties, click Role Assignments and view all current role assignments (there will not be any as the subscription is newly instantiated, there are some in the demo video).
11.	In the Access control (IAM) node of TT-2019-A’s properties, click Add and then click Add Role Assignment.
12.	On the Add Role Assignment page, configure the following settings and click Save:
- Role: Virtual Machine Contributor
- Name: TT-2019-A-ADMIN
13.	In the Resource Groups node, click on the TT-VMs resource group.
14.	In the Access control (IAM) node of the TT-VMs resource group, click Add and then click Add Role Assignment.
15.	On the Add Role Assignment page, configure the following settings and click Save:
    - Role: Virtual Machine Contributor
    - Name: TT-VM-ADMIN
16.	Sign out as prime.admin, sign in as TT-2019-A Admin
17.	In the VMs node, verify that you are only able to see one VM, TT-2019-A
18.	Sign out and sign in as TT-VM-ADMIN
19.	In the VMs node, verify that you are only able to see both VMs, TT-2019-A and TT-2019-B.
20.	Sign out of the Azure portal



~~


## Demo 2 - Block VM by SKU

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will limit the deployment of VMs to specific SKUs. To complete this demonstration, perform the following steps:
1.	Sign on to the Azure portal with the prime.admin account.
2.	On the Azure Portal home page, type Policy in the search bar and then click Policy.
3.	In the Policy page, click Definitions under Authoring.
4.	On the Definitions page, click Initiative Definition.
5.	On the Initiative Definition page, set the following settings:
    - Name :LIMIT VM SKU
    - Description: Limit VM SKU.
    - Category: Limitations
6.	In the list of available definitions, select Allowed Virtual Machine SKUs and click Add. 
7.	In the Allowed Virtual Machine SKUs drop down, select the following and click Save:
    - Standard_DS2_v2
    - Standard_DS3_v2
    - Standard_DS4_v2
8.	Verify in the list of policies and initiatives that LIMIT VM SKU is present.
9.	In the Policies page, click on Assignments under Authoring.
10.	Click Scope and then click Select to ensure that the subscription is selected.
11.	Click Assign Initiative.
12.	Under Basics, click the ellipsis (…) and select the LIMIT VM SKUs initiative.
13.	In the Description textbox, type “Limit the VMs that can be deployed in the subscription”
14.	Click Assign.
15.	You will need to wait approximately 30 minutes at this point  for the initiative to apply.
16.	On the Policy – Assignments page, click the LIMIT VM SKUS assignment. When the initiative is applied, resource compliance will be at 100%.
17.	Select the virtual machines node and click Add.
18.	On the Create a virtual machine page, configure the following settings and then click Review and Create:
    - Resource Group: TT-VMs.
    - Virtual Machine Name: Test-Policy
    - Region: Southeast Asia
    - Image: Windows Server 2019 Datacenter
    - Size: B2ms (as long as it’s not one of the three allowed, the demo works)
    - Administrator Username: Chancellor
    - Password: 88Tailwind88Tailwind  
19.	During final validation, you will see a validation failed message. Click to view the details.
20.	Sign out of the Azure portal.



~~


## Demo 3 - Enforce Tags through policy

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will enforce the use of tags through policy. To complete this demonstration, perform the following steps:
1.	Sign on to the Azure portal with the prime.admin account.
2.	On the Azure Portal home page, type Policy into the search bar and then click Policy.
3.	In the Policy node, under Authoring, click Assignments.
4.	On the Policy – Assignments page, click Assign Policy.
5.	On the Assign policy page, set the scope to the TT-VMs resource group and click Select.
6.	Select the ellipsis (…) next to Policy Definition and then select Require specified tag and then click Select.
7.	In the Description select Require use of the Environment tag (Production or Development)
8.	In the Tag Name page type Environment.
9.	Click Assign.
10.	Wait 30 minutes for the assignment to apply.
11.	In the Virtual Machines node, click Add
    - Resource Group: TT-VMs.
    - Virtual Machine Name: Test-Policy
    - Region: Southeast Asia
    - Image: Windows Server 2019 Datacenter
    - Size: Standard_DS2_v2  (remember it will need to be one of the allowed SKUs to not be blocked by an existing policy)
    - Administrator Username: Chancellor
    - Password: 88Tailwind88Tailwind  
12.	On the Tags node, ensure that you don’t provide any tags and then click Review and Create
13.	During validation, the VM deployment will be blocked by policy.
14.	Return to the Tags node, type the following and then click Review and Create:
    - Name: Environment
    - Value: Development 
15.	The deployment will proceed.
16.	Sign out of the Azure portal.



~~


## Demo 4 - Management Groups

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will configure a management group. This demonstration requires that you have three trial subscriptions linked to the same Azure AD instance. To do this with trial subscriptions, you’ll need a separate account to create each subscription, then an additional account that you can make a subscription co-owner. You then need to use this account to change the default directory to one used by the subscription that you have chosen as the root (the first one you created). You can find out more about this process here: [Associate or add an Azure subscription to your Azure Active Directory tenant](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory?WT.mc_id=msignitethetour2019-github-afun80)

Once you have linked subscriptions, configure the prime.admin account from the first subscription as a co-owner of the other subscriptions. Once this is all done, you can complete this demonstration by performing the following steps:
1.	Sign on to the Azure portal with the prime.admin account.
2.	On the Azure Portal home page, click the Search bar and click Management Groups.
3.	The tenant root group will be created when you perform this step.
4.	On the Management Groups page, ensure that all three subscriptions are present within the Tenant Root Group.
5.	Note the message that indicates the account is registered as a directory admin, but does not have permissions to access the root management group.
6.	Select the Azure AD Blade and then select Properties.
7.	At the bottom of the properties page, under Access management for Azure resources, click Yes and then click Save.
8.	Sign out of the Azure Portal and then sign back in as prime.admin.
9.	In the Azure Portal search bar, type Management and then click on Management Groups.
10.	Confirm that the message indicating that the account does not have requisite permissions has disappeared.
11.	Click Add Management Group.
12.	On the Add Management Group page, configure the following settings and click Save:
    - Management Group ID: TWT-MG-PRODUCTION
    - Management Group Display Name: TWT-MG-PRODUCTION
13.	Click on the TWT-MG-PRODUCTION item.
14.	On the TWT-MG-PRODUCTION page, click Details.
15.	Click Add Management Group.
16.	On the Add Management Group page, provide the following settings and click Save:
    - Management Group ID: TWT-PROD-CHILD-MG
    - Management Group Display Name: TWT-PROD-CHILD-MG
17.	When TWT-PROD-CHILD-MG is created, click on the management group and then click Details.
18.	On the TWT-PROD-CHILD-MG page, click the ellipsis (…) More item and then click Add Subscription.
19.	Select the first subscription and click Save.
20.	Click Details next to TWT-PROD-CHILD-MG. 
21.	On the TWT-PROD-CHILD-MG page, click the ellipsis (…) More item and then click Add Subscription.
22.	Select the second subscription and click Save.
23.	Click Details next to TWT-PROD-CHILD-MG. 
24.	On the TWT-PROD-CHILD-MG page, click Policies.
17.	On the Policy – Compliance page, select the ellipsis (…) next to Policy Definition and then select Require tag and its value and then click Select.
18.	In the Description select Require use of the Environment tag set to Production
19.	In the Tag Name page type Environment.
25.	In the Tag Value textbox type Production.
26.	Click Assign.
27.	Under the Search bar in the Azure portal, click TWT-PROD-CHILD-MG.
28.	On the TWT-PROD-CHILD-MG page, click Access Control (IAM).
29.	On the Access control (IAM) page, click Add and then click Add Role Assignment.
30.	On the Add Role Assignment page, configure the following settings and click Save.:
    - Role: Virtual Machine Contributor
    - Select: TT-VM-ADMIN
31.	Sign out of the Azure console.


~~


## Demo 5 - Azure Blueprints

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will configure Azure Blueprints. To complete this demonstration, perform the following steps:
1.	Sign on to the Azure portal with the prime.admin account.
2.	On the Azure Portal home page, click the Search bar and type Blueprints. Click on the Blueprints item.
3.	On the Getting Started page, click Create.
4.	On the Choose a blueprint sample page, click Start with blank blueprint.
5.	Provide the following information and then click Next: Artifacts:
    - Blueprint name: TWT-BLUEPRINT-ALPHA
    - Blueprint description: RBAC and Policy assignment
    - Definition Location: Subscription (the first one if there are multiple)
6.	Under Subscription, click Add Artifact.
7.	On the Add Artifact drop down, click Policy Assignment.
8.	Select Require tag and its value from the list of policy definitions and click Add.
9.	Click Add Artifact.
10.	On the Add Artifact drop down, click Role Assignment.
11.	On the Role drop down, select Virtual Machine Contributor.
12.	Click Add.
13.	Click Save Draft.
14.	On the Blueprints – Getting Started page, click Apply.
15.	On the Blueprint definitions page, click TWT-BLUEPRINT-ALPHA.
16.	On the TWT-BLUEPRINT-ALPHA page, click Publish Blueprint.
17.	On the Publish Blueprint page, provide the following information and click Publish.:	
    - Version: 1.0
    - Change Notes: Nothing to add
18.	On the TWT-BLUEPRINT-ALPHA page, click Assign Blueprint.
19.	On the Assign Blueprint page, configure the following settings and click Assign:
    - Location: South East Asia
    - Lock Assignment: Don’t Lock
    - User group or application name: tt-vm-admin
    - Tag name: Environment
    - Tag Value: Production

To clean up the environment, delete all resource groups and policy assignments.

