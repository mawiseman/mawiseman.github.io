---
layout: post
title:  "Confluence Deployment Plan Template"
categories: atlassian confluence jira documentation template
author: Mark Wiseman
comments: true
---

Deployment plans are an essential part of Software development but if you ask any developer to actually do one expect to see some eyes rolling! This article details the tempaltes that I regularly use in Conflunce to make this process easier to manage and report on.

## The Tempaltes in Action

| <a href="{{ site.url }}/assets/img/2020-01-09/confluence-deployment-plan-overview.png" target="_blank">![Confluence Deployment Plan Overview]({{ site.url }}/assets/img/2020-01-09/confluence-deployment-plan-overview-thumb.png)</a> | | <a href="{{ site.url }}/assets/img/2020-01-09/confluence-deployment-plan.png" target="_blank">![Confluence Deployment Plan]({{ site.url }}/assets/img/2020-01-09/confluence-deployment-plan-thumb.png)</a> |

## Deployment Plan Templates

To ensure this is a repeatable process create a template in Confluence for this page. If you can't, create a blank page that can be copied each time.

I can't stess enough here how valuable it is to use the Templates helpers. It will ensure that the authors of these templates know what values they should be using / what is expected in each section.

I will only talk to the key configuration elements here. The rest is really just content

### Page Properties Macro

<img alt="Confluence Deployment Plan Page Properties" src="{{ site.url }}/assets/img/2020-01-09/confluence-deployment-plan-page-properties.png" width="500px" />

At the top of the page we need a Page Properties Macro. This is what will allow us to produce the deployment plan overview report.

In the template I include all the valid status' of a deployment plan for reference. But you can see how the template helper text will be valuable as this deployment plan moves through each environment.

### Description of Change: Jira Issue/Filter Macro

<img alt="Confluence Deployment Plan Description of Change" src="{{ site.url }}/assets/img/2020-01-09/confluence-deployment-plan-description-of-change.png" width="500px" />

I recommend using Fix Versions in JIRA to track your deployments. These are more reliable than just referencing a sprint or tickets directly.

The query I set by default: `project = PHO fixVersion = 'XXX' ORDER BY priority DESC`

### Manual Steps: Jira Issue/Filter Macro

<img alt="Confluence Deployment Plan Manual Steps" src="{{ site.url }}/assets/img/2020-01-09/confluence-deployment-plan-manual-steps.png" width="500px" />

I like to use this technique to track manual steps because if developers are continually adding manual step to a deployment plan, then their feature is not included in the release, they need to come back delete and move it.

If they maintain any manual steps within the related ticket(s) everything is moved as one. 

So to support this technique
- Any JIRA tickets that require manual deployments need to be tagged with `deployment-steps`
- The deployment steps should then be recoded in the ticket. I prefer to have a separate field but if that is not an option you can do things like putting them in a comment with a bold `Deployment Steps` title

The default query I set in the template looks like this: `project = PHO fixVersion = 'XXX' AND labels = deployment-steps ORDER BY priority DESC`

### Labels

<img alt="Confluence Deployment Plan Labels" src="{{ site.url }}/assets/img/2020-01-09/confluence-deployment-plan-labels.png" width="500px" />

It's important that our tempalte has the `deployment-plan` label added by default. Otherwise it won't show up in our report.

## Deployment Plan Overviews

### Create Deployment Plan : Create from Template Macro

<img alt="Confluence Deployment Plan Create from Template" src="{{ site.url }}/assets/img/2020-01-09/confluence-deployment-plan-create-from-template-macro.png" width="500px" />

The only customisation i use here is for Template Name. 
- Template name: `@currentDate Deployment Plan`

Using `@currentDate` will prefix the deployment plan's name with todays date which helps for default sorting.

### Deployment Plan List : Page Properties Report

<img alt="Confluence Deployment Plan Page Properties Report" src="{{ site.url }}/assets/img/2020-01-09/confluence-deployment-plan-page-properties-report.png" width="500px" />

The customisation we use here are
- Lable: `deployment-plan`
- In space: `Current space`
- Columns to Show: `Author, Deployment Date, Version, Status`
- Sort By: `Deployment Date`
- Reverse Sort: `checked`
