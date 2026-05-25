```python
import os

print(os.csd()) # Where python scipts looks from when it runs

os.chdir("data") # go into folder  
os.chdir("..") # go up one level

os.listdir() # list files in current dir  
os.listdir("data") # list files in another dir

path = os.path.join("data", "file.txt")

Path("output").mkdir(exist_ok=True)

BASE_DIR = Path(__file__).resolve().parent.parent  
TEST_DOCS = BASE_DIR / "test_documents"
```