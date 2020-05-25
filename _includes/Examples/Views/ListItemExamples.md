## Examples

Static [List](List):

```xml
<List BackgroundColor="White">
  <ListItem Size="100;30">
    <Label Text="Item 1" AutoSize="True" Alignment="Left" 
           Margin="10,0,0,0" />
  </ListItem>
  <ListItem Size="100;30">
    <Label Text="Item 2" AutoSize="True" Alignment="Left" 
           Margin="10,0,0,0" />
  </ListItem>
  <ListItem Size="100;30">      
    <Label Text="Item 3" AutoSize="True" Alignment="Left" 
           Margin="10,0,0,0" />
    <CheckBox Alignment="Right" />
  </ListItem>
</List>  
```

Dynamic [List](List):

```xml
<List Items="{fruit in @Fruits}" BackgroundColor="White">
  <ListItem Width="150">
    <Image Sprite="{fruit.Icon}" Alignment="Left" Offset="10,0,0,0" />
    <Label Text="{fruit.Name}" AutoSize="True" Alignment="Left" 
           Margin="40,0,0,0" />
  </ListItem>
</List>
```

See the [Lists tutorial](../../Tutorials/Lists) for information on how to create scrollable lists, virtualized lists, flowing lists, paged lists and more. 