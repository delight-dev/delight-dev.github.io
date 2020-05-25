## Examples

**Fixed size 3x3 grid**

```xml
<Grid Rows="100,100,100" Columns="100,100,100" Size="300,300">
  <Region Grid.Cell="0,0" BackgroundColor="#5389e0">
    <Label Text="Cell00" AutoSize="True" />
  </Region>
  <Region Grid.Cell="0,1" BackgroundColor="#e375f9">
    <Label Text="Cell01" AutoSize="True" />
  </Region>
  <Region Grid.Cell="0,2" BackgroundColor="#74f9d5">
    <Label Text="Cell02" AutoSize="True" />
  </Region>
   
  <Region Id="Cell10" Grid.Cell="1,0" BackgroundColor="#f9c674">
    <Label Text="Cell10" AutoSize="True" />
  </Region>
  <Region Id="Cell11" Grid.Cell="1,1" BackgroundColor="#fced2d">
    <Label Text="Cell11" AutoSize="True" />
  </Region>
  <Region Id="Cell12" Grid.Cell="1,2" BackgroundColor="#2cf72f">
    <Label Text="Cell11" AutoSize="True" />
  </Region>

  <Region Id="Cell20" Grid.Cell="2,0" BackgroundColor="#ef552b">
    <Label Text="Cell20" AutoSize="True" />
  </Region>
  <Region Id="Cell21" Grid.Cell="2,1" BackgroundColor="#0087ff">
    <Label Text="Cell21" AutoSize="True" />
  </Region>
  <Region Id="Cell22" Grid.Cell="2,2" BackgroundColor="#8730ad">
    <Label Text="Cell22" AutoSize="True" />
  </Region>
</Grid>
```



**Grid with proportionally sized columns and rows**

```xml
<Grid Rows="100,*,100" Columns="50,1*,2*">
  <!-- content removed for brevity ---> 
</Grid>
```

The grid has 3 rows, first and last row is 100 pixels high and the middle row take up the remaining space. The grid has 3 columns where the first column is 50 pixels wide and the second column takes up 1/3 of the remaining space, and the last column takes up 2/3 of the remaining space. 



**Resizable Grids**

```xml
<Grid Rows="100[50],*,100" Columns="100[20-150],*,100">
  <!-- content removed for brevity ---> 
 <GridSplitter Thickness="5" InteractionThickness="20" 
               SplitterColor="#333333" SetSizeOnDragEnded="False" />
</Grid>
```

To create resizable grids add a [GridSplitter](GridSplitter) to the grid.  The gridsplitter creates interactable handles that can be used to resize the grid. The min/max size of columns/rows are specified as well, e.g. the first row `100[50]` has a minimum size of 50 pixels, and the first column `100[20-150]` has a minimum size of 20 pixels and a maximum size of 150 pixels.

You can also use control which rows/columns should be split, the extent of the splitter handle and use multiple grid-splitters if you want to split columns and rows differently. 

```xml
<GridSplitter Thickness="5" SplitMode="Rows" 
              Grid.Cell="0,1"
              SplitterColor="Black"/>
<GridSplitter Thickness="5" SplitMode="Columns" 
              Grid.Cell="1,0" Grid.CellSpan="1,2"
              SplitterColor="Green"/>
```

The first gridsplitter takes the area starting from the begining of first row, second column (0,1) and spans the rest of the grid, and splits all rows within. The second splitter takes the area r handle starts from the second column.  The second gridsplitter splits the first two columns but the handle only extends one row. 

![](grid-splitters.png)