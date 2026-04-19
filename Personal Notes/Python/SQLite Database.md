```python
import sqlite3

conn = sqlite3.connect("databaseName.db)
cursor = conn.cursor()

cursor.execute("""
CREATE TABLE IF NOT EXISTS tableName (
	id INTEGER PRIMARY KEY AUTOINCREMENT,
	variable INTEGER,
	variable1 TEXT
)
""")

# ? placeholders prevents SQL injection
# Data must be a tuple
cursor.execute("""
INSERT INTO tableName (
	variable, variable1
) VALUES (?, ?)
""", data)

cursor.execute("SELECT id, variable FROM tableName")
rows = cursor.fetchall()

for row in rows:
	print(f"{row[0]}. {row[1]}")

cursor.execute("""
UPDATE tableName
SET variable = ?, variable1 = ?
WHERE id = ?
""", (variable, variable1, id))

conn.commit()
conn.close()
```