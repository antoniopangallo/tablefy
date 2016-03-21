# Tablefy
Tablefy is a plug-in for Bootstrap framework, that permit to manage data pagination into a table, the addition, removal and editing a row, the instant search and the columns ordering.

## How to Use
### HTML CODE
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
### Javascript
```javascript
var table= new Tablefy("table");
var data=[
["Antonio Pangallo","Via Nazionale 32","Milano","87100","333333333","refuse@github.com"],
["Luca Bianchi","Via Nazionale 32","Roma","87100","333333333","refuse@github.com"],
["Paolo Rossi","Corso Garibaldi 32","Torino","87036","111111111","refuse@github.com"]
];
table.setDataTable(data);
```
