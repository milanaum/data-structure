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
*****************************************


2.Write a c++ program to implement insertion and deletion node in a rear position of linked list. <br>
**********************************************
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
        p=p->next;  <br>
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
	
****************************************************************************************************************************************************
4. TO implement maximum heap. <br>
****************************************************************************************************************************************************
#include <iostream> <br>
using namespace std; <br>
void max_heap(int *a, int m, int n) <br>
	{ <br>
   int j, t; <br>
   t = a[m]; <br>
   j = 2 * m; <br>
   while (j <= n) <br> 
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
void build_maxheap(int *a,int n)  <br>
{ <br>
   int k; <br>
   for(k = n/2; k >= 1; k--) <br>
	{ <br>
      max_heap(a,k,n); <br>
   } <br>
} <br>
int main() { <br>
   int n, i; <br>
   cout<<"enter no of elements of array\n"; <br>
   cin>>n; <br>
   int a[30]; <br>
   for (i = 1; i <= n; i++)  <br>
{ <br>
      cout<<"enter elements"<<" "<<(i)<<endl; <br>
      cin>>a[i]; <br>
   } <br>
   build_maxheap(a,n); <br>
   cout<<"Max Heap\n"; <br>
   for (i = 1; i <= n; i++) <br>
{ <br>
  cout<<a[i]<<endl; <br>
   } <br>
} <br>
OUTPUT: <br>
	![image](https://user-images.githubusercontent.com/97940333/156972942-873f94c7-2de2-494a-9031-b5b2330bb416.png)
	
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
 { 
 temp->info = value; 
 temp->next = NULL; 
 return temp; 
 } 
} 
void single_llist::insert_begin() 
{ 
 int value; 
 cout<<"Enter the value to be inserted : "; 
 cin>>value; 
 struct node *temp, *s; 
 temp = create_node(value); 
 if (start == NULL) 
 { 
 start = temp; 
 start->next = NULL; 
 cout<<temp->info<<" is inserted at first in the empty list"<<endl; 
 } 
 else 
 { 
 s = start; 
 start = temp; 
 start->next = s; 
 cout<<temp->info<<" is inserted at first"<<endl; 
 } 
} 
void single_llist::insert_last() 
{ 
 int value; 
 cout<<"Enter the value to be inserted : "; 
 cin>>value; 
 struct node *temp, *s; 
 temp = create_node(value); 
 if (start == NULL) 
 { 
 start = temp; 
 start->next = NULL; 
 cout<<temp->info<<" is inserted at last in the empty list"<<endl; 
 } 
 else 
 { 
 s = start; 
 while (s->next != NULL) 
 { 
 s = s->next; 
 } 
 temp->next = NULL; 
 s->next = temp; 
 cout<<temp->info<<" is inserted at last"<<endl; 
 } 
} 
void single_llist::insert_pos() 
{ 
 int value, pos, counter = 0, loc = 1; 
 struct node *temp, *s, *ptr; 
 s = start; 
 while (s != NULL) 
 { 
 s = s->next; 
 counter++; 
 } 
 if (counter == 0){} 
 else 
 { 
 cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; 
 cin>>pos; 
 s = start; 
 if(pos == 1) 
 { 
 cout<<"Enter the value to be inserted : "; 
 cin>>value; 
 temp = create_node(value); 
 start = temp; 
 start->next = s; 
 cout<<temp->info<<" is inserted at first"<<endl; 
 } 
 else if (pos > 1 && pos <= counter) 
 { 
 cout<<"Enter the value to be inserted : "; 
 cin>>value; 
 temp = create_node(value); 
 for (int i = 1; i < pos; i++) 
 { 
 ptr = s; 
 s = s->next; 
 } 
 ptr->next = temp; 
 temp->next = s; 
 cout<<temp->info<<" is inserted at position "<<pos<<endl; 
 } 
 else if (pos == counter+1) 
 { 
 cout<<"Enter the value to be inserted : "; 
 cin>>value; 
 temp = create_node(value); 
 while (s->next != NULL) 
 { 
 s = s->next; 
 } 
 temp->next = NULL; 
 s->next = temp; 
 cout<<temp->info<<" is inserted at last"<<endl; 
 } 
 else 
 { 
 cout<<"Positon out of range...!!!"<<endl; 
 } 
 } 
} 
void single_llist::delete_begin() 
{ 
 if (start == NULL){} 
 else 
 { 
 struct node *s, *ptr; 
 s = start; 
 start = s->next; 
 cout<<s->info<<" deleted from first"<<endl; 
 free(s); 
 } 
} 
void single_llist::delete_last() 
{ 
 int i, counter = 0; 
 struct node *s, *ptr; 
 if (start == NULL){} 
 else 
 { 
 s = start; 
 while (s != NULL) 
 { 
 s = s->next; 
 counter++; 
 } 
 s = start; 
 if (counter == 1) 
 { 
 start = s->next; 
 cout<<s->info<<" deleted from last"<<endl; 
 free(s); 
 } 
 else 
 { 
 for (i = 1;i < counter;i++) 
 { 
 ptr = s; 
 s = s->next; 
 } 
 ptr->next = s->next; 
 cout<<s->info<<" deleted from last"<<endl; 
 free(s); 
 } 
 } 
} 
void single_llist::delete_pos() 
{ 
 int pos, i, counter = 0, loc = 1; 
 struct node *s, *ptr; 
 s = start; 
 while (s != NULL) 
 { 
 s = s->next; 
 counter++; 
 } 
 if (counter == 0){} 
 else 
 { 
 if (counter == 1) 
 { 
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; 
 cin>>pos; 
 s = start; 
 if (pos == 1) 
 { 
 start = s->next; 
 cout<<s->info<<" deleted from first"<<endl; 
 free(s); 
 } 
 else 
 cout<<"Position out of range...!!!"<<endl; 
 } 
 else 
 { 
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; 
 cin>>pos; 
 s = start; 
 if (pos == 1) 
 { 
 start = s->next; 
 cout<<s->info<<" deleted from first"<<endl; 
 free(s); 
 } 
 else if (pos > 1 && pos <= counter) 
 { 
 for (i = 1;i < pos;i++) 
 { 
 ptr = s; 
 s = s->next; 
 } 
 ptr->next = s->next; 
 if(pos == counter) 
 {cout<<s->info<<" deleted from last"<<endl; 
 free(s);} 
 else 
 {cout<<s->info<<" deleted from postion "<<pos<<endl; 
 free(s);} 
 } 
 else 
 cout<<"Position out of range...!!!"<<endl; 
 } 
 } 
} 
void single_llist::update_begin() 
{ 
 int value, pos=1, i,counter = 0; 
 struct node *s, *ptr; 
 s = start; 
 while (s != NULL) 
 { 
 s = s->next; 
 counter++; 
 } 
 if (counter == 0){} 
 else if (pos == 1) 
 { 
 cout<<"Enter the new node : "; 
 cin>>value; 
 start->info = value; 
 cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; 
 } 
} 
void single_llist::update_last() 
{ 
 int value, pos, i,counter = 0; 
 struct node *s, *ptr; 
 s = start; 
 while (s != NULL) 
 { 
 s = s->next; 
 counter++; 
 } 
 s=start; 
 if (counter == 0){} 
 else 
 { 
 cout<<"Enter the new node : "; 
 cin>>value; 
 for (i = 1; i < counter ; i++) 
 { 
 s = s->next; 
 } 
 s->info = value; 
 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; 
 } 
} 
void single_llist::update_pos() 
{ 
 int value, pos, i,counter = 0, loc = 1; 
 struct node *s, *ptr; 
 s = start; 
 while (s != NULL) 
 { 
 s = s->next; 
 counter++; 
 } 
 if (counter == 0){} 
 else 
 { 
 if (counter == 1) 
 { 
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; 
 cin>>pos; 
 s = start; 
 if (pos == 1) 
 { 
 cout<<"Enter the new node : "; 
 cin>>value; 
 start->info = value; 
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; 
 } 
 else 
 cout<<"Position out of range...!!!"<<endl; 
 } 
 else 
 { 
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; 
 cin>>pos; 
 s = start; 
 if (pos == 1) 
 { 
 cout<<"Enter the new node : "; 
 cin>>value; 
 start->info = value; 
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; 
 } 
 else if (pos > 1 && pos <= counter) 
 { 
 cout<<"Enter the new node : "; 
 cin>>value; 
 for (i = 1; i < pos ; i++) 
 { 
 s = s->next; 
 } 
 s->info = value; 
 cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; 
 } 
 else 
 cout<<"Position out of range...!!!"<<endl; 
 } 
 } 
} 
void single_llist::sort() 
{ 
 struct node *ptr, *s; 
 int value; 
 if (start == NULL){} 
 else 
 { 
 ptr = start; 
 while (ptr != NULL) 
 { 
 for (s = ptr->next;s !=NULL;s = s->next) 
 { 
 if (ptr->info > s->info) 
 { 
 value = ptr->info; 
 ptr->info = s->info; 
 s->info = value; 
 } 
 } 
 ptr = ptr->next; 
 } 
 } 
} 
void single_llist::reverse() 
{ 
 struct node *ptr, *s; 
 int value; 
 if (start == NULL){} 
 else 
 { 
 ptr = start; 
 while (ptr != NULL) 
 { 
 for (s = ptr->next;s !=NULL;s = s->next) 
 { 
 if (ptr->info < s->info) 
 { 
 value = ptr->info; 
 ptr->info = s->info; 
 s->info = value; 
 } 
 } 
 ptr = ptr->next; 
 } 
 } 
} 
void single_llist::search() 
{ 
 int value, loc = 0, pos = 0, counter = 0; 
 struct node *s; 
 s = start; 
 while (s != NULL) 
 { 
 s = s->next; 
 counter++; 
 } 
 if (start == NULL){} 
 else 
 { 
 cout<<"Enter the value to be searched : "; 
 cin>>value; 
 struct node *s; 
 s = start; 
 while (s != NULL) 
 { 
 pos++; 
 if (s->info == value) 
 { 
 loc++; 
 if(loc == 1) 
 cout<<"Element "<<value<<" is found at position "<<pos; 
 else if(loc <= counter) 
 cout<<" , "<<pos; 
 } 
 s = s->next; 
 } 
 cout<<endl; 
 if (loc == 0) 
 cout<<"Element "<<value<<" not found in the list"<<endl; 
 } 
} 
void single_llist::display() 
{ 
 struct node *temp; 
 if (start == NULL) 
 cout<<"Linked list is empty...!!!"<<endl; 
 else 
 { 
 cout<<"Linked list contains : "; 
 temp = start; 
 while (temp != NULL) 
 { 
 cout<<temp->info<<" "; 
 temp = temp->next; 
 } 
 cout<<endl; 
 } 
}

