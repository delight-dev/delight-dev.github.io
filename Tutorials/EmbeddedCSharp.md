---
title: Embedded C# in XML
parent: Tutorials
has_children: false
nav_order: 12
---
# Embedded C# Expressions in XML

1. TOC
{:toc}

## Declaring Embedded Expression

You can embed C# expressions in property values in XML using the `$` prefix:

```xml
<EmbeddedExpressionsExample ClickCount="t:int">
  <Group Orientation="Horizontal" Spacing="5"> 
    <Button Text="Click Me" Click="$ ++ClickCount" />
    <Label Text="$ Math.Pow({ClickCount}, 2).ToString()" />
  </Group> 
</EmbeddedExpressionsExample>

```

The above example contains two embedded expressions:

1. Button click handler that increases the click count:

   `Click="$ ++ClickCount">` 

2. Label text that presents the click count squared: 

   `Text="$ Math.Pow({ClickCount}, 2).ToString()"`

   The above expression creates a [transform binding](DataBinding#multi-binding--transform-binding) that will update whenever ClickCount changes. 

Note that in the expression you have access to all the local properties of the parent view as well as any other code in your project. 



## String in expressions

Strings in expressions are specified using single quotes:

```xml
<Label Text="$ 'hello world' " /> 
```



## AND operator and the '&' symbol

XML treats `&` as a special character, so you need to use `&amp;` to insert the symbol. Since the conditional logical AND operator (&&) is so common the framework translates the word AND to &&:

```xml
<Label Text="Text" IsActive="$ {ClickCount} > 0 AND {ClickCount} < 10" /> 
```

Which translates to the C# code:  

`IsActive = ClickCount > 0 && ClickCount < 10`

You can also use the word OR instead of `||`  although it's not necessary as the symbols are allowed in XML. 



## Multi-line expressions

Multi-line expressions can be declared by inserting brackets into the expression. Start and end brackets are defined using two brackets:

{% raw %}

```xml
<Label Text="$ {{ string test = 'hello'; return test; }}" /> 
```

Note that you need to use a return statement to return the result of the evaluation.

{% endraw %}

## Common scenarios

1. Switching views on/off based on conditions:

   ```xml
   <Region IsActive="$ {MyEnum} == MyEnum.Active"> 
   </Region>
   ```

2. Invoking view actions:

   ```xml
   <MyView CloseClick="t:Action">
     <Button Text="Close" Click="$ CloseClick.Invoke()" />
   </MyView>
   ```

3. Invoking methods and passing list item data:

   ```xml
   <List Items="{fruit in @Fruits}" BackgroundColor="White">
     <Group>
       <Label Text="$ GetDisplayName({fruit})" />
       <Button Text="Delete" Click="$ Models.Fruits.Remove(fruit)" />
     </Group>
   </List>
   ```

   