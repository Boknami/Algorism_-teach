#include <stdio.h>
#include <stdlib.h>

int get_random(void);

int main(void)
{
    printf("%d\n", get_random());
    printf("%d\n", get_random());
    printf("%d\n", get_random());
    return 0;
}

int get_random(void) {
    static int init = 0;
    int random = 0;

    if (init == 0)
    {
        printf("Srand(20)으로 초기화 합니다.\n");
        init = 1;
        srand(20);
    }
    random = rand() % 100;
    return random;
}