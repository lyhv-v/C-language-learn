# C-language-learn
Some code for me when I learn C-language
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<time.h>
int start()
{
	int z = 0;
	printf("######################\n");
	printf("### Start Game ??? ###\n");
	printf("### 1 Yes ### 0 No ###\n");
	printf("######################\n");
	scanf("%d",&z);
	return z;
}
int againgime()
{
	int z = 0;
	printf("######################\n");
	printf("### Again Game ??? ###\n");
	printf("### 1 Yes ### 0 No ###\n");
	printf("######################\n");
	scanf("%d", &z);
	return z;
}
void gaming()
{
	int random_num = 0;
	int input = 0;
	int n = 0;
	do
	{
		random_num = rand() % 100 + 1;
		input = 0;
		while (input != random_num)
		{
			printf("请输入你猜的数字：");
			scanf("%d", &input);
			if (input > random_num)
			{
				printf("猜大了\n");
				continue;
			}
			else if (input < random_num)
			{
				printf("猜小了\n");
				continue;
			}
			else
				printf("恭喜你，猜对了！！！\n");
			break;
			/*printf("%d",random_num);*/
		}
		n = againgime();
	} while (n != 0);
}
int main()
{
	srand((unsigned)time(NULL));
	int n = 0;
	again:
	n=start();
	switch (n)
	{
	case 1:
			gaming();
			break;
	case 0:
		break;
	default:
		printf("输入错误，请重新输入\n");
		goto again;
	}

	return 0;
}
