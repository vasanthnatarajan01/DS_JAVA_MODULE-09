# Ex16 Check for Balanced Parentheses Using Stack
## DATE: 03-10-2026
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm
1. Read the input expression as a string.
2. Create a stack with capacity equal to the length of the string to store opening brackets.
3. Traverse each character: push it if it is an opening bracket; if it is a closing bracket, check if the stack is empty or if the popped bracket does not match.
4. If any mismatch occurs or a closing bracket appears when the stack is empty, return false.
5. After processing all characters, return true only if the stack is empty, indicating balanced brackets.


## Program:
```JAVA
/*
Program to verify whether the parentheses (brackets) in an input string are balanced
Developed by: Vasanth N
RegisterNumber: 212224110060
*/
import java.util.Scanner;

public class ParenChecker {
    //Type code here...
    static class ArrayStack {
        private char[] data;
        private int top;

        public ArrayStack(int capacity) {
            data = new char[capacity];
            top = -1;
        }

        public boolean isEmpty() { return top == -1; }
        public boolean isFull() { return top == data.length - 1; }

        public void push(char c) {
            if (isFull()) throw new RuntimeException("Stack overflow");
            data[++top] = c;
        }
        public char pop() {
            if (isEmpty()) throw new RuntimeException("Stack underflow");
            return data[top--];
        }
        public char peek() {
            if (isEmpty()) throw new RuntimeException("Stack is empty");
            return data[top];
        }
    }

    // Checks if expr has balanced brackets
    public static boolean isBalanced(String expr) {
        ArrayStack st = new ArrayStack(expr.length());
        for (char ch : expr.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                st.push(ch);
            } else if (ch == ')' || ch == '}' || ch == ']') {
                if (st.isEmpty()) return false;
                char top = st.pop();
                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }
        return st.isEmpty();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String expr = sc.nextLine();
        boolean ok = isBalanced(expr);
        System.out.println(ok);
        sc.close();
    }
}

```

## Output:
<img width="1293" height="290" alt="image" src="https://github.com/user-attachments/assets/72131d5a-e46d-48cb-a4f3-d3a7ee75ad80" />



## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
