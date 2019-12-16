# Azure Cost Management Fundamentals – Demo Guide

This guide describes the demo steps for the 5 different demos in the AFUN70 session for Microsoft Ignite the Tour FY20. It can be used to get familiar with the demo steps in the provided recordings, or with access to your own environment, you can reproduce these steps live (ensure you have reliable & fast internet access).


## DEMO 1-  Azure Pricing Calculator

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Demo steps:
1.	From the Azure Pricing Calculator https://azure.microsoft.com/en-au/pricing/calculator/  Point out that the calculator allows you to sign in (top right hand corner). This gives you extra functionality (Save & share estimates, select your own Enterprise Agreement pricing).
1.	Show Featured pane - explain you can add individual Azure services
1.	Click the Example Scenarios tab and choose CI/CD for Azure Web Apps – explain the architecture diagram and Products list.
    1.	Click Add to estimate & show individual components. Explain you can tweak these.
    1.	Hit X on that estimate tab to clear (continue without saving), and click back on the Products tab.
1.	Click on Virtual Machines
    1.	Explain Region etc all affect pricing.
    1.	Explain Tiers (Basic=no load balance, no auto scale. Low priority=uses spare data center capacity & can be turned off. Both are cheaper than Standard).
    1.	Explain instances (like t-shirt sizing). Click Pricing details (under More info) and scroll down to Explore all Virtual Machine options, for instance series explanations and configurations.
5.	Back on the pricing calculator, change to a different instance (e.g. D4v3).
6.	Under Billing Option 
    1.	Explain reserved instances (pre-payment of time commitment for a discount) and Azure Hybrid Benefit (re-use of existing Windows Server license that is enrolled in Software Assurance, not available with Dedicated Hosting).  
7.	Under Managed OS Disks
    1.	Change to Standard SSD. 
    1.	Explain Storage transactions (may be hard to estimate but do not have a large cost impact).
8.	Under Support options
    1.	show list of support offerings & explain. 
9.	Under Programs and Offers
    1.	click the Licensing Program dropdown & choose Enterprise Agreement (EA) 
    1.	then under Selected agreement click the blue None selected (change). 
    1.	Choose the Contoso (demo) EA (or your own EA account) and click Apply.
10.	Show Export/Save/Share buttons. Click Save.
11.	Scroll back up to the top of your estimate. 
    1.	In the product search bar type “backup” then select Azure Backup. 
    1.	On the Added dialogue, click View.
12.	Set the Region to West US and change to 1TB of data.
13.	Under Storage 
    1.	explain Redundancy options.
    1.	Set Retention Range of RPs (Recovery Points) to 4 Weekly RPs, 1 Monthly. 
    1.	Explain Storage Cost calculation (increases over time).
14.	Scroll back up to the top of Your Estimate - Explain the Clone button, if you want to duplicate this configuration of Virtual Machines in your estimate (instead of adding new from scratch). 



---


## DEMO 2-  Total Cost of Ownership Calculator

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Demo steps:
1.	From the Total Cost of Ownership Calculator https://azure.microsoft.com/pricing/tco/calculator/,  point out that the calculator allows you to sign in (top right hand corner). This gives you extra functionality (Download, Save & share and select your own Enterprise Agreement pricing).
2.	Change default settings for Workload 1 to be:
    1.	Servers = 3,  
    1.	Procs pers server = 2
    1.	Core(s) per proc = 1
3.	Turn on Windows Server 2008/2008 R2 toggle – explain this mimics paying for security updates if kept on-prem. 
4.	Scroll down and explain you can add Databases, more Storage and tweak Networking.
5.	Click Next.
6.	Under Adjust assumptions, explain assumptions you can tweak 
    1.	Software assurance
    1.	geo-redundant storage
    1.	no B-series burstable VMs).
7.	Show other cost assumptions: 
    1.	Electricity costs
    1.	Storage costs
    1.	IT labor costs.
8.	Show Other assumptions/Data center costs. 
    1.	Scroll down to Data center construction cost per rack, useful life, rack units per rack. 
9.	Show Networking costs/network maintenance cost. Click Next. 
10.	Show Timeframe, Region, Licensing program.
11.	Show savings graphs.
12.	Scroll down and show cost breakdown. 
    1.	Explain how even with Azure, the cost breakdown summary still includes an IT labor component.
13.	Scroll down and expand the detailed Estimated on-premises cost v Estimated Azure cost side-by-side.
14.	Scroll down and show Download, Share & Save buttons.



---


## DEMO 3 - Azure Budgets

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Demo steps:
1.	From the Azure Portal https://portal.azure.com, start on the Cost Management + Billing/Cost Management/Overview page.
2.	Click on Budgets
    1.	Explain progress bars, updating with latest cost data.
3.	Click +Add
4.	Under Budget scoping, click Add filter and show drop downs.
    1.	Set to Tags (very last one), then the environment tag and dev value (or choose appropriate for your own subscription)
    1.	Enter name DevEnv (no spaces)
    1.	Leave reset period and dates as default
    1.	Leave Budget Amount set to default
    1.	Scroll down to show historical cost data & suggested budget based on costs.
    1.	Scroll back up and change budget amount to $50 (or an appropriate amount). 
    1.	Click Next
5.	Scroll up to set alert conditions.
    1.	Enter 50, 75 & 90 percent
    1.	Explain that at some scopes (e.g. resource groups) budgets support Action Groups & triggering of automation via Runbooks (e.g. to shut down VMs), but by default, Budgets will NOT stop any services. 
    1.	Add email for alert recipient (e.g. budgetalerts@twt.com)
    1.	Click create.
6.	Click Name column title to sort alphabetically & explain the percentage bar is already showing.
7.	Click on DevEnv budget and show Pin to dashboard.



---


## DEMO 4 - Azure Cost Analysis

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Demo steps:
1.	From the Azure Portal https://portal.azure.com, start on the Cost Management + Billing/Cost Management/Overview page.
2.	Click on Cost Analysis
    a.	Show default graphs.
3.	For the Contoso Demo account, ensure date range is August 2019.
4.	Set BUDGET to NONE
5.	Change Group by: None to Resource Type
    1.	Explain the graph shows the top 9 things, then everything else in Others 
    1.	Hover over bars to show list of amounts
6.	Click on bright blue line for Virtual Machines. Explain how it adds the filter.
7.	Change Group by to Resource
    1.	Explain how you can choose different settings for different Azure resources e.g. storage & meters for disk activity, replication etc.
    1.	Show list of VMs
8.	Change view to Table for more info.
9.	For the Contoso demo account, explain “SQL” higher cost was for only 2 days, but “dvm” cost across the month is higher. 



---


## DEMO 5: Azure Advisor

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Demo steps:
1.	From the Azure Portal https://portal.azure.com, start on the Cost Management + Billing/Cost Management/Advisor recommendations page.
2.	Explain different types of recommendations (from descriptions).
3.	Click on Right-size or shutdown underutilized virtual machines
4.	Explain you can see 
    1.	which machines
    1.	you can click straight on one ot go into it’s properties
    1.	or you can click on the different recommended actions (explain them) 
    1.	or under Action you can postpone or dismiss the recommendation for that machine.
5.	Click on Resize the virtual machine (recommended action) in any VM
    1.	explain the VM sizing pane and the restart warning info bar.

