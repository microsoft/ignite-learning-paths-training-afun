# Azure Security Fundamentals

## Session Abstract
Tailwind Traders wants to improve the security of their workloads that are running in the cloud. In this session, learn how to use: Azure Security Center to determine how to configure Azure resources (using security best practices), Azure Sentinel to locate and respond to suspicious activity, and Azure Bastion for secure administrative connections into Azure.

## Session Story

In this session you’ll demonstrate how Tailwind Traders was able to perform traditional virtual machine management tasks using the tools that are built into Azure. You’ll be using the fictional company “Tailwind Traders” as a narrative device. Tailwind Traders represents “everyone”. In this case they’ve deployed virtual machines to the cloud, but they don’t have much understanding of what they need to do to perform traditional VM management tasks with those resources. They have assumed, incorrectly, that by deploying a VM to the cloud, all of the traditional things, like VM backup and operating system updates are automatically taken care of for them by Microsoft.

- You’ll start the session by providing a reminder about the shared responsibility model. You do this to contextualize the session and to remind the audience that while the security of the underlying fabric and infrastructure is Microsoft’s responsibility, the management and security of the IaaS VM workloads that organizations deploy to Azure is the responsibility of the subscription owner. In other words, Tailwind Traders has it wrong and Microsoft doesn’t handle things such as automatically backing up their VMs and applying software updates as they become available.
- You’ll move on to showing attendees how Tailwind Traders was able to allow secure administrative connections to VMs running in their subscription without allowing access to any RDP or SSH client on the internet. You’ll demonstrate how secure connections can be made without a VPN to an IaaS VM that does not have a public IP address using Bastion and how Just In Time VM access is configured and functions. This solves a problem Tailwind Traders has where some administrators opened up RDP and SSH to every host on the internet.
- You’ll next show how the native backup and recovery functionality of Azure can be enabled to allow Tailwind Traders to automatically backup and recover entire VMs. You’ll also show how this functionality can be leveraged to backup and recover SQL instances running within VMs. This allows Tailwind Traders to recover VMs and SQL databases in the event of data corruption or other problems.
- The next step is demonstrating how you can configure and manage software updates for both Tailwind Trader’s Windows and Linux virtual machines running in Azure. This will allow Tailwind Traders to be sure that their VMs are as secure as possible when it comes to software updates.
- You’ll then show attendees how Tailwind Traders was able to ensure that changes made to virtual machines, such as the installation of applications and packages, can be tracked by enabling Inventory and Change Tracking. This allows Tailwind Traders to be notified if unusual software is deployed within their VMs.


Many organizations are like Tailwind Traders and assume that because they have heard the functionality to do things like automatically back up virtual machines and apply software updates exists within Azure, it is turned on by default. In presenting this session you’ll help attendees understand that it is their organization’s responsibility under the shared responsibility model to leverage the tools that are provided for them, and that Microsoft does not enable these features by default.

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

- This guide</li>
- [Powerpoint Presentation that includes Speaker Notes](https://globaleventcdn.blob.core.windows.net/assets/afun/afun40/afun40.pptx)
- [Demo/Lab Instructions](https://globaleventcdn.blob.core.windows.net/assets/afun/afun40/AFUN%2040%20LAB%20NOTES-Draft1.docx)
- [Full Length Recording of Presentation](https://globaleventcdn.blob.core.windows.net/assets/afun/afun40/AFUN-40-BETA-RUN-2.mp4)
- [Director's Cut of Presentation](https://globaleventcdn.blob.core.windows.net/assets/afun/afun40/AFUN-40-DIRECTOR-CUT.mp4)


### Deployment

Almost all sessions can be performed from a trial Azure subscription. Instructions for configuring the subscription with specific assets such as Virtual Machines and resource groups can be found in the Demo/Lab instructions document linked above, often in the form of a script that can be run from Cloud Shell. 

### Demo Videos

- [Demo-1-ASC-Secure-Score](https://globaleventcdn.blob.core.windows.net/assets/afun/afun40/Demo-1-ASC-Secure-Score.mp4)
- [Demo-2-ASC-Compliance](https://globaleventcdn.blob.core.windows.net/assets/afun/afun40/Demo-2-ASC-Compliance.mp4)
- [Demo-3-Resource-Security-Hygiene](https://globaleventcdn.blob.core.windows.net/assets/afun/afun40/Demo-3-Resource-Security-Hygiene.mp4)
- [Demo-4-PIM](https://globaleventcdn.blob.core.windows.net/assets/afun/afun40/Demo-4-PIM.mp4)
- [Demo-5-Storage-Firewall](https://globaleventcdn.blob.core.windows.net/assets/afun/afun40/Demo-5a-Storage-Firewall.mp4)
- [Demo-6-Azure-SQL-Security](https://globaleventcdn.blob.core.windows.net/assets/afun/afun40/Demo-6-Azure-SQL-Security.mp4)
- [Demo-7-Azure-Sentinel](https://globaleventcdn.blob.core.windows.net/assets/afun/afun40/Demo-7-Azure-Sentinel.mp4)


