![image](https://github.com/user-attachments/assets/e4037b5c-5059-4838-92a4-89ef470f7ac2)EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node
struct Node {
    char data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

// Function to search for a character in the linked list
void search(struct Node* head, char target) {
    int position = 1;
    struct Node* current = head;
    
    while (current != NULL) {
        if (current->data == target) {
            printf("Element '%c' found at position %d.\n", target, position);
            return;
        }
        current = current->next;
        position++;
    }

    printf("Element '%c' not found in the linked list.\n", target);
}

int main() {
    // Creating a sample linked list: A -> B -> C -> D
    struct Node* head = createNode('A');
    head->next = createNode('B');
    head->next->next = createNode('C');
    head->next->next->next = createNode('D');

    char element;
    printf("Enter the character to search in the linked list: ");
    scanf(" %c", &element);

    search(head, element);

    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/93b16ad6-e083-490a-92b6-6315e1455902)
Result:
Thus, the program to search a given element in the given linked list is verified successfully. 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define the node structure
struct Node {
    char data;
    struct Node* next;
};

// Function to insert a node at the end of the list
void insert(struct Node** headRef, char value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (*headRef == NULL) {
        *headRef = newNode;
    } else {
        struct Node* temp = *headRef;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }

    printf("Inserted '%c' into the linked list.\n", value);
}

// Function to display the linked list
void display(struct Node* head) {
    printf("Linked List: ");
    while (head != NULL) {
        printf("%c -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    char ch;
    int choice;

    while (1) {
        printf("\n1. Insert Node\n2. Display List\n3. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter character to insert: ");
                scanf(" %c", &ch);
                insert(&head, ch);
                break;
            case 2:
                display(head);
                break;
            case 3:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice. Try again.\n");
        }
    }

    return 0;
}
```
Output:
![Uploading image.png…]
Result:
Thus, the program to insert a node in a linked list is verified successfully.
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a doubly linked list node
struct Node {
    char data;
    struct Node* prev;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to append a node at the end of the list
void append(struct Node** headRef, char value) {
    struct Node* newNode = createNode(value);
    if (*headRef == NULL) {
        *headRef = newNode;
    } else {
        struct Node* temp = *headRef;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
        newNode->prev = temp;
    }
}

// Function to traverse and display the doubly linked list
void traverse(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%c <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    char ch;
    int choice;

    while (1) {
        printf("\n1. Insert Node\n2. Traverse List\n3. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter character to insert: ");
                scanf(" %c", &ch);
                append(&head, ch);
                break;
            case 2:
                traverse(head);
                break;
            case 3:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice. Try again.\n");
        }
    }

    return 0;
}
```
Output:
Result:
Thus, the program to traverse a doubly linked list is verified successfully. 
EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a doubly linked list node
struct Node {
    char data;
    struct Node* prev;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node at the end
void insertAtEnd(struct Node** headRef, char value) {
    struct Node* newNode = createNode(value);

    if (*headRef == NULL) {
        *headRef = newNode;
        printf("Inserted '%c' as the first node.\n", value);
    } else {
        struct Node* temp = *headRef;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
        newNode->prev = temp;
        printf("Inserted '%c' at the end of the list.\n", value);
    }
}

// Function to display the doubly linked list
void display(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%c <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    char ch;
    int choice;

    while (1) {
        printf("\n1. Insert Element\n2. Display List\n3. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter character to insert: ");
                scanf(" %c", &ch);
                insertAtEnd(&head, ch);
                break;
            case 2:
                display(head);
                break;
            case 3:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice. Try again.\n");
        }
    }

    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/25a74388-16bb-466a-8743-ff678abe5384)
Result:
Thus, the program to insert an element in doubly linked list is verified successfully.
EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST
Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a singly linked list node
struct Node {
    int data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node at the end
void insert(struct Node** headRef, int value) {
    struct Node* newNode = createNode(value);
    if (*headRef == NULL) {
        *headRef = newNode;
    } else {
        struct Node* temp = *headRef;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
}

// Function to delete a node with a given key
void deleteElement(struct Node** headRef, int key) {
    struct Node* temp = *headRef;
    struct Node* prev = NULL;

    // Case 1: List is empty
    if (temp == NULL) {
        printf("List is empty. Cannot delete %d.\n", key);
        return;
    }

    // Case 2: Element is at the head
    if (temp != NULL && temp->data == key) {
        *headRef = temp->next;
        free(temp);
        printf("Element %d deleted from the list.\n", key);
        return;
    }

    // Case 3: Traverse to find the element
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    // If the element is not found
    if (temp == NULL) {
        printf("Element %d not found in the list.\n", key);
        return;
    }

    // Delete the node
    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted from the list.\n", key);
}

// Function to display the linked list
void display(struct Node* head) {
    printf("Linked List: ");
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    int choice, value;

    while (1) {
        printf("\n1. Insert Element\n2. Delete Element\n3. Display List\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                insert(&head, value);
                break;
            case 2:
                printf("Enter value to delete: ");
                scanf("%d", &value);
                deleteElement(&head, value);
                break;
            case 3:
                display(head);
                break;
            case 4:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice.\n");
        }
    }

    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/a75dfbfe-c4ac-467b-9340-c148ecf4725e)
Result:
Thus, the function that deletes a given element from a linked list is verified successfully.
