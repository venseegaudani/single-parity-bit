#include<stdio.h>
#include <stdlib.h>
int main()
{
    int n,a[20],sum1=0,sum2=0,opt,parity;
    
    printf("Enter the length of the Data(Original) : ");
    scanf("%d",&n);
    printf("Enter the elements of the string : ");
    for(int i=0;i<n;i++)
    {
        scanf("%d",&a[i]);
    }
    printf("Which parity you want 1.Odd 2.Even : ");
    scanf("%d",&opt);
    //Sender--------------------------------------------------------------------
    printf("\n\n***SENDER SIDE*");
    for(int i=0;i<n;i++)
    {
        sum1+=a[i];
    }
    //check parity acc to user required
    if(sum1%2!=0)
    {
        printf("\nParity : %d (odd)",sum1);
        parity=0;
    }
    else
    {
        printf("\nParity : %d (even)",sum1);
        parity=1;
    }
    //change data if required
    switch(opt)
    {
        case 1:
        {
            if(parity==0)
            {
                printf("\nNo Changes");
            }
            else
            {
                // adding an parity bit
                a[n] = 1;n++;
            }
            break;
        }
        case 2:
        {
            if(parity==1)
            {
                printf("\nNo Changes");
            }
            else
            {
                // adding an parity bit
                a[n] = 1;n++;
            }
            break;
        }
        default:
        {
            printf("\nPlease enter correct option!!!");
            exit(0);
        }
    }
    printf("\nTransmitted Data : ");
                for(int i=0;i<n;i++)
                {
                    printf("%d ",a[i]);
                }
    //Receiver------------------------------------------------------------------
    printf("\n\n***RECEIVER SIDE*");
    for(int i=0;i<n;i++)
    {
        sum2+=a[i];
    }
    //check parity acc to user required
    if(sum2%2!=0)
    {
        printf("\nParity : %d (odd)",sum2);
        parity=0;
    }
    else
    {
        printf("\nParity : %d (even)",sum2);
        parity=1;
    }
    
    switch(opt)
    {
        case 1:
        {
            if(parity==0)
            {
                printf("\nNo error occurred in the data during the transmission");
            }
            else
            {
                printf("\nError occurred in the data during the transmission");
            }
            break;
        }
        case 2:
        {
            if(parity==1)
            {
                printf("\nNo error occurred in the data during the transmission");
            }
            else
            {
                printf("\nError occurred in the data during the transmission");
            }
            break;
        }
    }
    return 0;
}

