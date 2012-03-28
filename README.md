# Useful Autocomplete Data #
A repo of useful data & examples for common form fields. 

Corrections & improvements welcome. If you have any suggestions for useful data to add please let me know. 

[Examples & Usage](http://samsargent.github.com/Useful-Autocomplete-Data)

## Countries ##

[countries.json](https://github.com/samsargent/Useful-Autocomplete-Data/blob/master/data/countries.json) 

Source - [http://en.wikipedia.org/wiki/ISO_3166-1](http://en.wikipedia.org/wiki/ISO_3166-1) - 7/03/2012

````
/* Modified from http://johndyer.name/html-table-to-json/
   Scraped in the chrome console using the following:
*/

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
````

## Nationalities ##

[nationalities.json](https://github.com/samsargent/Useful-Autocomplete-Data/blob/master/data/nationalities.json)

Source - [http://www.guavastudios.com/downloads/nationalities/nationalities.txt](http://www.guavastudios.com/downloads/nationalities/nationalities.txt) -7/03/2012

## Languages ##

[languages.json](https://github.com/samsargent/Useful-Autocomplete-Data/blob/master/data/languages.json)

Source - [http://stevehardie.com/2009/10/list-of-common-languages/](http://stevehardie.com/2009/10/list-of-common-languages/) - 8/03/2011 - scraped via the below console script in chrome dev tools:

````
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
rowData[ headers[j] ] = jQuery(tableRow.cells[j]).text();
else if(j==1 || j == 2)
rowData[ headers[j] ] = jQuery(tableRow.cells[j]).text();
} data.push(rowData);
}
return data; 
}
````

## Postcodes ##

[postcodes.json](https://github.com/samsargent/Useful-Autocomplete-Data/blob/master/data/postcodes.json)

## Google Maps Geocoded Addresses ##

[G Maps Geocoded Addresses](http://code.google.com/apis/maps/documentation/geocoding/index.html)
