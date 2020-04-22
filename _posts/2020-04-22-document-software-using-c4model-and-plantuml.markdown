---
layout: post
title:  "Documenting Software Architecture Using c4model and PlantUML"
categories: documentation c4model plantuml
author: Mark Wiseman
comments: true
---

As someone who has aways loved process improvement and finding patterns that are easily replicated and understood, I am constantly on the lookout for ways to do what we do better. On a recent project I was documenting the Software Architecture... again, and I so I opend Visio... again and that same dread of "How the hell am I going to document this so it makes sense" hit me. 

I decided to do a search and find out what is happening out there these days when I cam across the [c4model](https://c4model.com/) which can be easily authored using one of my favourite documentation tools [PlantUml](https://plantuml.com/) and I couldn't help but jump in.

Very briefley the c4model provides 4 (as is c4) levels of abstraction for documenting a project each. The top layer provides a limited set of components to keep the document simple. As we step down into each layer a few more components are added so that we can descripe each piece in more details.

<img alt="c4model overview" src="{{ site.url }}/assets/img/2020-04-22/c4model-overview.png" width="500px" />


The components are far simpler than tring to remember all the permutations of UML yet detaild enough to provide a consistent language for describing your application

Make sure you watch this video by Simon Brown the creator of the model because its a great introduction.

<iframe width="560" height="315"
    src="https://www.youtube.com/watch?v=x2-rSnhpw0g " 
    frameborder="0" 
    allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen></iframe>

## Testing it out online

You can esily test this process out online simply by using the free PlantUml Editor.

- Navigate to: https://www.planttext.com/
- Paste in this example Container diagram
- Play around!

```
@startuml C4_Elements
!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/release/1-0/C4_Container.puml

Person(personAlias, "Label", "Optional Description")
Container(containerAlias, "Label", "Technology", "Optional Description")
System(systemAlias, "Label", "Optional Description")

Rel(personAlias, containerAlias, "Label", "Optional Technology")
@enduml
```

## Setting it up locally

This process allows us to author the diagram directly from Visual Studio Code.

### Chocolatey

There are a few applications we need setup for this process.

```
choco install plantuml
choco install graphviz
```

### VS Code

Install PlantUML
```
ext install plantuml
```

Configure PlantUML
- Navigate to: **Extensions**
- Select: **PlantUML** > **Etension Settings**
- Update: 
  - Setting: **PlantUML: JAR**
  - Value: **C:\ProgramData\chocolatey\lib\plantuml\tools\plantuml.jar**

## Formatting PlantUML

I like to save my documents using the *.puml extension

<img alt="PlantUML c4model diagram generation" src="{{ site.url }}/assets/img/2020-04-22/PlantUML-c4model-generation.gif" width="500px" />

## References
- c4model: https://c4model.com/
- c4model PlantUML Extension: https://github.com/RicardoNiepel/C4-PlantUML
- VS Code Plant UML Extension: https://github.com/qjebbs/vscode-plantuml.git