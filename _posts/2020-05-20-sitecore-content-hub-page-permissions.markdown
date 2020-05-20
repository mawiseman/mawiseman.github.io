---
layout: post
title:  "Sitecore Content Hub Page Permissions"
categories: sitecore contenthub
author: Mark Wiseman
comments: true
---

I have been working through the Sitecore Content Hub Training and got stuck trying to configure page permissions for ages. Every time that I tried to add the **Portal.Page** condition all I could select was the **Home** value. 

It turns out it is just a slight oversight in user experience and the trick is to click on the actual name of the Home item.

This affects version **3.1.04**

<img alt="page permissions drill down" src="{{ site.url }}/assets/img/2020-05-20/page-drill-down.gif" />

I think updating it to function like the Taxonomy Selector for Asset details would be much better:

<img alt="taxonomy selector" src="{{ site.url }}/assets/img/2020-05-20/taxonomy-selector.gif" width="450px" />

## Adding page permissions
In case you are interested here is the process to add page permissions to a User Group here are the steps I use.

### Navigate to the User Group you would like to edit
1. Navigate to: Manage > Users > User Groups > Policies

### Create a new Rule
1. Click New Rule
1. Search for "page"
1. Select: "Portal page (Portal.page)"
1. Click OK

<img alt="select new rule" src="{{ site.url }}/assets/img/2020-05-20/01-new-rule.gif" />

### Add the Portal Pages
1. Click "Add Condition"
1. Search for "page"
1. Select: "Portal page (Portal.page)"
2. Click Select
3. Select the desired Pages: Asset Detail Page, Mass edit, Order, Reports
4. Click Select

<img alt="select new rule" src="{{ site.url }}/assets/img/2020-05-20/02-add-portal-page.gif" />

### Add the Rights & Save
1. Select the desired Permissions: Read
1. Click Save

<img alt="select new rule" src="{{ site.url }}/assets/img/2020-05-20/03-add-permission.gif" />
