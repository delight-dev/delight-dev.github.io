---
title: Embedding C# in XML
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



## Shorthands for AND, OR, etc.

XML treats `&`  and `<` and `>` as a special characters, which need to be escaped: `&amp;`, `&lt;` and `&gt;`. Since the conditional logical AND-operator `&&` and comparison operators like `<` is so common in C# the framework provides shorthands, like `AND` that is translated to `&&`,  `GT` (greater than) for `>`, and `LT` for `<`.

```xml
<Label Text="Text" IsActive="$ {ClickCount} GT 0 AND {ClickCount} LT 10" /> 
```

The above XML translates to the C# code:  

`IsActive = ClickCount > 0 && ClickCount < 10`

You can also use the word OR instead of `||`  although it's not necessary as the symbols are allowed in XML. It's also not necessary to replace the `>` symbol in attribute values, but shorthands are there for consistency.

| Shorthand | Equivalent C# | Necessary |
| --------- | ------------- | --------- |
| LT        | <             | Yes       |
| LTE       | <=            | Yes       |
| GT        | >             | No        |
| GTE       | >=            | No        |
| EQ        | ==            | No        |
| AND       | &&            | Yes       |
| OR        | \|\|          | No        |



## Multi-line expressions

Multi-line expressions can be declared by inserting brackets into the expression. Start and end brackets are defined using two brackets:

{% raw %}

```xml
<Label Text="$ {{ string test = 'hello'; return test; }}" /> 
```

Note that you need to use a return statement to return the result of the evaluation.

{% endraw %}



## XML values in expressions

In XML values like Width can be specified like `100%` and Offset like `0,0,0,0` this is a convenient way to specify values and to do it in C# expressions you can use the notation `XML(<xml value>)`, e.g:

```xml
<Region Width="$ {@IsPortrait} ? XML(100%) : XML(50%)">
```



## Common scenarios

1. Switching views on/off based on conditions:

   ```xml
   <Region IsActive="$ {MyEnum} == XML(Active)"> 
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

4. Using view-switcher:

   ```xml
   <MyView>
     <ViewSwitcher Id="MySwitcher">
       <Region Id="ViewA">
         <Button Text="Switch to B" Click="$ MySwitcher.SwitchTo(ViewB)" />
       </Region>
       <Region Id="ViewB">
         <Button Text="Switch to A" Click="$ MySwitcher.SwitchTo(ViewA)" />
       </Region>
     </ViewSwitcher>
   </MyView>
   ```


5. Using navigator:

   ```xml
   <MyView>
     <Navigator>
       <Region Id="ViewA" Navigator.Path="/">
         <Button Text="Open B" Click="$ Navigator.Open('/test')" />
       </Region>
       <Region Id="ViewB" Navigator.Path="/test">
         <Button Text="Open A" Click="$ Navigator.Open('/')" />
       </Region>
     </Navigator>
   </MyView>
   ```

   