# Backgrid.js - (Re)sizeable columns
Warning! This extension is not production ready yet, just a mere proof of concept. It lacks documentation, automatic testing and edge-case tests.

To discuss this extension, see [this](https://github.com/wyuenho/backgrid/issues/6) backgrid issue.

## Demo
Online demo can be found [here](http://wridder.github.io/backgrid-demo/)

## Browser support (tested)
- IE8+
- Firefox
- Chrome

## Features
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
Copyright © 2014 [Fortes Solutions](https://www.fortesglobal.com/en).

Licensed under the [MIT license](LICENSE-MIT "MIT License").

## Authors
This extension was created by [Wilbert van de Ridder](https://github.com/WRidder) and is currently maintained by [Fortes Solutions Team](https://github.com/orgs/FortesSolutions/people).
