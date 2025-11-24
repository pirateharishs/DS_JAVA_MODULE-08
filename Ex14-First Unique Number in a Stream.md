# Ex14 Tracking the First Unique Number in a Stream using LinkedHashMap
## DATE: 19/09/2025
## AIM:
To implement a program that tracks the first unique (non-repeating) number in a stream of integers using a LinkedHashMap.

## Algorithm
1. Start the program.
2. Create a LinkedHashMap to store integers as keys and their frequency (count) as
 values.
3. Read or define a stream of integers (array of numbers).
4. For each integer in the stream:
    1. If the number is not already in the map, insert it with count = 1.
    2. If it exists, increment its count by 1.
5. After processing each element, find the first number in the LinkedHashMap with count = 1 (the first unique number).
6.  Display the current stream and the first unique number.

## Program:
```java
/*
Program to tracks the first unique (non-repeating) number in a stream of integers using a LinkedHashMap.
Developed by: HARISH S
Register Number: 212223230071
*/

import java.util.*;

public class FirstUniqueNumberStream {

    public static void processStream(int n, Scanner sc) {
        LinkedHashMap<Integer, Integer> freqMap = new LinkedHashMap<>();
        for(int i=0; i<n; i++){
            int current = sc.nextInt();
            
            freqMap.put(current, freqMap.getOrDefault(current, 0)+1);
            
            int fUniq = -1;
            
            for(Map.Entry<Integer, Integer> entry : freqMap.entrySet()){
                if(entry.getValue() == 1){
                    fUniq = entry.getKey();
                    break;
                }
            }
            
            if(fUniq != -1){
                System.out.println("First unique number: "+fUniq);
            }else{
                System.out.println("No unique number");
            }
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        processStream(n, sc);
        sc.close();
    }
}

```

## Output:
<img width="767" height="563" alt="image" src="https://github.com/user-attachments/assets/c64e76a4-ba8d-4ab4-b7c9-7a47f5e9176b" />

## Result:
The program successfully tracks and returns the first unique number at any point in the integer stream using a LinkedHashMap.
