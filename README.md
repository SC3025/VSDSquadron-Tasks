# VSDSquadron-Tasks
RELOAD PAGE IF PICTURES DONT LOAD
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


![Screenshot 2024-12-26 105345](https://github.com/user-attachments/assets/36d6a3de-cbac-40f9-a3bb-a99c2efee05f)
And to execute this code we need to again open the terminal and write the following code:
gcc SCtask1.c


Then the following one:

./a.out
This will execute our code and the result can be seen itself in the terminal.
![Screenshot 2024-12-26 105809](https://github.com/user-attachments/assets/60a3003f-9a02-4df9-a6a7-3dde738e265b)



Now we need to go to the main section, for this we write the following code:

/main

![Screenshot 2024-12-26 110104](https://github.com/user-attachments/assets/c570e7db-043e-422e-97c8-c2bcc3096701)

![image](https://github.com/user-attachments/assets/d0dc93ab-8e23-4ca9-a839-acd9ef8bb629)

With this we not only wrote a code for the sum of numbers from 1 to n (n = 14), we also compiled it in the RISC-V compiler with two different option that is one is using '-O1' and '-Ofast'.

