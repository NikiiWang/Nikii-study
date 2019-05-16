#include <stdio.h>
#define N 13
struct person
{
	int number;
	int nextp;
}link[N+1];

int main()
{
	int i,count,h;
	for(i=1;i<=N;i++)
	{
		if(i==N)
			link[i].nextp=1;
		else
			link[i].nextp=i+1;
			link[i].number=i;
	}
	count=0;
	h=N;
	printf("\n出圈成员及顺序：");
	while(count<N-1)
	{
		i=0;
		while(i!=3)
		{
			h=link[h].nextp;
			if(link[h].number)
				i++;//222222
		}
		printf("%3d",link[h].number);
		link[h].number=0;
		count++;//1111111
	}
	printf("\n最后的成员是：");
	for(i=1;i<=N;i++)
		if(link[i].number)
			printf("%3d",link[i].number);
		printf("\n");
		return 0;
}
