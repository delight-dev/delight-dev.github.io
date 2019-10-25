---
title: Creating a Main Menu
parent: Tutorials
has_children: false
nav_order: 1
---
# Creating a Main Menu

1. TOC
{:toc}

## Introduction

This tutorial serves as a practical introduction to the framework by showing you how to create a main menu. Be sure to also check out the [Quick Start](../index.html#quick-start)  guide on how to get started and the [Feature Overview](FeatureOverview) to get a conceptual overview of the framework. 



## Creating the MainMenu scene

We'll start by creating a Main Menu scene. Right-click in your project hierarchy and choose `Create -> Delight Scene`. Give it the name `MainMenuScene` and press enter.

Open the scene `MainMenuScene.xml` and add a `MainMenu` view to it:

{: .xml-file }

MainMenuScene.xml

```xml
<MainMenuScene xmlns="Delight" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="Delight ../Delight.xsd">
    <MainMenu />    
</MainMenuScene>
```

You've now created a scene that is set up to display a single view, the `MainMenu`. The framework sees that the view `MainMenu` doesn't exist and will automatically generate it for you. You now should have the following files in your project:

![](main-menu-files.png)

{: .info-box }
Note you can also manually create new views by choosing `Create -> Delight View`

You can now open `MainMenuScene.unity` which you can run throughout the tutorial to see the main menu taking shape.

{: .info-box }
All content files, like the XML files MainMenuScene.xml and MainMenu.xml are automatically processed by the framework as they are changed (if the editor is open). To manually tell the framework to process all content, press the "Reload All" button in the Delight window (Window -> Delight). Also note that files with the "_g" postfix are generated (and overwritten) when the XML files are processed.



## Creating the Main Menu view

Open the `MainMenu` view and edit it so it contains the following:

{: .xml-file }

MainMenu.xml

   ```xml
<MainMenu xmlns="Delight" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
          xsi:schemaLocation="Delight ../Delight.xsd">
  <Group Spacing="10">
    <Button Text="Play" />
    <Button Text="Options" />
    <Button Text="Quit" />
  </Group>
</MainMenu>
   ```

The name of the root tag `<MainMenu>` is the name we've given the view. The view contains three [Button](../Api/Views/Button) views that are arranged vertically by a [Group](../Api/Views/Group) view. The [API](../Api/Views/Views) contains detailed information about all the 40+ views included in the framework.

`Spacing="10"` and `Text="Play"` are [dependency properties](FeatureOverview#dependency-properties) that changes the layout and behavior of the  view. E.g. `Spacing="10"` tells the `Group` view to insert a spacing of 10 pixels between the buttons.

Different views have different properties but most views are based on the `UIView` which has the following properties that are used to do layout:

| Dependency Property | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| Width               | Width of the view that can be specified in pixels "10" or percentage "100%". Some views are 100% by default (which means they take up the extent of their parent). The Group adjusts its size to its children by default. |
| Height              | Height of the view.                                          |
| Alignment           | Alignment of the view: TopLeft, Top, TopRight, Left, Center, Right, BottomLeft, Bottom, BottomRight. |
| Margin              | Specifies the view's margin from left, top, right and bottom. Defaults to "0,0,0,0". |
| Offset              | Specifies the view's offset from left, top, right, bottom. Defaults to "0,0,0,0". |
| BackgroundColor     | Background color of the view. Color values can be specified by name (Red, Blue, Coral, etc), hexcode (#aarrggbb or #rrggbb) or rgb/rgba value ("1.0,0.0,0.5" or "1,1,1,0.5"). Undefined by default. |
| BackgroundSprite    | The background sprite of the view. The value is the name of the sprite asset file without extension, e.g. "mysprite". |

You can also add your own custom dependency properties to your view which we'll go over later in this tutorial.



## Responding to button clicks

Open the `MainMenu` view and add the following click-handlers to the XML:

{: .xml-file }

MainMenu.xml

```xml
<MainMenu xmlns="Delight" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
          xsi:schemaLocation="Delight ../Delight.xsd">
  <Group Spacing="10">
    <Button Text="Play" Click="Play" />
    <Button Text="Options" Click="ShowOptions" />
    <Button Text="Quit" Click="Quit" />
  </Group>
</MainMenu>

```

{: .info-box }
`Click` is one of the standard view actions that can be set on all views (others include `Drag`, `MouseEnter`, `MouseUp`, `Scroll`, etc.).

This will generate the click handlers in the code-behind. Modify the handlers so they log messages:

{: .cs-file }

MainMenu.cs

```c#
namespace Delight
{
    public partial class MainMenu
    {
        public void Play()
        {
            Debug.Log("Play clicked");
        }

        public void ShowOptions()
        {
            Debug.Log("Options clicked");
        }

        public void Quit()
        {
            Debug.Log("Quit clicked");
        }
    }
}
```

If you run the scene and click on the buttons you'll see the text being logged in the console:

![](main-menu-clicklog.png)



## Doing Layout

This is the layout we are going for:

![](main-menu-layout.png)

The framework includes various views that can be used to do layout. We've seen the [Group](../Api/Views/Group) view that is used to group views vertically or horizontally with spacing between. A more basic layout view is the [Region](../Api/Views/Region) which is similar to the `<div>` element in HTML, simply used to create a region of space with a certain offset, width and height that child views can be placed inside. To get the above layout we add some regions to our main menu: 

{: .xml-file }

MainMenu.xml

```xml
<MainMenu xmlns="Delight" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
          xsi:schemaLocation="Delight ../Delight.xsd">
  <Region Width="25%" Alignment="Left" Margin="30,30,15,30" 
          BackgroundColor="#ef706a">
    <Group Spacing="10px" Alignment="Top">
      <Button Text="Play" Click="Play" Width="140" />
      <Button Text="Options" Click="ShowOptions" Width="140" />
      <Button Text="Quit" Click="Quit" Width="140" />
    </Group>
  </Region>
  <Region Width="75%" Alignment="Right" Margin="15,30,30,30" 
          BackgroundColor="#949494">
    <!-- content area --> 
  </Region>
</MainMenu>

```

We've added background color to the regions just to make it easy to see them. We'll remove the background colors as we move on. 



## Showing submenus

We want to show a LevelSelect view when the user clicks on the Play button and a Options view when the Options button is clicked. To do this we can add a [ViewSwitcher](../Api/Views/ViewSwitcher) view and add the submenu views as children:

{: .xml-file }

MainMenu.xml

```xml
<MainMenu xmlns="Delight" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
          xsi:schemaLocation="Delight ../Delight.xsd">
  <Region Width="25%" Alignment="Left" Margin="30,30,15,30" 
          BackgroundColor="#ef706a">
    <Group Spacing="10px" Alignment="Top">
      <Button Text="Play" Click="Play" Width="140" />
      <Button Text="Options" Click="ShowOptions" Width="140" />
      <Button Text="Quit" Click="Quit" Width="140" />
    </Group>
  </Region>
  <Region Width="75%" Alignment="Right" Margin="15,30,30,30" 
          BackgroundColor="#949494">
    <ViewSwitcher Id="SubmenuSwitcher" ShowFirstByDefault="False">
      <LevelSelect Id="LevelSelect" />
      <Options Id="Options" />
    </ViewSwitcher>
  </Region>
</MainMenu>

```


We've given the views names through the Id attribute, so we can easily reference them in code-behind. The LevelSelect and Option views are automatically generated and to switch between them we add the following to our code-behind:

{: .cs-file }

MainMenu.cs

```c#
namespace Delight
{
    public partial class MainMenu
    {
        public void Play()
        {
            SubmenuSwitcher.SwitchTo(LevelSelect);
        }

        public void ShowOptions()
        {
            SubmenuSwitcher.SwitchTo(Options);
        }

        public void Quit()
        {
            Debug.Log("Quit clicked");
        }
    }
}
```








