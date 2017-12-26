<p align="center"><img src="https://raw.githubusercontent.com/tbaljevic/GridTableJS/master/images/gridtablejs.png" title="GridTableJS Logo" /></p>

# [GridTableJS](https://github.com/tbaljevic/GridTableJS) - Complex Table Layouts, Simplified.
### What is GridTableJS?
GridTableJS is a lightweight javascript library that helps simplify the creation of web tables with complicated layouts.
Users are provided with simple row- and column-based alignment mechanisms, freeing them from worries of misaligned cells across rows.

### Can I improve upon GridTableJS?
Absolutely!
GridTableJS has been released under the GPL license, and I encourage anyone who wishes to make improvements to do so!
Please also remember to release any changes you've made back to the public under the same GPL license!

## Installation
### Technical Requirements
* An ES6-compliant browser

### Installation
Download a copy of the ```gridtable.js``` file from the /src folder in this repository, host it where it's required and import it into your project.

## Usage
### Table Creation
Once GridTableJS has been imported into your project, creating a new managed table is simple:
```js
table = gridtablejs.createTable(parentElemId = "parentElementIdHere");
```

### Table Manipulation
#### Adding Individual Cells
```js
// Individually adding a cell.
table.addCell(
    row = 0,
    column = 0,
    content = "Hello, World!",
    customAttributes = {
      "rowspan": 3,
      "colspan": 5,
      "class": "my-class"
    },
    domTag = "td"
  );

/**
* Adding an individual cell without the "customAttributes" or "domTag" properties 
* is also possible. In this case, no HTML attributes will be applied to the resultant 
* cell, and it is assumed to be a "td" element.
*/
table.addCell(
    row = 0,
    column = 1,
    content = "Hello again, World!"
  );
```
#### Adding groups of cells
```js
// Adding a group of cells. The "customAttributes" provided will be applied to all cells.
table.addCells(
    row = 100,
    column = 100,
    cellContents = [
      "This is the first cell",
      "This is the second...",
      "...and this is the third."
    ],
    customAttributes = {
      "custom-attribute": "custom-value"
    },
    domTag = "th"
  );

/**
* As with individual cell creation, it is also possible to create a group of cells 
* without the "customAttributes" or "domTag" properties.
*/
table.addCells(
    row = 10,
    column = 10,
    cellContents = [
      "Cell #1",
      "Cell #2"
    ]
  );
```

### Table Display
Once the table has been completely populated, a render call will create and display the table:
```js
table.render()
```

### Error Management
#### Clashes
If an attempt is made to insert a cell into a location that clashes with a previously-inserted cell, a warning will be displayed in the browser console.
