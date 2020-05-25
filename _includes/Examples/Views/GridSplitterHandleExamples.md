## Examples

[Grid](LayoutGrid) with resizable rows and columns:

```xml
<Grid Rows="100[50],*,100" Columns="100[20-150],*,100">
  <!-- content removed for brevity ---> 
 <GridSplitter Thickness="5" InteractionThickness="20" 
               SplitterColor="#333333" SetSizeOnDragEnded="False" />
</Grid>
```

To create a resizable [Grid](LayoutGrid) add a GridSplitter to the grid.  The gridsplitter creates interactable handles that can be used to resize the grid. The min/max size of columns/rows are specified as well, e.g. the first row `100[50]` has a minimum size of 50 pixels, and the first column `100[20-150]` has a minimum size of 20 pixels and a maximum size of 150 pixels.

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