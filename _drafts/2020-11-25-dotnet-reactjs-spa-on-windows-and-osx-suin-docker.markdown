---
layout: post
title:  "Dotnet React.js SPA running on Windows and OSX using Docker"
categories: dotnet react.js SPA ENV
author: Mark Wiseman
comments: true
---
Over the last few months I have been working on a single page application using react.js and a dotnet core API that was based of the `dotnet new react` template. We faced a few challenges: How do we get ou front end developer access to a persistant database and how do we share application settings between the API and the SPA. Also how do we support the different development styles: npm run, dotnet run, F5 from Visual Studio. 

The demo has been simplified a fair bit but demonstrates the main principles we implemented.

What we are going to do is:
- Create a new dotnet react app
- Add Docker support
- Add EF core for database access
- Add Controller to retrieve data from the database
- Support for all the developers

If you just want to see the code you can get it here: XXXX

## Create a new dotnet react app

```
cd c:\temp\demo
dotnet new react
dotnet run
```

Easy. We can noew view the application by navigating to http://localhost:5001

## Add Docker support

We are adding docker support first so our database will exist for OSX users




## Add EF core for database access

We are just going to do something super simple here

```
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
```