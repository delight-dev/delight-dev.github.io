---
title: "Home"
permalink: /index.html
nav_order: 1
---

# Component-oriented UI framework for Unity

{: .fs-6 .fw-300} 

Delight is an open source component-oriented framework for Unity, mainly centered around creating user-interface components that can easily be extended, combined and shared using a text based declarative design language (similar to HTML). 

[View it on Asset Store](https://assetstore.unity.com/packages/slug/150494){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [View it on GitHub](//github.com/delight-dev/Delight){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } &nbsp;[![Discord Chat](https://img.shields.io/discord/764484415681593355?color=%23d867ff&label=Discord%20Chat&style=for-the-badge)](https://discord.gg/9BVyVsB)


## Quick Start

1. Import the latest [Delight unity package](https://assetstore.unity.com/packages/slug/150494) into your Unity project. 



2. Create a new scene by right-clicking in your project hierarchy and choosing: 

   `Create -> Delight Scene`. 

   Press enter and open the newly created `NewScene.xml`  XML file and edit it so it contains the following content:

   {: .xml-file }

   NewScene.xml

   ```xml
   <NewScene xmlns="Delight" 
             xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
             xsi:schemaLocation="Delight ../Delight.xsd">
     
       <Label Text="Awesome!" />
   
   </NewScene>
   ```



3. Open the Unity scene `NewScene.unity` that has been created in the same folder and run the scene.

Congratulations, you've created your first scene in Delight :). 

![](Tutorials/awesome.png)

Check out the [Tutorials](Tutorials/Tutorials) and get started creating some awesome UI components.



## News

{% include recent-posts.html %}
