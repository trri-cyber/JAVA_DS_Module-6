# EX3 Write a program to count the number of digits in an integer.

## DATE:
10.11.2025  

## AIM:
To write a Java program to count the number of digits in an integer using recursion.

## Algorithm
1. Start the program.  
2. Read an integer from the user.  
3. Define a recursive function `countDigits()` that counts digits by dividing the number by 10 each time.  
4. Base condition: if the number is 0, return 0.  
5. Recursive step: return 1 + countDigits(number / 10).  
6. Display the total count of digits.  
7. Stop the program.  

## Program:
```java
/*
Program to count the number of digits in an integer.
Developed by: Kishore B
RegisterNumber: 212224100032
*/
import java.util.Scanner;

public class CountDigitsRecursive {
    static int countDigits(int n) {
        if (n == 0)
            return 0;
        return 1 + countDigits(n / 10);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter an integer: ");
        int n = sc.nextInt();
        if (n == 0)
            System.out.println("Number of digits: 1");
        else
            System.out.println("Number of digits: " + countDigits(Math.abs(n)));
        sc.close();
    }
}
```
## OUTPUT
<img width="948" height="88" alt="image" src="https://github.com/user-attachments/assets/ad1bdb8c-1d0f-45a6-885f-fe60fd96e5d3" />

## RESULT
Thus, the Java program to count the number of digits in an integer is implemented successfully.
