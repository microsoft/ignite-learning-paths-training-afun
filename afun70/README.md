# AFUN70: Keeping costs down in Azure

 ![Learning Path](https://img.shields.io/badge/Learning%20Path-AFUN-fe5e00?logo=microsoft)

## Session Abstract
Tailwind Traders wants to keep the costs of running their workloads in Azure predictable and within the organization's spending limits. In this session, learn about the factors that go into Azure costs and hear some tips and tools to keep costs manageable - from using Azure calculators and setting spending limits and quotas to utilizing tagging to identify cost owners.

## Table of Contents

| Resources         | Links                            |
|-------------------|----------------------------------|
| PowerPoint        | - [Presentation](presentations.md) |
| Videos            | - [Dry Run Rehearsal](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/AFUN70-Draft2-08OCT-SALEAN.mp4) <br/>- [Microsoft Ignite Orlando Recording](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/AFUN_70_IGNITE.mp4) <br/>- [Director's Cut of Presentation](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/AFUN70-Directors-Cut.mp4) |
| Demos             | - [Demo 1 - Azure Pricing Calculator](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/1.%20Azure%20Pricing%20Calculator_Edited.mp4)  <br/>- [Demo 2 - Azure TCO Calculator](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/2.%20Azure%20TCO%20Calculator%20Edit%20No%20Audit%20OT.mp4)  <br/>- [Demo 3 - Azure Budgets](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/3.%20Azure%20Budgets%20Edited%20No%20Audio%20OT.mp4)  <br/>- [Demo 4 - Azure Cost Analysis](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/4.%20Azure%20Cost%20Analysis%20Edit%20No%20Audio%20OT.mp4)  <br/>- [Demo 5 - Azure Advisor](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/5.%20Azure%20Advisor%20Edit%20No%20Audio%20OT.mp4) |

## Session Story

Within this session we are talking about a fictional customer called “Tailwind Traders”.   They are looking to migrate their workloads to the cloud and have approached us for advice around cost management within the cloud.

<li>We start off the session talking about on-prem workloads and how we are familiar with pricing them up and their various components and highlighting that there are often costs we forget about in the on prem world and we set the scene that costing up virtual machines in Azure is different.</li>
<li>Our aim is to take the audience and Tailwind Traders through three key stages of cost management, estimating cloud costs, setting cost guardrails and reviewing actual costs.</li>
<li>Within the Estimating Cloud Costs section of the session, we talk about the importance of there being no fixed cost for the cloud and it all depends.  We introduce the audience to the Azure Pricing Calculator and demonstrate how it can be used to estimate the cost of the workloads we wish to host within Azure.   We also cover off that it’s not just the people deploying the workloads that are responsible for keeping an eye on costs and that it’s a community approach from Chief Financial Officer(CFO) to IT Pro.</li>
<li>We also introduce the audience to the notion that when moving to the cloud it can be a bit complex as we maybe deploying that workload in a different way in the cloud, i.e VMs on prem and serverless in the cloud.</li>
<li>We then go on to elaborate on how pricing up the cloud can depend.  And talk about how design decisions such as which disk type you use or the region you use can affect cost.  And remind the audience to be mindful of these things during their design phase.</li>
<li>Another common question by customers is “Will the cloud be cheaper?” And our fictional customers, Tailwind Traders are no different.  This is the section where we introduce the Azure Total Cost of Ownership calculator and show the audience how you can use it to compare cloud costs with on prem costs.</li>
<li>The second section Setting up Cost Guardrails, this section isn’t about highlighting how we stop innovation, it’s about showing we can protect the people deploying solutions and the company from spending far to much by mistake.</li>
<li>We introduce RBAC roles and how we can share set up roles for the CFO to see the cost data but not interact with the resources etc.  We also talk about how tags can be used to track costs and then using Azure Policy to enforce those tags.  This session just plants the seeds for using these products in Azure for cost management purposes.</li>
<li>Tailwind Traders are hoping to be able to track where they are with the spend before the bill comes in and this is where we suggest using Azure budgets to set up tracking and alerting for that purpose.</li>
<li>The third section Reviewing Cost Actuals, starts off talking about how we can help Tailwind Traders understand the bill they now have.  We want to help them break down that bill and understand where they are spending the most money and identify those areas.  Here we introduce and demo Azure Cost Analysis to do this.</li>
<li>Now they’ve reviewed their bill and can understand it, they want to try and find the areas for cost savings. And this is a common question out in the field. And we introduce and show how Azure Advisor recommendations can help with that.</li>
<li>In the summary section of the presentation we talk to the audience and Tailwind Traders about how sometimes your bill can come out higher than expected but tooling won’t be able to explain all of that so it’s key to remember to speak to your staff to find out why and what has been happening. It could be that the bill is higher due to positive moves elsewhere. And we wrap up with some cost saving tips.</li> 
</ul>
By the end of the session the audience should have basic understanding of the cost management tools that are built into Azure and how to use them within a real world scenario by relating them to problems that the fictional customer Tailwind Traders has. 

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


- This guide
- [Powerpoint Presentation that includes Speaker Notes](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/afun70.pptx)
- [Demo/Lab Instructions](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/AFUN70%20Demo%20Guide.docx)
- [Full Length Recording of Presentation](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/AFUN70-Draft2-08OCT-SALEAN.mp4)
- [Director's Cut of Presentation](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/AFUN70-Directors-Cut.mp4)
- [Ignite 2019 Session Presentation](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/AFUN_70_IGNITE.mp4)


### Deployment

Almost all sessoins can be performed from a trial Azure subscription. Instructions for configuring the subscription with specific assets such as Virtual Machines and resource groups can be found in the Demo/Lab instructions document linked above, often in the form of a script that can be run from Cloud Shell. 

### Demo Videos

- [Demo 1: Azure Pricing Calculator](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/1.%20Azure%20Pricing%20Calculator_Edited.mp4)
- [Demo 2: Azure TCO Calculator](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/2.%20Azure%20TCO%20Calculator%20Edit%20No%20Audit%20OT.mp4)
- [Demo 3: Azure Budgets](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/3.%20Azure%20Budgets%20Edited%20No%20Audio%20OT.mp4)
- [Demo 4: Azure Cost Analysis ](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/4.%20Azure%20Cost%20Analysis%20Edit%20No%20Audio%20OT.mp4)
- [Demo 5: Azure Advisor](https://globaleventcdn.blob.core.windows.net/assets/afun/afun70/5.%20Azure%20Advisor%20Edit%20No%20Audio%20OT.mp4)

