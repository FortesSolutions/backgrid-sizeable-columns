# Backgrid.js - (Re)sizeable columns PoC
Warning! This is by far not production ready code, just a mere proof of concept. It lacks documentation, automatic testing, IE browser support (somehow, did work before) and edge-case tests.

## Demo website
Online demo of PoC can be found [here](http://techwuppet.com/backgrid_poc_demo/)

## (Re)sizeable columns
- Uses html5 valid colgroup method to (re)size columns
- Supports nonresizeable, width, min and max width
- Trigger event on column resize
- Supports 'renderable' and add/removal of columns
- Supports Grouped columns in header

### Example

```javascript

// Add sizeable columns
var sizeAbleCol = new Backgrid.Extension.sizeAbleColumns({
  collection: pageableTerritories,
  columns: columns
});
$backgridContainer.find('thead').before(sizeAbleCol.render().el);

// Add resize handlers
var sizeHandler = new Backgrid.Extension.sizeAbleColumnsHandlers({
  sizeAbleColumns: sizeAbleCol,
  grid: pageableGrid,
  saveModelWidth: true
});
$backgridContainer.find('thead').before(sizeHandler.render().el);

// Listen to resize events
columns.on('resize', function(columnModel, newWidth, oldWidth) {
  console.log('Resize event on column; name, model, new and old width: ', columnModel.get("name"), columnModel, newWidth, oldWidth);
});
```

## License
Copyright (c) 2014 Wilbert van de Ridder
Licensed under the [MIT license](LICENSE-MIT "MIT License").
