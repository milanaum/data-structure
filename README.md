# Data Structure
1.Array using binary search
***********************************
#include <stdio.h> <br>
int main() <br>
{ <br>
  int c, first, last, middle, n, search, array[100]; <br>
  printf("Enter number of elements\n"); <br>
  scanf("%d", &n); <br>
  printf("Enter %d integers\n", n); <br>
  for (c = 0; c < n; c++) <br>
    scanf("%d", &array[c]); <br>
  printf("Enter value to find\n"); <br>
  scanf("%d", &search); <br>
  first = 0; <br>
  last = n - 1; <br>
  middle = (first+last)/2; <br>
  while (first <= last) <br>
  { <br> 
   if (array[middle] < search) <br>
   first = middle + 1; <br>
  else if (array[middle] == search) <br>
  { <br>
  printf("%d found at location %d.\n", search, middle+1); <br>
  break; <br>
  } <br>
  else <br>
  last = middle - 1; <br>
  middle = (first + last)/2; <br>
  } <br>
  if (first > last) <br>
  printf("Not found! %d isn't present in the list.\n", search); <br>
 return 0; <br>
} <br>
OUTPUT: <br>
![image](https://user-images.githubusercontent.com/97940333/154896970-ac2b1d40-dd79-443c-a62e-58e2fa0a6530.png)


****************************************************************************************************************************************
2.Write a c++ program to implement insertion and deletion node in a rear position of linked list. <br>
******************************************************************************************************************************************
#include<bits/stdc++.h> <br>
using namespace std; <br>
struct Node <br>
{ <br>
int data; <br>
struct Node *next; <br>
}; <br>
void Insert(struct Node **head,int position,int x) <br>
{ <br>
struct Node *p,*q,*newNode; <br>
newNode=new Node(); <br>
newNode->data=x; <br>
p=*head; <br>
if(position==1) <br>
{ <br>
 newNode->next=p; <br>
*head=newNode; <br>
return; <br>
} <br>
else <br>
{ <br>
int k=1; v
while(p!=NULL && k<position) <br>
{ <br>
k++; <br>
q=p; <br>
p=p->next; <br>
} <br>
q->next=newNode; <br>
newNode->next=p; <br>
} <br>
} <br>
void Delete(struct Node **head,int position) <br>
{ <br>
struct Node *p,*q; <br>
p=*head; <br>
if(*head==NULL) <br>
{ <br>
cout<<"List empty!!\n"; <br>
return; <br>
} <br>

 if(position==1) <br>
 { <br>
*head=(*head)->next; <br>
free(p); <br>
return; <br>
} <br>
else <br>
{ <br>
int k=1; <br>
while(p!=NULL && k<position) <br>
{ <br>
 k++; <br>
q=p; <br>
p=p->next; <br>
} <br>
if(p==NULL) <br>
{ <br>
 cout<<"Position not found!!\n"; <br>
return; <br>
} <br>
else <br>
{ <br>
q->next=p->next; <br>
delete(p); <br>
} <br>
} <br>
} <br>
void Print(struct Node **head) <br>
{ <br>
struct Node *p=*head; <br>
while(p) <br>
{ <br>
cout<<p->data<<" "; <br> 
*p=p->next;  <br>
} <br>
cout<<"\n"; <br>
} <br>
int main()  <br>
{ <br>
struct Node *head=NULL; <br>
Insert(&head,1,5); <br>
Insert(&head,1,4); <br>
Insert(&head,3,3); <br>
Insert(&head,2,2); <br>
Insert(&head,2,1); <br>
Print(&head); <br>

Delete(&head,1); <br>
Print(&head); <br>
Delete(&head,4); <br>
Print(&head); <br>
Delete(&head,4); <br>
Print(&head); <br>
} <br>
  OUTPUT: <br>
  ![image](https://user-images.githubusercontent.com/97940333/155066987-2c873ab1-1274-486b-8b2b-2e3bfa58dea3.png)

  ****************************************************************************************************************************************
  3. To implement minimum heap. <br>
  ****************************************************************************************************************************************
  #include <iostream> <br>
#include <conio.h> <br>
using namespace std; <br>
void min_heap(int *a, int m, int n) <br>
{ <br>
   int j, t; <br>
   t= a[m]; <br>
   j = 2 * m; <br>
   while (j <= n) <br>
  { <br>
      if (j < n && a[j+1] < a[j]) <br>
         j = j + 1; <br>
      if (t < a[j]) <br>
         break; <br>
      else if (t >= a[j]) <br>
	  { <br>
         a[j/2] = a[j]; <br>
         j = 2 * j; <br>
      } <br>
   } <br>
   a[j/2] = t;  <br>
   return;  <br>
} <br>
void build_minheap(int *a, int n)  <br>
{ <br>
   int k; <br>
   for(k = n/2; k >= 1; k--)  <br>
   { <br>
      min_heap(a,k,n); <br>
   } <br>
} <br>
int main() <br>
 { <br>
   int n, i; <br>
   cout<<"enter no of elements of array\n"; <br>
   cin>>n;  <br>
   int a[30];  <br>
   for (i = 1; i <= n; i++)  <br>
    {  <br>
      cout<<"enter element"<<" "<<(i)<<endl;  <br>
      cin>>a[i];  <br>
   }  <br>
   build_minheap(a, n);  <br>
   cout<<"Min Heap\n";  <br>
   for (i = 1; i <= n; i++)  <br>
    {  <br>
      cout<<a[i]<<endl;  <br>
   }  <br>
   getch();  <br>
}  <br>
  OUTPUT:  <br>
  ![image](https://user-images.githubusercontent.com/97940333/156971371-19daacaf-b12c-4433-bcef-495e4b3f3560.png)
	

	
************************************************************************************************************************************************************
5. To implemnet heap sort. <br>
****************************************************************************************************************************************************************
#include <iostream> <br>
using namespace std; <br>
void max_heap(int *a, int m, int n)  <br>
{ <br>
   int j, t; <br>
   t = a[m]; <br>
   j = 2 * m; <br>
   while (j <= n)  <br>
   { <br>
      if (j < n && a[j+1] > a[j]) <br>
         j = j + 1; <br>
      if (t > a[j]) <br>
         break; <br>
      else if (t <= a[j]) <br>
	   { <br>
         a[j / 2] = a[j]; <br>
         j = 2 * j; <br>
      } <br>
   } <br>
   a[j/2] = t; <br>
   return; <br>
} <br>
void build_maxheap(int *a,int n) <br>
 { <br>
   int k; <br>
   for(k = n/2; k >= 1; k--)  <br>
   { <br>
      max_heap(a,k,n); <br>
   } <br>
} <br>
int main() <br>
 { <br>
   int n, i; <br>
   cout<<"enter no of elements of array\n"; <br>
   cin>>n; <br>
   int a[30]; <br>
   for (i = 1; i <= n; i++) <br>
    { <br>
      cout<<"enter elements"<<" "<<(i)<<endl; <br>
      cin>>a[i]; <br>
   } <br>
   build_maxheap(a,n); <br>
   cout<<"Max Heap\n"; <br>
   for (i = 1; i <= n; i++)  <br>
   { <br>
      cout<<a[i]<<endl; <br>
   } <br>
} <br>
	OUTPUT: <br>
	![image](https://user-images.githubusercontent.com/97940333/156981083-5b988011-39a5-4e1b-b430-ec625d22f2f4.png)
	
********************************************************************************************************************************************************
6. Array using linked list. <br>
********************************************************************************************************************************************************
#include <iostream> <br>
using namespace std; <br>
struct info { <br>
    int data; <br>
    info* next; <br>
}; <br>
int main() <br>
{ <br>
    int size = 10; <br>
    info** head; <br>
    head = new info*[size]; <br>
    for (int i = 0; i < size; ++i) { <br>
        *(head + i) = NULL; <br>
    } <br>
    for (int i = 0; i < size; ++i) { <br>
        info* prev = NULL; <br>
        int s = 4; <br>
  
    while (s--) { <br>
   info* n = new info; <br>
   n->data = i * s; <br>
   n->next = NULL; <br>
   if (*(head + i) == NULL) { <br>
   *(head + i) = n; <br>
   } <br>
   else { <br>
   prev->next = n; <br>
   } <br>
  prev = n; <br>
  } <br>
  } <br>
   for (int i = 0; i < size; ++i) { <br>
   info* temp = *(head + i); <br>
  cout << i << "-->\t"; <br>
  while (temp != NULL) { <br>
  cout << temp->data << " "; <br>
  temp = temp->next; <br>
  } <br>
  
cout << '\n'; <br>
} <br>
  
return 0; <br>
} <br>
	OUTPUT: <br>
	![image](https://user-images.githubusercontent.com/97940333/157170115-027e7e34-a543-45d8-bfec-59783d307a1f.png)

********************************************************************************************************************************
7. TO implement using binary tree search. <br>
********************************************************************************************************************************
# include <iostream> <br>
# include <cstdlib> <br>
using namespace std; <br>
struct node <br>
{ <br>
 int info; <br>
 struct node *left;<br> 
 struct node *right; <br>
}*root; <br>
class BST <br>
{ <br>
 public: <br>
 void find(int, node **, node **); <br>
 void insert(node *, node *); <br>
 void del(int); <br>
 void case_a(node *,node *); <br>
 void case_b(node *,node *); <br>
 void case_c(node *,node *); <br>
 void preorder(node *); <br>
 void inorder(node *); <br>
 void postorder(node *); <br>
 void display(node *, int); <br>
 BST() <br>
 { <br>
 root = NULL; <br>
 } <br>
}; <br>
int main() <br>
{ <br>
 int choice, num; <br>
 BST bst; <br>
 node *temp; <br>
 while (1) <br>
 { <br>
 cout<<"-----------------"<<endl; <br>
 cout<<"Operations on BST"<<endl; <br>
 cout<<"-----------------"<<endl; <br>
 cout<<"1.Insert Element "<<endl; <br>
 cout<<"2.Delete Element "<<endl; <br>
 cout<<"3.Inorder Traversal"<<endl; <br>
 cout<<"4.Preorder Traversal"<<endl; <br>
 cout<<"5.Postorder Traversal"<<endl; <br>
 cout<<"6.Display"<<endl; <br>
 cout<<"7.Quit"<<endl; <br>
 cout<<"Enter your choice : "; <br>
 cin>>choice; <br>
 switch(choice) <br>
 { <br>
 case 1: <br> 
 temp = new node; <br>
 cout<<"Enter the number to be inserted : "; <br>
 cin>>temp->info; <br>
 bst.insert(root, temp); <br>
 break; <br>
 case 2: <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty, nothing to delete"<<endl; <br>
 continue; <br>
 } <br>
 cout<<"Enter the number to be deleted : "; <br>
 cin>>num; <br>
 bst.del(num); <br>
 break; <br>
 case 3: <br>
 cout<<"Inorder Traversal of BST:"<<endl; <br>
 bst.inorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 4: <br>
 cout<<"Preorder Traversal of BST:"<<endl; <br>
 bst.preorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 5: <br>
 cout<<"Postorder Traversal of BST:"<<endl; <br>
 bst.postorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 6: <br>
 cout<<"Display BST:"<<endl; <br>
 bst.display(root,1); <br>
 cout<<endl; <br>
 break; <br>
 case 7: <br>
 exit(1); <br>
 default: <br>
 cout<<"Wrong choice"<<endl; <br>
 } <br>
 } <br>
} <br>
void BST::find(int item, node **par, node **loc) <br>
{ <br>
 node *ptr, *ptrsave; <br>
 if (root == NULL) <br>
 { <br>
 *loc = NULL; <br>
 *par = NULL; <br>
 return; <br>
 } <br>
 if (item == root->info) <br>
 { <br>
 *loc = root; <br>
 *par = NULL; <br>
 return; <br>
 } <br>
 if (item < root->info) <br>
 ptr = root->left; <br>
 else <br>
 ptr = root->right; <br>
 ptrsave = root; <br>
 while (ptr != NULL) <br>
 { <br>
 if (item == ptr->info) <br>
 { <br>
 *loc = ptr; <br>
 *par = ptrsave; <br>
 return; <br>
 } <br>
 ptrsave = ptr; <br>
 if (item < ptr->info) <br>
 ptr = ptr->left; <br>
 else <br>
 ptr = ptr->right; <br>
 } <br>
 *loc = NULL; <br>
 *par = ptrsave; <br>
} <br>

void BST::insert(node *tree, node *newnode) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 root = new node; <br>
 root->info = newnode->info; <br>
 root->left = NULL; <br>
 root->right = NULL; <br>
 cout<<"Root Node is Added"<<endl; <br>
 return; <br>
 } <br>
 if (tree->info == newnode->info) <br>
 { <br>
 cout<<"Element already in the tree"<<endl; <br>
 return; <br>
 } <br>
 if (tree->info > newnode->info) <br>
 { <br>
 if (tree->left != NULL) <br>
 { <br>
 insert(tree->left, newnode); <br>
 } <br>
 else <br>
 { <br>
 tree->left = newnode; <br>
 (tree->left)->left = NULL; <br>
 (tree->left)->right = NULL; <br>
 cout<<"Node Added To Left"<<endl; <br>
 return; <br>
 } <br>
 } <br>
 else <br>
 { <br>
 if (tree->right != NULL) <br>
 { <br>
 insert(tree->right, newnode); <br>
 } <br>
 else <br>
 { <br>
 tree->right = newnode; <br>
 (tree->right)->left = NULL; <br>
 (tree->right)->right = NULL; <br>
 cout<<"Node Added To Right"<<endl; <br>
 return; <br>
 } <br>
 } <br>
} <br>

void BST::del(int item) <br>
{ <br>
 node *parent, *location; <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree empty"<<endl; <br>
 return; <br>
 } <br>
 find(item, &parent, &location); <br>
 if (location == NULL) <br>
 { <br>
 cout<<"Item not present in tree"<<endl; <br>
 return; <br>
 } <br>
 if (location->left == NULL && location->right == NULL) <br>
 case_a(parent, location); <br>
 if (location->left != NULL && location->right == NULL) <br>
 case_b(parent, location); <br>
 if (location->left == NULL && location->right != NULL) <br>
 case_b(parent, location); <br>
 if (location->left != NULL && location->right != NULL) <br>
 case_c(parent, location); <br>
 free(location); <br>
} <br>
 

void BST::case_a(node *par, node *loc ) <br>
{ <br>
 if (par == NULL) <br>
 { <br>
 root = NULL; <br>
 } <br>
 else <br>
 { <br>
 if (loc == par->left) <br>
 par->left = NULL; <br>
 else <br>
 par->right = NULL; <br>
 } <br>
} <br>
 

void BST::case_b(node *par, node *loc) <br>
{ <br>
 node *child; <br>
 if (loc->left != NULL) <br>
 child = loc->left; <br>
 else <br>
 child = loc->right; <br>
 if (par == NULL) <br>
 { <br>
 root = child; <br>
 } <br>
 else <br>
 { <br>
 if (loc == par->left) <br>
 par->left = child; <br>
 else <br>
 par->right = child; <br>
 } <br>
} <br>
 

void BST::case_c(node *par, node *loc) <br>
{ <br>
 node *ptr, *ptrsave, *suc, *parsuc; <br>
 ptrsave = loc; <br>
 ptr = loc->right; <br>
 while (ptr->left != NULL) <br>
 { <br>
 ptrsave = ptr; <br>
 ptr = ptr->left; <br>
 } <br>
 suc = ptr; <br>
 parsuc = ptrsave; <br>
 if (suc->left == NULL && suc->right == NULL) <br>
 case_a(parsuc, suc); <br>
 else <br>
 case_b(parsuc, suc); <br>
 if (par == NULL) <br>
 { <br>
 root = suc; <br>
 } <br>
 else <br>
 { <br>
 if (loc == par->left) <br>
 par->left = suc; <br>
 else <br>
 par->right = suc; <br>
 } <br>
 suc->left = loc->left; <br>
 suc->right = loc->right; <br>
} <br>
 
 
void BST::preorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty"<<endl; <br>
 return; <br>
 } <br>
 if (ptr != NULL) <br>
 { <br>
 cout<<ptr->info<<" "; <br>
 preorder(ptr->left); <br>
 preorder(ptr->right); <br>
 } <br>
} <br>

void BST::inorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty"<<endl; <br>
 return; <br>
 } <br>
 if (ptr != NULL) <br>
 { <br>
 inorder(ptr->left); <br>
 cout<<ptr->info<<" "; <br>
 inorder(ptr->right); <br>
 } <br>
} <br>
 
void BST::postorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty"<<endl; <br>
 return; <br>
 } <br>
 if (ptr != NULL) <br>
 { <br>
 postorder(ptr->left); <br>
 postorder(ptr->right); <br>
 cout<<ptr->info<<" "; <br>
 } <br>
} <br>
 
void BST::display(node *ptr, int level) <br>
{ <br>
 int i; <br>
 if (ptr != NULL) <br>
 { <br>
 display(ptr->right, level+1); <br>
 cout<<endl; <br>
 if (ptr == root) <br>
 cout<<"Root->: "; <br>
 else <br>
 { <br>
 for (i = 0;i < level;i++) <br>
 cout<<" "; <br>
 } <br>
 cout<<ptr->info; <br>
 display(ptr->left, level+1); <br>
 } <br>
}<br>

OUTPUT: <br>
![image](https://user-images.githubusercontent.com/97940333/157176982-7a554b5c-97ea-453b-b461-8576c3d1803d.png) <br> ![image](https://user-images.githubusercontent.com/97940333/157177215-9da7d7e2-387c-4ab5-aaf3-230b37ba32a7.png)<br>![image](https://user-images.githubusercontent.com/97940333/157177348-113acabe-5e87-4d9c-9b5b-0338f4ff4a32.png)

****************************************************************************************************************************************
8. Subset of sum problem using backtracking. <br>
****************************************************************************************************************************************
#include <iostream> <br>
#include <stack> <br>
 using namespace std; <br>
 int set[] = {12,8,4,15,5,9,20,3}; <br>
int numberOfElements = 8, sum = 20; <br>
 
class SubSet{ <br>
public: <br>
  stack<int> solutionSet; <br>
  bool hasSolution; <br>
  
  void solve(int s, int idx){ <br>
    if(s>sum) <br>
        return; <br>
    if(s==sum){ <br>
        hasSolution = true; <br>
        displaySolutionSet(); <br>
        return; <br>
    } <br>
          for(int i=idx; i<numberOfElements; i++){ <br>
        solutionSet.push(set[i]); <br>
        solve(s+set[i],i+1); <br>
        solutionSet.pop(); <br>
    } <br>
  } <br>
  void displaySolutionSet(){ <br>
  stack<int> temp; <br>
      
  while (!solutionSet.empty())  <br>
 {  <br>
cout <<  solutionSet.top() << " ";  <br>
 temp.push(solutionSet.top());  <br>
solutionSet.pop(); <br>
}  <br>
cout << '\n'; <br>
while (!temp.empty())  <br>
{  <br>
 solutionSet.push(temp.top());  <br>
 temp.pop(); <br>
 } <br>
} <br>
}; <br>
 
int main() <br>
{ <br>
SubSet ss; <br>
ss.solve(0,0); <br>
if(ss.hasSolution == false) <br>
cout << "No Solution"; <br>
 
return 0; <br>
} <br>
	OUTPUT: <br>
	![image](https://user-images.githubusercontent.com/97940333/157178017-577822aa-a997-486b-ae5a-f6a9bda9391d.png)

************************************************************************************************************************************************************
9. Write a program to store k keys into an array of size n at the location compute using a hash function, loc=key%n, where k<=n and  key takes values from [1 to m], m>n. Handle the collision using Linear Probing technique. <br>
****************************************************************************************************************************************************************
#include<iostream> <br>
#include<limits.h> <br>
using namespace std; <br>
void Insert(int ary[],int hFn, int Size){ <br>
    int element,pos,n=0; <br>
cout<<"Enter key element to insert\n"; <br>
cin>>element; <br>
pos = element%hFn;  <br>
while(ary[pos]!= INT_MIN) {   <br>
if(ary[pos]== INT_MAX) <br>
            break; <br>
pos = (pos+1)%hFn; <br>
n++; <br>
if(n==Size) <br>
            break;  <br>
} <br>
if(n==Size) <br>
        cout<<"Hash table was full of elements\nNo Place to insert this element\n\n"; <br>
else <br>
        ary[pos] = element;  <br>  
} <br>
void display(int ary[],int Size){ <br>
int i; <br>
 
cout<<"Index\tValue\n"; <br>
for(i=0;i<Size;i++) <br>
        cout<<i<<"\t"<<ary[i]<<"\n"; <br>
} <br>
int main(){ <br>
int Size,hFn,i,choice; <br>
cout<<"Enter size of hash table\n"; <br>
cin>>Size; <br>
 hFn=Size; <br>
int ary[Size]; <br>
for(i=0;i<Size;i++) <br>
        ary[i]=INT_MIN;  <br>
do{ <br>
cout<<"Enter your choice\n"; <br>
cout<<" 1-> Insert\n 2-> Display\n 0-> Exit\n"; <br>
cin>>choice; <br>
switch(choice){ <br>
case 1: <br>
Insert(ary,hFn,Size); <br>
break; <br>
case 2: <br>
display(ary,Size); <br>
break; <br>
default: <br>
cout<<"Enter correct choice\n"; <br>
break; <br>
} <br>
}while(choice); <br>
return 0; <br>
} <br>
OUTPUT: <br>
![image](https://user-images.githubusercontent.com/97940333/157179715-1e94a2b8-99ff-4859-8c56-ccceab41ab4c.png)

********************************************************************************************************************************************************
10. Stack using array. <br>
********************************************************************************************************************************************************
#include<stdio.h> <br>
void push(char element, char stack[], int *top, int stackSize)  <br>
{  <br>
 if(*top == -1)  <br>
 {  <br>
  stack[stackSize - 1] = element;  <br>
  *top = stackSize - 1;  <br>
 }  <br>
 else if(*top == 0)  <br>
 {  <br>
  printf("The stack is already full. \n");  <br>
 }  <br>
 else  <br>
 {  <br>
  stack[(*top) - 1] = element;  <br>
  (*top)--;  <br>
 }  <br>
}  <br>
void pop(char stack[], int *top, int stackSize)  <br>
{  <br>
 if(*top == -1)  <br>
 {  <br>
   printf("The stack is empty. \n");  <br>
 }  <br>
 else{  <br>
  printf("Element popped: %c \n", stack[(*top)]);  <br>
  if((*top) == stackSize - 1)  <br>
  {  <br>
    (*top) = -1;  <br>
  }  <br>
  else{  <br>
    (*top)++;  <br>
  }  <br>
 }  <br>
}  <br>
int main()   <br>
{  <br>
  int stackSize = 4; <br>
  char stack[stackSize];  <br>
  int top = -1;  <br>
  push('a', stack, &top, stackSize);  <br>
  printf("Element on top: %c\n", stack[top]);  <br>
  push('b',stack, &top, stackSize);  <br>
  printf("Element on top: %c\n", stack[top]);  <br>
  pop(stack, &top, stackSize);  <br>
  printf("Element on top: %c\n", stack[top]);  <br>
  pop(stack, &top, stackSize);  <br>
  printf("Top: %d\n", top);  <br>
  pop(stack, &top, stackSize);  <br>
  return 0;  <br>
}  <br>
OUTPUT:  <br>
![image](https://user-images.githubusercontent.com/97940333/157183136-b9a5b6c4-494f-4a6d-b700-6a90d5e02577.png)
	
****************************************************************************************************************************
11. Sliptting position. <br>
****************************************************************************************************************************
#include<iostream> <br>
#include<iostream> <br>
using namespace std; <br>
struct Node{ <br>
int value; <br>
struct Node *next;<br>
}; <br>
struct Node* head = NULL; <br>
struct Node* sHead = NULL; <br>
struct Node* temp = NULL; <br>
void insert(int new_data){ <br>
struct Node* new_node = new Node();  <br>
new_node->value = new_data; <br>
new_node->next = head; <br>
head = new_node; <br>
} <br>
int n; <br>
int ele; <br>
int splitIndex; <br>
int main(){ <br>
int i; <br>
cout<<"Enter number of elements you want in the list\t"; <br>
cin>>n; <br>
cout<<"Enter elements :" <<endl; <br>
for(i=0;i<n;i++){ <br>
cin>>ele; <br>
insert(ele); <br>
} <br>
cout<<"\nList of elements : "<<endl; <br>
Node *t; <br>
t = head; <br>
while(t != NULL){ <br>
cout<<t->value<<"\t"; <br>
t = t->next; <br>
} <br>
cout<<"\n\nEnter the position you want the list to split "; <br>
cin>>splitIndex; <br>
while(splitIndex < 0 || splitIndex > n-1){ <br>
cout<<"Invalid position. Try again."<<endl; <br>
cin>>splitIndex; <br>
} <br>
temp = head; <br>
for(i=0;i<=splitIndex;i++){ <br>
if(i==splitIndex-1){ <br>
Node *tN; <br>
tN = temp->next; <br>
sHead = tN; <br>
temp->next = NULL; <br>
break; <br>
} <br>
temp = temp->next; <br>
} <br>
temp = head; <br>
if(temp == NULL){ <br>
cout<<"\nFirst list is empty"<<endl; <br>
}else{ <br>
cout<<"\n\nFirst list element "<<endl; <br>
while(temp != NULL){ <br>
cout<<temp->value<<"\t"; <br>
temp = temp->next; <br>
} <br> 
} <br>
temp = sHead; <br>
if(temp == NULL){ <br>
cout<<"\nSecond list is empty"<<endl; <br>
}else{ <br>
cout<<"\n\nSecond list elements "<<endl; <br>
while(temp != NULL){ <br>
cout<<temp->value<<"\t"; <br>
temp = temp->next; <br>
} <br>
}<br>
return 0; <br>
} <br>
OUTPUT: <br>
![image](https://user-images.githubusercontent.com/97940333/157184448-07937d89-c7d6-4e07-9936-d535fadf5167.png)

********************************************************************************************************************************************************
12. .Write a C++ program to implement singly linked list. <br>
**********************************************************************************************************************************************************
#include<iostream> <br>
#include<cstdlib> <br>
using namespace std; <br>
struct node <br>
{ <br>
 int info; <br>
 struct node *next; <br>
}*start; <br>
class single_llist <br>
{ <br>
 public: <br>
 node* create_node(int); <br>
 void insert_begin(); <br>
 void insert_last(); <br>
 void insert_pos(); <br>
 void delete_begin(); <br>
 void delete_last(); <br>
 void delete_pos(); <br>
 void update_begin(); <br>
 void update_last(); <br>
 void update_pos(); <br>
 void sort(); <br>
 void reverse(); <br>
 void search(); <br>
 void display(); <br>
 single_llist() <br>
 { <br>
 start = NULL; <br>
 } <br>
}; <br>
int main() <br>
{ <br>
 int choice; <br>
 single_llist sl,s2; <br>
 start = NULL; <br>
 do <br>
 { <br>
 cout<<"---------------------------------"<<endl; <br>
 cout<<"Operations on singly linked list"<<endl; <br>
 cout<<"---------------------------------"<<endl; <br>
 cout<<"1.Insert at first"<<endl; <br>
 cout<<"2.Insert at last"<<endl; <br>
 cout<<"3.Insert at position"<<endl; <br>
 cout<<"4.Delete at first"<<endl; <br>
 cout<<"5.Delete at Last"<<endl; <br>
 cout<<"6.Delete at position"<<endl; <br>
 cout<<"7.Update at first"<<endl; <br>
 cout<<"8.Update at last"<<endl; <br>
 cout<<"9.Update at position"<<endl; <br>
 cout<<"10.Ascending order"<<endl; <br>
 cout<<"11.Descending order"<<endl; <br>
 cout<<"12.Search"<<endl; <br>
 cout<<"13.Display"<<endl; <br>
 cout<<"14.Exit "<<endl; <br>
 cout<<"Enter your choice :"; <br>
 cin>>choice; <br>
 switch(choice) <br>
 { <br>
 case 1: sl.insert_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 2: sl.insert_last(); <br>
 sl.display(); <br>
 break; <br>
 case 3: sl.insert_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 4: s2.delete_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 5: s2.delete_last(); <br>
 sl.display(); <br>
 break; <br>
 case 6: sl.delete_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 7: sl.update_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 8: sl.update_last(); <br>
 sl.display(); <br>
 break; <br>
 case 9: sl.update_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 10:sl.sort(); <br>
 sl.display(); <br>
 break; <br>
 case 11:sl.reverse(); <br>
 sl.display(); <br>
 break; <br>
 case 12:sl.search(); <br>
 sl.display(); <br>
 break; <br>
 case 13:sl.display(); <br>
 break; <br>
 case 14:exit(0); <br>
 break; <br>
 default:cout<<"Wrong choice...???"<<endl; <br>
 break; <br>
 } <br>
 } <br>
 while(choice != 14); <br>
} <br>
node *single_llist::create_node(int value) <br>
{ <br>
 struct node *temp, *s; <br>
 temp = new(struct node); <br>
 if (temp == NULL) <br>
 { <br>
 cout<<"Memory not allocated"<<endl; <br>
 return 0; <br>
 } <br>
 else <br>
 { <br>
 temp->info = value; <br>
 temp->next = NULL; <br>
 return temp; <br>
 } <br>
} <br>
void single_llist::insert_begin() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at first in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
} <br>
void single_llist::insert_last() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at last in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 while (s->next != NULL) <br>
 { <br>
 s = s->next; <br>
 } <br>
 temp->next = NULL; <br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
} <br>
void single_llist::insert_pos() <br>
{ <br>
 int value, pos, counter = 0, loc = 1; <br>
 struct node *temp, *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if(pos == 1) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 for (int i = 1; i < pos; i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = temp; <br>
 temp->next = s; <br>
 cout<<temp->info<<" is inserted at position "<<pos<<endl; <br>
 } <br>
 else if (pos == counter+1) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 while (s->next != NULL) <br>
 { <br>
 s = s->next; <br>
 } <br>
 temp->next = NULL; <br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Positon out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::delete_begin() <br>
{ <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
} <br>
void single_llist::delete_last() <br>
{ <br>
 int i, counter = 0; <br>
 struct node *s, *ptr; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s = start; <br>
 if (counter == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 else <br>
 { <br>
 for (i = 1;i < counter;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 } <br>
} <br>
void single_llist::delete_pos() <br>
{ <br>
 int pos, i, counter = 0, loc = 1; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 for (i = 1;i < pos;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 if(pos == counter) <br>
 {cout<<s->info<<" deleted from last"<<endl; <br>
 free(s);} <br>
 else <br>
 {cout<<s->info<<" deleted from postion "<<pos<<endl; <br>
 free(s);} <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::update_begin() <br>
{ <br>
 int value, pos=1, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
} <br>
void single_llist::update_last() <br>
{ <br>
 int value, pos, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s=start; <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < counter ; i++) <br>
 { <br>
 s = s->next; <br>
 } <br>
 s->info = value; <br>
 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; <br>
 } <br>
} <br>
void single_llist::update_pos() <br>
{ <br>
 int value, pos, i,counter = 0, loc = 1; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < pos ; i++) <br>
 { <br>
 s = s->next; <br>
 } <br>
 s->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::sort() <br>
{ <br>
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 { <br>
 if (ptr->info > s->info) <br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info; <br>
 s->info = value; <br>
 } <br>
 } <br>
 ptr = ptr->next; <br>
 } <br>
 } <br>
} <br>
void single_llist::reverse() <br>
{ <br>
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 { <br>
 if (ptr->info < s->info) <br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info; <br>
 s->info = value; <br>
 } <br>
 } <br>
 ptr = ptr->next; <br>
 } <br>
 } <br>
} <br>
void single_llist::search() <br>
{ <br>
 int value, loc = 0, pos = 0, counter = 0; <br>
 struct node *s; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 cout<<"Enter the value to be searched : "; <br>
 cin>>value; <br>
 struct node *s; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 pos++; <br>
 if (s->info == value) <br>
 { <br>
 loc++; <br>
 if(loc == 1) <br>
 cout<<"Element "<<value<<" is found at position "<<pos; <br>
 else if(loc <= counter) <br>
 cout<<" , "<<pos; <br>
 } <br>
 s = s->next; <br>
 } <br>
 cout<<endl; <br>
 if (loc == 0) <br>
 cout<<"Element "<<value<<" not found in the list"<<endl; <br>
 } <br>
} <br>
void single_llist::display() <br>
{ <br>
 struct node *temp; <br>
 if (start == NULL)<br>
 cout<<"Linked list is empty...!!!"<<endl; <br>
 else <br>
 { <br>
 cout<<"Linked list contains : "; <br>
 temp = start; <br>
 while (temp != NULL) <br>
 { <br>
 cout<<temp->info<<" "; <br>
 temp = temp->next; <br>
 } <br>
 cout<<endl; <br>
 } <br>
}<br>
	
OUTPUT: <br>![image](https://user-images.githubusercontent.com/97940333/162892333-0c489835-1ff9-4e3f-901b-b1dd0d12a531.png)<br>
![image](https://user-images.githubusercontent.com/97940333/162892443-dee06073-0e67-4a72-871f-66a109213d29.png)<br>![image](https://user-images.githubusercontent.com/97940333/162892522-c830f2e3-37e5-4ad3-a69d-4ccf61c8fd17.png)<br>![image](https://user-images.githubusercontent.com/97940333/162892630-d90f31a6-2c6e-42ad-b352-60787c48e7b5.png)<br>![image](https://user-images.githubusercontent.com/97940333/162892683-00b81e15-3c2e-4671-8b03-71023d29bc40.png)<br>![image](https://user-images.githubusercontent.com/97940333/162892824-6a4e248f-e7b4-49f1-bb6d-331465e7afb8.png)<br>![image](https://user-images.githubusercontent.com/97940333/162892904-82166b91-926e-4f04-a86c-2d87bfaabdbf.png)

************************************************************************************************************************************
13.Write C++ program to implement merge sort technique using divide and conquer method <br>
***********************************************************************************************************************************
#include <iostream><br>
#include<conio.h><br>
using namespace std;<br>
void Merge(int *a, int low, int high, int mid)<br>
{<br>
int i, j, k, temp[high-low+1];<br>
i = low;<br>
k = 0;<br>
 j = mid + 1;<br>
while (i <= mid && j <= high)<br>
{<br>
if (a[i] < a[j])<br>
{<br>
temp[k] = a[i];<br>
k++;<br>
i++;<br>
}<br>
else<br>
{<br>
temp[k] = a[j];<br>
k++;<br>
j++;<br>
}<br>
}<br>
while (i <= mid)<br>
{<br>
temp[k] = a[i];<br>
k++;<br>
i++;<br>
}<br>
while (j <= high)<br>
{<br>
temp[k] = a[j];<br>
k++;<br>
j++;<br>
}<br>
for (i = low; i <= high; i++)<br>
{<br>
a[i] = temp[i-low];<br>
}<br>
}<br>
void MergeSort(int *a, int low, int high)<br>
{<br>
int mid;<br>
if (low < high)<br>
{<br>
mid=(low+high)/2;<br>
MergeSort(a, low, mid);<br>
 MergeSort(a, mid+1, high);<br>
Merge(a, low, high, mid);<br>
}<br>
}<br>
int main()<br>
{<br>
int n, i;<br>
cout<<"\nEnter the number of data element to be sorted: ";<br>
cin>>n;<br>
 
int arr[n];<br>
for(i = 0; i < n; i++)<br>
{<br>
cout<<"Enter element "<<i+1<<": ";<br>
cin>>arr[i];<br>
}<br>
MergeSort(arr, 0, n-1);<br>
cout<<"\nSorted Data ";<br>
for (i = 0; i < n; i++)<br>
cout<<"->"<<arr[i];<br>
 
getch();<br>
}<br>

OUTPUT: <br>![image](https://user-images.githubusercontent.com/97940333/162889228-a8ccf32d-361e-41f8-a546-72cfabebea0b.png)
************************************************************************************************************************************************

***************************************************************************************************************************************
14. Implement program to doubly linked listed <br>
****************************************************************************************************************************************
#include<iostream><br>
#include<cstdio><br>
#include<cstdlib><br>
using namespace std;<br>
struct node<br>
{<br>
 int info;<br>
struct node *next;<br>
struct node *prev;<br>
}*start;<br>
class double_llist<br>
{<br>
public:<br>
void create_list(int value);<br>
void add_begin(int value);<br>
void add_after(int value, int position);<br>
void delete_element(int value);<br>
void search_element(int value);<br>
void display_dlist();<br>
void count();<br>
void reverse();<br>
double_llist()<br>
{<br>
start = NULL; <br> <br>
 }<br>
};<br>
 int main()<br>
{<br>
int choice, element, position;<br>
double_llist dl;<br>
while (1)<br>
{<br>
 cout<<endl<<"----------------------------"<<endl;<br>
 cout<<endl<<"Operations on Doubly linked list"<<endl;<br>
 cout<<endl<<"----------------------------"<<endl; <br>       
 cout<<"1.Create Node"<<endl;<br>
 cout<<"2.Add at begining"<<endl;<br>
 cout<<"3.Add after position"<<endl;<br>
 cout<<"4.Delete"<<endl;<br>
 cout<<"5.Display"<<endl;<br>
 cout<<"6.Count"<<endl;<br>
 cout<<"7.Reverse"<<endl;<br>
 cout<<"8.Quit"<<endl;<br>
 cout<<"Enter your choice <br>
	
 cin>>choice;<br>
 switch ( choice )<br>
 {<br>
 case 1:<br>
 cout<<"Enter the element: ";<br>
 cin>>element;<br>
 dl.create_list(element);<br>
 cout<<endl;<br>
 break;<br>
 case 2:<br>
 cout<<"Enter the element: ";<br>
 cin>>element;<br>
 dl.add_begin(element);<br>
 cout<<endl;<br>
 break;<br>
 case 3:<br>
 cout<<"Enter the element: ";<br>
 cin>>element;<br>
 cout<<"Insert Element after postion: ";<br>
 cin>>position;<br>
 dl.add_after(element, position);<br>
 cout<<endl;<br>
 break;<br>
 case 4:<br>
 if (start == NULL)<br>
 { <br>                     
 cout<<"List empty,nothing to delete"<<endl; <br> 
 break;<br>
 }<br>
 cout<<"Enter the element for deletion: ";<br>
 cin>>element;<br>
 dl.delete_element(element);<br>
 cout<<endl;<br>
 break;<br>
 case 5:<br>
 dl.display_dlist();<br>
 cout<<endl;<br>
 break;<br>
case 6:<br>
dl.count();<br>
break;  <br>  
case 7:<br>
if (start == NULL)<br>
{<br>
cout<<"List empty,nothing to reverse"<<endl;<br>
break;<br>
}<br>
dl.reverse();<br>
cout<<endl;<br>
break;<br>
case 8:<br>
exit(1);<br>
default:<br>
cout<<"Wrong choice"<<endl;<br>
}<br>
}<br>
return 0;<br>
}<br>
 void double_llist::create_list(int value)<br>
{<br>
struct node *s, *temp;<br>
temp = new(struct node);<br>
temp->info = value;<br>
temp->next = NULL;<br>
if (start == NULL)<br>
{<br>
temp->prev = NULL;<br>
start = temp;<br>
}<br>
else<br>
{<br>
s = start;<br>
while (s->next != NULL)<br>
s = s->next;<br>
s->next = temp;<br>
temp->prev = s;<br>
}<br>
}<br>
void double_llist::add_begin(int value)<br>
{<br>
if (start == NULL)<br>
{<br>
cout<<"First Create the list."<<endl;<br>
return;<br>
}<br>
struct node *temp;<br>
temp = new(struct node);<br>
temp->prev = NULL;<br>
temp->info = value;<br>
temp->next = start;<br>
start->prev = temp;<br>
start = temp;<br>
cout<<"Element Inserted"<<endl;<br>
}<br>
void double_llist::add_after(int value, int pos)<br>
{<br>
if (start == NULL)<br>
{<br>
cout<<"First Create the list."<<endl;<br>
return;<br>
}<br>
struct node *tmp, *q;<br>
int i;<br>
q = start;<br>
for (i = 0;i < pos - 1;i++)<br>
{<br>
q = q->next;<br>
if (q == NULL)<br>
{<br>
cout<<"There are less than ";<br>
cout<<pos<<" elements."<<endl;<br>
return;<br>
}<br>
}<br>
tmp = new(struct node);<br>
tmp->info = value;<br>
if (q->next == NULL)<br>
{<br>
q->next = tmp;<br>
tmp->next = NULL;<br>
tmp->prev = q;<br>      
}<br>
else
{<br>
tmp->next = q->next;<br>
tmp->next->prev = tmp;<br>
q->next = tmp;<br>
tmp->prev = q;<br>
}<br>
cout<<"Element Inserted"<<endl;<br>
}<br>
 void double_llist::delete_element(int value)<br>
{<br>
struct node *tmp, *q;<br>
if (start->info == value)<br>
{<br>
tmp = start;<br>
start = start->next; <br> 
start->prev = NULL;<br>
cout<<"Element Deleted"<<endl;<br>
free(tmp);<br>
return;<br>
}<br>
q = start;<br>
while (q->next->next != NULL)<br>
{  <br>
if (q->next->info == value) <br> 
{<br>
tmp = q->next;<br>
q->next = tmp->n
tmp->next->prev = q;<br>
cout<<"Element Deleted"<<endl;<br>
free(tmp);<br>
return;<br>
}<br>
q = q->next;<br>
}<br>
if (q->next->info == value)<br>    
{<br>
tmp = q->next;<br>
free(tmp);<br>
q->next = NULL;<br>
cout<<"Element Deleted"<<endl;<br>
return;<br>
}<br>
cout<<"Element "<<value<<" not found"<<endl;<br>
}<br>
void double_llist::display_dlist()<br>
{<br>
struct node *q;<br>
if (start == NULL)<br>
{<br>
cout<<"List empty,nothing to display"<<endl;<br>
return;<br>
}<br>
q = start;<br>
cout<<"The Doubly Link List is :"<<endl;<br>
while (q != NULL)<br>
{<br>
cout<<q->info<<" <-> ";<br>
q = q->next;<br>
}<br>
cout<<"NULL"<<endl;<br>
}<br>
 void double_llist::count()<br>
{<br>
struct node *q = start;<br>
int cnt = 0;<br>
while (q != NULL)<br>
{<br>
q = q->next;<br>
cnt++;<br>
}<br>
cout<<"Number of elements are: "<<cnt<<endl;<br>
}<br>
 void double_llist::reverse()<br>
{<br>
struct node *p1, *p2;<br>
p1 = start;<br>
p2 = p1->next;<br>
p1->next = NULL;<br>
p1->prev = p2;<br>
while (p2 != NULL)<br>
{<br>
p2->prev = p2->next;<br>
p2->next = p1;<br>
p1 = p2;<br>
p2 = p2->prev;<br>
}<br>
start = p1;<br><br>
cout<<"List Reversed"<<endl;<br>
}<br>
	
OUTPUT:<br>![image](https://user-images.githubusercontent.com/97940333/163939873-96b4219c-3c03-462e-8e49-c708f599ed4d.png)<br>
![image](https://user-images.githubusercontent.com/97940333/163939962-92989485-7588-43e3-aeb2-42de30156d06.png)<br>![image](https://user-images.githubusercontent.com/97940333/163940118-632e04ea-2c7a-47a6-bd57-30aff4d79d85.png)<br>![image](https://user-images.githubusercontent.com/97940333/163940315-f90e43ac-e5be-4787-98ca-2f80953955e9.png)<br>![image](https://user-images.githubusercontent.com/97940333/163940463-909912f0-2ad5-4107-841e-69eb38148fc5.png)
	
************************************************************************************************************************
15. Hashing<br>
************************************************************************************************************************
#include<iostream><br>
#include<limits.h><br>
using namespace std;<br>
void Insert(int ary[],int hFn, int Size)<br>
{<br>
int element,pos,n=0;<br>
cout<<"Enter key element to insert\n";<br>
cin>>element;<br>
pos = element%hFn;<br> 
while(ary[pos]!= INT_MIN) <br>
{ <br> 
if(ary[pos]== INT_MAX)<br>
break;<br>
pos = (pos+1)%hFn;<br>
n++;<br>
if(n==Size)<br>
break;  <br>   
}<br>
if(n==Size)<br>
cout<<"Hash table was full of elements\nNo Place to insert this element\n\n";<br>
else<br>
ary[pos] = element;  <br>  
}<br>
void display(int ary[],int Size)<br>
{<br>
int i;<br>
 
cout<<"Index\tValue\n";<br>
for(i=0;i<Size;i++)<br>
cout<<i<<"\t"<<ary[i]<<"\n";<br>
}<br>   
int main()<br>
{<br>
 int Size,hFn,i,choice;<br>
 cout<<"Enter size of hash table\n";<br>
 cin>>Size;<br>
 hFn=Size;<br>
 int ary[Size];<br>
 for(i=0;i<Size;i++)<br>
 ary[i]=INT_MIN; <br>
 do<br>
{<br>
cout<<"Enter your choice\n";<br>
 cout<<" 1-> Insert\n 2-> Display\n 0-> Exit\n";<br>
 cin>>choice;<br>
 switch(choice)<br>
{<br>
 case 1:<br>
 Insert(ary,hFn,Size);<br>
 break;<br>
 case 2:<br>
 display(ary,Size);<br>
 break;<br>
 default:<br>
 cout<<"Enter correct choice\n";<br>
 break;<br>
}<br>
}<br>
while(choice);<br>
return 0;<br>
}<br>


OUTPUT:<br>
![image](https://user-images.githubusercontent.com/97940333/163760722-623c2b65-9e5c-4b35-8d37-7abebd6115d8.png)<br>![image](https://user-images.githubusercontent.com/97940333/163760887-0836ede3-ca63-4cc4-b1cb-10d39bee0ce8.png)

************************************************************************************************************************************************
16. Write a C++ program for solving N-Queen???s problem using Backtracking.<br>
************************************************************************************************************************************************
#define N 6<br>
#include <stdbool.h><br>
#include <stdio.h><br>
void printSolution(int board[N][N])<br>
{<br>
for (int i = 0; i < N; i++) {<br>
for (int j = 0; j < N; j++)<br>
printf(" %d ", board[i][j]);<br>
printf("\n");<br>
}<br>
}<br>
bool isSafe(int board[N][N], int row, int col)<br>
{<br>
int i, j;<br>
for (i = 0; i < col; i++)<br>
if (board[row][i])<br>
return false;<br>
for (i = row, j = col; i >= 0 && j >= 0; i--, j--)<br>
if (board[i][j])<br>
return false;<br>
for (i = row, j = col; j >= 0 && i < N; i++, j--)<br>
if (board[i][j])<br>
return false;<br>
return true;<br>
}<br>
bool solveNQUtil(int board[N][N], int col)<br>
{<br>
if (col >= N)<br>
return true;<br>
for (int i = 0; i < N; i++) {<br>
if (isSafe(board, i, col)) {<br>
board[i][col] = 1;<br>
if (solveNQUtil(board, col + 1))<br>
return true;<br>
board[i][col] = 0; }<br>
}<br>
return false;<br>
}<br>
bool solveNQ()<br>
{<br>
int board[N][N]; <br>
for(int i=0;i<N;i++){<br>
for(int j=0;j<N;j++){<br>
board[i][j] = 0;<br>
}<br>
}<br>
if (solveNQUtil(board, 0) == false) {<br>
printf("Solution does not exist");<br>
return false;<br>
}<br>
printSolution(board);<br>
return true;<br>
}<br>
int main()<br>
{<br>
solveNQ();<br>
return 0;<br>


OUTPUT: <br>
![image](https://user-images.githubusercontent.com/97940333/163764279-a6b0756a-a7fb-42ef-91f6-7f19becb7bef.png)

****************************************************************************************************************************************************
17. Binary search 
*****************************************************************************************************************************************************
#include <stdio.h><br>
int main()<br>
{<br>
  int c, first, last, middle, n, search, array[100];<br>

  printf("Enter number of elements\n");<br>
  scanf("%d", &n);<br>

  printf("Enter %d integers\n", n);<br>

  for (c = 0; c < n; c++)<br>
    scanf("%d", &array[c]);<br>

  printf("Enter value to find\n");<br>
  scanf("%d", &search);<br>

  first = 0;<br>
  last = n - 1;<br>
  middle = (first+last)/2;<br>

  while (first <= last) {<br>
    if (array[middle] < search)<br>
      first = middle + 1;<br>
    else if (array[middle] == search) {<br>
      printf("%d found at location %d.\n", search, middle+1);<br>
      break;<br><br>
    }<br>
    else<br>
      last = middle - 1;<br>

    middle = (first + last)/2;<br>
  }<br>
  if (first > last)<br>
    printf("Not found! %d isn't present in the list.\n", search);<br>

  return 0;<br>
}<br>

OUTPUT:<br>
![image](https://user-images.githubusercontent.com/97940333/163939406-cf2e753f-85e1-41f7-b604-683eaac70cf6.png)
	
********************************************************************************************************************************************
18.Write a C++ program to find  MST Using  Kruskal???s algorithm.<br>
********************************************************************************************************************************************

#include<bits/stdc++.h><br>
using namespace std;<br>
typedef pair<int, int> iPair;<br>
struct Graph<br>
{<br>
int V, E;<br>
vector< pair<int, iPair> > edges;<br>
Graph(int V, int E)<br>
{<br>
this->V = V;<br>
this->E = E;<br>
}<br>
void addEdge(int u, int v, int w)<br>
{<br>
edges.push_back({w, {u, v}});<br>
}<br>
int kruskalMST();<br>
};<br>

struct DisjointSets<br>
{<br>
int *parent, *rnk;<br><br>
int n;<br>
DisjointSets(int n)<br>
{<br>
this->n = n;<br>
parent = new int[n+1];<br>
rnk = new int[n+1];<br>
for (int i = 0; i <= n; i++)<br>
{<br>
rnk[i] = 0;<br>
parent[i] = i;<br>
}<br>
}<br>
int find(int u)<br>
{<br>
if (u != parent[u])<br>
parent[u] = find(parent[u]);<br>
return parent[u];<br>
}<br>
void merge(int x, int y)<br>
{<br>
x = find(x), y = find(y);<br>
if (rnk[x] > rnk[y])<br>
parent[y] = x;<br>
else // If rnk[x] <= rnk[y]<br>
parent[x] = y;<br>
if (rnk[x] == rnk[y])<br>
rnk[y]++;<br>
}<br>
};<br>
int Graph::kruskalMST()<br>
{<br>
int mst_wt = 0; <br>
sort(edges.begin(), edges.end());<br>
DisjointSets ds(V);<br>
vector< pair<int, iPair> >::iterator it;<br>
for (it=edges.begin(); it!=edges.end(); it++)<br>
{<br>
int u = it->second.first;<br>
int v = it->second.second;<br>
int set_u = ds.find(u);<br>
int set_v = ds.find(v);<br>
if (set_u != set_v)<br>
{<br>
cout << u << " - " << v << endl;<br>
mst_wt += it->first;<br>
ds.merge(set_u, set_v);<br>
}<br>
}<br>
return mst_wt;<br>
}<br>
int main()<br>
{<br>
int V = 9, E = 14;<br>
Graph g(V, E);<br>
g.addEdge(0, 1, 4);<br>
g.addEdge(0, 7, 8);<br>
g.addEdge(1, 2, 8);<br>
g.addEdge(1, 7, 11);<br>
g.addEdge(2, 3, 7);<br>
g.addEdge(2, 8, 2);<br>
g.addEdge(2, 5, 4);<br>
g.addEdge(3, 4, 9);<br><br>
g.addEdge(3, 5, 14);<br>
g.addEdge(4, 5, 10);<br>
g.addEdge(5, 6, 2);<br>
g.addEdge(6, 7, 1);<br>
g.addEdge(6, 8, 6);<br>
g.addEdge(7, 8, 7);<br>
cout << "Edges of MST are \n";<br>
int mst_wt = g.kruskalMST();<br>
cout << "\nWeight of MST is " << mst_wt;<br>
return 0;<br>
}<br>

OUTPUT:<br>
![image](https://user-images.githubusercontent.com/97940333/165032052-37116e8e-2756-4e6f-b266-f7f72ac7b4a1.png)

******************************************************************************************************************************************************
19.Write a C++ program to find   MST using Prim???s algorithm..<br>
********************************************************************************************************************************************************
#include <bits/stdc++.h><br>
using namespace std;<br>
#define V 5<br>
int minKey(int key[], bool mstSet[])<br>
{<br>
int min = INT_MAX, min_index;<br>
for (int v = 0; v < V; v++)<br>
if (mstSet[v] == false && key[v] < min)<br>
min = key[v], min_index = v;<br>
return min_index;<br>
}<br>
void printMST(int parent[], int graph[V][V])<br>
{<br>
cout<<"Edge \tWeight\n";<br>
for (int i = 1; i < V; i++)<br>
cout<<parent[i]<<" - "<<i<<" \t"<<graph[i][parent[i]]<<" \n";<br>
}<br>

void primMST(int graph[V][V])<br>
{<br>
int parent[V];<br>
int key[V];<br>
bool mstSet[V];<br>
for (int i = 0; i < V; i++)<br>
key[i] = INT_MAX, mstSet[i] = false;<br>
key[0] = 0;<br>
parent[0] = -1; // First node is always root of MST<br>
for (int count = 0; count < V - 1; count++)<br>
{<br>
int u = minKey(key, mstSet);<br>
mstSet[u] = true;<br>
for (int v = 0; v < V; v++)<br>
if (graph[u][v] && mstSet[v] == false && graph[u][v] < key[v])<br>
parent[v] = u, key[v] = graph[u][v];<br>
}<br>
printMST(parent, graph);<br>
}<br>
int main()<br>
{<br>
int graph[V][V] = { { 0, 2, 0, 6, 0 },<br>
{ 2, 0, 3, 8, 5 },<br>
{ 0, 3, 0, 0, 7 },<br>
{ 6, 8, 0, 0, 9 },<br>
{ 0, 5, 7, 9, 0 } };<br>
primMST(graph);<br>
return 0;<br>
}<br>

OUTPUT:<br>
![image](https://user-images.githubusercontent.com/97940333/165033094-4caaf9b8-3f72-46b3-acba-aa84ce3f5490.png)

********************************************************************************************************************
20. Implementing DFS.<br>
********************************************************************************************************************
#include<iostream>
#include<conio.h>
#include<stdlib.h>
using namespace std;
int cost[10][10],i,j,k,n,stk[10],top,v,visit[10],visited[10];
int main()
{
int m;
cout <<"Enter no of vertices:";
cin >> n;
cout <<"Enter no of edges:";
cin >> m;
cout <<"\nEDGES \n";
for(k=1; k<=m; k++)
{
cin >>i>>j;
cost[i][j]=1;
}
cout <<"Enter initial vertex to traverse from:";
cin >>v;
cout <<"DFS ORDER OF VISITED VERTICES:";
cout << v <<" ";
visited[v]=1;
k=1;
while(k<n)
{
for(j=n; j>=1; j--)
if(cost[v][j]!=0 && visited[j]!=1 && visit[j]!=1)
{
 visit[j]=1;
 stk[top]=j;
 top++;
 }
 v=stk[--top];
 cout<<v << " ";
 k++;
 visit[v]=0;
 visited[v]=1;
 }
 return 0;
}
	
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/97940333/165232625-25fb469e-03a4-4442-9259-cb29707dc08f.png)

********************************************************************************************************************
21.implement BFS.<br>
************************************************************************************************************************
#include<iostream>
#include<conio.h>
#include<stdlib.h>
using namespace std;
 int cost[10][10],qu[10],front,rare,visit[10],visited[10];
int main()
{

int m,n,j,i,v,k;
cout <<"Enter no of vertices:";
cin >> n;
cout <<"Enter no of edges:";
cin >> m;
cout <<"\nEDGES \n";
for(k=1; k<=m; k++)
{
cin >>i>>j;
cost[i][j]=1;
}
cout <<"Enter initial vertex to traverse from:";
cin >>v;
cout <<"Visitied vertices:";
cout <<v<<" ";
visited[v]=1;
k=1;
while(k<n)
{
for(j=1; j<=n; j++)
if(cost[v][j]!=0 && visited[j]!=1 && visit[j]!=1)
{
visit[j]=1;
qu[rare++]=j;
}
v=qu[front++];
cout<<v <<" ";
k++;
visit[v]=0;
visited[v]=1;
 }
 return 0;
}
	
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/97940333/165232018-fd8d2a10-dc5b-4c9c-be99-cd20633c03da.png)

**********************************************b
Tower of hanoi

  #include <iostream>
   using namespace std;
    void towers(int, char, char, char);
       int main()
  {
     int num;
     cout<<"Enter the number of disks : ";
     cin>>num;
       cout<<"The sequence of moves involved in the Tower of Hanoi are :\n";
       towers(num, 'A', 'C', 'B');
        return 0;
      }
     void towers(int num, char frompeg, char topeg, char auxpeg)
        {
     if (num == 1)
        {
    cout<<"Move disk 1 from peg "<<frompeg<<" to peg "<<topeg<<"\n";
    return;
         }
       towers(num - 1, frompeg, auxpeg, topeg);
         cout<<"Move disk "<<num<<" from peg "<<frompeg<<" to peg "<<topeg<<"\n";
          towers(num - 1, auxpeg, topeg, frompeg);
       }


out put 
image

             Write a C++ program to count the number of connected components in an undirected graph
		#include <iostream>
		#include <list>
		using namespace std;
		class Graph {
		int V; 
		list<int>* adj;
		void DFSUtil(int v, bool visited[]);
		public:
		Graph(int V); 
		~Graph();
		void addEdge(int v, int w);
		void connectedComponents();
		};
		void Graph::connectedComponents()
		{
		bool* visited = new bool[V];
		for (int v = 0; v < V; v++)
		visited[v] = false;
		for (int v = 0; v < V; v++) {
		if (visited[v] == false) {
		DFSUtil(v, visited);
		cout << "\n";
		}
		}
		delete[] visited;
		}
		void Graph::DFSUtil(int v, bool visited[])
		{
		visited[v] = true;
		cout << v << " ";
		list<int>::iterator i;
		for (i = adj[v].begin(); i != adj[v].end(); ++i)
		if (!visited[*i])
		
		DFSUtil(*i, visited);
		}
		Graph::Graph(int V)
		{
		this->V = V;
		adj = new list<int>[V];
		}
		Graph::~Graph() { delete[] adj; }
		void Graph::addEdge(int v, int w)
		{
		adj[v].push_back(w);
		adj[w].push_back(v);
		}
		int main()
		{
		Graph g(5); 
		g.addEdge(1, 0);
		g.addEdge(2, 3);
		g.addEdge(3, 4);
		cout << "Following are connected components \n";
		g.connectedComponents();
		return 0;
		}
image
	
	
	#include using namespace std;
struct node
{
int key;
node *parent;
char color;
node *left;
node *right;
};
class RBtree
{
node *root;
node *q;
public :
RBtree()
{
q=NULL;
root=NULL;
}
void insert();
void insertfix(node *);
void leftrotate(node *);
void rightrotate(node );
void del();
node successor(node *);
void delfix(node *);
void disp();
void display( node *);
void search();
};
void RBtree::insert()
{
int z,i=0;
cout<<"\nEnter key of the node to be inserted: ";
cin>>z;
node *p,*q;
node *t=new node;
t->key=z;
t->left=NULL;
t->right=NULL;
t->color='r';
p=root;
q=NULL;
if(root==NULL)
{
root=t;
t->parent=NULL;
}
else
{
while(p!=NULL)
{
q=p;
if(p->keykey)
p=p->right;
else
p=p->left;
}
t->parent=q;
if(q->keykey)
q->right=t;
else
q->left=t;
}
insertfix(t);
}
void RBtree::insertfix(node *t)
{
node *u;
if(root==t)
{
t->color='b';
return;
}
while(t->parent!=NULL&&t->parent->color=='r')
{
node *g=t->parent->parent;
if(g->left==t->parent)
{
if(g->right!=NULL)
{
u=g->right;
if(u->color=='r')
{
t->parent->color='b';
u->color='b';
g->color='r';
t=g;
}
}
else
{
if(t->parent->right==t)
{
t=t->parent;
leftrotate(t);
}
t->parent->color='b';
g->color='r';
rightrotate(g);
}
}
else
{
if(g->left!=NULL)
{
u=g->left;
if(u->color=='r')
{
t->parent->color='b';
u->color='b';
g->color='r';
t=g;
}
}
else
{
if(t->parent->left==t)
{
t=t->parent;
rightrotate(t);
}
t->parent->color='b';
g->color='r';
leftrotate(g);
}
}
root->color='b';
}
}

void RBtree::del()
{
if(root==NULL)
{
cout<<"\nEmpty Tree." ;
return ;
}
int x;
cout<<"\nEnter the key of the node to be deleted: ";
cin>>x;
node *p;
p=root;
node *y=NULL;
node *q=NULL;
int found=0;
while(p!=NULL&&found==0)
{
if(p->key==x)
found=1;
if(found==0)
{
if(p->key<x)
p=p->right;
else
p=p->lef
;
}
}
if(found==0)
{
cout<<"\nElement Not Found.";
return ;
}
else
{
cout<<"\nDeleted Element: "<key;
cout<<"\nColour: ";
if(p->color=='b')
cout<<"Black\n";
else
cout<<"Red\n";

     if(p->parent!=NULL)<br>
           cout<<"\nParent: "<<p->parent->key;<br>
     else<br>
           cout<<"\nThere is no parent of the node.  ";<br>
     if(p->right!=NULL)<br>
           cout<<"\nRight Child: "<<p->right->key;<br>
     else<br>
           cout<<"\nThere is no right child of the node.  ";<br>
     if(p->left!=NULL)<br>
           cout<<"\nLeft Child: "<<p->left->key;<br>
     else<br>
           cout<<"\nThere is no left child of the node.  ";<br>
     cout<<"\nNode Deleted.";<br>
     if(p->left==NULL||p->right==NULL)<br>
          y=p;<br>
     else<br>
          y=successor(p);<br>
     if(y->left!=NULL)<br>
          q=y->left;<br>
     else<br>
     {<br>
          if(y->right!=NULL)<br>
               q=y->right;<br>
          else<br>
               q=NULL;<br>
     }<br>
     if(q!=NULL)<br>
          q->parent=y->parent;<br>
     if(y->parent==NULL)<br>
          root=q;<br>
     else<br>
     {<br>
         if(y==y->parent->left)<br>
            y->parent->left=q;<br>
         else<br>
            y->parent->right=q;<br>
     }<br>
     if(y!=p)<br>
     {<br>
         p->color=y->color;<br>
         p->key=y->key;<br>
     }<br>
     if(y->color=='b')<br>
         delfix(q);<br>
 }<br>
}

void RBtree::delfix(node *p)
{
node *s;
while(p!=root&&p->color=='b')
{
if(p->parent->left==p)
{
s=p->parent->right;
if(s->color=='r')
{
s->color='b';
p->parent->color='r';
leftrotate(p->parent);
s=p->parent->right;
}
if(s->right->color=='b'&&s->left->color=='b')
{
s->color='r';
p=p->parent;
}
else
{
if(s->right->color=='b')
{
s->left->color=='b';
s->color='r';
rightrotate(s);
s=p->parent->right;
}
s->color=p->parent->color;
p->parent->color='b';
s->right->color='b';
leftrotate(p->parent);
p=root;
}
}
else
{
s=p->parent->left;
if(s->color=='r')
{
s->color='b';
p->parent->color='r';
rightrotate(p->parent);
s=p->parent->left;
}
if(s->left->color=='b'&&s->right->color=='b')
{
s->color='r';
p=p->parent;
}
else
{
if(s->left->color=='b')
{
s->right->color='b';
s->color='r';
leftrotate(s);
s=p->parent->left;
}
s->color=p->parent->color;
p->parent->color='b';
s->left->color='b';
rightrotate(p->parent);
p=root;
}
}
p->color='b';
root->color='b';
}
}

void RBtree::leftrotate(node *p)
{
if(p->right==NULL)
return ;
else
{
node *y=p->right;
if(y->left!=NULL)
{
p->right=y->left;
y->left->parent=p;
}
else
p->right=NULL;
if(p->parent!=NULL)
y->parent=p->parent;
if(p->parent==NULL)
root=y;
else
{
if(p==p->parent->left)
p->parent->left=y;
else
p->parent->right=y;
}
y->left=p;
p->parent=y;
}
}
void RBtree::rightrotate(node *p)
{
if(p->left==NULL)
return ;
else
{
node *y=p->left;
if(y->right!=NULL)
{
p->left=y->right;
y->right->parent=p;
}
else
p->left=NULL;
if(p->parent!=NULL)
y->parent=p->parent;
if(p->parent==NULL)
root=y;
else
{
if(p==p->parent->left)
p->parent->left=y;
else
p->parent->right=y;
}
y->right=p;
p->parent=y;
}
}

node* RBtree::successor(node *p)
{
node *y=NULL;
if(p->left!=NULL)
{
y=p->left;
while(y->right!=NULL)
y=y->right;
}
else
{
y=p->right;
while(y->left!=NULL)
y=y->left;
}
return y;
}

void RBtree::disp()
{
display(root);
}
void RBtree::display(node *p)
{
if(root==NULL)
{
cout<<"\nEmpty Tree.";
return ;
}
if(p!=NULL)
{
cout<<"\n\t NODE: ";
cout<<"\n Key: "<key;
cout<<"\n Colour: ";
if(p->color=='b')
cout<<"Black";
else
cout<<"Red";
if(p->parent!=NULL)
cout<<"\n Parent: "<parent->key;
else
cout<<"\n There is no parent of the node. ";
if(p->right!=NULL)
cout<<"\n Right Child: "<right->key;
else
cout<<"\n There is no right child of the node. ";
if(p->left!=NULL)
cout<<"\n Left Child: "<left->key;
else
cout<<"\n There is no left child of the node. ";
cout<<endl;
if(p->left)
{
cout<<"\n\nLeft:\n";
display(p->left);
}

if(p->right)<br>
{<br>
 cout<<"\n\nRight:\n";<br>
             display(p->right);<br>
}<br>

 }<br>
}
void RBtree::search()
{
if(root==NULL)
{
cout<<"\nEmpty Tree\n" ;
return ;
}
int x;
cout<<"\n Enter key of the node to be searched: ";
cin>>x;
node *p=root;
int found=0;
while(p!=NULL&& found==0)
{
if(p->key==x)
found=1;
if(found==0)
{
if(p->key<x)
p=p->right;
else
p=p->left;
}
}
if(found==0)
cout<<"\nElement Not Found.";
else
{
cout<<"\n\t FOUND NODE: ";
cout<<"\n Key: "<key;
cout<<"\n Colour: ";
if(p->color=='b')
cout<<"Black";
else
cout<<"Red";
if(p->parent!=NULL)
cout<<"\n Parent: "<parent->key;
else
cout<<"\n There is no parent of the node. ";
if(p->right!=NULL)
cout<<"\n Right Child: "<right->key;
else
cout<<"\n There is no right child of the node. ";
if(p->left!=NULL)
cout<<"\n Left Child: "<left->key;
else
cout<<"\n There is no left child of the node. ";
cout<<endl;

 }<br>
}
int main()
{ int ch,y=0;
RBtree obj;
do
{
cout<<"\n\t RED BLACK TREE " ;
cout<<"\n 1. Insert in the tree ";
cout<<"\n 2. Delete a node from the tree";
cout<<"\n 3. Search for an element in the tree";
cout<<"\n 4. Display the tree ";
cout<<"\n 5. Exit " ;
cout<<"\nEnter Your Choice: ";
cin>>ch;
switch(ch)
{
case 1 : obj.insert();
cout<<"\nNode Inserted.\n";
break;
case 2 : obj.del();
break;
case 3 : obj.search();
break;
case 4 : obj.disp();
break;
case 5 : y=1;
break;
default : cout<<"\nEnter a Valid Choice.";
}
cout<<endl;

}while(y!=1);<br>
return 1;<br>
}
