# Java File Handling (My Notes)
## What I understood till now
So basically this part is about how Java deals with files like creating, deleting, checking etc.
At first I thought just writing "**File file = new File()**" will create the file, but it actually does NOT — it just kind of points to the file.

# Creating a file
```java
File file = new File("data.txt");
file.createNewFile(); 
```
- This actually creates the file in system
- Returns true if file is created
- Returns false if file already exists

-> So yeah, Java won’t overwrite automatically which is good.

# Deleting a file
```java
File file = new File("example.txt");
file.delete();
```
- Returns true if deleted
- Returns false if something goes wrong (file not found or permission issue I guess)
- Checking if file exists
``` java
File file = new File("data.txt");

if(file.exists()){
System.out.println("File exists");
}else{
file.createNewFile();
}
```
### This is actually important because:
- prevents duplicate files
- makes program safer 
- # Important thing (I almost ignored this)
### try-catch 😐
```java
try {
File file = new File("data.txt");
file.createNewFile();
} catch (IOException e) {
System.out.println(e.getMessage());
}
```
- File operations can throw errors
- Like permission issues or invalid path
- So wrapping in try-catch is kinda necessary
- write me above things for markdown