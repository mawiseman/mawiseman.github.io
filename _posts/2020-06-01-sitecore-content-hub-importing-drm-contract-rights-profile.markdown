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

When they didn't work I clicked around aimlessly until the lightbulb finally went off... 

> 
> I wonder if an **Excel Export** of Assets linked the the DRM Contracts will work?
> 

Sure enough the export had the data I needed and the value we use is the identifier.

If you're not sure how to set up and excel export or what the look for then read on!

## 1. Creaet Assets to export
So as not to muddy the water with the assets already in the system I created a new image with the name of each Rights Profile I wanted to Export

## 2. Create an DRM Contract & Assigning it to an Asset
1. Navigate to **DRM** > **DRM Contracts**
2. Click **New Contract**
3. On the **Rights Profiles** tab Click **Create New**
4. Set the values you reqiure and click **Save**
5. Click the **Info Icon** for you new profile 
6. Select the **Assets** Tab
7. Click **Link Assets**
8. Select the Assets you would like to associate with this for export

## 3. Enabling Excel Export
1. Navigate to **Manage**
2. Select **Pages**
3. Select the **Content** Page
4. Click the **selection** component
5. On the **General Settings** tab ensure that **Enable export to Excel** is turned on

## 4. Add the Right Profile to the Excel Export
1. Navigate to **Manage**
2. Select **Export Profile**
3. Edit **AssetProfile** (you can create new ones if you like)
4. Under the **relations** section add **DRM.RightsProfile.RightsProfileToAsset**

<img alt="add property to content hub excel export" width="250px" src="{{ site.url }}/assets/img/2020-06-01/add-property-to-content-hub-excel-export.png" />

## 5. Export to Excel and get values
You now should be all set to get the values required to configure your import.

1. Navigate to **Content**
2. Select the **Assets** we associated the the **Rights Profiles** in **Step 2**
3. Click the **Ellipsis (...)** and select **Expor to Excel** 

<img alt="excel export result" src="{{ site.url }}/assets/img/2020-06-01/excel-export.png" />

## 6. Importing via Excel
To use the Right Profile as a part of your import, just make sure you use the same column and values that you coped from your sample export.

- Column Name: **DRM.RightsProfile.RightsProfileToAsset**
