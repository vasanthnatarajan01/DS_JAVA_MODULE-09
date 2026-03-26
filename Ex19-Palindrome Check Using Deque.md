# Ex19 Palindrome Check Using Deque
## DATE: 03-10-2026
## AIM:
To design a program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm
1. Read the input string and keep only alphanumeric characters, converting them to lowercase to form a cleaned string.
2. Create a deque and insert all characters of the cleaned string into it.
3. While the deque has more than one character, remove one from the front and one from the rear.
4. Compare the two removed characters; if they differ, return false because it is not a palindrome.
5. If all comparisons match, return true and print “Palindrome”; otherwise print “Not a palindrome.”

## Program:
```JAVA
/*
Program to checks whether a given message is a palindrome by removing all non-alphanumeric characters.
Developed by: Vasanth N
RegisterNumber: 212224110060
*/
import java.util.*;

public class PalindromeChecker {
    
    public static boolean isPalindrome(String message) {
        //Type code here...
        StringBuilder cleaned = new StringBuilder();
        for (char c : message.toCharArray()) {
            if (Character.isLetterOrDigit(c)) {
                cleaned.append(Character.toLowerCase(c));
            }
        }

        // Step 2: Use a deque to check palindrome
        Deque<Character> deque = new LinkedList<>();
        for (char c : cleaned.toString().toCharArray()) {
            deque.addLast(c);
        }

        // Step 3: Compare front and rear characters
        while (deque.size() > 1) {
            if (deque.removeFirst() != deque.removeLast()) {
                return false;
            }
        }

        return true;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();

        if (isPalindrome(input)) {
            System.out.println("Palindrome");
        } else {
            System.out.println("Not a palindrome");
        }

        scanner.close();
    }
}

```

## Output:
<img width="1267" height="318" alt="image" src="https://github.com/user-attachments/assets/6e7527fd-49be-430c-a111-5bc63f896c34" />



## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
