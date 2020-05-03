## Examples

Static tab panel:

```xml
<TabPanel>
  <Tab Text="Tab 1">
    <Label Text="Tab Content 1" />
  </Tab>
  <Tab Text="Tab 2">
    <Label Text="Tab Content 2" />
  </Tab>
</TabPanel>
  
```

Dynamic tab panel:

```xml
<TabPanel Items="{player in @Players}">
  <TabHeader Text="{player.Name}"/>
  <Tab>
    <Label Text="Content for {player.Name}" />
  </Tab>
</TabPanel>
```

Static tab panel with multiple custom tab headers: 

```xml
<TabPanel>
  <TabHeader Id="Header1" />
  <TabHeader Id="Header2" TextMargin="20,0,0,0">
     <CheckBox Alignment="Left" Offset="10,0,0,0" />
  </TabHeader>
    
  <Tab Text="Tab 1" TabHeaderId="Header1">
    <Label Text="Tab Content 1" />
  </Tab>
  <Tab Text="Tab 2" TabHeaderId="Header1">
    <Label Text="Tab Content 2" />
  </Tab>
  <Tab Text="Tab 3" TabHeaderId="Header2">
    <Label Text="Tab Content 2" />
  </Tab>
</TabPanel>
  
```
