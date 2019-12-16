# AFUN90 Azure Identity Fundamentals – Demo Guide

This guide describes the demo steps for the 6 different demos in the AFUN90 session for Microsoft Ignite the Tour FY20. It can be used to get familiar with the demo steps in the provided recordings, or with access to your own environment, you can reproduce these steps live (ensure you have reliable & fast internet access).

> **Note**: Some of these steps take time, so reproducing these live is not recommended for conference talks.



## Demo 1: Configuring Azure Active Directory and an Administrator account

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Demo steps:
1.	From the Azure Portal, start on the Azure Active Directory/Overvire blade.
2.	Click on Custom domain names.
3.	Click + Add custom domain.
4.	Enter the name tailwindtraders.org (or the name of the domain you have access to) and click Add domain. 
5.	Explain the TXT record ‘destination or points to address’ and  copy that value.
6.	Switch to your DNS record management system (demo shows Azure DNS/Overview tab).
    1.	Click + Record set
        - Leave name blank
        - Change Type to TXT
        - Paste the MS=value into the Value box
        - Click OK
7.	Back in the Azure portal/Custom domain name page, click Verify.
8.	Click Make primary & explain. Click Yes to confirmation message.
9.	Click the Default Directory – Custom domain name breadcrumb navigation, to show the new verified domain name.
10.	Under Manage, click the Users blade.
11.	Click + New User
    1.	Enter the User name as secondary.administrator. tailwintraders.org (or your domain name) should be filled in by default.
    1.	Enter Name as Secondary Administrator 
    1.	Scroll down to Password and click Show Password
    1.	Highlight it, right click and copy it
    1.	Click Create
12.	In another window, log into the Azure Portal as secondary.administrator@tailwindtraders.org
    1.	Click Next
    1.	Enter the initial password you copied in step 11d
    1.	Click Sign in
    1.	Re-enter the password into the Current password field
    1.	Type a new password in both the New password and Confirm password fields
    1.	Click Sign in
13.	Back in the Azure Portal with your original global administrator account, under Azure Active Directory/All Users, click on the Default Directory navigation breadcrumb.
14.	Click Roles and administrators
15.	Click Global administrator
    1.	Click +Add assignment
    1.	Select the Secondary Administrator account
    1.	Click Add



---


## Demo 2: Azure AD Connect

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.


Demo steps:
1.	From the Azure Portal, start on the Azure Active Directory/Default Directory/All Users blade.
    1.	Show that only the two admin accounts exist, with the Source “Azure Active Directory”.
2.	Change to your Windows Server\Active Directory Administrative Center and show the Users.
3.	Run the AzureADConnect installation msi file
    1.	Tick to agree to the license terms & privacy notice, click Continue
    1.	Click Use Express Settings
    1.	Enter the username and password for your Azure AD Global Admin (e.g. secondary.administrator@tailwindtraders.org), click Next
    1.	Enter the username and password for your Active Director Administrator (e.g. TAILWINDTRADERS\administrator, click Next
    1.	The box ‘Start the synchronization process’ should be ticked by default, click Install
    1.	When the configuration is complete, click Exit
4.	Back in the Azure Portal Azure Active Directory/Default Directory/All Users blade, refresh the browser page.
    1.	Show the new user accounts that have appeared, all with the Source “Windows Server AD”
    1.	Click on one user (e.g. Cheryll Duck), scroll down and show the Windows Server AD source under Identity
5.	In a new window, sign in to the Azure Portal as one of the on-prem synced users (e.g. c.duck@tailwindtraders.org) with their on-prem password.



---


## Demo 3: External User

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.


Demo steps:
1.	From the Azure Portal, start on the Azure Active Directory/Default Directory/All Users blade.
2.	Click +New Guest User
    1.	Enter Name: Extra Tailwind
    1.	Email address: extra.tailwind@outlook.com (or another outlook.com account you have access to)
    1.	First name: Extra
    1.	Last name: Tailwind
    1.	Add a Personal message (e.g. Hello Extra Tailwind, We would like to give you access to the Tailwindtraders.org AAD instance)
    1.	Click Invite
3.	Show the Outlook.com mailbox for the invited account.
    1.	Open the Microsoft Invitations email and click Get Started
    1.	On the Review permissions box, click Accept
    1.	The Apps screen will show, with no Apps
4.	Show the Azure Portal, Azure Active Directory/Default Directory/All Users blade.
5.	Click on the Extra Tailwind account
    1.	Under Identity, show the source as Microsoft Account



---


## Demo 4: Self service password reset

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.


Demo steps:
1.	From the Azure Portal, start on the Azure Active Directory/Default Directory/Password reset page (under Manage).
2.	Click the purple banner Get a free Premium trial to use this feature
    1.	Under Azure AD PremiumP2, click the Free trial drop down arrow
    1.	Click Activate
3.	On your Server, run Azure AD Connect and show the Welcome screen.
4.	Click Configure
    1.	Click Customize synchronization options (to highlight it) then click Next
    1.	Enter the Azure AD Global Admin account password, click Next
    1.	At Connect your directories, click Next
    1.	At Domain/OU filtering, click Next
    1.	At Optional Features, tick Password writeback, click Next
    1.	At Ready to configure, check that Start the synchronization is ticked (by default) and click Configure
5.	Show the Azure Portal, Azure Active Directory/Default Directory/All Users blade.
6.	Click on user Cheryll Duck
    1.	Scroll down to Settings and click Edit
    1.	Set the Usage location to Australia, click Save
7.	Click the Default Directory navigation breadcrumb (to return to the Overview page)
8.	Under Manage, click the Licenses blade
    1.	Under Purchased, click on “1 Product”
    1.	Click the product name Azure Active Directory Premium P2
    1.	Click +Assign
    1.	Click Users and groups
    1.	Scroll to find Cheryll Duck, click her name and click Select
    1.	Click Assignment options to verify AAD P2 is on, then click OK
    1.	Click Assign
9.	Click the Default Directory navigation breadcrumb (to return to the Overview page), then click the Password reset blade
a.	Set Self service password reset enabled to All, click Save
10.	Click the Authentication methods blade
    1.	Number of methods required to reset: 1
    1.	Tick Security questions
    1.	Untick Mobile phone (SMS only)
    1.	Leave Number of questions required to register at 5 and Number of questions required to reset at 3
    1.	Click Select security questions
        - Click +Predefined
        - Select 5 questions from the list (e.g. In what city did your parents meet, In what city does your nearest sibling live, In what city was your father born, In what city was your first job, In what city was your mother born) and click OK.
    1.	Click +Custom
        - Type in a New custom security question (e.g. Who is your least favorite sibling?) and click Add.
        - Click OK, OK, Save
11.	Click the Registration blade. Should be set to Require users to register when signing in? as Yes
12.	Sign into the Azure Portal as your user (e.g. c.duck@tailwindtraders.org)
    a.	At the More information required screen, click Next
    b.	 On the don’t lose access to your account screen, at the Security Questions warning, click Set them up now.
    c.	Select 5 security questions and enter their answers, e.g.
        - In what city did your parents meet? Melbourne
        - In what city does your nearest sibling live? Canberra
        - In what city was your father born? Newcastle
        - In what city was your first job? Carlton
        - In what city was your mother born?  Warragul
    d.	Click save answers
    e.	Click Finish
13.	In the Azure Portal, click C.Duck@tailwindtraders at the top right corner and click Sign in with a different account
14.	At Pick an account, click + Use another account
15.	At the Sign in screen, click Can’t access your account
16.	Click Work or school account
17.	At Get back into your account, enter the User ID: as c.duck@tailwindtraders.org
    1.	Enter the characters displayed, click Next
    1.	Enter the correct answers to the 3 displayed security questions, click Next
    1.	Enter a new password and enter the same password again at Confirm new password
    1.	Click Finish



---


## Demo 5: Conditional Access

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.


Demo steps:
1.	From the Azure Portal, start on the Azure Active Directory/Default Directory/Overview.  
2.	Under Security, click on the Conditional Access blade.
3.	Click + New location
    1.	Add Name: USA
    1.	Click Countries/Regions and select United States, click Create
4.	Click the Policies blade
5.	Click + New Policy
    1.	Name: RiskHigh-Block
    2.	Under Assignments, click Users and groups
        - Under Include, click All users, click Done
    3.	Click Cloud apps or actions
        - Under Include, click All cloud apps, click Done
    4.	Click Conditions
        - Click Sign-in risk. Change Configure to Yes and tick High. Click Select
        - Click Done
    5.	Under Access controls, click Grant
        - Tick Require multi-factor authentication, Require device to be marked as compliant, Require Hybrid Azure AD joined device
        - Under For multiple controls, set to Require one of the selected controls
        - Click Select
    6.	Under Enable policy, click On. Leave default to Exclude current user. Click Create.


---


## Demo 6: Custom banned password list

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.


Demo steps:
1.	From the Azure Portal, start on the Azure Active Directory/Default Directory/Overview.  
2.	Under Security, click the Authentication methods blade
3.	Click the Password protection blade
    1.	Under Custom banned passwords/Enforce custom list, click Yes
    1.	Enter some words in the Custom banned password list box, each on a new line (e.g. tailwind and traders
    1.	Click Save
    1.	Change the Mode to Enforced and click Save
