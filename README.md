## Ex11 Convert HashSet to ArrayList in Java
## AIM:
To convert a collection of distinct integers stored in a HashSet into an ArrayList and display its contents.

## Algorithm:

1.Start and create an empty HashSet.

2.Insert all the required integers into the HashSet.

3.Create an ArrayList and pass the HashSet to its constructor.

4.Store all elements of the HashSet into the ArrayList.

5.Display the elements of the ArrayList.

## Program:
```
/*
Program to To convert a collection of distinct integers stored in a HashSet into an ArrayList and display its contents.
Developed by: HARISH S
Register Number: 212223230071
*/
import java.util.*;

public class HashSetToArrayList {
    public static void main(String[] args) {

        // Create a HashSet of integers
        HashSet<Integer> numberSet = new HashSet<>();

        Scanner sc = new Scanner(System.in);
        System.out.print("Enter how many numbers you want to add: ");
        int n = sc.nextInt();

        // Taking input from the user
        System.out.println("Enter " + n + " distinct integers:");
        for (int i = 0; i < n; i++) {
            numberSet.add(sc.nextInt());
        }

        // Convert HashSet to ArrayList
        ArrayList<Integer> numberList = new ArrayList<>(numberSet);

        // Display the ArrayList
        System.out.println("\nArrayList contents:");
        for (int num : numberList) {
            System.out.println(num);
        }

        sc.close();
    }
}
```
## Output:

<img width="588" height="611" alt="image" src="https://github.com/user-attachments/assets/7c73d82d-8df2-4448-9637-9638cc91f379" />

## Result:
The program successfully converts a collection of distinct integers stored in a HashSet into an ArrayList

## Ex12 Add Elements from an Array into a TreeSet

## AIM:
To write a Java program that adds elements from an array into a TreeSet and displays the elements in sorted order.

## Algorithm:

1.Start and create an integer array.

2.Create an empty TreeSet.

3.Traverse the array using a loop.

4.Insert each array element into the TreeSet.

5.Display the TreeSet (elements appear in sorted order automatically).

## Program:

```
/*
Program that adds elements from an array into a TreeSet and displays the elements in sorted order.

*/
import java.util.*;

public class ArrayToTreeSet {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        // Take array size from user
        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();

        int[] arr = new int[n];

        // Input array elements
        System.out.println("Enter " + n + " integers:");
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        // Create a TreeSet
        TreeSet<Integer> set = new TreeSet<>();

        // Add array elements to TreeSet
        for (int num : arr) {
            set.add(num);
        }

        // Display sorted elements
        System.out.println("Elements in sorted order (TreeSet): " + set);

        sc.close();
    }
}
```

## Output:

<img width="694" height="483" alt="image" src="https://github.com/user-attachments/assets/40b4378f-1f4d-4337-ae72-9d15f66b2723" />

## Result:
The program successfully adds elements from an array into a TreeSet.

## Ex13 Fill the First 10 Elements of an Array with a Constant using Arrays.fill()

## AIM:
To write a Java program that fills the first 10 elements of an array with a constant value using the Arrays.fill() method.

## Algorithm:

1.Create an integer array of desired size.

2.Choose the constant value to fill.

3.Use Arrays.fill(array, startIndex, endIndex, value) to fill the first 10 elements.

4.Traverse the array (optional) to verify or display elements.

5.Print the array contents.

## Program:

```
/*
Program to FILL the first 10 elements of an array with a constant value using the Arrays.fill() method.

*/
import java.util.Arrays;

public class FillArrayExample {
    public static void main(String[] args) {

        // Create an array of size 15
        int[] arr = new int[15];

        // Constant value to fill
        int value = 7;

        // Fill first 10 elements with the value
        Arrays.fill(arr, 0, 10, value);  // from index 0 to 9

        // Display the array
        System.out.println("Array after filling first 10 elements: " + Arrays.toString(arr));
    }
}
```

## Output:

<img width="790" height="189" alt="image" src="https://github.com/user-attachments/assets/7b986008-2b6e-4d79-bddb-bd52d3e2a36f" />

## Result:
The program successfully fills the first 10 elements of the array with the constant value 5 using the Arrays.fill() method.

## Ex14 Tracking the First Unique Number in a Stream using LinkedHashMap

## AIM:
To implement a program that tracks the first unique (non-repeating) number in a stream of integers using a LinkedHashMap.

## Algorithm:

1.Create a LinkedHashMap<Integer, Integer> to store each number and its frequency.

2.Read a stream of integers from the user (array or until a certain count).

3.For each number, update its frequency in the LinkedHashMap.

4.Traverse the LinkedHashMap entries in insertion order and find the first entry whose frequency is 1.

5.Display the first unique number. If none exists, print "No unique number".

## Program:

```
/*
Program to tracks the first unique (non-repeating) number in a stream of integers using a LinkedHashMap.

*/
import java.util.*;

public class FirstUniqueNumber {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Step 1: LinkedHashMap to maintain insertion order + frequency
        LinkedHashMap<Integer, Integer> map = new LinkedHashMap<>();

        System.out.print("Enter number of elements: ");
        int n = scanner.nextInt();

        System.out.println("Enter " + n + " integers:");

        // Step 2 & 3: Take input & update frequency
        for (int i = 0; i < n; i++) {
            int num = scanner.nextInt();
            map.put(num, map.getOrDefault(num, 0) + 1);
        }

        // Step 4: Find first unique number
        Integer firstUnique = null;

        for (Map.Entry<Integer, Integer> entry : map.entrySet()) {
            if (entry.getValue() == 1) {
                firstUnique = entry.getKey();
                break;
            }
        }

        // Step 5: Output the result
        if (firstUnique != null) {
            System.out.println("First unique (non-repeating) number: " + firstUnique);
        } else {
            System.out.println("No unique number exists.");
        }

        scanner.close();
    }
}
```

## Output:

<img width="767" height="563" alt="image" src="https://github.com/user-attachments/assets/c64e76a4-ba8d-4ab4-b7c9-7a47f5e9176b" />

## Result:
The program successfully tracks and returns the first unique number at any point in the integer stream using a LinkedHashMap.

## Ex15 Value Existence Check in a TreeMap

## AIM:
To write a Java program that checks whether a given value exists in a TreeMap.

## Algorithm:

1.Create a TreeMap<Integer, String> to store key–value pairs in sorted order.

2.Ask the user how many entries they want to insert into the TreeMap.

3.Read keys and values from the user and insert them into the TreeMap.

4.Ask the user for the value they want to search.

5.Use containsValue() to check if the value exists and display the result.

## Program:

```
/*
Program to checks whether a given value exists in a TreeMap.

*/
import java.util.*;

public class TreeMapValueSearch {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Step 1: Create a TreeMap
        TreeMap<Integer, String> map = new TreeMap<>();

        System.out.print("Enter number of entries: ");
        int n = sc.nextInt();
        sc.nextLine(); // consume newline

        // Step 2 & 3: Take key-value pairs from user
        for (int i = 0; i < n; i++) {
            System.out.print("Enter key (integer): ");
            int key = sc.nextInt();
            sc.nextLine();

            System.out.print("Enter value (string): ");
            String value = sc.nextLine();

            map.put(key, value);
        }

        // Step 4: Ask value to search
        System.out.print("\nEnter value to search: ");
        String searchValue = sc.nextLine();

        // Step 5: Check value exists
        if (map.containsValue(searchValue)) {
            System.out.println("Value \"" + searchValue + "\" exists in the TreeMap.");
        } else {
            System.out.println("Value \"" + searchValue + "\" does NOT exist in the TreeMap.");
        }

        sc.close();
    }
}
```
## Output:

<img width="970" height="664" alt="image" src="https://github.com/user-attachments/assets/cdbab398-2834-42ce-9b3e-8d24c188fd1d" />

## Result:
Thus, the program successfully checks whether a specified value exists in a TreeMap using the containsValue() method.
