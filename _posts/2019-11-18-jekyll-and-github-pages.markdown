---
layout: post
title:  "Generating pfx file using p7s and key"
categories: iis ssl
author: Mark Wiseman
---
It's the end of 2019 and I can't believe I am dealing with this again. 

I can't remember the last time I had to generate a pfx for installation in IIS but it has been frustrating enough for me to blog about so I remember for next time.

## Pre-requisites

OpenSSL. A quick way to install in on Windows is via chocolatey
{% highlight powershell %}
choco install OpenSSL.Light
{% endhighlight %}

Files form client
- my_domain.p7s
- my_domain.key

## Generate PKS

{% highlight powershell %}
# First generate a cer file
openssl pkcs7 -print_certs -in my_domain.p7s -out my_domain.cer

# Second generate a cer file
openssl pkcs12 -export -inkey my_domain.key -in my_domain.cer -out my_domain.pfx
{% endhighlight %}

You can now install the pfx on the windows server!