# Tablefy
Tablefy is a plug-in for Bootstrap framework, that permit to manage data pagination into a table, the addition, removal and editing a row, the instant search and the columns ordering.
#### Create a Tablefy
```javascript
var table= new Tablefy( HTMLElement || DOMidProperty[, opt ]);
```
##### Parameters
* *HTMLElement*
 ```
     var table= new Tablefy(document.getElementById("table"));
```
* *DOMidProperty*
 ``` 
   var table= new Tablefy("table");
```
* *opt*
```javascript
var opt = {
            showElemet:10,     // numbers max of rows for page
            showSearch:true,   // if is true show the search bar
            showEdit:true,     // if is true show the Edit Button
            showDelete:true,   // if is true show the Delete Button
            showAdd:true,      // if is true show the Add Button
            ajax:{
                    url: "path/test.php", // A string containing the URL to which the request is sent.
                    data: { key :"value", ... }  // Data to be sent to the server.
                 } 
}
```

#### Properties
* *length* 
* *pages*   
* *item*    

##### Syntax
```javascript
var table= new Tablefy("table");
table.length // Returns the number of rows of this table
table.pages // Returns the number of pages of this table
table.item // Returns the selected row
```
##### Methods
* Tablefy.prototype.addRow()
#####```Add a row into table```
##### Parameters

 | Name    | Type         | Default | Description                |
 | --------|--------------|---------|----------------------------|
 | row     | Array<String>|         | The row that you want add  |
 
##### Syntax
```javascript
var table= new Tablefy("table");
var row=["antonio","roma","3333333345","1200$"];
table.addRow(row) // Add a row into table
```

* Tablefy.prototype.removeRow()
###### ```Remove a specific row of the table```
###### Parameters

 | Name    | Type         | Default | Description                  |
 | --------|--------------|---------|------------------------------|
 | row     | Array<String>|         | The row that you want remove |

###### Syntax
```javascript
var table= new Tablefy("table");
var row=["antonio","roma","3333333345","1200$"];
table.removeRow(row) // Remove a specific row of the table
```
> > ##### Parameters
  row ``` An array of String. Example : ["antonio","roma","3333333345","1200$"] ```
 
* Table.prototype.sort()
 
>> ##### Syntax
```javascript
var table= new Tablefy("table");
table.sort(mode,colum) // Sort a specific colum of the table
```
>> ##### Parameters
  * mode ``` A string whit possible values "asc" and "desc" ```
  * colum ``` The colum number that you want order"  ```

### Usage
#### Simple Example
```html
<div class="table-responsive">
	<table id="table" class="table table-hover">
		 <thead>
			<tr>
				<th>Name</th>
				<th>Address</th>
				<th>City</th>
				<th>Cap</th>
				<th>Phone</th>
				<th>Email</th>
			</tr>
		</thead>
        </table>
</div>
```
```javascript
var table= new Tablefy("table");
var data=[
["Antonio Pangallo","Via Nazionale 32","Cosenza","87100","333333333","refuse@github.com"],
["Luca Bianchi","Via Nazionale 32","Roma","87100","333333333","refuse@github.com"],
["Paolo Rossi","Corso Garibaldi 32","Rende","87036","111111111","refuse@github.com"]
];
table.setDataTable(data);
```
