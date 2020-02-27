---
layout: post
title:  "Developer Machine Setup"
categories: windows chocolatey powershell software
author: Mark Wiseman
comments: true
---
There are periods of your life as a developer either at home of at work where you go through a cycle of re-build your machine (and other) a seemingly high number of times and the real grind is getting your tools setup and installed each time.

The Windows 10 Development environment is a good place to start if you need a VM running Visual Studio but what about all of your other sweet dev tools?

The applications listed below are what I use everyday as a Sitecore developer you will want to update your to suite your situation.

Here is the process.

## Install PowerShell Modules & Windows Components

1. Download **powershell-iis-and-default-modules.ps1** file to **c:\temp** [https://gist.github.com/mawiseman/cab07877576d5122ab3d7690266110b5](https://gist.github.com/mawiseman/cab07877576d5122ab3d7690266110b5){:target="_blank"}
1. Open **Powershell** as an **Administrator** and run the following script

{% highlight powershell %}
cd c:\temp
.\powershell-iis-and-default-modules.ps1
{% endhighlight %}

## Install Applications via Chocolatey

1. Install Chocolatey: [https://chocolatey.org/install](https://chocolatey.org/install){:target="_blank"}
1. Download **chocolatey-packages.config** file to **c:\temp** [https://gist.github.com/mawiseman/54fef1543f6ac8c06a16a49a15d80b36](https://gist.github.com/mawiseman/54fef1543f6ac8c06a16a49a15d80b36){:target="_blank"} 
1. Open **Powershell** as an **Administrator** and isntall the applications via Chocolatey

{% highlight powershell %}
cd c:\temp
choco install chocolatey-packages.config -y
{% endhighlight %}

## Install SQL Server 2016

1. Download SQL Server from [https://my.visualstudio.com](https://my.visualstudio.com){:target="_blank"}
1. Mount the ISO
1. Download **SQLServer2016ConfigurationFile.ini** file to **c:\temp** [https://gist.github.com/mawiseman/e6e4143ddafa55cd9d67253af31e9937](https://gist.github.com/mawiseman/e6e4143ddafa55cd9d67253af31e9937){:target="_blank"}
1. Open **Powershell** as an **Administrator** and run the following script
1. Download and Install [SQL Server Management Studio](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms){:target="_blank"}

{% highlight powershell %}
$saPassword = "YOUR-UNIQUE-PASSWORD"

.\setup.exe /CONFIGURATIONFILE=C:\temp\SQLServer2016ConfigurationFile.ini /SQLSYSADMINACCOUNTS=$([System.Security.Principal.WindowsIdentity]::GetCurrent().Name) /SAPWD=$saPassword
{% endhighlight %}

## Install Node Modules
1. Open **Powershell** run the following script

{% highlight powershell %}
npm install -g windows-build-tools
npm install -g gulp
npm install -g gulp-cli
npm install -g bower
{% endhighlight %}