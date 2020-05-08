---
title: Styles
parent: Tutorials
has_children: false
nav_order: 6
---
# Styles

1. TOC
{:toc}

## Introduction

Styles are used to define classes of views and to change their default properties. If you're familiar with HTML it works similar to CSS. 



## Declaring a Style

Styles are declared in an XML file under the `Content/Styles`  folder: 

{: .xml-file }

MyStyles.xml

```xml
<MyStyles>
  <Button BackgroundColor="Red" /> 
  <Button Style="BigBlueButton" BackgroundColor="Blue" 
          Width="300" Height="80" /> 
</MyStyles>
```

The above file defines two styles. The first one changes the *BackgroundColor* on all buttons to red. The second style changes the *BackgroundColor*, *Width* and *Height* on all buttons with the style *BigBlueButton* to the values defined. Here is an example of using the style in a view:

{: .xml-file }

MyView.xml

```xml
<MyView>
  <Group>
    <Button Text="Button1"/> 
    <Button Style="BigBlueButton" Text="Button2" /> 
  </Group>
</MyView>
```

The first button will have the default button style applied and be red. The second button will have the *BigBlueButton* style applied and be blue. 



## Basing Styles on Others

If you want to create a new style that is based on an existing style you can use the *BasedOn* attribute:

{: .xml-file }

MyStyles.xml

```xml
<Button Style="BigButton" Width="300" Height="80" /> 
<Button Style="BigBlueButton" BasedOn="BigButton" 
        BackgroundColor="Blue"  /> 
```



## Not Just Looks

It's worth pointing out that, despite what the name implies, styles can be used to define any property and not just those that changes the appearance of the view. E.g. if you're creating a mobile game and want all lists to select on mouse up by default you can change this using styles:

{: .xml-file }

MyStyles.xml

```xml
<MyView>
   <List SelectOnMouseUp="True" />
</MyView>
```


