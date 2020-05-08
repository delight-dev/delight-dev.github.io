---
title: On-Demand Loading
parent: Tutorials
has_children: false
nav_order: 8
---
# On-Demand Loading

1. TOC
{:toc}

## Introduction

On-demand loading is a way to optimize memory usage and the initial load time of your scenes by only loading certain views and their assets when they are displayed. On-demand loading in Delight is simple and transparent, we'll go over a few ways it can be done in this tutorial. 



## LoadMode="Manual"

By setting LoadMode="Manual" on a view in XML you tell the framework that the view isn't to be loaded until explicitly requested. The following example shows how a view is loaded/unloaded when the user clicks on a button:

{: .xml-file }

MyView.xml

```xml
<MyView>
  <Button Text="Load/Unload" Click="ToggleBigView" />
  <MyBigView Id="BigView" LoadMode="Manual" />
</MyView>
```

{: .cs-file }

MyView.cs

```cs
namespace Delight
{
    public partial class MyView
    {
        public async void ToggleBigView()
        {
            if (!BigView.IsLoaded)
            {
                await BigView.LoadAsync();
            }
            else
            {
                BigView.Unload();
            }
        }
    }
}
```

We check `IsLoaded`, which is a boolean indicating if the view has been loaded, to either load the view by calling `LoadAsync()` (if you want to do it synchronously you can call  `Load()` instead), or unload the view by calling `Unload().`



## View Switcher

If you have multiple views you want to switch between and load on-demand you can make use of the [ViewSwitcher](../Api/Views/ViewSwitcher) view and set  `SwitchMode="Load"`: 

{: .xml-file }

MyView.xml

```xml
<MyView>
  <ViewSwitcher Id="ViewSwitcher" SwitchMode="Load">
    <Region Id="BigRegion1">
        <!-- lots of content -->
    </Region>
    <Region Id="BigRegion2">
        <!-- lots of content -->
    </Region>
  </ViewSwitcher>
</MyView>
```

{: .cs-file }

MyView.cs

```cs
namespace Delight
{
    public partial class MyView
    {
        public void SomeMethod()
        {            
            ViewSwitcher.SwitchTo(BigRegion1);
        }
        
        public void SomeOtherMethod()
        {
            ViewSwitcher.SwitchTo(BigRegion2);
        }
    }
}
```

See the [Creating a Main Menu](MainMenu) tutorial for a practical example of how to use the `ViewSwitcher`



## Asset Bundles

Delight greatly simplifies the use of asset bundles by making the process of loading and unloading them transparent. All assets (Sprites, Fonts, Materials, etc) that are referenced by views will automatically be loaded from their asset bundles on-demand. To create an asset bundle you simply need to make sure the assets reside in an a certain folder. See the [Asset Management](AssetManagement#asset-bundles) tutorial for more details.

