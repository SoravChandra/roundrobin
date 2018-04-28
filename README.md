#include<stdio.h>

void Iteration(int a[],int size,int ts, int x,char pn[]);

int main()
{
int et[30],ts,n,i,x=0,tot=0;
char pn[10][10];

printf("Enter the no of processes:");
scanf("%d",&n);

printf("Enter the time quantum:");
scanf("%d",&ts);

for(i=0;i<n;i++)
{
printf("enter process name & estimated time:");
scanf("%s %d",pn[i],&et[i]);
}

printf("The processes are:");
for(i=0;i<n;i++)
printf("process %d: %s\n",i+1,pn[i]);

for(i=0;i<n;i++)
tot=tot+et[i];

while(x!=tot)
{
	
  for(i=0;i<n;i++)
  {
  	if(x==6 || x==12 || x==18)
  		 Iteration(et,n,ts,x,pn[10]);
	else
	{
		if(et[i]>ts)
        {
           x=x+ts;
           printf("\n %s -> %d",pn[i],ts);
           et[i]=et[i]-ts;
        }
	    else
	        if((et[i]<=ts)&&et[i]!=0)
            {
                x=x+et[i];
                printf("\n %s -> %d",pn[i],et[i]);
                et[i]=0;
	        }
	  }  
  }
}

printf("\n Total Estimated Time:%d",x);
}

void Iteration(int a[],int size,int ts, int x,char pn[])
{
	  int largest1,largest2;
      
        largest1 = a[0];
        for(int H = 0; H< size; H++)
		{
            if (a[H]>largest1) 
			{
               largest1 = a[H];
            }
        }
        
        largest2 = a[0];
        for (int g=1;g<size;g++) 
		{
            if(a[g]>largest2 && a[g]<largest1){
             largest2 = a[g];
			 }
        }
		
	   
		if(a[largest1]>ts)
        {
           x=x+ts;
           printf("\n %s -> %d",pn[largest1],ts);
           a[largest1]=a[largest1]-ts;
        }
	    else
	    {
	    	if((a[largest1]<=ts)&&a[largest1]!=0)
            {
                x=x+a[largest1];
                printf("\n %s -> %d",pn[largest1],a[largest1]);
                a[largest1]=0;
	        }
		}

		if(a[largest2]>ts)
        {
           x=x+ts;
           printf("\n %s -> %d",pn[largest2],ts);
           a[largest2]=a[largest2]-ts;
        }
	    else
	    {
	    	if((a[largest2]<=ts)&&a[largest2]!=0)
            {
                x=x+a[largest2];
                printf("\n %s -> %d",pn[largest2],a[largest2]);
                a[largest2]=0;
	        }
		}
}

