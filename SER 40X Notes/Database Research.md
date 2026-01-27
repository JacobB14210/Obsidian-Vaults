# Research
## MongoDB
- Stores JSON as BSON (Binary JSON)
- Supports nested JSON objects
- Flexible Schema
- Project doesn't need complex database relationships like JOINs
- Light write and heavy read
	- Majority of data stored won't be changed a lot
- Documents map naturally to python dictionaries
## Data to Populate DB With
- Municipality Profiles
- Scoring
- Scraper settings
	- Layout in a JSON when it runs
- Analysis Ready directory (Text Extraction Result)
- Generated Reports?
## How to Install
- Install "MongoDB for VS code" if using vs code
- Install MongoDB Community Server
	- Install as a service
	- Run as a network service
	- Install MongoDB Compass
- Install MongoDB Shell
	- Lets you manage databases through the terminal
- python -m pip install pymongo
## MongoDB Architecture
- MongoDB Server -> Databases -> Collections -> Documents
## MongoDB Shell Commands List
- mongosh: Open connection to local MongoDB instance
- show dbs: Show List of databases on the server
	- Can do the same for collections
- use {db}: Switch current database to {db}
	- Can do the same for collections
## MongoDB Python Syntax
```python
import pymongo

# Connect to MongoDB database
myclient = pymongo.MongoClient("mongodb://localhost:27017")

# Connect to specific database
mydb = myclient["mydatabase"] # Database

# Move to specific collection
mycollection = mydb["customers"] # Collection

mydict = { "name": "John", "address": "Highway 37" }
mycollection.update_one(
  { "name": mydict["name"]}, # Filter
  # Key to look for when updating
  { "$set": mydict}, # Update
  # Will add any new data
  upsert=True # Insert if key wasn't found
)
```