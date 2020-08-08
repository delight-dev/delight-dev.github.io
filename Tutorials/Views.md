---
title: Views
parent: Tutorials
has_children: false
nav_order: 4
---
# Views

1. TOC
{:toc}

## Introduction

This tutorial goes a bit more in-depth what views are. After going through this tutorial you'll know the basic inner workings of a view and be able to create custom views that can be re-used and built upon in your project.



## Anatomy of a View


We'll start by creating a simple view and break down its parts to see how it ticks. If you don't know how to create a view and display it in a scene, check out the initial steps in [Creating a Main Menu](MainMenu) tutorial.

{: .xml-file }

MyView.xml

```xml
<MyView MyString="t:string">
  <Button Id="MyButton" Text="Hello" />
</MyView>
```

The view has one dependency property declared called `MyString` which is of the type `string`  and  it has one child view that is a `Button` with its Id and Text property values defined. The framework parses this XML file and generates the code-behind. The below excerpt highlights the main parts of the generated code-behind:

{: .cs-file }

MyView_g.cs

```csharp
public partial class MyView : UIView
{ 
    public MyView(...)
    {
        // constructing Button (MyButton)
        MyButton = new Button(this, this, "MyButton", MyButtonTemplate);
    }

    public static DependencyProperty<string> MyStringProperty = 
        new DependencyProperty<string>("MyString");
    public string MyString
    {
        get { return MyStringProperty.GetValue(this); }
        set { MyStringProperty.SetValue(this, value); }    
    }
    
    public Button MyButton { get; }
    
    // etc ...
}

public static class MyViewTemplates 
{ 
    // etc ...
}    
```

Note that the auto-generated code-behind will be overwritten every time the XML changes or when *Rebuild All* is pressed in the Delight window. It contains the following important parts:

1. The generated class `MyView` that is inherits from `UIView` by default, which allows the view to be presented and arranged in the UI hierarchy. This class is used to instantiate the view and access its properties during runtime. 
2. It has a constructor that initializes the view, constructs the child views - `MyButton` in this case. And this is where bindings are created as well.
3. The class contains the `MyString` dependency property we declared in the XML. 
4. The class contains a reference to the child view `MyButton`. If we hadn't specified the Id of the button it would've gotten a generic name like `Button1`.
5. finally we have the data templates that that defines the default values of our dependency properties. In this case the value `Text="Hello"`. Note that those values are defined per type and not instance, which is one advantage of the dependency properties as it saves a lot of memory. 

The framework also generates a blank code-behind for the view:

{: .cs-file }

MyView.cs

```csharp
public partial class MyView
{
}
```

This code-behind can be  customized to add methods and internal logic to the view. This file won't be overwritten when the XML changes. Also note that it's a partial class so you have access to the content generated in *MyView_g.cs*.



## Deriving Views

To create a view that derives from another view use the `BasedOn` attribute:

{: .xml-file }

MyView.xml

```xml
<MyView BasedOn="LayoutRoot" MyString="t:string" PixelPerfect="True">
  <Button Id="MyButton" Text="Hello" />
</MyView>
```

{: .cs-file }

MyView_g.cs

```csharp
public partial class MyView : LayoutRoot
{ 
    ...
}
```

In this example `MyView` now inherits all the logic and content from the [LayoutRoot](../Api/Views/LayoutRoot) view, that is derived from by views that are at the root of the UI hierarchy, giving access to properties on the main UI canvas such as *PixelPerfect*, *RenderMode*, etc. Another common view to inherit from is [UIImageView](../Api/Views/UIImageView) that allows us to set things like *BackgroundColor* and *BackgroundSprite* on our view. Lastly you might want to consider basing your view on another if you want to extend and build upon their functionality.



## Dependency Properties

Dependency properties are declared in the view XML root element using the following syntax: 

`PropertyName="t:PropertyType"`

or

`PropertyName="t:PropertyType = DefaultValue"`

{: .xml-file }

MyView.xml

```xml
<MyView MyString="t:string = Default Text">
</MyView>
```

The dependency property can then be accessed through view XML:

{: .xml-file }

AnotherView.xml

```xml
<AnotherView>
  <MyView MyString="Test" />
</AnotherView>
```

You can also access it through code: 

{: .cs-file }

MyView.cs

```csharp
public partial class MyView
{
    public void SomeMethod()
    {
        MyString = "Test";
    }
}
```

### Generic Dependency Properties

Dependency properties with generic types can be declared using the following syntax:

```xml
<MyView MyPlayerCollection="t:BindableCollection[Player]">
</MyView>
```

Which creates a dependency property with the generic type `BindableCollection<Player>` in code. 



## Custom Initialization and Load Logic

{: .cs-file }

MyView.cs

```csharp
public partial class MyView
{
    protected override void AfterLoad()
    {
        base.AfterLoad(); // execute load logic in base class
        
        // your custom load logic goes here
    }
}
```

The most common way to add custom load/initialization logic is to override the `AfterLoad()` method. This method is called after the view and its children has been loaded. The following methods can be overridden to do custom logic during the load/initialization of the view. They are shown in the order they are called:

| Method                | Description                                                  |
| --------------------- | ------------------------------------------------------------ |
| BeforeInitialize()    | Called once in the object's lifetime before construction of children and before load. |
| AfterInitialize()     | Called once in the object's lifetime after construction of children and before load. |
| BeforeLoad()          | Called just before the view and its children are loaded.     |
| AfterChildrenLoaded() | Called just after the children are loaded, but before dependency properties are loaded. |
| AfterLoad()           | Called after the view and its children has been loaded.      |
| BeforeUnload()        | Called just before the view and its children are unloaded.   |
| AfterUnload()         | Called after the view and its children has been unloaded.    |



## Update(), Awake(), Start(), etc.

To respond to unity script events such as `Update()`, `Awake()`,`Start()`, etc. add `EnableScriptEvents="True"` to the view XML:

{: .xml-file }

MyView.xml

```xml
<MyView MyString="t:string" EnableScriptEvents="True">
  <Button Id="MyButton" Text="Hello" />
</MyView>
```

And override the corresponding method in your code-behind:

{: .cs-file }

MyView.cs

```csharp
public partial class MyView
{
    protected override void Update()
    {
        base.Update();
        
        // called once per frame if EnableScriptEvents is true
    }
}
```



## Responding to Property Changes

In custom views you might want to perform some action whenever a property changes value. To do this you can override the `OnChanged()` method that is called when a property is changed: 

```csharp
public override void OnChanged(string property)
{
    base.OnChanged(property);
    switch (property)
    {
        case nameof(MyString):
            // code executed whenever MyString value changes
            break;
    }
}
```


## Action Handlers

If you want to respond to actions you can attach action handlers to your views. 

{: .xml-file }

MyView.xml

```xml
<Button Id="MyButton" Text="Hello" Click="MyButtonClick" />
```

{: .cs-file }

MyView.cs

```csharp
public void MyButtonClick()
{
    // do something when button is clicked
}
```

You can also add parameters that are passed along by the action, different actions passes along different parameters. However, you can always add the source view that invokes the action as a parameter. The below example shows three different ways to implement the `MyButtonClick()`action handler:

```csharp
public void MyButtonClick(Button button)
{
    Debug.Log(button.Name + " Clicked!");
}

public void MyButtonClick(PointerEventData pointerData)
{
    // Click, Drag, MouseDown, etc. may pass along PointerEventData
}

public void MyButtonClick(Button button, PointerEventData pointerData)
{
    // receive both source and event data
}
```



### Passing Arguments to Action Handlers in XML

In some cases you might want to pass parameters to your action handlers through XML. The example below shows a common scenario when having click handlers inside a dynamic list item and wanting to pass along the list item to the action handler:

```xml
<List Items="{fruit in @Fruits}" BackgroundColor="White">
  <ListItem Width="150">
    <Button Text="Click Me" Click="MyClickHandler(fruit)" />
  </ListItem>
</List>
```

And you can add the parameter in code:

```csharp
public void MyClickHandler(Fruit fruit)
{
    // do something with the fruit
}
```



## Custom View Actions

Standard view actions exists for the unity event system events such as `Click`, `Drag`, `Scroll`, `MouseDown` etc. But sometimes you want to define your own actions, and you do this by declaring it in the XML: 

{: .xml-file }

MyView.xml

```xml
<MyView MyString="t:string" MyAction="t:Action">
  <Button Id="MyButton" Text="Hello" />
</MyView>
```

And you can invoke this action in your code-behind: 

{: .cs-file }

MyView.cs

```csharp
public partial class MyView
{
    private void SomeMethod()
    {
        MyAction.Invoke(this, "Action parameter");
    }
}
```

Someone using `MyView` can then attach action handlers to your custom action:

{: .xml-file }

AnotherView.xml

```xml
<AnotherView>
  <MyView MyAction="SomeActionHandler" />
</AnotherView>
```

{: .cs-file }

AnotherView.cs

```csharp
public partial class AnotherView
{
    private void SomeActionHandler(string actionArgs)
    {
        Debug.Log(actionArgs);
    }
}
```

The action argument passed is a string in this case but can be of any type. 



## Runtime Instantiation of a View

```csharp
var myView = new MyView();
myView.Load(); // load the view synchronously
// await myView.LoadAsync(); // load the view asynchronously
```

The above code manually instantiates a view during run-time. You can also attach a `ViewPresenter` unity component to a game object in your scene, to automatically create and load a specified view upon scene start. 



## Mapped Dependency Properties

Mapped dependency properties refers to properties that reside in either another view or on a custom type, most commonly unity components. This allows easy access to those properties. We declare mapped dependency properties using the `m.` prefix. 

### Mapping Unity Components

Mapping the [Shadow](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/script-Shadow.html) unity component to our view: 

```xml
<MyView MyShadow="t:UnityEngine.UI.Shadow" 
        m.MyShadow="">
</MyView>
```

1. First we declare the unity component as a dependency property `MyShadow="t:UnityEngine.UI.Shadow"`.
2. Then we generate the mapped dependency properties through `m.MyShadow=""`. We use the `m.` prefix followed by the name of the property that will be mapped. This declaration tells the framework to scan the MyShadow property type for public fields and generate mapped dependency properties for them.  The value we set (in this case an empty string) gets added as a prefix to the generated dependency properties. 

After doing this we can access the new properties:

`<MyView EffectColor="Red" EffectDistance="1,1" />`

Note that it's the view's responsibility to add the component on load. This should be done in `BeforeLoad()`: 

{: .cs-file }

MyView.cs

```csharp
public partial class MyView
{
    protected override void BeforeLoad()
    {
        base.BeforeLoad();
        if (MyShadow == null)
        {
            MyShadow = GameObject.AddComponent<UnityEngine.UI.Shadow>();
        }
    }
}
```



### Mapping Child View Properties

```xml
<MyView m.MyLabel="">
  <Label Id="MyLabel" />
</MyView>
```

The above example creates mapped dependency properties for all the properties on the `Label` view. This enables us to do things like: `<MyView Text="Hello" />` to set the `Text` property on the Label view.



### Renaming Generated Properties

The `rename.` prefix can be used to rename generated properties to e.g. give them names that are more descriptive. 

```xml
<MyView m.MyLabel="" rename.Text="Title">
  <Label Id="MyLabel" />
</MyView>
```

The above example  renames the `Text` property to be called `Title` instead.



## Attached Properties

Attached properties allows values to be associated with child views, e.g:

```xml
<GridExample>
  <Grid Id="MyGrid">
    <Label Id="MyLabel1" Grid.Cell="0,0" />
    <Label Id="MyLabel2" Grid.Cell="0,1" />
  </Grid>
</GridExample>
```

The [Grid](../Api/Views/Grid) view has an attached property called `Cell`. In the above example the grid gets the equivalent call in code: 

```csharp
MyGrid.Cell.SetValue(MyLabel1, new CellIndex(0, 0));
MyGrid.Cell.SetValue(MyLabel2, new CellIndex(0, 1));
```

The Grid view uses it to arrange the child labels into the specified cells. 

To declare a custom attached property we use the `at:` prefix in our property declaration:

{: .xml-file }

MyView.xml

```xml
<MyView AttachedString="at:string">
</MyView>
```

Now the attached property can be set in other views:

{: .xml-file }

AnotherView.xml

```xml
<AnotherView>    
  <MyView>
    <Button MyView.AttachedString="Test" />
  </MyView>
</AnotherView>
```

Attached properties are useful when you want child views of any type to be able to set values associated with it on some parent view. 



## Property Initializors

Property initializors are a construct that allows the user to specify multiple property values through one attribute. A common property initializor is `Size` declared using the `i.`prefix:

```xml
<UIView Width="t:ElementSize" Height="t:ElementSize" 
        i.Size="Width, Height">   
</UIView> 
```

This initializor allows us to set `Width` and `Height` property values through the `Size` attribute. So `<Region Size="100, 50" />` simply gets translated to: `<Region Width="100" Height="50" />` .



