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

	
