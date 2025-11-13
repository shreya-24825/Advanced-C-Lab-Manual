

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void display() {
    struct Node* p = head;
    if (p == NULL) {
        printf("Stack is empty\n");
        return;
    }
    printf("Stack elements:\n");
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}

int main() {
    struct Node* n1 = malloc(sizeof(struct Node));
    struct Node* n2 = malloc(sizeof(struct Node));
    n1->data = 10; n2->data = 20;
    n1->next = n2; n2->next = NULL;
    head = n1;
    display();
    return 0;
}
```

Output:

<img width="521" height="287" alt="image" src="https://github.com/user-attachments/assets/9f82c449-aff5-4a20-8f5d-c879d43208ec" />



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void pop() {
    if (head == NULL) {
        printf("Stack is empty\n");
        return;
    }
    struct Node* temp = head;
    head = head->next;
    printf("Popped element: %d\n", temp->data);
    free(temp);
}

int main() {
    struct Node* n1 = malloc(sizeof(struct Node));
    n1->data = 10;
    n1->next = NULL;
    head = n1;

    pop();
    pop(); // try popping again to test empty stack
    return 0;
}
```

Output:

<img width="520" height="292" alt="image" src="https://github.com/user-attachments/assets/dd837b22-bb34-45a7-a386-d82728d71e0a" />




Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void display() {
    if (front == NULL) {
        printf("Queue is empty\n");
        return;
    }
    struct Node* temp = front;
    printf("Queue elements:\n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node* n1 = malloc(sizeof(struct Node));
    struct Node* n2 = malloc(sizeof(struct Node));
    n1->data = 10; n1->next = n2;
    n2->data = 20; n2->next = NULL;
    front = n1; rear = n2;

    display();
    return 0;
}
```

Output:

<img width="452" height="315" alt="image" src="https://github.com/user-attachments/assets/1275acb5-f70c-47f6-9067-3cda37be73d2" />


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int val) {
    struct Node* p = malloc(sizeof(struct Node));
    p->data = val;
    p->next = NULL;
    if (rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void display() {
    struct Node* temp = front;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    printf("Queue elements:\n");
    display();
    return 0;
}
```

Output:

<img width="407" height="241" alt="image" src="https://github.com/user-attachments/assets/564d96e5-d09f-40ef-8793-b4afef741e2a" />


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int val) {
    struct Node* p = malloc(sizeof(struct Node));
    p->data = val;
    p->next = NULL;
    if (rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void peek() {
    if (front == NULL)
        printf("Queue is empty\n");
    else
        printf("Front element: %d\n", front->data);
}

int main() {
    enqueue(10);
    enqueue(20);
    peek();
    return 0;
}
```

Output:

<img width="431" height="232" alt="image" src="https://github.com/user-attachments/assets/88265f82-4e4a-47e7-872e-1dbaca116c2d" />




Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


