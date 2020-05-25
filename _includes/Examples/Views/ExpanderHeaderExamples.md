## Examples

Expander with custom header:

```xml
<Expander Width="300" Alignment="TopLeft">
  <ExpanderHeader Size="300,20">
    <Image Sprite="CheckBox" Expanded-Sprite="CheckBoxPressed" 
           ExpanderHeader.SetExpanderState="True" Alignment="Left" />
    <Label Text="Expand Me" Alignment="Left" AutoSize="True" Margin="30,0,0,0" />
  </ExpanderHeader>
  
  <ExpanderContent Size="300,200" BackgroundColor="Blue">
    <Label Text="Expanded Content" AutoSize="True" />
  </ExpanderContent>
</Expander>
```

