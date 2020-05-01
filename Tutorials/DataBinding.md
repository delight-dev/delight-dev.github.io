---
title: Data Binding
parent: Tutorials
has_children: false
nav_order: 3
---
# Data Binding

1. TOC
{:toc}

## Introduction

Data binding is a way to connect data to your views and to keep data synchronized.



## Declaring a Binding

Bindings are declared using `{}` syntax: 

{: .xml-file }

MyView.xml

```xml
<NewView MyBoolValue="t:bool = True">
     
  <CheckBox IsChecked="{MyBoolValue}" />
   
</NewView>
```

If the checkbox is toggled `IsChecked` will get a new value that will propagate to `MyBoolValue`. And if you change `MyBoolValue` in code the checkbox will be updated. 



## Binding Paths

You can bind to nested properties:

{: .xml-file }

MyView.xml

```xml
<MyView>
     
  <Group>
    <InputField Id="Input" />
    <Label Text="{Input.Text}" />   
  </Group>
   
</MyView>
```

Here we bind the nested `Input.Text` property to the label text. 



## Model Binding

Binding directly to your model by using the `@` symbol:

{: .xml-file }

MyView.xml

```xml
<MyView>
     
  <Label Text="{@MyModelValue}" />
   
</MyView>
```

This assumes there is a property called `MyModelValue` in the `Models` static class. You can declare it like this: 

{: .cs-file }

MyModel.cs

```c#
namespace Delight
{
    public partial class Models
    {
        public static string MyModelValue = "Hello";
    }
}
```



## Multi Binding

You can bind multiple values to a single target property using a transformation method specified using the `$` symbol:

{: .xml-file }

MyView.xml

```xml
<MyView>
  
  <Group>
    <InputField Id="Input1" />
    <InputField Id="Input2" />
    <Label Text="$Sum({Input1.Text}, {Input2.Text})" />   
  </Group>
   
</MyView>
```

{: .cs-file }

MyView.cs

```c#
namespace Delight
{
    public partial class MyView
    {
        public string Sum(string input1, string input2)
        {
            if (int.TryParse(input1, out var number1) && 
                int.TryParse(input2, out var number2))
            {
                return (number1 + number2).ToString();
            }

            return "specify two numbers";
        }
    }
}
```

If either `Input1.Text` or `Input2.Text` changes value the values are transformed and propagated to the label text using the `Sum()` method.



## Format String Binding

To transform multiple values into a formatted string:

{: .xml-file }

MyView.xml

```xml
<MyView>
  
  <Group>
    <InputField Id="Firstname" />
    <InputField Id="Lastname" />
    <Label Text="Hello {Firstname.Text} {Lastname.Text}!" />
  </Group>
   
</MyView>
```

You can also add format modifiers to control things like number of decimals printed:

{: .xml-file }

MyView.xml

```xml
<MyView>
  
  <Group Orientation="Vertical">
    <Slider Id="Slider1" Orientation="Vertical" Min="20" Max="180" Value="50" />
    <Label Text="{Slider1.Value:0.0}" />
  </Group> 
   
</MyView>
```

It translates to the following C# operation: 

`Label.Text = String.Format("{0:0.0}", Slider1.Value);`

To print the slider value with one decimal. For a comprehensive list of string formatting options check out the [String.Format Method](https://docs.microsoft.com/en-us/dotnet/api/system.string.format?view=netcore-3.1) documentation. 



## Binding to Collections

You can bind to collections using the `{item in MyCollection}` syntax:

{: .xml-file }

HighscoreTest.xml

```xml
<HighscoreTest>
  
    <List Id="HighscoreList" Items="{highscore in @Highscores}" Width="300">
      <ListItem Width="100%">
        <Label Text="{highscore.Name}: {highscore.ScoreText}"/>
      </ListItem> 
    </List>
   
</HighscoreTest>
```

Here we bind the collection `Highscores` that resides in our model to the list view. The list view dynamically generates a `ListItem` view for each item in the collection. To bind to item properties we use the name `highscore` we've given each item (we can name it whatever we want) to access the properties. It works similar to the `foreach` statement in C#.



## Negated Binding

When binding to a boolean we have the option to negate the value using the `!` symbol:

{: .xml-file }

NewView.xml

```xml
<NewView MyBoolValue="t:bool = True">
   
  <Group>   
    <CheckBox IsChecked="{MyBoolValue}" />
    <CheckBox IsChecked="{!MyBoolValue}" />
  </Group>
   
</NewView>
```

The second checkbox will always have the negated value. 



## Localization Binding

To bind to localized labels we can use the `@Loc` syntax:

{: .xml-file }

NewView.xml

```xml
<NewView>

  <Label Text="{@Loc.Greeting1}" /> 
   
</NewView>
```

This binds to the `Greeting1` label in the localized dictionary.



## Binding Cheat Sheet

| Binding               | Example Syntax                                               |
| --------------------- | ------------------------------------------------------------ |
| Simple Binding        | `<CheckBox IsChecked="{MyBoolValue}" />` |
| Binding Path          | `<Label Text="{Input.Text}" />` |
| Model Binding         | `<Label Text="{@MyModelValue}" />` |
| Multi Binding         | `<Label Text="$Sum({Input1.Text}, {Input2.Text})" />` |
| Format String         | `<Label Text="Hello {Firstname.Text} {Lastname.Text}!" />`<br>`<Label Text="{Progress:0.0} %" />` |
| Collection Binding    | `<List Id="HighscoreList" Items="{highscore in @Highscores}">` |
| Negated Binding       | `<CheckBox IsChecked="{!MyBoolValue}" />` |
| Localization Binding  | `<Label Text="{@Loc.Greeting1}" />` |

