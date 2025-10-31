# ObjectMapper
```java
private static final ObjectMapper mapper = new ObjectMapper();

public static void readFile() {
	try {
	    File file = new File(FilePath*);  
	    return mapper.readValue(file, DataType*);  
	}  
	catch(IOException e) {
	    System.err.println("Error getting active user");  
	    return null;  
	}
}

public static void saveUsers() {
	try {
       mapper.writerWithDefaultPrettyPrinter().writeValue(new File(FilePath*), Data*);  
    }  
    catch(IOException e) {
       throw new RuntimeException("Failed to save Users.json", e);  
    }  
}
```