# Useful Autocomplete Data #
A repo of useful data & examples for common form fields. 

Corrections to existing material are always welcome and I hope that together we can provide a useful resource that is of help.

[Examples & Usage](http://samsargent.github.com/Useful-Autocomplete-Data)

## Countries ##

[countries.json](https://github.com/samsargent/Useful-Autocomplete-Data/blob/master/data/countries.json) 

Source - [http://en.wikipedia.org/wiki/ISO_3166-1](http://en.wikipedia.org/wiki/ISO_3166-1) - 7/03/2012

````
// Modified from http://johndyer.name/html-table-to-json/

function tableToJson(table) {
var data = []; // first row needs to be headers 
var headers = [];
for (var i=0; i<table.rows[0].cells.length; i++) {
 headers[i] = table.rows[0].cells[i].innerHTML.toLowerCase().replace(/ /gi,'');
}
// go through cells
for (var i=1; i<table.rows.length; i++) {
var tableRow = table.rows[i]; var rowData = {};
for (var j=0; j<tableRow.cells.length; j++) {

if(j==0)
rowData[ headers[j] ] = $(tableRow.cells[j]).find('a').text();
else if(j==1 || j == 2)
rowData[ headers[j] ] = $(tableRow.cells[j]).find('tt').text();
} data.push(rowData);
}
return data; 
}