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
