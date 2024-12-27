# VSDSquadron-Tasks
Risc V internship Weekly Tasks
WEEK 1 

Intialisation included opening the Oracle virtual box machine and creating a new textpad and terminal.

![Screenshot 2024-12-26 105132](https://github.com/user-attachments/assets/b096bc4a-9349-4155-a905-f488c4f711dc)


An interface opens where we need to write the following code which gives us the sum of the numbers from 1 to a particular chosen number n (in our case we are taking n = 14).

#include <stdio.h>
int main(){
      int i , sum = 0 , n = 14;
      for (i =1 ; i <= n ; ++i){
      sum += i;
      }
      printf("Sum of the numbers from 1 to %d is %d\n :" n , sum);
      return 0;
}
