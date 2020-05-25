## Examples

ComboBox with static items:

```xml
<ComboBox Id="ComboBox" ItemSelected="ItemSelected" IsDropUp="False">
  <ComboBoxListItem>
    <Label Text="Option 1" Width="100%" Margin="10,0,0,0" />
  </ComboBoxListItem>
  <ComboBoxListItem>
    <Label Text="Option 2" Width="100%" Margin="10,0,0,0" />
  </ComboBoxListItem>
  <ComboBoxListItem>
    <Image Sprite="RainbowSquare" Alignment="Left" Offset="5,0,0,0" />
    <Label Text="Option 3" Width="100%" Margin="30,0,0,0" />
  </ComboBoxListItem>
</ComboBox>
```

ComboBox with dynamic items:

```xml
<ComboBox Items="{player in @Players}" ItemSelected="ItemSelected">
  <ComboBoxListItem>
    <Label Text="{player.Name}" Width="100%" Margin="10,0,0,0" />
  </ComboBoxListItem>
</ComboBox>
```
