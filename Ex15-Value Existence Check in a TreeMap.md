# Ex15 Value Existence Check in a TreeMap
## DATE: 24/09/2025
## AIM:
To write a Java program that checks whether a given value exists in a TreeMap.

## Algorithm
1. Create a TreeMap to store key–value pairs.
2. Insert some sample key–value pairs into the TreeMap.
3. Display the contents of the TreeMap.
4. Use the containsValue() method to check whether a specific value exists in the map  
5. Display the result based on the check.  

## Program:
```java
/*
Program to checks whether a given value exists in a TreeMap.
Developed by: HARISH S
Register Number: 212223230071
*/

import java.util.*;

public class TreeMapValueExistenceCheck {

    public static void checkValue(TreeMap<Integer, String> map, String searchValue) {
        if(map.containsValue(searchValue)){
            System.out.println("Value \""+searchValue+"\" exists in the TreeMap.");
        }else{
            System.out.println("Value \""+searchValue+"\" does not exist in the TreeMap.");
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        TreeMap<Integer, String> map = new TreeMap<>();

        int n = sc.nextInt();

        for (int i = 0; i < n; i++) {
            int key = sc.nextInt();
            sc.nextLine();  
            String value = sc.nextLine();
            map.put(key, value);
        }
        String searchValue = sc.nextLine();

        checkValue(map, searchValue);
        sc.close();
    }
}

```

## Output:
<img width="970" height="664" alt="image" src="https://github.com/user-attachments/assets/cdbab398-2834-42ce-9b3e-8d24c188fd1d" />


## Result:
Thus, the program successfully checks whether a specified value exists in a TreeMap using the containsValue() method.
