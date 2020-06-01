---
layout: post
title:  "Sitecore Content Hub Importing DRM Contracts Rights Profiles"
categories: sitecore contenthub
author: Mark Wiseman
comments: true
---

When importing data into Sitecore's Content Hub, finding the required fields and values generally makes sense. Howerver when trying to import the Rights Profiles for DRM Contracts though, the mapping isn't as simple as you would expect. 

In this article I'd like to show you the steps I followed to get the import to work.

First I tried following the Taxonomy pattern:
  - Field name: AssetToAssetType
  - Value name: M.AssetType.**Backdrop**

Then I tried using the Id:
  - URL: https://xxx.stylelabsdemo.com/en-us/drm/contract/**11000**
  - Value: **11000**

The right place to look is the **Entity Manager** to find the **Identifier**

1. Click on **Manage**
2. Click on **Entities**
3. Select **M.DRM.RightsProfile**
4. Click **View detail** for the right's profile you'd like to use
5. Select the **Technical** Section
6. Copy the **Identifier**

<img alt="Rights Profile Identifier" src="{{ site.url }}/assets/img/2020-06-01/rights-profile-identifier.png" />


