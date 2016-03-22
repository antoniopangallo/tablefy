# Tablefy
Tablefy is a plug-in for Bootstrap framework, that permit to manage data pagination into a table, the addition, removal and editing a row, the instant search and the columns ordering.

#### Properties
* length  Returns the number of rows of this table
* pages   Returns the number of pages of this table
* item    Returns the selected row

* Item 1
* Item 2
* Item 3
  * Item 3a
  * Item 3b
  * Item 3c

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
