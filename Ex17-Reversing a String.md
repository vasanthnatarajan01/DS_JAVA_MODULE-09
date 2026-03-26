Skip to content
karthiksaravanan88
DS_JAVA_MODULE-09
Repository navigation
Code
Pull requests
Actions
Projects
Security
Insights
Important update
On April 24 we'll start using GitHub Copilot interaction data for AI model training unless you opt out. Review this update and manage your preferences in your GitHub account settings.
Files
Go to file
t
Ex16-Balanced Parentheses Using Stack.md
Ex17-Reversing a String.md
Ex18-Simulation of a Ticket Counter Using Queue .md
Ex19-Palindrome Check Using Deque.md
Ex20-Merge Sort Algorithm.md
You’re making changes in a project you don’t have write access to. Submitting a change will write it to a new branch in your fork vasanthnatarajan01/DS_JAVA_MODULE-09, so you can send a pull request.
DS_JAVA_MODULE-09
/
Ex17-Reversing a String.md
in
main

Edit

Preview
Indent mode

Spaces
Indent size

4
Line wrap mode

Soft wrap
Editing Ex17-Reversing a String.md file contents
  1
  2
  3
  4
  5
  6
  7
  8
  9
 10
 11
 12
 13
 14
 15
 16
 17
 18
 19
 20
 21
 22
 23
 24
 25
 26
 27
 28
 29
 30
 31
 32
 33
 34
 35
 36
 37
 38
 39
 40
 41
 42
 43
 44
 45
 46
 47
 48
 49
 50
 51
# Ex17 Reversing a String Using Stack Data Structure
## DATE: 03-10-2026
## AIM:
To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm
1. Read the input string from the user.
2. Create a stack and push each character of the string onto it.
3. Create a StringBuilder to build the reversed string.
4. Pop characters from the stack one by one and append them to the StringBuilder.
5. Return and print the final reversed string.

## Program:
```JAVA
/*
Program to reverses an input string using a stack
Developed by: Vasanth N
RegisterNumber: 212224110060
*/
import java.util.Scanner;
import java.util.Stack;

public class ReverseStringWithStack {

    public static String reverseString(String input) {
        //Type code here...
        Stack<Character> stack = new Stack<>();
        for (char ch : input.toCharArray())
        stack.push(ch);
        StringBuilder reversed = new StringBuilder();
        while (!stack.isEmpty())
        reversed.append(stack.pop());
        return reversed.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();

        // Reverse using stack
        String reversed = reverseString(input);

        // Display result
        System.out.println(reversed);

        scanner.close();
    }
}
```
## Output:
<img width="1291" height="285" alt="image" src="https://github.com/user-attachments/assets/1148eae1-6f96-41f6-b360-48f56040a286" />
Use Control + Shift + m to toggle the tab key moving focus. Alternatively, use esc then tab to move to the next interactive element on the page.
No file chosen
Attach files by dragging & dropping, selecting or pasting them.
