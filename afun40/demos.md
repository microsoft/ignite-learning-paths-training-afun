# Demos



## DEMO 1 - Azure Security Center Secure Score

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will view the secure score of a subscription with 2 VMs deployed. To complete this demonstration, perform the following steps:

1. Sign on to the Azure portal with the prime.admin account.

2. On the Azure Portal home page, click Security Center. If Security Center is not present, type Security Center in the search bar.

3. When the Security Center page opens, click Secure Score. This will open the Secure Score blade of Azure Security Center.

4. Review the following section of the Secure Score page, taking note of each score
   - Overall secure score
   - Compute &amp; apps resources
   - Networking resources
   - Data &amp; storage resources
   - Identity &amp; access resources.

1. Click on Compute &amp; apps resources to open the Compute and Apps resources page.

1. On the Overview page, make note of each recommendation and the Secure Score Impact for each recommendation.

1. Click on the VMs and Computers section. Note that one VM is listed, TT-2019-A. This is the VM that you created prior to performing this demo from the Cloud Shell environment.

1. Click on TT-2019-A to see recommendations specific to this virtual machine. By default, there will be a number of high and medium status recommendations related to the VM.

1. Click on Passed assessments to view a list of security controls that the VM meets.

1. Click on Unavailable assessments to view a list of assessments that are unavailable for this specific VM.

1. Near the top of the screen, below the title bar, click on Security Center – Secure Score. This will return you to the Secure Score blade of azure Security Center.

1. Click on Network Resources.

1. Review the items including Network Map and Adaptive Network Hardening.

1. Review the recommendations and their associated secure scores.

1. Near the top of the screen, below the title bar, click on Security Center – Secure Score. This will return you to the Secure Score blade of Azure Security Center.

1. Click on Identity &amp; Access.

1. Review the recommendations and their associated secure scores. These are likely to involve MFA.

1. Keep the browser window open for the next demo.


---


## DEMO 2 - Azure Security Center Policy and Compliance

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will view an assessment of the security of resources in the subscription when measured against the Azure CIS benchmark and the ISO 27001 security controls benchmark.

1. In the Security Center section of the Azure Console, click Regulatory Compliance.

1. Review the summary compliance status of Azure CIS, PCI DSS, ISO 27001 and SOC TSP.

1. With the Azure CIS benchmark selected, scroll down and expand the Storage Account section.

1. Click on section 3.7 Ensure default network access rule for Storage Accounts is set to deny to expand this subsection.

1. Review the Threats, Remediation Steps, and Effected Resources. Also view which resource is the source of this control warning.

1. Go back to the list of Azure CIS controls, expand Virtual machines, and review flagged non-compliant controls.

1. Click on control 7.1 to expand it and review the recommendation.

1. Click on control 7.2 to expand it and review the recommendation.

1. Click on control 7.5 to expand it and review the recommendation.

1. Scroll back up and then click on ISO 27001.

1. Review each of the compliance controls that the workloads are compliant with and non-compliant with the ISO 27001 controls.

1. Expand A12 and review the details of where the workloads are compliant and non-compliant.

1. Click on Control A12.5 and review which steps need to be taken to bring the workload back into compliance.

1. Expand A13 and review the details of where workloads are compliant.

1. Keep the browser window open for the next demo.


---


## DEMO 3: Azure Resource Security Hygiene

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will remediate several resource security issues using the Azure Security Center console.

1. In the Security Center section of the Azure Console, click Recommendations.

1. Review the list of recommendations and there associated security score. Note which recommendations have the highest security score. Also note the severity assigned to each recommendation.

1. Click on the recommendation  **Install endpoint protection solution on virtual machines**.

1. Ensure that VM TT-2019-A is selected and then click Install on 1 VMs.

1. On the Select Endpoint Protection page, click Microsoft Antimalware and then click Create.

1. Review the Install Microsoft Antimalware Protection settings and then click OK.

1. Towards the top of the page, under the search bar, click Security Center – Recommendations to return to the list of available recommendations.

1. Click on Disk encryption should be applied on virtual machines. Review the recommendations.

1. Towards the top of the page, under the search bar, click Security Center – Recommendations to return to the list of available recommendations.

1. In the list of available recommendations, click on  **Just-In-Time network access control Should be applied on virtual machines**.

1. On the Apply just in time VM access control, select the checkbox next to TT-2019-A and then click Enable JIT.

1. Click the ellipsis and then click Delete next to ports 22, 5985 and 5986.

1. Click on port 3389 and modify the settings so that the maximum request time is set to 10 hours. Click OK and then click Save.

1. Towards the top of the page, under the search bar, click Security Center – Recommendations to return to the list of available recommendations.

1. Click Refresh in the browser and note that the recommendations related to Just-In-Time and Endpoint Protection are no longer present.


---


## DEMO 4 - Privileged Identity Management

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will configure privileged identity management to allow for passwords to be changed once and appropriate role has been requested and assigned.

1. Sign in to the Azure Portal as don.funk

1. In the Azure Active Directory blade, click Users and in the list of users, click Sam Abolrous.

1. On the Sam Abolrous user properties page, click Reset Password.

1. Review the warning message instructing you that the password cannot be reset.

1. In the Search Bar, type Privileged Identity Management. Click Privileged Identity Management in the list of results.

1. In the Privileged Identity Management quick start blade, click My Roles.

1. In the list of Eligible Roles, click Activate next to Password Administrator.

1. On the Password Administrator page, click Activate.

1. On the Activation page, enter the Activation reason as &quot;Change Sam Abolrous Password&quot; and click Activate.

1. Return to the Privileged Identity Management, My Roles, Azure AD Roles page that the Password Administrator role has been granted.

1. In the Azure Active Directory blade, click Users and in the list of users, click Sam Abolrous.

1. On the Sam Abolrous user properties page, click Reset Password.

1. On the Reset Password page, click Reset Password again.

1. Sign out of the Azure portal and sign back in as prime.admin.

---

## DEMO 5 - Storage Account Network Traffic Restrictions

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will configure traffic restrictions so that only specific subnets are able to communicate with a specific storage account.

1. Navigate to the Virtual Networks blade and select the NewVNet virtual network.

1. With NewVNet selected, click Subnets.

1. In the NewVNet – Subnets blade, click +Subnet.

1. In the Add Subnet blade, provide the following information and then click OK

   - Name: Private
   - Address Range: 192.168.15.0/24
   - Service Endpoints: Microsoft.Storage

1. In the Azure Portal Search Bar, type Storage Accounts and then click on the Storage Account item.

1. In the Storage Accounts blade, click +Add.

1. On the Create Storage Account page, set the resource group to TT-VMs.

1. On the Create Storage Account page, configure the following additional settings:
   
   - Storage account name: twtstorage
   - Location: Southeast Asia
   - Performance: Standard
   - Account kind: StorageV2
   - Replication: Locally-redundant storage (LRS)

2. Click Next: Advanced.

3. On the Create a storage account:Advanced page, next to Virtual Networks: Allow Access From click Selected network.

4. On the Virtual Network dropdown, select NewVNet.

5. On the Subnets drop down, ensure that only Private subnet is selected.

6. Click Review + Create.

7. Keep the browser window open for the next demo.


---


## DEMO 6: Azure SQL Advanced Data Security

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will demonstrate the configuration of advanced data security for an Azure SQL Instance.

1. In the Azure console, select the Vector-Sigma Azure SQL server that you created from the Azure CLI prior to starting the demonstrations.

1. Under Security, click Advanced Data Security.

1. Under Advanced Data Security, select On.

1. Under Vulnerability Assessment Settings, click on the Storage Account and select the sqlsecurityemphemera account.

1. Under send scan reports to, enter the email address that you used to sign up to the azure trial subscription.

1. Under Advanced Threat Protection Settings, enter the email address that you used to sign up to the azure trial subscription.

1. Click on Advanced Threat Protection types.

1. In the Advanced Threat Protection Types, ensure that the following are enabled:

   - SQL injection
   - SQL injection vulnerability
   - Data exfiltration
   - Unsafe action
   - Anomalous client login

1. Click OK.

1. Click Save.


---


## DEMO 7: Azure Sentinel

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will configure Azure Sentinel to examine Azure AD logs and Azure administration logs for suspicious activity.

1. In the search bar of the Azure console, type Sentinel and then click on Azure Sentinel.

2. In the Azure Sentinel workspaces pane, click on Add.

3. Click Create a New Workspace and enter the name as Tailwind-AzureAD. Click Add Azure Sentinel.

4. In the Azure Sentinel pane, click Data Connectors under Configuration.

5. In the list of data connectors, click Azure Active Directory and then click Open connector page.

6. Next to Azure Active Directory Sign-In Logs, click Connect

7. Next to Azure Active Directory Audit Logs, click Connect.

8. Once both logs are connected, close the window to return to the list of data connectors.

9. Click Azure Activity and then click Open Connector Page.

10. On the Azure Activity connector page, click Configure Azure Activity Logs.

11. On the Azure Activity Log page, click on the subscription that you are using and then click Connect.

12. Under the search bar, click Azure Sentinel – Data Connectors.

13. In the list of connectors, click Azure Active Directory Identity Protection and then click Open Connector Page.

14. Next to Azure Active Directory Identity Protection, click Connect.

15. Under the search bar, click Azure Sentinel – Data Connectors.

16. In the list of connectors, click Azure Active Directory. You may have to wait some time. Next to the connector should be a status message indicating the last time data was received. Wait until this field is populated.

17. Click on Workbooks.

18. Click on Azure AD Sign-in logs.

19. Click on Azure AD Sign-in logs workbook.

20. Scroll down on the workbook detail page and click View Workbook.

21. Review the sign in analysis and the events that are present in the logs.