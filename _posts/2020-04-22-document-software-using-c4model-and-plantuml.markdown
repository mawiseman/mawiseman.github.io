---
layout: post
title:  "Documenting Software Architecture using the c4model and PlantUML"
categories: documentation c4model plantuml
author: Mark Wiseman
comments: true
---

As someone who has aways loved process improvement and finding the patterns is what we do, I am constantly on the lookout for ways to do things better. On a recent project I was documenting the Software Architecture... again, and I so I opend Visio... again and that same dread of "How the hell am I going to document this so it makes sense" hit me. 

I decided to do a search and find out what other people are doing now when I came across the [c4model](https://c4model.com/) which can be easily authored using one of my favourite documentation tools [PlantUml](https://plantuml.com/). I couldn't help but jump in.

Very briefly the c4model provides 4 (as in c4) levels of abstraction for documenting a project. 

The top layer provides a limited set of components to keep the document simple. As we step down into each layer a few more components are added, gradually adding more detail.

<img alt="c4model overview" src="{{ site.url }}/assets/img/2020-04-22/c4-overview.png" />

The components are far simpler to remember than all the permutations of UML yet detaild enough to provide a consistent language for describing your application.

Make sure you watch this video by Simon Brown (the creator of the model) because its a great introduction.

{% include youtubePlayer.html id="x2-rSnhpw0g" %}

## Combining c4 with PlantUML

The process to generate these documents with PlantUML is really simple thanks to the [C4-PlantUML](https://github.com/RicardoNiepel/C4-PlantUML) extension created by RicardoNiepel.

### 1. Include a reference to the required extension from at the top of our document.

```
' Context Diagram
!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/release/1-0/C4_Context.puml

' Container Diagram
!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/release/1-0/C4_Container.puml

' Component Diagram
!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/release/1-0/C4_Component.puml
```

### 2. Start adding the custom types included in the extension for your diagram.
```
Person(personAlias, "Label", "Optional Description")
Container(containerAlias, "Label", "Technology", "Optional Description")
System(systemAlias, "Label", "Optional Description")
```

### 3. Add the required relationships.
```
Rel(personAlias, containerAlias, "Label", "Optional Technology")
```

## Testing it out online

You can esily test this process out online simply by using the free PlantUml Editor.

- Navigate to: [https://www.planttext.com/](https://www.planttext.com/)
- Paste the example Container diagram below
- Hit **Refresh**

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

This process allows us to author the diagram directly from Visual Studio Code. I like it because everything is local, your business sensitive diagrams aren't going out to the interwebs.

### Chocolatey

There are a few applications we need setup for this process.

```
choco install plantuml
choco install graphviz
```

### VS Code

Install the PlantUML Extension
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

Here is an example of how simple it is to author and preview these documents in VS Code.

<img alt="PlantUML c4model diagram generation" src="{{ site.url }}/assets/img/2020-04-22/PlantUML-c4model-generation.gif" width="500px" />

## References
- c4model: [https://c4model.com/](https://c4model.com/)
- c4model PlantUML Extension: [https://github.com/RicardoNiepel/C4-PlantUML](https://github.com/RicardoNiepel/C4-PlantUML)
- VS Code Plant UML Extension: [https://github.com/qjebbs/vscode-plantuml.git](https://github.com/qjebbs/vscode-plantuml.git)
- PlantUML [https://plantuml.com/](https://plantuml.com/)