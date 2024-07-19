# Java Cheatsheet

## Basic Syntax

### Variables
```java
int myInt = 5;
double myDouble = 5.99;
char myChar = 'A';
boolean myBool = true;
String myString = "Hello";
```

### Arrays
```java
int[] myArray = new int[5];
int[] myArray = {1, 2, 3, 4, 5};
```

## Data Structures

### ArrayList
```java
import java.util.ArrayList;

ArrayList<String> list = new ArrayList<>();
list.add("Item");                 // Add to end
list.add(0, "First");             // Add at index
String item = list.get(0);        // Get item
list.set(1, "New Item");          // Set item
list.remove(0);                   // Remove by index
list.remove("Item");              // Remove object
int size = list.size();           // Get size
boolean contains = list.contains("Item");  // Check if contains
list.clear();                     // Remove all elements
```

### HashSet
```java
import java.util.HashSet;

HashSet<String> set = new HashSet<>();
set.add("Item");                  // Add item
set.remove("Item");               // Remove item
boolean contains = set.contains("Item");  // Check if contains
int size = set.size();            // Get size
set.clear();                      // Remove all elements

// Iterate over set
for (String item : set) {
    System.out.println(item);
}
```

### HashMap
```java
import java.util.HashMap;

HashMap<String, Integer> map = new HashMap<>();
map.put("Key", 1);                // Add or update
int value = map.get("Key");       // Get value
map.remove("Key");                // Remove pair
boolean containsKey = map.containsKey("Key");  // Check if key exists
boolean containsValue = map.containsValue(1);  // Check if value exists
int size = map.size();            // Get size
map.clear();                      // Remove all pairs

// Iterate over map
for (Map.Entry<String, Integer> entry : map.entrySet()) {
    System.out.println(entry.getKey() + ": " + entry.getValue());
}
```

## File I/O
```java
import java.io.*;

// Reading a file
try (BufferedReader br = new BufferedReader(new FileReader("file.txt"))) {
    String line;
    while ((line = br.readLine()) != null) {
        System.out.println(line);
    }
} catch (IOException e) {
    e.printStackTrace();
}

// Writing to a file
try (BufferedWriter bw = new BufferedWriter(new FileWriter("file.txt"))) {
    bw.write("Hello, World!");
} catch (IOException e) {
    e.printStackTrace();
}
```

## Useful Methods

### Math Methods
```java
double power = Math.pow(2, 3);
double squareRoot = Math.sqrt(16);
int absolute = Math.abs(-5);
int max = Math.max(10, 20);
```

## Lambda Expressions
```java
Arrays.asList("a", "b", "c").forEach(e -> System.out.println(e));
```

### String Methods
```java
String str = "Hello, World!";
int length = str.length();        // Get length
char ch = str.charAt(0);          // Get char at index
String sub = str.substring(0, 5); // Get substring
boolean equals = str.equals("Hello");  // Compare strings
String lower = str.toLowerCase(); // Convert to lowercase
String upper = str.toUpperCase(); // Convert to uppercase
String trimmed = str.trim();      // Remove leading/trailing whitespace

// Replace methods
String replaced = str.replace('o', '0');     // Replace char
String replacedAll = str.replaceAll("o", "0"); // Replace all occurrences (regex)
String replacedFirst = str.replaceFirst("o", "0"); // Replace first occurrence (regex)
```

### Character Array and String Conversion
```java
// String to char array
String str = "Hello";
char[] charArray = str.toCharArray();

// Char array to String
char[] chars = {'H', 'e', 'l', 'l', 'o'};
String newStr = new String(chars);

// Substring of char array to String
String partialStr = new String(chars, 1, 3);  // "ell"

// String to byte array
byte[] bytes = str.getBytes();

// Byte array to String
String fromBytes = new String(bytes);
```
