# Tablefy
Tablefy is a plug-in for Bootstrap framework, that permit to manage data pagination into a table, the addition, removal and editing a row, the instant search and the columns ordering.

## How to Use 
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
table.setDataTable(data);
```
