#define _CRT_SECURE_NO_WARNINGS
#include <stdlib.h>
#include <stdio.h>
#define row 10
#define colume 10

int main()
{
    int sum100 = 0, i = 0, j = 0, ro = 0, co = 0, half = 0, startX = 0, startY = 0, x = 0, y = 0, sum4 = 0;

    int mtrx3[row][colume] = { {0,2,3,4,1,0,0,0,0,0},
                               {0,6,7,8,5,0,0,0,0,0},
                               {0,10,11,12,9,0,0,0,0,0},
                               {0,14,15,16,13,0,0,0,0,0},
                               {0,0,0,0,0,0,0,0,0,0},
                               {0,0,0,0,0,0,0,0,0,0},
                               {0,0,0,0,0,0,0,0,0,0},
                               {0,0,0,0,0,0,0,0,0,0},
                               {0,0,0,0,0,0,0,0,0,0},
                               {0,0,0,0,0,0,0,0,0,136} };

    for (ro = 0; ro < colume; ro++)
    {
        for (co = 0; co < row; co++)
        {
            sum100 = mtrx3[ro][co] + sum100;
        }
    }

    half = sum100 / 2;
    printf("sum of 100 is: %d\nhalf of it is: %d\n", sum100, half);


    for (ro = 0; ro < colume; ro++)
    {
        for (co = 0; co < row; co++)
        {
            startX = ro;
            startY = co;
            for (x = startX; x < startX + 4; x++)
            {
                for (y = startY; y < startY + 4; y++)
                {
                    sum4 = sum4 + mtrx3[x][y];
                }
            }
            
            if (sum4 == half)
            {
                i = ro;
                j = co;
                printf("sum of 4 is %d, and the other half is %d in the %d x %d\n", sum4, half, i, j);
                break;
            }
            sum4 = 0;
        }
    }

    system("pause");
}
