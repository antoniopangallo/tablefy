# Tablefy
Tablefy is a plug-in for Bootstrap framework, that permit to manage data pagination into a table, the addition, removal and editing a row, the instant search and the columns ordering.
You can see Tablefy in action at [http://antoniopangallo.github.io/tablefy](http://antoniopangallo.github.io/tablefy) inline link.

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
##### ```Remove a specific row of the table```
##### Parameters

 | Name    | Type         | Default | Description                  |
 | --------|--------------|---------|------------------------------|
 | row     | Array        |         | The row that you want remove |

##### Syntax
```javascript
var table= new Tablefy("table");
var row=["antonio","roma","3333333345","1200$"];
table.removeRow(row) // Remove a specific row of the table
```
 
* Table.prototype.sort()
##### ```Sort a specific colum of the table```
##### Parameters

 | Name    | Type         | Default | Description                                         |
 | --------|--------------|---------|-----------------------------------------------------|
 | mode    | String       |  "asc"  | "asc" for ascendig sort, "desc" for descending sort |
 | colum   | Numbers      |    1    | The colum number that you want order                |
 
##### Syntax
```javascript
var table= new Tablefy("table");
table.sort("asc",2) // Sort a colum 2 in ascendig mode
table.sort("desc",3) // Sort a colum 3 in descending mode
```

* Table.prototype.addEventListener()
##### ```Registers an event listener object so that the listener receives notification of an event```
##### Parameters

 | Name    | Type         | Default | Description                                                              |
 | --------|--------------|---------|--------------------------------------------------------------------------|
 | type    | String       |         | Possible Values : onAddRow,onRemoveRow,onEditRow,onClickRow,ondblClickRow|
 | fn      | Function     |         | The listener function that processes the event                           |
 
##### Syntax
```javascript
var table= new Tablefy("table");
table.addEventListener("onAddRow",function(target){
   console.log(target) // target is array that contains the added row
});  
table.addEventListener("onRemoveRow",function(target){
   console.log(target) // target is array that contains the removed row
}); 
table.addEventListener("onEditRow",function(target){
   console.log(target.current) // target.current is array that contains the row before the change
   console.log(target.prev)   // target.prev is array that contains the row after the change
});
table.addEventListener("onClickRow",function(target){
   console.log(target) // target is array that contains the selected row
});
table.addEventListener("ondblClickRow",function(target){
   console.log(target) // target is array that contains the selected row
});
```

* Table.prototype.setDataTable()
##### ```Set a data source into table```
##### Parameters

 | Name    | Type      | Default | Description     |
 | --------|-----------|---------|-----------------|
 | data    | Array     |         | Data Source     |
  
##### Syntax
```javascript
var table= new Tablefy("table");
var data_source=[
["Antonio Pangallo","Via Nazionale 32","Cosenza","87100","333333333","refuse@github.com"],
["Luca Bianchi","Via Nazionale 32","Roma","87100","333333333","refuse@github.com"],
["Paolo Rossi","Corso Garibaldi 32","Rende","87036","111111111","refuse@github.com"]
];
table.setDataTable(data_source) // Sort a colum 2 in ascendig mode
```

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
#### Example Ajax 
```javascript
var opt = {
            showElemet:20,     // numbers max of rows for page
            showSearch:true,   // if is true show the search bar
            showEdit:true,     // if is true show the Edit Button
            showDelete:true,   // if is true show the Delete Button
            showAdd:true,      // if is true show the Add Button
            ajax:{
                    url: "client/read.php", // A string containing the URL to which the request is sent.
                    data: { read : "client" }  // Data to be sent to the server.
                 } 
}
var table= new Tablefy("table",opt);
```
