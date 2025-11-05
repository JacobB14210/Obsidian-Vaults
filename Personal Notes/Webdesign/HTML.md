- Format of a blank HTML file

```html
<html>
	<head>
		<meta charset="UTF-8">
		<!-- Set the page width equal to the device width-->
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<title> Example title </title>
		<!-- Can use stylesheet or style tag for css -->
		<link rel="stylesheet" type="text/css" href="styles.css">
		<style>
			/* Class style */
			.ClassName {
		        
			}
			
			/* Tag style */
			TagName {
				
			}
		</style>
	</head>
	<body>
		<div class="ClassName">
			<!-- Unordered List -->
			<ul>
				<li> Item in list </li>
			</ul>
			<!-- Ordered List -->
			<ol>
				<li> Item in list</li>
			</ol>
		</div>
	</body>
</html>
```

- padding: Pixels outside of the grid
- gap: Pixels between each element
- display: 
	- flex: Items line up horizontally
	- grid: Grid of items
- grid-template-columns: Amount of columns
	- Auto  set width based on elements length
	- 1fr sets columns for a fraction of a space (1fr for each column)
		- Number represents how much bigger the section is compared to others
- grid-column:
	- span #: cell will span that many cells