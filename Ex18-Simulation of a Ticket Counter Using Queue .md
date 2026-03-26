# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)
## DATE: 03-10-2026
## AIM:
To simulate the functioning of a ticket counter that operates on a First-In-First-Out (FIFO) basis using a queue implemented via a linked list in Java.
## Algorithm
1. Initialize an empty queue with front and rear pointers set to null.
2. For enqueue, create a new node; if the queue is empty, set both front and rear to it, otherwise link it to the end and update rear.
3. For dequeue, check if the queue is empty; if not, print and remove the front element, and update rear to null if the queue becomes empty.
4. For display, traverse from front to rear and print each customer name in order.
5. Continuously read commands (enqueue, dequeue, display, exit) and perform the corresponding queue operations.

## Program:
```JAVA
/*
Program to functioning of a ticket counter that operates on a First-In-First-Out (FIFO)
Developed by: Vasanth N
RegisterNumber: 212224110060
*/
import java.util.Scanner;

class Node {
    String customerName;
    Node next;

    public Node(String name) {
        this.customerName = name;
        this.next = null;
    }
}

class TicketQueue {
    private Node front;
    private Node rear;

    public TicketQueue() {
        this.front = this.rear = null;
    }

    public void enqueue(String customerName) {
        //Type code here...
        Node newNode = new Node(customerName);
        if (rear == null) {
            front = rear = newNode;
            return;
        }
        rear.next = newNode;
        rear = newNode;
    }

    public void dequeue() {
        //Type code here...
        if (front == null) {
            System.out.println("Queue is empty. No customer to serve.");
            return;
        }
        System.out.println("Serving customer: " + front.customerName);
        front = front.next;
        if (front == null) {
            rear = null;
        }
    }

    public void displayQueue() {
        //Type code here...
        if (front == null) {
            System.out.println("Queue is empty.");
            return;
        }
        System.out.print("Queue: ");
        Node temp = front;
        while (temp != null) {
            System.out.print(temp.customerName);
            if (temp.next != null) System.out.print(" -> ");
            temp = temp.next;
        }
        System.out.println();
    }
}

public class TicketCounter {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        TicketQueue queue = new TicketQueue();
        String command;
        
        while (true) {

            // Fix for NoSuchElementException
            if (!scanner.hasNextLine()) {
                //System.out.println("No more input. Exiting simulation.");
                break;
            }

            command = scanner.nextLine().trim();
            if (command.isEmpty()) continue;

            String[] parts = command.split(" ");

            switch (parts[0]) {
                case "enqueue":
                    if (parts.length >= 2) {
                        queue.enqueue(parts[1]);
                    } else {
                        System.out.println("Please provide a customer name.");
                    }
                    break;
                case "dequeue":
                    queue.dequeue();
                    break;
                case "display":
                    queue.displayQueue();
                    break;
                case "exit":
                    System.out.println("Exiting simulation.");
                    scanner.close();
                    return;
                default:
                    System.out.println("Invalid command.");
            }
        }

        scanner.close(); // Safe close
    }
}

```

## Output:
<img width="1322" height="709" alt="image" src="https://github.com/user-attachments/assets/f40f832b-87d0-48de-a57d-e8345b2818da" />



## Result:
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.
