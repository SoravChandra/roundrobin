#include<stdio.h>
#include<conio.h>
#include<sys/types.h>
#include<stdlib.h>
#include<string.h>

int main()
{
void waitingt()
{
int p{},n,bt[],wt[],quantum,i;
int r_bt[n];
for(int i=0;i<n:i++)
r_bt[i]=bt[i];
int t=0; //current time
while(1)
{
bool a = true;
//traverse all processes one by one repeadly
for(int o=0;i<n;i+++)
{
//if burst time of a process is greater than 0 thwn ony need to process further
if(r_bt[i]>quantum)
{
t += quantum;
r_bt[i] -= quantum;
}
// if burst time is smaller than or equal to quantum last cycle for this process
else
{
t = t + r_bt[i];
wt[i] = t - bt[i];
r_bt[i] = 0;
}
