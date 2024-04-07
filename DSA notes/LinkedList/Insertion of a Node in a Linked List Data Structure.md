	To insert an element in a linked list the following steps can be done:

1. A void has to be made to insert an element.
2. Creating a void causes the rest of the elements to shift to their adjacent right.
3. Time complexity: O(no. of elements shifted)

**Inserting in a linked list:**

Consider the following Linked List,

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-15/Image_1.webp)

Insertion in this list can be divided into the following categories:

**Case 1**: Insert at the beginning

**Case 2**: Insert in between

**Case 3**: Insert at the end

**Case 4**: Insert after the node

For insertion following any of the above-mentioned cases, we would first need to create that extra node. And then, we overwrite the current connection and make new connections. And that is how we insert a new node at our desired place.

**Syntax for creating a node:**

```c
struct Node *ptr = (struct Node*) malloc (sizeof (struct Node))
```

The above syntax will create a node, and the next thing one would need to do is set the data for this node.

```c
ptr -> data = 9 
```

This will set the data.

Now, let's begin with each of these cases of insertion.

**Case 1: Insert at the beginning**

In order to insert the new node at the beginning, we would need to have the head pointer pointing to this new node and the new node’s pointer to the current head.

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-15/Image_2.webp)

**Case 2: Insert in between:**

Assuming index starts from 0, we can insert an element at index i>0 as follows:

1. Bring a temporary pointer p pointing to the node before the element you want to insert in the linked list.
2. Since we want to insert between 8 and 2, we bring pointer p to 8.

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-15/Image_3.webp)

**Case 3: Insert at the end:**

In order to insert an element at the end of the linked list, we bring a temporary pointer to the last element.

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-15/Image_4.webp)

**Case 4: Insert after a node:**

Similar to the other cases, ptr can be inserted after a node as follows:

ptr->next = prevNode-> next;

prevNode-> next = ptr;

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-15/Image_5.webp)

Summarizing, inserting at the beginning has the time complexity O(1), and inserting at some node in between puts the time complexity O(n) since we have to go through the list to reach that particular node. Inserting at the end has the same time complexity O(n) as that of inserting in between. But if we are given the pointer to the previous node where we want to insert the new node, it would just take a constant time O(1). 

#### Insertion at the beginning:

1. Create a struct Node* function _insertAtFirst_ which will return the pointer to the new head.
2. We’ll pass the current head pointer and the data to insert at the beginning, in the function.
3. Create a new struct Node* pointer _ptr_, and assign it a new memory location in the heap.
4. Assign head to the next member of the ptr structure using ptr-> next = head, and the given data to its data member.
5. Return this pointer __ptr.
6. 
    #### Understanding the snippet below:
    
1. So, the first thing would be to create a struct _Node._ This is a known thing to us. We have covered this in our traversal video.
2. Create the _linkedlistTraversal_ function. Earlier tutorials can be referred to.
3. Do include the header file <stdlib.h>, since we’ll be using malloc to reserve memory locations.
4. As we did last time, create the same four nodes, the first node being the _head._ Define a pointer to head node by _struct node* head._ And similarly for the other nodes. Request the memory location for each of these nodes from the heap via malloc. Link these nodes using the arrow operator.
5. Now that we have created a linked list, we can create functions according to the different cases.
    
    ```c
    // Case 1
    struct Node * insertAtFirst(struct Node *head, int data){
        struct Node * ptr = (struct Node *) malloc(sizeof(struct Node));
        ptr->data = data;
     
        ptr->next = head;
        return ptr; 
    }
    ```
    
    _**Code Snippet 1: Implementing** **insertAtFirst****.**_
    
#### Insertion in between:

1. Create a struct Node* function _insertAtIndex_ which will return the pointer to the head.
2. We’ll pass the current head pointer and the data to insert and the index where it will get inserted, in the function.
3. Create a new struct Node* pointer _ptr_, and assign it a new memory location in the heap.
4. Create a new struct Node* pointer pointing to _head_, and run a loop until this pointer reaches the index, where we are inserting a new node.
5. Assign p->next to the next member of the ptr structure using ptr-> next = p->next, and the given data to its data member.
6. Break the connection between p and p->next by assigning p->next the new pointer. That is, p->next = ptr.
7. Return head.

```c
// Case 2
struct Node * insertAtIndex(struct Node *head, int data, int index){
    struct Node * ptr = (struct Node *) malloc(sizeof(struct Node));
    struct Node * p = head;
    int i = 0;
 
    while (i!=index-1)
    {
        p = p->next;
        i++;
    }
    ptr->data = data;
    ptr->next = p->next;
    p->next = ptr;
    return head;
}
```

_**Code Snippet 2: Implementing** **insertAtIndex****.**_

#### Insertion at the end:

1. Inserting at the end is very similar to inserting at any index. The difference holds in the limit of the while loop. Here we run a loop until the pointer reaches the end and points to NULL.
2. Assign NULL to the next member of the new ptr structure using ptr-> next = NULL, and the given data to its data member.
3. Break the connection between p and NULL by assigning p->next the new pointer. That is, p->next = ptr.
4. Return head.  
    
```c
// Case 3
struct Node * insertAtEnd(struct Node *head, int data){
    struct Node * ptr = (struct Node *) malloc(sizeof(struct Node));
    ptr->data = data;
    struct Node * p = head;
 
    while(p->next!=NULL){
        p = p->next;
    }
    p->next = ptr;
    ptr->next = NULL;
    return head;
}
```

_**Code Snippet 3: Implementing** **insertAtEnd****.**_

#### Insertion after a given node:

1. Here, we already have a struct Node* pointer to insert the new node just next to it.
2. Create a struct Node* function _insertAfterNode_ which will return the pointer to the head.
3. Pass into this function, the head node, the previous node, and the data.
4. Create a new struct Node* pointer _ptr_, and assign it a new memory location in the heap.
5. Since we already have a struct Node* _prevNode_ given as a parameter, use it as p we had in the previous functions.
6. Assign prevNode->next to the next member of the ptr structure using ptr-> next = prevNode->next, and the given data to its data member.
7. Break the connection between prevNode and prevNode->next by assigning prevNode->next the new pointer. That is, prevNode->next = ptr.
8. Return head.  
    
    ```c
    // Case 4
    struct Node * insertAfterNode(struct Node *head, struct Node *prevNode, int data){
        struct Node * ptr = (struct Node *) malloc(sizeof(struct Node));
        ptr->data = data;
     
        ptr->next = prevNode->next;
        prevNode->next = ptr;
     
        return head;
    }
    ```
    
    **Code Snippet 4: Implementing** **_insertAfterNode_****.**
    
So those were the cases we had in insertion. Below is the whole source code.

```c
#include<stdio.h>
#include<stdlib.h>

struct Node{
    int data;
    struct Node * next;
};

void linkedListTraversal(struct Node *ptr)
{
    while (ptr != NULL)
    {
        printf("Element: %d\n", ptr->data);
        ptr = ptr->next;
    }
}

// Case 1
struct Node * insertAtFirst(struct Node *head, int data){
    struct Node * ptr = (struct Node *) malloc(sizeof(struct Node));
    ptr->data = data;

    ptr->next = head;
    return ptr; 
}

// Case 2
struct Node * insertAtIndex(struct Node *head, int data, int index){
    struct Node * ptr = (struct Node *) malloc(sizeof(struct Node));
    struct Node * p = head;
    int i = 0;

    while (i!=index-1)
    {
        p = p->next;
        i++;
    }
    ptr->data = data;
    ptr->next = p->next;
    p->next = ptr;
    return head;
}

// Case 3
struct Node * insertAtEnd(struct Node *head, int data){
    struct Node * ptr = (struct Node *) malloc(sizeof(struct Node));
    ptr->data = data;
    struct Node * p = head;

    while(p->next!=NULL){
        p = p->next;
    }
    p->next = ptr;
    ptr->next = NULL;
    return head;
}

// Case 4
struct Node * insertAfterNode(struct Node *head, struct Node *prevNode, int data){
    struct Node * ptr = (struct Node *) malloc(sizeof(struct Node));
    ptr->data = data;

    ptr->next = prevNode->next;
    prevNode->next = ptr;

    
    return head;
}


int main(){
    struct Node *head;
    struct Node *second;
    struct Node *third;
    struct Node *fourth;

    // Allocate memory for nodes in the linked list in Heap
    head = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));
    fourth = (struct Node *)malloc(sizeof(struct Node));

    // Link first and second nodes
    head->data = 7;
    head->next = second;

    // Link second and third nodes
    second->data = 11;
    second->next = third;

    // Link third and fourth nodes
    third->data = 41;
    third->next = fourth;

    // Terminate the list at the third node
    fourth->data = 66;
    fourth->next = NULL;

    printf("Linked list before insertion\n");
    linkedListTraversal(head);
    // head = insertAtFirst(head, 56);
    // head = insertAtIndex(head, 56, 1);
    // head = insertAtEnd(head, 56);
    head = insertAfterNode(head, third, 45);
    printf("\nLinked list after insertion\n");
    linkedListTraversal(head);

    
    return 0;
}
```
