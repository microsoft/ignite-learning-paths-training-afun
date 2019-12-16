# AFUN90: Azure Identity Fundamentals

 ![Learning Path](https://img.shields.io/badge/Learning%20Path-AFUN-fe5e00?logo=microsoft)

## Session Abstract
Identity is the core of most workloads in Azure, and Tailwind Traders wants to implement Azure Active Directory in a way that correctly meshes their on-premises identities with those required in the cloud. In this session, learn the difference between authentication and authorization, as well as different identity models. Then, dive into the benefits of conditional access and multi-factor authentication (MFA) and wrap up with a demo showing you how to implement these types of extra protection.

## Table of Contents

| Resources         | Links                            |
|-------------------|----------------------------------|
| PowerPoint        | - [Presentation](presentations.md) |
| Videos            | - [Dry Run Rehearsal](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/AFUN90%20Identity%20Fundamentals.mp4) <br/>- [Microsoft Ignite Orlando Recording](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/AFUN_90_IGNITE.mp4) <br/>- [Director's Cut of Presentation](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/AFUN90%20Identity%20Fundamentals.mp4) |
| Demos             | - [Demo 1 - Create user and convert to global admin](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/1.AAD-Rename-New-User-Global-Administrator.mp4)  <br/>- [Demo 2 - Azure AD Connect](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/2.Azure-AD-Connect.mp4)  <br/>- [Demo 3 - Add External User](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/3.External-User.mp4)  <br/>- [Demo 4 - Self Service Password Reset](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/4.Self-Service-Password-Reset.mp4)  <br/>- [Demo 5 - Conditional Access](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/5.ConditionalAccess.mp4)  <br/>- [Demo 6 - Custom Banned Password List](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/6.CustomBannedPasswordList.mp4)  |

## Session Story
In this session you’ll demonstrate how fictional customer Tailwind Traders has adopted Azure Active Directory and configured some of its features. This talk starts with some basic concepts, like the difference between authentication & authorization, and finishes by introducing the concept of passwordless. It also explains the difference between Active Directory, Azure Active Directory and Microsoft Accounts. 

Tailwind Traders starts out with a blank Azure Active Directory, connects their on-premises Active Directory users (using Azure AD Connect), then allow guest access, self-service password reset, conditional access and MFA, and Azure AD Password protection (with a custom banned password list).  The capabilities build on each other, as the customer extends their use of the AAD platform, starting with the basics. 

This session is intended to get the audience familiar with Azure Identity concepts, why & when they would use different features and how to get started with basic configuration of the most common features. It also features some demo components from the end user perspective, so attendees can see the consequences of the things that have been configured. 

<ul>
<li>You’ll start the session by setting the scene of why Identity is so important - taking the audience back to a time when we used to secure things by keeping all our data on-premises behind a firewall, and only being able to access it from the office. You’ll explain that now people want to work from any device and any place at any time, Identity is the new control plane that’s protecting access to company data. Then, you’ll explain how both Authentication & Authorization are needed for an effective security posture. (note: this is included in the AZ-900 Azure Fundamentals exam objectives).</li> 
<li>Then you’ll set the scene with Tailwind Traders’ Identity & Access goals, noting that while security is the driver, any initiatives also need to be easy & simple for the end users. You’ll then break down those goals into how they will be achieved, which sets the talk up for the demos that will follow.</li> 
<li>Next, you’ll demonstrate how Tailwind Trader’s configure their first Azure Active Directory and add a second global administrator account. You’ll explain the technical basics of Azure Active Directory, including using roles for Admin access, and explain the differences between that product and Active Directory. This is an important piece of bridging knowledge, as many attendees are familiar with AD and think of Azure AD in the same context (e.g. where are the domain controllers?)</li> 
<li>Then, there’s a quick mention of Office 365 and Microsoft 365, and you’ll explain how AAD is the underlying directory services for these products. That’s important to customer who may have lead in the Cloud with those, before looking at Azure services. Also explain that the admin centers for those products contain specific service settings, but the users are still AAD accounts.</li> 
<li>Then you’ll demonstrate configuring Azure AD Connect to an existing Active Directory server and syncing across user accounts. Follow this with an explanation of how that works (at a high level), then add more detail to explain Password Hash Sync and Pass thru authentication and their differences. Highlight that the passwords themselves are never synced, and that pass thru authentication is an option for highly regulated companies that can’t even have their passwords hashes in the Cloud. Both of these options give a Seamless Single Sign On solution, linking back to one of Tailwind Traders’ key goals for end user simplicity.</li>  
<li>You’ll then move on to Guest access and demonstrate how to add an external account that’s an Outlook.com account. Here you’re showing the power of linking to a different trusted Identity provider, but explain that you will never be able to sync enterprise-grade accounts (AAD or AD) to the consumer Microsoft Account service. You’ll also explain Azure AD B2B and B2C, but this is to highlight that the products exist and when you would use them, as there is not time in this session to include these in depth (remember, it’s a Fundamentals session).</li> 
<li>Next, you’ll demonstrate configuring Self-Service Password Reset, from both the org level (configuring org-wide allowed secret passwords) and the end-user experience. Explain how this takes the burden off the helpdesk, even for on-prem user accounts, and lets the user get back into their systems securely and as fast as possible.</li>  
<li>Then, you’ll demonstrate configuring Conditional Access and explaining how it works. This is an important piece in the MFA story – that we can prompt for another authentication factor when risky conditions or behaviour have been detected. Note the difference between the two – you can set those conditions AND Microsoft also analyses login behaviour for risk.</li> 
<li>There’s now a series of slides explaining Smart Lockout, which will animate as they are clicked through. If you’re finding time is tight on this session, you can drop this section out. It’s a good scenario though compares to the traditional Active Directory lockout, which would lock the account out on too many incorrect password attempts, regardless if they were valid user mistakes or not, and shows people that Cloud identities can be protected from that sort of password spray attack.</li>
<li>Next, you’ll demonstrate configuring the custom banned password list. This is a pretty quick demo, but then explain how this can also protect on-premises Active Directory accounts with the same interface. There’s an architecture slide on this, that you don’t need to go into too much detail on.</li>
<li>Finally, you’ll talk about Passwordless access with Windows Hello for Business, the Microsoft Authenticator app and FIDO security keys. Note that the Authenticator app in this instance isn’t being used for an MFA code, and that the FIDO keys have to be unlocked (eg with biometrics).</li>
</ul>
At the end of this session, you’ll refer back to Tailwind Traders’ original goals and how we’ve solved them. You’ve now taken the attendees through the customer journey, from just starting out with AAD to exploring the advanced features that come with this Cloud Identity platform. 

## How to use this repository
Welcome, Presenter!

We're glad you are here and look forward to your delivery of this content.

As an experienced presenter, we know you know HOW to present so this guide will focus on WHAT you need to present.

Among many resources, a full run-through video of the presentation, delivered by the original content creator is available to review and a great starting point. A director's cut edition, with additional information from the original content creator, is also available for review.

Along with the video of the presentation, this document will link to all the assets you need to successfully present including PowerPoint slides, demo videos, and demo instructions.

Read this document in its entirety. Watch the video presentation(s), review and practice with the demo videos and have a fantastically successful time presenting this content.

Ask questions of the Lead Presenter and trained speakers (list below).

## Getting Started
These instructions consist of the steps you should go through in preparing to present this content:

### Assets in the Train-the-Trainer Kit


This guide</li>
- [Powerpoint Presentation that includes Speaker Notes](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/afun90.pptx)
- [Demo Lab Instructions](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/AFUN90%20Demo%20Guide.docx)
- [Full Length Recording of Presentation](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/AFUN90%20Identity%20Fundamentals.mp4)
- [Director's Cut of Presentation](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/AFUN90%20Identity%20Fundamentals.mp4)
- [Ignite 2019 Session Presentation](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/AFUN_90_IGNITE.mp4)


### Deployment

Almost all sessions can be performed from a trial Azure subscription. Instructions for configuring the subscription with specific assets such as Virtual Machines and resource groups can be found in the Demo/Lab instructions document linked above, often in the form of a script that can be run from Cloud Shell. 

### Demo Videos
All technical steps are provided in the form of pre-recorded video demos, which have had “time slow” tasks sped up or edited. You can narrate the videos at your own pace, pausing when necessary, or you can reproduce live (though this is not recommended due to some steps taking time eg user account sync). Details on environment perquisites (inc AAD P2 licensing) are included in the lab guide. 

- [Demo 1: Create new user and convert to global administrator](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/1.AAD-Rename-New-User-Global-Administrator.mp4)
- [Demo 2: Azure Active Directory Connect](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/2.Azure-AD-Connect.mp4)
- [Demo 3: Add External User](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/3.External-User.mp4)
- [Demo 4: Self Service Password Reset](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/4.Self-Service-Password-Reset.mp4)
- [Demo 5: Conditional Access](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/5.ConditionalAccess.mp4)
- [Demo 6: Custom Banned Password List](https://globaleventcdn.blob.core.windows.net/assets/afun/afun90/6.CustomBannedPasswordList.mp4)

