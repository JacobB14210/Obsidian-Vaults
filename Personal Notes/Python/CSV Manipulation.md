```python
import csv
import os

csv.reader() # Read rows
csv.writer() # Write rows

def importCSV(filepath):
	if not os.path.exists(filePath):
		print("File not found")
		return

	with open(filePath, newline='', encoding='utf-8') as file:
		reader = csv.reader(file)
		
		next(reader) # Skips first row (header in this case)
		
		for row in reader:
			variable = row[column] # Get element in that row at that column
			print(row) # Print entire row

def exportCSV(filePath, rows):
    with open(filePath, mode='w', newline='', encoding='utf-8') as file:
        writer = csv.writer(file)

        for row in rows:
            writer.writerow(row)
```