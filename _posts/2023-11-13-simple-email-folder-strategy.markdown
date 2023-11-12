---
layout: post
title:  "Simple Email Folder Strategy"
categories: email
author: Mark Wiseman
comments: true
---

Managing emails can be tough and I have been through a number of different patterns & practices over the years trying to wrangle the breast. Most of these strategies require manaully action / move emails to be organised and ulitmatley it gets out of control.

I've now landed on a four folder system that allows me to quickly action email that I need to and remove "most" of the noise.

Here are the folders you need:
  - Inbox
  - Invite
  - CC
  - Feed

To enable automatically sorting of emails we only need 3-ish simple Rules and it's important that we keep them in this order so that they land in the right place.

1. Feed Rule(s)
2. Invite Rule
3. CC Rule

## 1. Feed Rule(s)

This rule will evolve over time. For me it is a "Sender Based Rule". 

> If the `sender address includes` the following `@sharepointonline.com`, `@atlassian.com` then `Move to` the `Feed` folder

This can end up being multiples rules if you want to target specific subject lines or body text
- Feed - Sender Address Includes
- Feed - Body Includes
- Feed - Subject Includes

## 2. Invite Rule

This is really easy and helps with managing your schedule a lot.

> If the `Type` is `Invitation` then `Move to` the `Invite` folder

## 3. CC Rule

CC emails can get realy noisy when you work for a large company. This is antoher great one for clearing out the noise

> If `I'm not in the To line` then `Move to` the `CC` folder