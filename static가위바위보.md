#include <stdio.h>
#include <stdlib.h>


int user_input(void);
int rps_game(int user);

void main()
{
   int user = 0;

   do {
      user = user_input();
   } while (rps_game(user) == 0);
}

int user_input(void)
{
   int user = 0;
   printf("가위(1) 바위(2) 보(3) : ");
   scanf_s("%d", &user);

   return user;
}

int rps_game(int user)
{
   int com = 0;
   com = rand() % 3 + 1;

   static int won = 0;
   static int lost = 0;
   static int tie = 0;

   if (user > 0 && user < 4)
   {
      if (user == 3 && com == 1) {
         printf("Lost!!   user:%d, com:%d\n", user, com);
         lost++;
      }
      if (user == 1 && com == 2) {
         printf("Lost!!   user:%d, com:%d\n", user, com);
         lost++;
      }
      if (user == 2 && com == 3) {
         printf("Lost!!   user:%d, com:%d\n", user, com);
         lost++;
      }
      if (user == 1 && com == 1) {
         printf("Tie!!    user:%d, com:%d\n", user, com);
         tie++;
      }
      if (user == 2 && com == 2) {
         printf("Tie!!    user:%d, com:%d\n", user, com);
         tie++;
      }
      if (user == 3 && com == 3) {
         printf("Tie!!    user:%d, com:%d\n", user, com);
         tie++;
      }
      if (user == 2 && com == 1) {
         printf("Won!!    user:%d, com:%d\n", user, com);
         won++;
      }
      if (user == 3 && com == 2) {
         printf("Won!!    user:%d, com:%d\n", user, com);
         won++;
      }
      if (user == 1 && com == 3) {
         printf("Won!!    user:%d, com:%d\n", user, com);
         won++;
      }
      printf("\n");
      return 0;
   }
   else
   {
      printf("\nWon : %d | Lost : %d | Tie : %d ", won, lost, tie);
      return 1;
   }
}