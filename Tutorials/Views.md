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



## Anotomy of a View


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

    public readonly static DependencyProperty<string> MyStringProperty = 
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

This code-behind can be  customized to add methods and internal logic to the view. This file won't be overwritten when the XML changes.   



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

The most common way to add custom load/initialization logic is to override the `AfterLoad()` method. This method is called after the view and its children has been loaded. A view can be loaded/unloading

The following methods can be overridden to do custom logic during the load/initialization of the view. They are shown in the order they are called:

| Method                | Description                                                  |
| --------------------- | ------------------------------------------------------------ |
| BeforeInitialize()    | Called once in the object's lifetime before construction of children and before load. |
| AfterInitialize()     | Called once in the object's lifetime after construction of children and before load. |
| BeforeLoad()          | Called just before the view and its children are loaded.     |
| AfterChildrenLoaded() | Called just after the children are loaded, but before dependency properties are loaded. |
| AfterLoad()           | Called after the view and its children has been loaded.      |



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



Unity Components

Mapped Dependency Properties

Attached Properties

On-demand loading



## Runtime Instantiation of a View

```csharp
var myView = new MyView();
myView.Load(); // load the view synchronously
// await myView.LoadAsync(); // can be called instead to load the view asynchronously
```

The above code manually instantiates a view during run-time. You can also attach a `ViewPresenter` unity component to a game object in your scene, to automatically create and load a specified view upon scene start. 

