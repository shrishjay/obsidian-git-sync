
#### Understanding the snippet below:

1. An element in a linked list is a _struct Node._ It is made to hold integer _data_ and a pointer of data type _struct Node*,_ as it has to point to another _struct Node._ 

2. We’ll create the below illustrated linked list.

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-14/Image_1.webp)

**Figure 1: Illustration of the below implemented linked list.**

3. We will always create individual nodes and link them to the next node via the arrow operator ‘→’.

4. First, we’ll define a structure _Node_ and create two of its members, an int variable _data,_ to store the current node's value and a struct node* pointer variable _next._ 

5. Now, we can move on to our main() and start creating these nodes. We’ll name the first node, _head._ Define a pointer to head node by _struct node* head._ And similarly for the other nodes. Request the memory location for each of these nodes from heap via malloc using the below snippet.

```c
head = (struct Node *)malloc(sizeof(struct Node));
```

6. Link these nodes using the arrow operator and call the traversal function.

7. Create a void function _linkedlistTraversal_ and pass into it the pointer to the head node.

8. Run a while loop while the pointer doesn’t point to a NULL. And keep changing the pointer _next_ each time you are done printing the data of the current node.

```c
#include <stdio.h>
#include <stdlib.h>
 
struct Node
{
    int data;
    struct Node *next;
};
 
void linkedListTraversal(struct Node *ptr)
{
    while (ptr != NULL)
    {
        printf("Element: %d\n", ptr->data);
        ptr = ptr->next;
    }
}
 
int main()
{
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
 
    linkedListTraversal(head);
    return 0;
}
```

**Code Snippet 1: Creating and traversing in a linked list**

Let’s check if it works all fine. Refer to the output below.

```c
Element: 7
Element: 11
Element: 41
Element: 66
PS D:\MyData\Business\code playground\Ds & Algo with Notes\Code>
```

**Figure 2: Output of the above program**

