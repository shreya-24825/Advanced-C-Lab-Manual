EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
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
struct node {
    int data;
    struct node *next;
};

void search(struct node *head, int key) {
    while (head != NULL) {
        if (head->data == key) {
            printf("Element %d found\n", key);
            return;
        }
        head = head->next;
    }
    printf("Element %d not found\n", key);
}

int main() {
    struct node *head = NULL, *n1, *n2, *n3;
    n1 = malloc(sizeof(struct node));
    n2 = malloc(sizeof(struct node));
    n3 = malloc(sizeof(struct node));
    n1->data = 100; n1->next = n2;
    n2->data = 200; n2->next = n3;
    n3->data = 300; n3->next = NULL;
    head = n1;

    search(head, 100);
    return 0;
}
```

Output:

<img width="334" height="152" alt="Screenshot 2025-11-13 165620" src="https://github.com/user-attachments/assets/d5289475-2511-49ce-821c-515f8f71fa40" />




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
struct node {
    int data;
    struct node *next;
};
struct node *head = NULL;

void insert(int value) {
    struct node *newNode = malloc(sizeof(struct node));
    newNode->data = value;
    newNode->next = NULL;
    if (head == NULL)
        head = newNode;
    else {
        struct node *temp = head;
        while (temp->next != NULL)
            temp = temp->next;
        temp->next = newNode;
    }
}

void display() {
    struct node *temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    insert(10);
    insert(20);
    insert(30);
    display();
    return 0;
}
```


Output:

<img width="383" height="174" alt="image" src="https://github.com/user-attachments/assets/a9fb18d0-5370-4340-8599-886c14929739" />


 
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
struct node {
    int data;
    struct node *prev, *next;
};

void traverse(struct node *head) {
    struct node *temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main() {
    struct node *n1, *n2, *n3;
    n1 = malloc(sizeof(struct node));
    n2 = malloc(sizeof(struct node));
    n3 = malloc(sizeof(struct node));
    n1->data = 100; n1->prev = NULL; n1->next = n2;
    n2->data = 200; n2->prev = n1; n2->next = n3;
    n3->data = 300; n3->prev = n2; n3->next = NULL;
    traverse(n1);
    return 0;
}
```

Output:

<img width="301" height="139" alt="image" src="https://github.com/user-attachments/assets/59a9839d-0b5d-48da-b664-13e2442d38f6" />



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
struct node {
    int data;
    struct node *prev, *next;
};
struct node *head = NULL;

void insert(int value) {
    struct node *newNode = malloc(sizeof(struct node));
    newNode->data = value;
    newNode->next = NULL;
    if (head == NULL) {
        newNode->prev = NULL;
        head = newNode;
    } else {
        struct node *temp = head;
        while (temp->next != NULL)
            temp = temp->next;
        temp->next = newNode;
        newNode->prev = temp;
    }
}

void display() {
    struct node *temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main() {
    insert(10);
    insert(20);
    insert(30);
    display();
    return 0;
}
```

Output:

<img width="562" height="214" alt="image" src="https://github.com/user-attachments/assets/883d5bed-932f-400d-9f7a-b497151b7e86" />



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
struct node {
    int data;
    struct node *next;
};
struct node *head = NULL;

void insert(int x) {
    struct node *newNode = malloc(sizeof(struct node));
    newNode->data = x;
    newNode->next = head;
    head = newNode;
}

void delete(int key) {
    struct node *temp = head, *prev = NULL;
    if (temp != NULL && temp->data == key) {
        head = temp->next;
        free(temp);
        return;
    }
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("Element not found\n");
        return;
    }
    prev->next = temp->next;
    free(temp);
}

void display() {
    struct node *temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main() {
    insert(400);
    insert(300);
    insert(200);
    insert(100);
    printf("Before deletion: ");
    display();
    delete(300);
    printf("\nAfter deletion: ");
    display();
    return 0;
}
```

Output:

<img width="364" height="155" alt="image" src="https://github.com/user-attachments/assets/2cf3da05-f87b-4d88-907b-54c94e3de29d" />







Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





