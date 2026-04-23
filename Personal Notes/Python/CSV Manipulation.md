- csv.reader(): Read rows
- csv.writer(): Write rows

```python
import csv
from datetime import datetime
import os


def importCSV(filepath):
	if not os.path.exists(filePath):
		print("File not found")
		return

	with open(filePath, newline='', encoding='utf-8') as file:
		reader = csv.reader(file)
		readerDict = csv.DictReader(file)
		
		next(reader) # Skips first row (header in this case)
		
		for row in reader:
			variable = row[columnIndex] # Get element in that row at that column
			variable = row["column"] # Get element with column label
			print(row) # Print entire row


def exportCSV(filePath, rows):
	os.makedirs("output", exists_ok=True)
	
	filename = f"output/Exported Records + {datetime.now().strftime('%Y%m%d_%H%M%S')}.csv"
	
    with open(filePath, mode='w', newline='', encoding='utf-8') as file:
        writer = csv.writer(file)
		
		writer.writerow(["column1", "column2"]) # Write header first
		
        for row in rows:
            writer.writerow(row)
            
```