---
title: Enabling TextMeshPro
parent: Tutorials
has_children: false
nav_order: 4
---
# Enabling TextMeshPro

1. Download and import the latest TextMeshPro package into your project. 

2. Open Content/Config.txt and add the TextMeshPro module:

   {: .xml-file }

   Config.txt

   ```yaml
   Modules: 
     TextMeshPro 
   ```

   This makes it so all Label and InputField views uses TextMeshPro components and enables additional TextMeshPro specific properties to be set. Any fonts and materials you use need to be converted to TextMeshPro font assets using the Font Asset Creator utility accessed at `Window -> TextMeshPro -> Font Asset Creator`

