# Deployment

## Prerequisites for reproducing live:

- You will need access to an Azure tenant that you have Global Administrator rights too.
- If you are a Microsoft FTE, you will NOT be able to reproduce these steps under the standard Microsoft Ignite the Tour Demo Subscription, as it lives under your @microsoft.com work account.
- Access to a domain name that you can add a TXT record to. However, it is not recommended that you do this step live, as DNS record updates can take time to populate.
- Access to one Windows Server 2016 or later, with fake user accounts.
- The Azure AD Connect installer (.msi file) on your Server, dowloaded from https://www.microsoft.com/en-us/download/details.aspx?id=47594 
- Azure Active Directory P2 licenses are needed for the Self servics password reset demo. These can be trial licenses (activated during the demo, as the recordings show), or you may need to purchase these prior if your Azure tenant has already used a AAD P2 trial before.  
- If your Azure login shows the Preview portal by default, instead use https://portal.azure.com/?feature.customportal=false#home


## Before your session begins:

1.	The Azure Portal contents can look tiny at a high resolution. Recommend 1280x720 and collapse the Portal blades as you go (with the << symbol) to increase the screen real estate.
