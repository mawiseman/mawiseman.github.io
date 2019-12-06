---
layout: post
title:  "Sitecore Solr Setup Script"
categories: sitecore solr powershell
author: Mark Wiseman
comments: true
---

Running multiple versions of Solr when managing different versions of Sitecore can be a pain.

To make life easier I put this script together that will allow you to install the correct version of Solr using SSL that matches your version of Sitecore.

See the Git repo for full instructions details: [https://github.com/mawiseman/sitecore-setup-solr](https://github.com/mawiseman/sitecore-setup-solr)

{% highlight powershell %}
PS C:\projects\sitecore-solr-setup\src> .\install.ps1
{% endhighlight %}

![Solr Install Menu]({{ site.url }}/assets/img/2019-12-06-sitecore-solr-setup-script/solr-install-menu.gif)
