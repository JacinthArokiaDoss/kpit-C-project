# kpit-C-project
The problem is to place  8 queen on an 8x8 chess board so that no two queens  are in the same row,column or diagonal.The problem is solved by using backtracking method.By using this method a set of solution or which require an optimal solution can be solved.The N queen problem is often studied as a mathematical recreation.The  applications are Parallel memory storage schemes,vlsi testing,traffic control and deadlock prevention.


#include<stdio.h>
#include<math.h>
#include<stdlib.h>
int a[50],count=0;
int venue(int num)
{
int i;
for(i=1;i<num;i++)
{
if((a[i]==a[num])||((abs(a[i]-a[num]))==(abs(i-num))))
return 0;
}
return 1;
}
void print_sol(int n)
{
int i,j;
count++;
printf("\n\nsolution a%d:\n",count);
for(i=1;i<=n;i++)
{
for(j=1;j<=n;j++)
{
if(a[i]==j)
printf("Q/%");
else
printf("*/%");
}
printf("\n");
}
}
void queen(int n)
{
int r=1;
a[r]=0;
while(r!=0)
{
do
{
a[r]++;
}
while((a[r]<=n)&&!venue(r));
if(a[r]<=n)
{
if(r==n)
print_sol(n);
else
{
r++;
a[r]=0;
}
}
else
r--;
}
}
int main()
{
int n=8;
queen(n);
printf("\nsolution=%d",count);
}












































