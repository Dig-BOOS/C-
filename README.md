# C-
定义四个函数分别求1最低分，2最高分，3平均分，4各分数段人数 59以下，60-74， 75-89 ，90以上。main中初始化20个学生成绩，调用4个函数完成各项统计
#include "stdafx.h"
#include "stdio.h"
                    
int max(int a[])
{
	int i,j=0;
	for(i=0;i<20;i++)
	{
		if (a[i]>=j)
			j=a[i];
	}
	return j;
}
int min(int a[])
{
	unsigned int i,j=a[0];
	for(i=0;i<20;i++)
	{
		if (a[i]<=j)
			j=a[i];
	}
	return j;
}
int average(int a[])
{
	int i;
	unsigned int sum=0,ave=0;
	for(i=0;i<20;i++)
	{
		sum=sum+a[i];
	}
	ave=sum/20;
	return (ave);
}
void fenduan(int a[])
{
	int i,A=0,b=0,c=0,d=0;
	 for(i=0;i<20;i++)
	 {
		 if(a[i]<=100 && a[i]>=90)
			A+=1;

		 else if(a[i]<=89 && a[i]>=75)
			b+=1;

		 else if(a[i]<=74 && a[i]>=60)
			c+=1;

		 else if(a[i]<=59 && a[i]>=0)
			d+=1;
	 }
	 printf("90以上人数为：%d\n",A);
	 printf("75-89人数为：%d\n",b);
	 printf("60-74以上人数为：%d\n",c);
	 printf("59以下人数为：%d\n\n",d);
}
int main(int argc, char* argv[])    
{
	int a[20]={88,59,33,15,89,45,26,48,98,64,65,48,31,39,21,15,38,16,58,89};
	int n=20;
	printf("最高分为：%d\n",max(a));
	printf("最低分为：%d\n",min(a));
	printf("平均分为：%d\n",average(a));
	fenduan(a);

	return 0;
}
