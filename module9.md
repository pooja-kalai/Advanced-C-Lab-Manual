EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
```
#include <stdio.h>
#define MAX 100

int stack[MAX];
int top = -1;

// Function to display stack elements
void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}

// Function to push an element into stack
void push(int val) {
    if (top == MAX - 1) {
        printf("Stack overflow.\n");
    } else {
        top++;
        stack[top] = val;
        printf("%d pushed to stack.\n", val);
    }
}

// Function to pop an element from stack
void pop() {
    if (top == -1) {
        printf("Stack underflow.\n");
    } else {
        printf("%d popped from stack.\n", stack[top]);
        top--;
    }
}

int main() {
    int choice, value;

    while (1) {
        printf("\n--- Stack Menu ---\n");
        printf("1. Push\n2. Pop\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter the value to push: ");
                scanf("%d", &value);
                push(value);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice.\n");
        }
    }
}
```
Output:![image](https://github.com/user-attachments/assets/89b326ec-7269-45dc-9db3-f23fdae5c7de)

Result:
Thus, the program to display stack elements using an array is verified successfully.
EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
```
#include <stdio.h>
#define MAX 100

// Global declarations
float stack[MAX];
int top = -1;

// Function to push a float value into the stack
void push(float val) {
    if (top == MAX - 1) {
        printf("Stack Overflow: Cannot push %.2f\n", val);
    } else {
        top++;
        stack[top] = val;
        printf("%.2f pushed into the stack.\n", val);
    }
}

int main() {
    float value;
    int choice;

    while (1) {
        printf("\n--- Stack Push Operation ---\n");
        printf("1. Push Element\n2. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter the float value to push: ");
                scanf("%f", &value);
                push(value);
                break;
            case 2:
                return 0;
            default:
                printf("Invalid choice.\n");
        }
    }

    return 0;
}

```
Output:
![image](https://github.com/user-attachments/assets/65805272-f503-4858-a3c0-932f4aa41ae9)


Result:
Thus, the program to push the given element in to a stack using array is verified successfully
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
```
#include <stdio.h>
#define MAX 100

int queue[MAX];
int front = -1, rear = -1;

// Function to display queue elements
void display() {
    if (front == -1) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements are:\n");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

// Enqueue operation
void enqueue(int val) {
    if (rear == MAX - 1) {
        printf("Queue Overflow.\n");
    } else {
        if (front == -1) front = 0;
        rear++;
        queue[rear] = val;
        printf("%d enqueued to queue.\n", val);
    }
}

// Dequeue operation
void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue Underflow.\n");
    } else {
        printf("%d dequeued from queue.\n", queue[front]);
        front++;
    }
}

int main() {
    int choice, value;

    while (1) {
        printf("\n--- Queue Menu ---\n");
        printf("1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                dequeue();
                break;
            case 3:
                display();
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice.\n");
        }
    }
}

```
Output:
![image](https://github.com/user-attachments/assets/0eec983e-b84e-4999-9789-dcf48d84b7b8)
Result:
Thus, the program to display queue elements using array is verified successfully. 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
```#include <stdio.h>
#define MAX 100

// Global declarations
float queue[MAX];
int front = -1, rear = -1;

// Enqueue function to add a float to the queue
void enqueue(float value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow. Cannot insert %.2f\n", value);
    } else {
        if (front == -1) front = 0;
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into the queue.\n", value);
    }
}

int main() {
    int choice;
    float value;

    while (1) {
        printf("\n--- Queue Menu ---\n");
        printf("1. Insert (Enqueue)\n");
        printf("2. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter float value to insert: ");
                scanf("%f", &value);
                enqueue(value);
                break;
            case 2:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice. Please enter 1 or 2.\n");
        }
    }

    return 0;
}
Output:
![image](https://github.com/user-attachments/assets/d0871d4c-93a7-4dd8-8f3e-ba2488416228)
Result:
Thus, the program to insert elements in queue using array is verified successfully.
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY
Aim:
To create a function in C that deletes an element from a queue implemented using an array.
Algorithm:
1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:
```
#include <stdio.h>
#define MAX 100

// Global declarations
int queue[MAX];
int front = -1, rear = -1;

// Function to delete an element from the queue
void dequeue() {
    if (front == -1) {
        // Queue is empty
        printf("Queue Underflow: The queue is empty. No elements to delete.\n");
    } else {
        // Deleting the front element
        printf("Element %d dequeued from the queue.\n", queue[front]);
        front++;
        
        // Check if the queue is now empty
        if (front > rear) {
            front = rear = -1;
            printf("Queue is now empty.\n");
        }
    }
}

int main() {
    int choice;
    while (1) {
        printf("\n--- Queue Menu ---\n");
        printf("1. Delete (Dequeue)\n");
        printf("2. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                dequeue();
                break;
            case 2:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice. Please enter 1 or 2.\n");
        }
    }

    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/80cd8b68-55bf-4da5-8fa2-eac306dc5e0f)
Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
