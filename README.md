# OS-EX.9-IMPLEMENTATION-OF-PAGING---MEMORY-MANAGEMENT-

## AIM:
To write a C program to implement Page Replacement technique using FIFO.

## ALGORITHM:
1.Start the program.

2.Get the number of pages and their sequence from the user

3.Get the number of available page frames from the user.

4.In FIFO, on the basics of first in first out, replace the pages respectively, then find number of page faults occurred.

5.Compare all frames with incoming page-

6.If the incoming page is already available in page frame, set the match flag to indicate ‘no need of page replacement’.

7.If the incoming page is not available in all frames, then remove the page which is loaded into the memory long back and give space for new incoming page.

8.Increment the ‘number of Page faults counter

9.Print the number of page faults.

10.Stop the program.

## PROGRAM:
```
#include<stdio.h>
#include<conio.h>
int main()
{
int ms, ps, nop, np, rempages, i, j, x, y, pa, offset;
int s[10], fno[10][20];
printf("\nEnter the memory size -- ");
scanf("%d",&ms);
printf("\nEnter the page size -- ");
scanf("%d",&ps);
nop = ms/ps;
printf("\nThe no. of pages available in memory are -- %d ",nop);
printf("\nEnter number of processes -- ");
scanf("%d",&np);
rempages = nop;
for(i=1;i<=np;i++)
{
printf("\nEnter no. of pages required for p[%d]-- ",i);
scanf("%d",&s[i]);
if(s[i] >rempages)
{
printf("\nMemory is Full");
break;
}
rempages = rempages - s[i];
printf("\nEnter pagetable for p[%d] --- ",i);
for(j=0;j<s[i];j++)
scanf("%d",&fno[i][j]);
}
printf("\nEnter Logical Address to find Physical Address ");
printf("\nEnter process no. and page number and offset -- ");
scanf("%d %d %d",&x,&y, &offset);
if(x>np || y>=s[i] || offset>=ps)
printf("\nInvalid Process or Page Number or offset");
else
{ pa=fno[x][y]*ps+offset;
printf("\nThe Physical Address is -- %d",pa);
}
getch();
}

```

## OUTPUT:
![image](https://github.com/Thirukaalathessvarar-S/OS-EX.9-IMPLEMENTATION-OF-PAGING---MEMORY-MANAGEMENT-/assets/121166390/7983904a-4215-45a9-9681-97701da12abb)

## RESULT:
Thus the implementation of FIFO page replacement is successfully executed.
