---
title: Using TextMeshPro
parent: Tutorials
has_children: false
nav_order: 11
---

# Using TextMeshPro

1. TOC
{:toc}

## Enabling TextMeshPro Module

To start using TextMeshPro in Delight follow these steps:

1. Import the latest TextMeshPro package into your project. You can do this through the package manager.

2. Import the Essential TextMeshPro Resources, through `Window -> TextMeshPro -> Import TMP Essential Resources`

2. Open Content/Config.txt and add the TextMeshPro module:

   {: .xml-file }

   Config.txt

   ```yaml
   Modules: 
     TextMeshPro 
   ```

   This makes it so all Label and InputField views uses TextMeshPro components and enables additional TextMeshPro specific properties to be set. Any fonts and materials you use need to be converted to TextMeshPro font assets using the Font Asset Creator utility accessed at `Window -> TextMeshPro -> Font Asset Creator`



## Upgrading TextMeshPro

If you already have the TextMeshPro module enabled and want to upgrade TextMeshPro, follow these steps:

1. Open Content/Config.txt and remove the TextMeshPro module. 
2. Make sure the views are rebuilt and make sure the code compiles - you might need to temporarily comment any custom code-behind that accesses TextMeshPro properties.
3. Upgrade the TextMeshPro package.
4. Add the TextMeshPro module back to Config.txt
5. Uncomment any code you had to comment.

Disabling, upgrading and then enabling the TextMeshPro module again ensures that the framework can scan the new TextMeshPro components and add the necessary dependency properties for them. 